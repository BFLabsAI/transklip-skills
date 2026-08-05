---
name: transklip-api
description: "Use esta skill sempre que o usuário quiser transformar vídeos em transcrições ou em Agent Skills usando a API do Transklip — criar transcrição a partir de um link, acompanhar processamento, pausar/retomar, listar com filtros, e gerar, refinar, renomear ou regerar skills. Acione também quando aparecer uma chave tk_, uma URL /api/v1/transcriptions ou /api/v1/skills, ou quando o pedido envolver automatizar o pipeline de vídeo para conhecimento sem usar a interface web."
language: pt
---

# Transklip API

O Transklip transforma qualquer vídeo da internet em uma Agent Skill instalável.
Esta skill ensina a operar isso por HTTP, sem passar pela interface.

## Antes de qualquer chamada

Base: `https://transklip.bflabs.com.br/api/v1`
Auth: `Authorization: Bearer tk_...` — a chave sai da página API do Transklip.

Confirme que a chave funciona e descubra o escopo dela antes de operar:

```bash
curl -s https://transklip.bflabs.com.br/api/v1/me \
  -H "Authorization: Bearer $TRANSKLIP_KEY"
```

A resposta traz `account_id`, `is_super_admin` e `max_results`. Guarde os três:

- **`account_id`** — tudo que a chave enxerga pertence a essa conta.
- **`is_super_admin`** — se `false`, o parâmetro `all=true` não amplia nada. Não
  insista nele achando que vai ver mais.
- **`max_results`** — teto de itens por página. Pedir `limit` acima disso **não dá
  erro**: a API limita em silêncio ao teto. Para varrer tudo, pagine com `offset`
  em vez de aumentar o `limit`.

## O fluxo que resolve o caso mais comum

O pedido típico é "pega esse vídeo e vira uma skill". São três passos, e o
segundo é espera.

### 1. Criar a transcrição

```bash
curl -s -X POST https://transklip.bflabs.com.br/api/v1/transcriptions \
  -H "Authorization: Bearer $TRANSKLIP_KEY" \
  -H "Content-Type: application/json" \
  -d '{"url": "https://www.youtube.com/watch?v=VIDEO_ID"}'
```

Responde **202** com o registro em `pending`. Guarde o `id`.

Campos opcionais: `model_id` (veja `GET /models`) e `language` (dica de idioma
para o STT — o enriquecimento detecta sozinho e sobrescreve).

### 2. Acompanhar até `done`

Faça polling em `GET /transcriptions/{id}` a cada ~5s. Os estágios são
`pending` → `downloading` → `extracting_audio` → `transcribing` → `enriching` →
`done`. Um vídeo de 3 minutos leva ~20s; um de 40 minutos, ~90s.

**Não** faça polling de segundo em segundo: o trabalho é assíncrono e o estado só
muda quando o worker avança de estágio.

Se voltar `error`, leia `error_message` antes de tentar de novo. Reprocessar é
`POST /transcriptions/{id}/action` com `{"action": "retry"}`.

### 3. Gerar a skill

```bash
curl -s -X POST https://transklip.bflabs.com.br/api/v1/skills \
  -H "Authorization: Bearer $TRANSKLIP_KEY" \
  -H "Content-Type: application/json" \
  -d '{"transcription_id": 42, "usage_context": "no meu Claude Code, para escrever propostas"}'
```

Responde **202**. Faça polling em `GET /skills/{transcription_id}` até
`status: "completed"`. A resposta traz `install_command` — é o comando pronto para
instalar a skill em qualquer agente.

Campos opcionais que mudam bastante o resultado:

| Campo | Efeito |
|---|---|
| `usage_context` | Onde a skill vai ser usada. Ancora os exemplos e a descrição de acionamento |
| `tech_stack` | Linguagem/framework a considerar |
| `name` | Nome escolhido por você. **Se enviar, é mantido** — a IA não inventa outro |
| `model_id` | Modelo que gera a skill. Default: o da transcrição |

## Nome da skill: o que a API faz com o que você manda

Se você **não** manda `name`, o modelo gera um no padrão do ecossistema: 2 a 4
palavras, kebab-case, descrevendo a capacidade — não o título do vídeo.

Se você **manda**, o nome é preservado inteiro; só é sanitizado:

