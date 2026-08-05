---
name: bf-labs-company-second-brain-ibeia
description: "Montar um segundo cérebro da empresa (Segment Brain) para todos os seus agentes de IA consumirem e documentarem conteúdo da mesma fonte centralizada. Use esta skill quando precisar criar, estruturar ou integrar um repositório unificado de conhecimento empresarial que sirva como contexto para múltiplos agentes de IA, automatizar a alimentação desse repositório com dados internos e externos, ou transformar processos repetitivos em habilidades reutilizáveis que acessam esse conhecimento compartilhado. Ative esta skill sempre que o usuário mencionar criação de segundo cérebro, base de conhecimento empresarial para IA, ou integração de contexto para agentes."
language: pt
---

## Princípio Fundamental

Inteligência artificial sem contexto é apenas um jogo de perguntas e respostas. Inteligência com contexto estruturado e profundo é onde a mágica acontece. O Segment Brain é o sistema operacional do conhecimento da sua empresa: uma pasta centralizada que armazena tudo o que define o negócio — documentos, roteiros, criativos, informações sobre produtos, clientes, posicionamento, tom de voz e processos. Quando um agente de IA acessa esse repositório, ele já conhece a empresa e não precisa receber as mesmas explicações repetidamente.

## Passo 1: Instalar o Ambiente de Trabalho

### 1.1 Escolher e instalar uma IDE

Use o VS Code (gratuito, Microsoft) como interface. A IDE não é apenas para programação: é uma interface que permite que a IA interaja com as pastas e arquivos do computador. Instale o VS Code pelo site oficial e faça o download gratuito.

### 1.2 Instalar a extensão de IA

No VS Code, vá em Extensões (ícone à esquerda) e instale uma das seguintes ferramentas:
- **Claude Code** (recomendado) — se já assina o Claude, instale a extensão oficial
- **Codex** (OpenAI) — plano gratuito disponível
- **Google Antigravity** — alternativa com cota gratuita
- **Open Code** — para usuários mais alternativos

Qualquer uma serve. O importante é ter uma IA que consiga ler, criar e manipular arquivos diretamente no computador.

## Passo 2: Criar a Estrutura do Segment Brain

### 2.1 Criar a pasta raiz

Crie uma nova pasta no computador chamada `segment-brain-[nome-da-empresa]`. Essa pasta será o repositório central de todo o conhecimento.

### 2.2 Abrir a pasta na IDE

No VS Code, vá em "Abrir Pasta" (Open Folder) e selecione a pasta criada. A pasta aparecerá vazia do lado esquerdo da tela.

### 2.3 Conectar a IA

No painel da IDE, selecione a ferramenta de IA que instalou (Claude Code, Codex, etc.). Agora a IA pode interagir diretamente com os arquivos da pasta.

## Passo 3: Alimentar a Base de Conhecimento

### 3.1 Pesquisa inicial via internet

Envie o seguinte prompt para a IA:

```
Estou criando nessa pasta um Segment Brain da minha empresa. Neste primeiro passo, faça uma pesquisa aprofundada na internet para buscar tudo que existe sobre a empresa. Inclua:
- História da empresa e do fundador
- Produtos, preços e ofertas
- Público-alvo e dores
- Tom de voz e posicionamento
- Presença digital (site, redes sociais)
- Clientes e provas sociais
- Artigos, vídeos e outros conteúdos já publicados

Site da empresa: [INSIRA O URL AQUI]
Me faça quaisquer perguntas necessárias antes de começar.
```

### 3.2 Adicionar conteúdo proprietário

Copie e cole na pasta todos os arquivos existentes da empresa:
- Roteiros de vídeo (prontos e em produção)
- Criativos e imagens
- Documentos de posicionamento
- Listas de clientes e depoimentos
- Contratos, termos e processos internos
- Qualquer outro material relevante

**Não se preocupe em organizar agora.** Jogue tudo na pasta. A própria IA fará a classificação depois.

### 3.3 Transcrever conteúdos existentes

Forneça os canais de YouTube, profiles de redes sociais e outros canais de conteúdo da empresa. Peça à IA:

