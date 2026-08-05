---
name: bf-labs-company-second-brain-ibeia
description: "Use esta skill sempre que precisar criar, documentar, estruturar ou consumir um Second Brain / Empresa OS para qualquer agente de IA. Deve ser acionada quando o usuário falar em montar um cérebro da empresa, criar uma base de conhecimento organizacional, documentar processos da empresa para IA, preparar contexto para que agents consumam conteúdos da mesma fonte, configurar um OS corporativo com IA, ou quando precisar transformar conhecimento disperso em uma pasta centralizada que qualquer AI agent possa consultar."
language: pt
---

# Montar um Second Brain / Empresa OS para AI Agents

Este é um framework agnóstico para construir um "Second Brain" corporativo — uma pasta centralizada com todo o conhecimento da empresa — que qualquer AI agent pode documentar, consumir e operar a partir da mesma fonte.

## Por que isso existe

Inteligência artificial sem contexto é apenas um jogo de perguntas e respostas. IA munida do conhecimento da empresa consegue produzir resultados relevantes, específicos e alinhados ao negócio. O Second Brain é o mecanismo que transforma um chatbot genérico em um colaborador que já conhece a empresa.

## Passo 1 — Preparar o ambiente

1. Instale uma IDE como VS Code (ou qualquer alternativa).
2. Instale uma extensão/ferramenta de IA no ambiente: Claude Code, Codex, Gemini CLI, ou outra.
3. A IDE não é apenas para programação — é uma interface que permite à IA interagir com pastas e arquivos do computador.
4. Crie uma pasta para o Second Brain (ex: `empresa-os`, `secondbrain`) e abra-a na IDE.

> **Nota:** Para iniciantes, o ambiente local é mais simples. Para automações permanentes e colaboração em equipe, avalie opções em nuvem (Google Drive, GitHub, Nextcloud, VPS). Comece localmente e migre depois quando dominar.

## Passo 2 — Alimentar a base de conhecimento

Peça à IA que pesquise na internet tudo sobre a empresa e crie os primeiros arquivos. Inclua:

- **História da empresa** e perfil do fundador
- **Produtos e serviços**, preços, ofertas, garantias
- **Público-alvo**: dores, desejos,objeções, linguagem
- **Posicionamento e tom de voz** (inclua exemplos de textos)
- **Prova social**: depoimentos, cases, resultados
- **Presença digital**: site, redes sociais, canal do YouTube
- **Conteúdos existentes**: artigos, vídeos, roteiros, criativos
- **Integrações e ferramentas** usadas (analytics, tráfego, pagamento, gestão)
- **Processos recorrentes** da empresa

**Dica:** Forneça links de canais de YouTube, redes sociais e sites. A IA pode baixar, transcrever e indexar conteúdos antigos. Não se preocupe em organizar agora — a própria IA classifica e estrutura os arquivos depois.

**Formato da pasta inicial:**
```
secondbrain/
  empresa/
    historia.md
    produtos.md
    publico-alvo.md
    tom-de-voz.md
    provas-sociais.md
    integracoes.md
  conteudos/
    videos/
    artigos/
    criativos/
    roteiros/
  dados/
    metricas.md
    clientes.md
```

## Passo 3 — Construir Skills reutilizáveis

Todo processo que se repete deve ser transformado em uma **skill** — um arquivo de instruções que descreve como executar uma tarefa do início ao fim.

**Como criar uma skill:**
1. Quando terminar um resultado bom (relatório, carrossel, roteiro, criativo), peça à IA: "Transforme isso em uma skill para eu poder reproduzir sempre sem reexplicar."
2. A IA escreve o arquivo da skill com todas as instruções passo a passo.
3. Para executar a skill, basta acioná-la (ex: `/gerar-carousel`, `/relatorio-vendas`).

**Exemplos de skills que todo Second Brain deve ter:**
- Gerar carrosséis do Instagram
- Criar roteiros de vídeo com ganchos e variações
- Gerar artigos para blog alinhados a SEO
- Puxar relatórios de vendas e tráfego
- Buscar comentários sem resposta no YouTube
- Produzir criativos estáticos e em vídeo
- Organizar e classificar arquivos da pasta
- Integrar e corrigir problemas de tracking (Google Tag Manager)
- Enviar relatórios automatizados (Telegram, WhatsApp, Slack, Discord)
- Criar apresentações e palestras a partir de carrosséis

**Regra:**
- Toda vez que se perguntar "Isso vai se repetir?" → transforme em skill.
- Se nunca mais usar, delete o arquivo — são apenas arquivos de texto.

## Passo 4 — Melhorar as Skills constantemente

