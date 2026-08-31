---
name: breno-veras-editar-video-profissional
description: "Transforma vídeos crus e gravações brutas em produções audiovisuais de alta retenção usando técnicas profissionais de cinema e redes sociais. Use esta skill sempre que o usuário solicitar edição de vídeo, organização de cortes, escolha de trilha sonora, estruturação de sound design, planejamento de match cuts ou orientações de color grading, mesmo que não mencione a skill explicitamente."
language: pt
---

# Guia de Edição de Vídeo Profissional

Este guia estabelece o fluxo de trabalho e os critérios técnicos para transformar vídeos crus em conteúdos audiovisuais de alta retenção, aplicável a projetos no Claude Code e pipelines de pós-produção.

---

## 1. Estruturação da Narrativa (O Cérebro do Vídeo)
Antes de efetuar qualquer corte no material bruto, defina a espinha dorsal narrativa da produção.

- **Conecte cenas soltas com propósito:** Analise os takes disponíveis e organize a sequência lógica para que cada trecho responda a uma intenção emocional (suspense, empolgação, clareza pedagógica ou urgência).
- **Regra dos 5 segundos:** Crie um gancho visual e auditivo forte nos primeiros 5 segundos para prender a atenção imediata do espectador.
- **Eliminação de excessos:** Remova hesitações, silêncios prolongados e redundâncias que interrompam o fluxo da história.

---

## 2. Seleção e Seleção da Trilha Sonora (O Coração da Edição)
A música define a batida cardíaca e a velocidade da edição.

- **Escolha a trilha antes de cortar:** Defina a música de fundo como primeiro passo técnico da timeline para ditar a velocidade e o tempo das transições.
- **Alinhamento emocional:** Selecione trilhas que reflitam o tom exato do momento narrativa (ex: músicas mais dinâmicas para introduções/transições e tons sutis para momentos explicativos).
- **Variedade de repertório:** Evite se prender a um único gênero musical; explore ritmos diversos para manter o interesse visual e auditivo ativo.

---

## 3. Arte e Técnica dos Cortes (Fluidez Visual)
O corte é a ferramenta fundamental para conduzir o olhar da audiência.

- **Aplicação de Match Cut:**
  1. Identifique duas cenas com objetos, movimentos ou enquadramentos semelhantes.
  2. Centralize o ponto focal do elemento principal na tela em ambas as cenas.
  3. Ajuste os frames de entrada e saída para que a transição ocorra de forma contínua e imperceptível.
- **Intencionalidade em cada corte:** Não faça cortes aleatórios. Alterne planos (geral, médio, close-up) para enfatizar pontos-chave do discurso do apresentador ou da ação principal.

---

## 4. Arquitetura do Sound Design (A Tríplice Sensorial)
Incorpore a **Tríplice Sensorial do Som** para transformar transições visuais em experiências imersivas:

1. **Ambiência (Camada de Fundo):** Insira ruídos de fundo sutis (rua, sala, natureza, estúdio) para dar tridimensionalidade ao ambiente visual.
2. **Ação (Camada de Interação):** Adicione foley e efeitos sonoros diretos para cada elemento visível na tela (ex: cliques de câmera, passos, digitação no teclado, objetos tocando superfícies).
3. **Emoção / Pontuação (Camada Dramática):** Utilize impactadores, *whooshes*, *risers* e graves (*drones*) para acentuar cortes estratégicos e mudanças de capítulo.

---

## 5. Color Grading e Finalização Estética
Ganta qualidade estética de nível de cinema utilizando um fluxo de trabalho de cor estruturado.

- **Captação em perfil LOG:** Sempre que possível, utilize materiais gravados em perfil plano ou LOG para preservar amplitude dinâmica e detalhamento de sombras e destaques.
- **Tratamento no DaVinci Resolve:**
  - Faça a conversão do espaço de cor (Color Space Transform) para Rec.709.
  - Busque o equilíbrio natural entre contraste e saturação.
  - Evite superexposição, sombras lavadas ou saturação excessiva que causem distração visual.
- **Consistência Visual:** Mantenha a mesma paleta e tom de cor ao longo de todo o vídeo para reforçar a identidade do conteúdo.

---

## Checklist de Pós-Produção
- [ ] O gancho inicial prende a atenção nos primeiros 5 segundos?
- [ ] A trilha sonora dita o ritmo dos cortes na timeline?
- [ ] Os *match cuts* estão com o ponto focal alinhado?
- [ ] A Tríplice de Sound Design (Ambiência, Ação, Emoção) foi aplicada?
- [ ] O color grading está equilibrado e sem excessos de saturação?