```
Baixe e transcreva todos os vídeos dos seguintes canais nos últimos 2 anos:
- [CANAL DO YOUTUBE]
- [PERFIL DO INSTAGRAM]
- [OUTRO CANAL]

Armazene as transcrições em uma pasta chamada 'transcricoes'.
```

### 3.4 Organizar o repositório

Após todo o material estar na pasta, peça:

```
Organize toda a pasta segment-brain. Classifique os arquivos por categoria (produtos, clientes, conteúdos, processos, etc.). Crie uma estrutura de pastas lógica. Delete arquivos duplicados. Gere um índice README.md com o resumo de tudo que está disponível.
```

## Passo 4: Integrar com Ferramentas Externas

O Segment Brain ganha poder real quando se conecta a sistemas de dados. Integre com:

### 4.1 Dados de marketing e vendas
- **Google Analytics** — acesso a tráfego, visualizações, comportamento
- **Meta Ads** — vendas, receita, ROAS, campanhas
- **Google Ads** — desempenho de campanhas
- **Hotmart / Shopify / Mercado Livre** — dados de produto e venda

### 4.2 Gestão e operação
- **ClickUp / Trello** — tarefas pendentes e status
- **Conta Azul / Blin / Nibo** — financeiro
- **Sistemas de pagamento** — transações

### 4.3 Canais de comunicação
Configure a IA para enviar relatórios automaticamente para:
- Telegram
- WhatsApp
- Slack
- Discord

**Prompt de integração exemplo:**

```
Conecte-se ao Google Analytics e me diga quantas pessoas acessaram o site ontem. Depois, puxe as vendas do Meta Ads e me envie um resumo no Telegram com: vendas totais, receita, ROAS e custo por conversão.
```

## Passo 5: Transformar Processos em Habilidades (Skills)

Todo processo repetitivo deve ser transformado em uma habilidade — um arquivo de instruções que descreve como executar uma tarefa do início ao fim.

### 5.1 Identificar o que se repete

Pergunte-se:
- Esse processo vou precisar fazer mais de uma vez?
- Posso deixar a IA executar sozinha com as mesmas instruções?

Se a resposta for sim, crie uma skill.

### 5.2 Criar uma skill

Peça à IA:

```
Transforme este processo em uma skill reutilizável. Escreva um arquivo de instruções completo, passo a passo, que eu possa acionar sempre que precisar executar essa tarefa. O processo é: [DESCRIÇÃO DO PROCESSO]
```

**Exemplos de skills úteis:**
- Gerar carrosséis para Instagram
- Criar artigos para o blog com SEO
- Buscar comentários sem resposta no YouTube
- Corrigir problemas de pixel e rastreamento
- Gerar relatórios de vendas e tráfego
- Produzir ebooks e materiais ricos
- Conectar e subir campanhas no Meta Ads

### 5.3 Usar uma skill

Basta acionar o nome da skill:

```
/executar [nome-da-skill]
```

A IA segue o processo definido sem receber todas as orientações novamente.

## Passo 6: Melhorar Contínuo as Habilidades

Criar uma skill é como contratar um colaborador. Melhorar a skill é como treinar esse colaborador.

### 6.1 Fornecer feedback quando o resultado não for bom

Quando a entrega não estiver adequada, explique:
- O que ficou errado
- O que esperava ver
- O que deve mudar para a próxima vez

**Exemplo:**

```
Esse carrossel que você gerou tem um problema: você falou sobre um filme mas não incluiu nenhuma cena dele. A partir de agora, sempre que falar de um produto, filme ou vídeo, ilustre com imagens ou trechos reais. Também inclua pelo menos 1 vídeo curto dentro do carrossel. Atualize a skill de geração de carrosséis com essas novas regras.
```

### 6.2 Iterar diariamente

Melhe 1% por dia. Cada feedback corrigido evita que o erro se repita. Ao longo de 90 dias, a qualidade do trabalho da IA será comparável à de um profissional sênior.

A fórmula é: 1.01³⁶⁵ ≈ 37x de melhoria acumulada em um ano.

## Passo 7: Automatizar as Habilidades

Uma skill parada na pasta não produz valor. Automatize as mais importantes para rodar todos os dias.

### 7.1 Automatizar localmente

