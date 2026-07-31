# My Second Brain

Sistema pessoal de organização de conhecimento, baseado no método **PARA** (Projects, Areas, Resources, Archive), com um Inbox de captura rápida e uma camada de memória (pessoas, projetos, termos) para que eu (e o Claude) entendamos o jargão do dia a dia.

## Estrutura

- **0-Inbox/** — captura rápida (notas de reunião, ideias soltas, links). Tudo entra aqui primeiro e depois é triado para as pastas certas.
- **1-Projetos/** — iniciativas com início/fim definidos.
- **2-Areas/** — responsabilidades contínuas, sem prazo final (ex: Agendas recorrentes, acompanhamentos, etc).
- **3-Recursos/** — material de referência reutilizável (padrões, glossários técnicos, comunidades internas).
- **4-Arquivo/** — projetos/áreas encerrados, mantidos só por histórico.
- **templates/** — modelos para nota diária, nota de reunião, insight e plano de ação.
- **memory/** — memória de trabalho: pessoas, projetos e termos/siglas do dia a dia (para contexto rápido).
- **TASKS.md** — lista de tarefas ativas.
- **CLAUDE.md** — memória de trabalho resumida (visão geral rápida).

## Fluxo de uso

1. **Captura**: qualquer coisa nova (reunião, ideia, aprendizado) vira uma nota em `0-Inbox/`.
2. **Triagem**: periodicamente, mover/organizar as notas do Inbox para o Projeto, Área ou Recurso correspondente.
3. **Insight**: quando um padrão ou conclusão importante aparece, registrar com o template `insight.md` dentro da Área/Projeto relevante.
4. **Plano de ação**: quando um insight ou problema pede execução, gerar um plano com o template `action-plan.md` (imediato / 30 / 90 / 180 dias).
5. **Peça para o Claude**: "adiciona isso no meu segundo cérebro", "resume minha semana", "cria um plano de ação pra X" — ele lê e escreve direto nessas pastas.

## Backup / Exportação

A pasta é um repositório **git local**. Isso dá:

- Histórico completo de versões (nada se perde, dá pra ver o que mudou e quando).
- Portabilidade: para levar para outra máquina, basta copiar a pasta inteira (ela já carrega o `.git` com todo o histórico) ou rodar `git clone` a partir dela.
- Se quiser sync automático entre máquinas no futuro, é só adicionar um remoto (GitHub, GitLab, Azure Repos pessoal) com `git remote add origin <url>` e `git push`.

Para gerar um snapshot pontual: peça "gera um zip de backup do meu segundo cérebro".

## Primeira carga

Importe o contexto da última semana (Outlook, Teams, SharePoint) para começar a popular o sistema. Reuniões, projetos e pessoas recorrentes serão registrados — revise e ajuste conforme necessário.

## Guia operacional (VS Code + Claude)

Para uso manual com compatibilidade total com o Claude CoWork, veja:

- `3-Recursos/guia-operacional-vscode-claude-compatibilidade.md`
