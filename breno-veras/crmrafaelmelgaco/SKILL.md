---
name: breno-veras-crmrafaelmelgaco
description: "Ensina a instalar, configurar e operar um CRM open-source inteligente com suporte nativo a atendimento via WhatsApp, agentes de IA, Supabase, transbordo humano, roteador de intenções e automação de vendas. Use esta skill sempre que o usuário solicitar o deploy de CRM em VPS, criação de agentes de atendimento de WhatsApp, configuração de transbordo contextual ou integração de webhooks."
language: pt
---

# Guia de Configuração e Implementação do CRM Inteligente com WhatsApp e IA

Este guia instrui a instalação, configuração e colocação em produção de um sistema de CRM Open Source com Inteligência Artificial e atendimento automatizado via WhatsApp.

---

## 1. Pré-Requisitos e Infraestrutura

Antes de iniciar o deploy na VPS, garanta os seguintes itens:

1. **Servidor VPS**: Instância Linux (Ubuntu 20.04/22.04) com acesso root via SSH.
2. **Domínio e DNS**:
   - Crie um registro **Tipo A** no seu provedor de DNS.
   - Apunte o subdomínio escolhido (ex: `crm.seudominio.com.br`) para o IP público da VPS.
3. **Projeto no Supabase**:
   - Crie um novo projeto no Supabase.
   - Obtenha a `Project URL`, `anon / public key` e `service_role key` em **Project Settings > API**.
   - Em **Project Settings > Database**, copie a `DATABASE_URL` (substituindo a senha mestre na string).
4. **Chaves de API de IA**:
   - **Anthropic API Key**: Obrigatória para o motor principal de IA.
   - **OpenAI API Key**: Necessária para transcrição de áudio e funções auxiliares.

---

## 2. Instalação e Deploy na VPS via SSH

### Passo 1: Conectar à VPS
Abra o terminal e conecte-se ao servidor via SSH:
```bash
ssh -p 22022 root@IP_DA_SUA_VPS
```
*(Ajuste a porta caso o provedor utilize a porta padrão 22).* 

### Passo 2: Executar o Script Automatizado
Copie e rode o script de instalação no terminal da VPS. Insira os parâmetros conforme solicitado:
1. **Domínio**: Informe a URL (ex: `crm.seudominio.com.br`).
2. **E-mail do Administrador**: E-mail do usuário master.
3. **Supabase URL**: Cole a `Project URL`.
4. **Supabase Anon Key**: Cole a chave `anon`.
5. **Supabase Service Role Key**: Cole a chave `service_role`.
6. **Database URL**: Cole a URI do PostgreSQL formatada com a senha.
7. **Anthropic API Key**: Cole a chave `sk-ant-...`.
8. **OpenAI API Key**: Cole a chave `sk-...`.
9. **Senha do Administrador**: Defina a senha para acesso ao CRM.
10. **Nome da Aplicação**: Identificação visual do sistema.

Aguarde o término da compilação e inicialização dos serviços (aproximadamente 5 a 10 minutos).

---

## 3. Configuração de Funcionalidades do CRM

### A. Roteador de Intenções (Intent Router)
O roteador avalia a mensagem do lead e escolhe o agente mais indicado.
1. Acesse **Agentes de IA > Roteador**.
2. Crie intenções separadas por objetivo de negócio:
   - **Suporte Técnico**: Adicione frases como "problema com acesso", "erro no sistema", "como configurar".
   - **Comercial**: Adicione frases como "quanto custa", "preço do produto", "solicitar orçamento".
3. Associe cada intenção a um agente específico.
4. Defina um **Agente Fallback** para quando nenhuma intenção atingir a pontuação mínima de confiança.
5. Teste a classificação no painel inserindo frases para verificar o percentual de confiança.

### B. Transbordo Inteligente para Atendimento Humano (Casos)
Quando a IA identifica situações que exigem intervenção humana:
1. Ative o módulo **Casos Humano** nas configurações do agente.
2. A IA gera um **Caso** automático contendo:
   - O motivo resumido do acionamento.
   - O histórico contextualizado do diálogo prévio.
3. No painel de suporte, o operador humano envia ordens diretas para a IA (ex: "Peça o e-mail de acesso do cliente"), e a própria IA responde ao cliente no WhatsApp seguindo o direcionamento.

### C. Memória Global e Aprendizados Contínuos
1. **Memória Global**: Cadastre diretrizes corporativas compartilhadas por todos os agentes de IA (regras da empresa, tom de voz, apresentação).
2. **Aprendizados Contínuos**: Adicione instruções de restrição rígida no painel, tais como:
   - "Nunca oferecer frete grátis no primeiro contato."
   - "Nunca solicitar dados bancários ou CPF diretamente sem autorização prévia."
   - "Exigir validação de e-mail antes de abrir chamados técnicos."

### D. Kanban e Aprovação de Propostas
1. Acompanhe as negociações pela visualização Kanban.
2. Quando o agente comercial formaliza um pedido ou orçamento, o sistema exibe um **Alerta de Proposta** na linha do tempo.
3. Utilize as opções de **Aprovar** ou **Reprovar** direto na interface para atualizar os estágios da negociação.

### E. Entrada Automática de Leads via Webhook
1. Vá até **Webhooks > Criar Fonte**.
2. Vincule a entrada a um funil e etapa específicos.
3. Utilize a URL do Webhook gerada para receber cadastros automaticamente vindos de landing pages, formulários ou automações externas.

---

## 4. Modelo de Aplicação e Monetização

- **Implementação para Nichos**: Configure a estrutura para prestação de serviço recorrente em clínicas, imobiliárias e e-commerces.
- **Treinamento e Consultoria**: Capacite equipes para supervisionar os agentes e interpretar os dados de atendimento do CRM.
- **Programas de Parceria**: Indique provedores de infraestrutura VPS para criar novas fontes de receita recorrente.
