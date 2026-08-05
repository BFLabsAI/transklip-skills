# Transklip Skills

<sub>By BF Labs</sub>

Skills de agente de IA geradas pelo [Transklip](https://transklip.bflabs.com.br) a partir de
transcrições de vídeo. Cada conta tem sua própria pasta; cada skill é um `SKILL.md`
autocontido.

## Instalação

```bash
npx skills add https://github.com/BFLabsAI/transklip-skills --skill <nome-da-skill>
```

O nome da skill é qualificado pela conta (`{conta}-{skill}`), então skills de contas
diferentes sobre o mesmo tema não colidem — o CLI `skills` deduplica pelo campo `name`
do frontmatter, não pelo caminho do arquivo.

Para listar tudo que está disponível:

```bash
npx skills add https://github.com/BFLabsAI/transklip-skills --list
```

## Estrutura

```
{conta}/
  {skill}/
    SKILL.md
```

## Sobre

Gerado automaticamente. Para criar ou editar uma skill, use o Transklip — edições feitas
direto neste repositório são sobrescritas na próxima publicação.
