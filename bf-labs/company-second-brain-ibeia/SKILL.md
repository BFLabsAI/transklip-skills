---
name: bf-labs-company-second-brain-ibeia
description: "Use esta skill sempre que precisar criar, organizar ou melhorar um 'Empresa OS' — um sistema operacional centralizado de conhecimento da empresa conectado a IA — para produzir conteúdos, relatórios, criativos e automações com contexto real do negócio. Use também quando o usuário quiser transformar processos repetitivos em skills reutilizáveis, automatizar tarefas com IA ou configurar integrações entre IA e ferramentas externas."
language: pt
---

## O que é o Empresa OS

O Empresa OS é uma pasta centralizada no computador que reúne todo o conhecimento da empresa — documentos, roteiros, criativos, informações sobre produtos, clientes, posicionamento, tom de voz e processos — e é conectada a uma ferramenta de IA por meio de uma IDE. A ideia é eliminar a necessidade de começar cada tarefa em uma tela em branco, oferecendo à IA contexto real sobre o negócio.

**Regra fundamental:** IA sem contexto é apenas um jogo de perguntas e respostas genéricas. IA com contexto profundo e estruturado da empresa é onde a mágica acontece — ela entrevista o usuário, faz perguntas específicas e entrega resultados alinhados ao negócio.

---

## Passo 1 — Instalar uma IDE e uma ferramenta de IA

1. **Instale o VS Code** (gratuito, da Microsoft) no computador.
2. **Instale uma extensão de IA** dentro do VS Code. Opções recomendadas:
   - **Claude Code** (plano Pro ~20 USD/mês para uso normal; plano Max ~100 USD/mês para uso intensivo).
   - **Codex da OpenAI** (plano Plus ~20 USD/mês; possui plano gratuito limitado).
   - **Google Antigravity / Open Code** (possui cota gratuita).
3. A IDE é apenas uma interface que permite conversar com a IA e fazer com que ela interaja com as pastas e arquivos do computador. Não é exclusiva de programação — é uma ferramenta de produtividade.

> **Nota sobre objeções:** A IDE pode parecer intimidante, mas a maioria das pessoas se familiariza em 48 a 72 horas. Não deixe a aparência técnica impedir o uso — é o equivalente a um "vira-lata feio" que faz tudo, em contraste com interfaces bonitas mas limitadas como ChatGPT ou Gemini para trabalho contextualizado.

---

## Passo 2 — Criar a pasta Empresa OS e popular com conhecimento

1. Crie uma pasta no computador chamada **"[Nome da Empresa] OS"**.
2. Abra essa pasta no VS Code (Open Folder / Abrir Pasta).
3. Selecione a extensão de IA instalada na barra lateral.
4. **Envie o seguinte prompt à IA:**

```
Olá, estou criando nessa pasta o sistema operacional da minha empresa (o "Empresa OS"). Neste primeiro passo, faça uma pesquisa aprofundada na internet para buscar tudo que existe sobre minha empresa: história, fundador, produtos, preços, ofertas, público-alvo, tom de voz, presença digital, clientes e provas sociais. O site da minha empresa é [SEU SITE]. Me faça quaisquer perguntas necessárias antes de começar.
```

5. **Forneça canais de YouTube e redes sociais** da empresa e peça:
   - Baixe e transcreva todos os vídeos e conteúdos antigos.
6. **Jogue todos os arquivos existentes** (roteiros, criativos, documentos) na pasta, mesmo sem organização — a própria IA se encarregará de classificar e estruturar depois.

---

## Passo 3 — Usar o Empresa OS no dia a dia

Após montada a base de conhecimento, a IA já conhece profundamente a empresa. Substitua todas as interações genéricas por interações via Empresa OS:

- **Produção de conteúdo:** Peça criativos, roteiros, carrosséis, artigos, ebooks, apresentações. A IA fará perguntas direcionadas e entregará resultados alinhados ao posicionamento e tom de voz.
- **Pesquisas aprofundadas:** Peça para analisar vídeos no YouTube, identificar dúvidas frequentes do público, montar dossiês de concorrentes.
- **Organização de arquivos:** Peça para a IA organizar pastas com milhares de arquivos.
- **Integrações externas:** Conecte o Empresa OS com ferramentas como Google Analytics, Meta Ads, Google Ads, Hotmart, ClickUp, Shopify, Mercado Livre, Conta Azul, entre outras. A IA pode buscar vendas, métricas, tarefas pendentes e gerar relatórios.
- **Envio de relatórios:** Peça para enviar relatórios para Telegram, WhatsApp, Slack ou Discord.

**Nunca mais:**
- Abra o Google Docs para escrever algo do zero.
- Acesse o sistema de gestão diretamente — interaja via Empresa OS.
- Use o ChatGPT genérico para dúvidas sobre o seu negócio — use sempre o Empresa OS.
- Crie dashboards manuais quando pode pedir os dados diretamente à IA.

---

## Passo 4 — Decidir entre ambiente local ou nuvem