Criar uma skill é o equivalente a contratar um colaborador. Melhorar a skill é o equivalente a treinar esse colaborador.

**Como treinar (refinar):**
1. Execute a skill e analise o resultado.
2. Quando o resultado não estiver bom, abra a skill e escreva:
   - O que ficou errado
   - O que precisa mudar
   - As novas regras ou restrições
3. Salve. A partir da próxima execução, o erro não se repete.

**Exemplo concreto:**
- Skill original: "Gere um carrossel sobre o tema X"
- Resultado: carrossel sem ilustrações, sem vídeos
- Feedback para a skill: "Sempre ilustre o que está sendo falado. Insira trechos de vídeo quando disponível."
- Skill v2: agora gera carrosséis com imagens contextuais e vídeos integrados.

**Regra:** melhore 1% por dia. Ao final de 90 dias, o resultado será 37x melhor (baseado em hábitos atômicos: 1,01^365 ≈ 37).

## Passo 5 — Automatizar as Skills

Uma skill parada é um colaborador que não aparece para trabalhar. Automatize as skills mais importantes para executar todos os dias.

**Como automatizar:**
1. Defina a frequência (diária, semanal, sob demanda).
2. Configure o agendamento usando:
   - Agendador nativo da ferramenta de IA (ex: `/agendar`)
   - Agendador de tarefas do sistema operacional (Windows Task Scheduler, cron no Linux)
   - Scripts simples que disparam a skill
3. Defina o canal de entrega: Telegram, WhatsApp, Slack, Discord, e-mail.
4. Receba o resultado automaticamente e revise rapidamente.

**Exemplos de automações essenciais:**
- Relatório de vendas e tráfego → entregue às 8h da manhã no Telegram
- 5 novos carrosséis gerados por dia → entregues às 20h
- Blog com novos artigos publicados → 5 artigos/dia às 8h
- Comentários sem resposta no YouTube → busca e sugere respostas a cada 6h
- Tarefas pendentes no gestor de projetos → resumo diário

**Regra:** Automatize antes de tentar melhorar. Se o colaborador não aparece para trabalhar, não há o que treinar.

## Passo 6 — Integrações externas

Conecte o Second Brain às ferramentas da empresa para que a IA possa buscar dados e executar ações sem acesso manual.

**Ferramentas comuns para integrar:**
- **Tráfego:** Meta Ads, Google Ads, Google Analytics
- **Pagamento:** Hotmart, Pagar.me, Shopify, Mercado Livre
- **Gestão:** ClickUp, Trello, Notion, Conta Azul, Blin, Nibo
- **Comunicação:** Telegram, WhatsApp, Slack, Discord
- **Conteúdo:** WordPress, YouTube API, Instagram

**Como integrar:**
1. Peça à IA que pesquise a documentação oficial da ferramenta.
2. Siga o passo a passo de autenticação (API keys, OAuth).
3. Crie uma skill específica para cada integração.
4. Teste com dados reais antes de automatizar.

## Passo 7 — Organizar e manter a pasta

Periodicamente, peça à IA que organize os arquivos do Second Brain:
- Delete arquivos duplicados ou obsoletos
- Reestruture pastas conforme novos conteúdos surgirem
- Mantenha um índice atualizado dos arquivos principais

**Regra:** não é humano que organiza pasta — é a IA. Deixe que ela classifique e estruture.

## Referência Rápida

| Etapa | Ação |
|---|---|
| Ambiente | Instalar IDE + extensão de IA |
| Alimentar | Pesquisar, transcrever, documentar tudo sobre a empresa |
| Skills | Transformar todo processo recorrente em skill |
| Treinar | Dar feedback constante e refinar as skills |
| Automatizar | Agendar execução diária + entrega em canal |
| Integrar | Conectar ferramentas externas (tráfego, pagamento, gestão) |
| Manter | Organizar e limpar a pasta periodicamente |

## Dicas Finais

- **Nunca comece do zero:** sempre abra o Second Brain e peça à IA com contexto.
- **Nunca use ChatGPT puro** para tarefas do negócio — a resposta sempre será melhor com contexto.
- **Não se intimide pela IDE:** em 48 a 72 horas você estará familiarizado.
- **Não se preocupe com dashboards bonitos:** peça o dado direto à IA. O esforço de montar gráficos manualmente é por ego.
- **Quando a IA cair no ar:** descanse. Não tente trabalhar sem contexto. Aproveite para viver.
- **Framework agnóstico:** este Second Brain serve para qualquer AI agent — documente tudo uma única vez e deixe todos os agents consumirem da mesma fonte.