Use o agendador de tarefas do sistema operacional:
- **Windows:** Agendador de Tarefas
- **Mac/Linux:** cron jobs

Configure para que a IA execute a skill em horários fixos:
- Relatórios de vendas → toda manhã às 8h
- Geração de carrosséis → toda noite às 20h
- Análise de comentários YouTube → toda sexta às 18h

### 7.2 Automatizar na nuvem (quando necessário)

Se precisar de automações que rodem mesmo com o computador desligado, migre para um VPS ou servidor na nuvem. Essa opção é indicada apenas para quem já domina infraestrutura.

### 7.3 Revisar e ajustar

Ao receber o resultado automatizado, revise rapidamente. Se encontrar erros, abra a IA e corrija:

```
O relatório de vendas de hoje veio com o número zero no campo de receita. Verifique a integração com o Hotmart e corrija. A partir de amanhã, inclua também os dados do Google Analytics no relatório.
```

## Arquitetura Recomendada para Múltiplos Agentes

Para que todos os agentes de IA da organização consumam e documentem conteúdo da mesma fonte:

### Estrutura de pastas

```
segment-brain-empresa/
├── README.md              # Índice e resumo do conteúdo
├── identidade/
│   ├── historia.md
│   ├── fundador.md
│   ├── posicionamento.md
│   ├── tom-de-voz.md
│   └── publico-alvo.md
├── produtos/
│   ├── [produto-1].md
│   ├── [produto-2].md
│   └── precos.md
├── conteudos/
│   ├── transcricoes/
│   ├── roteiros/
│   ├── criativos/
│   └── artigos/
├── clientes/
│   ├── perfis.md
│   └── depoimentos.md
├── processos/
│   ├── skills/
│   │   ├── gerar-carousel.md
│   │   ├── relatorio-vendas.md
│   │   ├── comentarios-youtube.md
│   │   └── [outras-skills].md
│   └── automacoes/
├── integracoes/
│   ├── google-analytics.md
│   ├── meta-ads.md
│   ├── clickup.md
│   └── [outras-integracoes].md
└── dados/
    └── metricas/
```

### Regras para múltiplos agentes

1. **Única fonte da verdade:** Todos os agentes devem ler e gravar no mesmo Segment Brain. Nunca crie cópias paralelas.
2. **Documentação automática:** Quando um agente gerar um conteúdo novo (roteiro, criativo, relatório), ele deve salvá-lo na pasta correspondente dentro do Segment Brain.
3. **Leitura antes de escrever:** Antes de gerar qualquer conteúdo, o agente deve ler o README.md e os arquivos de identidade para entender o contexto.
4. **Skills compartilhadas:** Habilidades criadas por um agente ficam disponíveis para todos os outros. Qualquer agente pode acionar qualquer skill.
5. **Versionamento:** Use Git ou GitHub para controlar alterações. Isso permite reverter erros e acompanhar a evolução do conhecimento.

### Exemplo de prompt para novo agente

```
Você é um agente de IA conectado ao Segment Brain da empresa. Antes de executar qualquer tarefa, leia o README.md e os arquivos na pasta identidade/ para entender o contexto do negócio. Use as skills disponíveis na pasta processos/skills/ sempre que aplicável. Ao gerar um conteúdo novo, salve-o na pasta correspondente dentro de conteudos/.
```

## Considerações Finais

- **Não use chatbots genéricos** (ChatGPT, Gemini, Perplexity) como ambiente principal de trabalho. Eles não mantêm contexto nem acessam arquivos. Use-os apenas para dúvidas pontuais não relacionadas ao negócio.
- **Comece localmente.** A nuvem é opcional e indicada apenas para quem domina infraestrutura.
- **Não tenha medo da IDE.** Em 48 a 72 horas você estará familiarizado. O que parece intimidante é apenas uma interface para a IA interagir com seus arquivos.
- **Invista em planos pagos** quando precisar de uso intensivo. O retorno em produtividade supera o custo por um fator de 10x ou mais.
- **Se a IA sair do ar, não trabalhe sem ela.** Aproveite o tempo para descansar. Nas outras 15 horas úteis do dia, você não vai querer fazer mais nada sem o Segment Brain.