- espaços e `_` viram `-`
- acentos são transliterados (`Prospecção` → `Prospeccao`)
- números e símbolos são removidos
- **maiúsculas são preservadas**

Então `"Minha Skill de Prospecção 2026!"` vira `Minha-Skill-de-Prospeccao`.
Se sobrar vazio (só símbolos), a API responde 400 — não gera um nome aleatório.

## Refinar × Regerar: a distinção que mais gera confusão

Errar aqui destrói trabalho.

| | `POST /skills/{id}/refine` | `POST /skills/{id}/regenerate` |
|---|---|---|
| O que faz | **Edita** o SKILL.md que já existe | **Recria do zero** a partir da transcrição |
| Preserva o texto atual | Sim, exceto o que você pediu para mudar | Não. O conteúdo anterior é perdido |
| Body | `instruction` (obrigatório) | Mesmo de `POST /skills`, sem `transcription_id` |
| Resposta | **200 síncrono**, com o SKILL.md já alterado | **202**, precisa de polling |

Use `refine` quando o conteúdo está quase certo:

```bash
curl -s -X POST https://transklip.bflabs.com.br/api/v1/skills/42/refine \
  -H "Authorization: Bearer $TRANSKLIP_KEY" \
  -H "Content-Type: application/json" \
  -d '{"instruction": "adicione uma seção de erros comuns e deixe a descrição mais específica sobre quando acionar"}'
```

Use `regenerate` só quando a skill saiu no rumo errado e você quer recomeçar com
outro contexto ou outro modelo.

## Listar sem se perder

`GET /transcriptions` aceita, todos combináveis:

| Parâmetro | Exemplo | Observação |
|---|---|---|
| `status` | `done` | Um dos estágios do pipeline |
| `source` | `youtube` | `instagram`, `tiktok`, `twitter`, `vimeo`, `local` |
| `model_id` | `mimo/mimo-v2.5` | Modelo usado no processamento |
| `title` | `opensquad` | Busca parcial, ignora maiúsculas |
| `created_from` / `created_to` | `2026-08-01` | Data ISO; `created_to` inclui o dia inteiro |
| `limit` / `offset` | `50` / `100` | `limit` é limitado por `max_results` |
| `all` | `true` | Só tem efeito para super admin |

A listagem **não** traz `md_content` nem `skill_md` — seriam megabytes por página.
Busque o detalhe por id quando precisar do conteúdo.

`GET /skills` segue a mesma ideia, com `name` para busca parcial. Ela lista
skills em qualquer estado, inclusive `generating` e `error`, para você conseguir
acompanhar o assíncrono.

## Controlar um processamento em andamento

`POST /transcriptions/{id}/action` com `{"action": "..."}`:

| Ação | Quando funciona |
|---|---|
| `pause` | Enquanto está processando. A parada é cooperativa: acontece em segundos, no próximo ponto seguro |
| `resume` | Só em registro `paused` |
| `retry` | Só em `error` ou `done`. Reprocessa do zero |
| `delete` | Sempre. Remove o registro e o conteúdo gerado |

Qualquer outro valor responde 400 com a lista de ações válidas.

## Erros

Sempre no mesmo formato:

```json
{"error": {"code": "not_found", "message": "Transcrição não encontrada"}}
```

| Código HTTP | O que fazer |
|---|---|
| 400 | Corrija o corpo. Não repita a chamada igual |
| 401 | Chave ausente, errada ou substituída por uma nova. Não tente de novo sem trocar a chave |
| 404 | O registro não existe **ou é de outra conta** — a API não diferencia, de propósito |
| 502 | Falha na chamada de IA (refine). Pode tentar de novo |

Um 404 em algo que você sabe que existe quase sempre significa que a chave
pertence a outra conta.

## Regras que não são óbvias

- **Toda chamada é registrada** — usuário, conta, rota, status e duração, inclusive
  as rejeitadas por chave inválida.
- **Gerar chave nova invalida a anterior na hora.** Não existe segunda chave ativa
  por usuário.
- **Regerar uma skill muda o nome** (a IA gera outro) e o endereço de instalação
  muda junto. Se o nome importa, use `rename` depois, ou mande `name` fixo.
- **`rename` republica a skill** no endereço novo e remove o antigo. Quem já
  instalou pelo comando velho não recebe atualização.