### Local (recomendado para iniciantes)
- **Vantagens:** Simplicidade, sem necessidade de manter servidor, menor preocupação com segurança de dados.
- **Desvantagem:** Automações dependem do computador ligado.
- **Para automatizar localmente:** Use o agendador de tarefas do sistema operacional (Windows Task Scheduler, cron no Mac/Linux) ou o próprio comando `/schedule` dentro da IDE.

### Nuvem (recomendado para quem já domina infraestrutura)
- **Vantagens:** Automações rodam 24/7, mesmo com o computador desligado.
- **Desvantagens:** Complexidade de configuração e manutenção de VPS/servidor, preocupações com segurança.
- **Colaboração:** Use Google Drive, GitHub, Nextcloud ou similar para compartilhar o Empresa OS entre equipe.

---

## Passo 5 — Transformar todo processo repetitivo em uma Skill

Uma **skill** é um arquivo de instruções (texto) que descreve como executar um processo do início ao fim. Quando acionada, a IA reproduz o processo inteiro sem necessidade de reexplicação.

### Como criar uma skill:
1. Execute um processo manualmente na IA até obter um resultado satisfatório.
2. Peça: **"Transforme isso em uma skill para que eu possa reproduzir esse processo sempre, sem ter que reexplicar."**
3. O próprio Claude Code possui uma ferramenta chamada "criador de skills" que auxilia nesse processo.

### Exemplos de skills:
- Gerar 5 carrosséis para Instagram.
- Buscar comentários sem resposta no YouTube nos últimos 14 dias.
- Corrigir problemas de pixel e rastreamento no Google Tag Manager.
- Gerar relatório diário de vendas e tráfego.
- Criar artigos para blog com base em palavras-chave pesquisadas.

**Regra:** Toda vez que se perguntar "Isso vai se repetir?", a resposta é transformar em skill. Não há desvantagem — se nunca mais usar, é apenas um arquivo que pode ser deletado.

---

## Passo 6 — Melhorar as Skills Constantemente

Criar uma skill é como **contratar um colaborador**. Melhorar a skill é como **treinar esse colaborador**.

### Processo de melhoria:
1. Quando o resultado de uma skill não ficar bom, **dê feedback específico à IA**:
   - "Esse carrossel não ilustra o que está sendo falado — sempre inclua imagens ou vídeos que representem o conteúdo."
   - "Esse relatório veio com um número zero que não existia — verifique a fonte de dados."
   - "Essa skill deveria trazer os últimos 14 dias, não 7, por motivos de X."
2. O feedback passa a fazer parte da skill e evita que o erro se repita.
3. **Refine diariamente.** Pequenas melhorias de 1% por dia acumulam resultados expressivos ao longo do tempo (princípio de Hábitos Atômicos: 1.01^365 ≈ 37x de melhoria ao ano).

---

## Passo 7 — Automatizar as Skills Mais Importantes

Criar e melhorar skills não basta — as mais cruciais precisam ser **automatizadas** para executar todos os dias.

### Por que automatizar?
- Uma skill parada na gaveta é como um colaborador que não aparece para trabalhar.
- A automação garante que você terá um novo resultado todo dia para revisar, ajustar e melhorar 1%.

### Como automatizar:
- **Na IDE:** Use o comando `/schedule` para agendar execuções em horários específicos (ex: todo dia às 8h da manhã, gerar relatório de vendas).
- **No sistema operacional:** Use o agendador de tarefas do Windows/Mac/Linux.
- **No canal de entrega:** Configure a IA para enviar o resultado para Telegram, WhatsApp, Slack ou Discord automaticamente.

### Exemplo de rotina automatizada:
- Todo dia às 8h: relatório de vendas e tráfego no Telegram.
- Todo dia às 8h: 5 novos carrosséis gerados.
- Todo dia às 8h: 5 novos artigos publicados no blog.
- A cada 14 dias: análise de comentários sem resposta no YouTube.

---

## Regras de Conduta Gerais

1. **Contexto é tudo.** Nunca faça perguntas genéricas à IA quando o assunto é o seu negócio. Sempre interaja via Empresa OS.
2. **Skills substituem memorização.** Nunca reexplique um processo — documente em skill.
3. **Melhoria contínua.** Nunca deixe uma skill estática. Dê feedback sempre que o resultado não for ideal.
4. **Automação é obrigatória.** As skills cruciais devem rodar diariamente, entregando resultados no canal escolhido.
5. **Não resista à ferramenta.** Quando a IA estiver fora do ar, não tente trabalhar sem ela — aproveite para descansar. Nas 15+ horas úteis do dia em que estiver funcionando, não faz sentido trabalhar manualmente.
6. **Comece localmente.** Use o plano gratuito para montar a base de conhecimento e se familiarizar. Evolua para planos pagos conforme a necessidade.
7. **Invista nos planos adequados:** Para uso normal da equipe, planos de ~20 USD/mês (Claude Pro ou Codex Plus). Para uso intensivo (múltiplas operações simultâneas), planos de ~100 USD/mês (Claude Max ou Codex Pro).
