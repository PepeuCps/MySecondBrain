# Guia Operacional My Second Brain (MSB) no VS Code (Compatível com Claude)

## Objetivo
Manter uso diário do MSB no VS Code, com mínimo esforço manual, sem quebrar compatibilidade para voltar ao Claude CoWork quando quiser.

## Princípios de compatibilidade
- Não alterar a estrutura PARA já existente.
- Não renomear pastas raiz: `0-Inbox`, `1-Projetos`, `2-Areas`, `3-Recursos`, `4-Arquivo`, `memory`, `templates`.
- Usar Markdown simples (sem formatos proprietários).
- Seguir templates oficiais da pasta `templates/`.
- Manter tarefas em `TASKS.md` no padrão checkbox.
- Registrar horários sempre em Brasília (UTC-3).

## Fluxo diário (10 a 20 min no total)
1. Captura rápida durante o dia
- Tudo novo entra em `0-Inbox/`.
- Se vier de reunião, usar template de reunião.

2. Fechamento do dia (10 a 15 min)
- Consolidar aprendizados na nota diária.
- Extrair ações novas e atualizar `TASKS.md`.
- Triar itens do Inbox para Projeto, Área ou Recurso.

3. Fechamento semanal (20 a 30 min)
- Revisar `TASKS.md`: remover ruído e destacar próximos 5 itens críticos.
- Converter aprendizados importantes em `insight`.
- Quando houver execução estruturada, abrir `action-plan`.

## Templates que devem ser usados
- Nota diária: `templates/daily-note.md`
- Reunião: `templates/meeting-note.md`
- Insight: `templates/insight.md`
- Plano de ação: `templates/action-plan.md`

## Protocolo de triagem do Inbox
1. É trabalho com início e fim?
- Mover para `1-Projetos/`.

2. É responsabilidade contínua?
- Mover para `2-Areas/`.

3. É referência reutilizável?
- Mover para `3-Recursos/`.

4. Perdeu relevância?
- Arquivar em `4-Arquivo/`.

## Convenções de escrita (para IA entender melhor)
- Título explícito com contexto (assunto + data).
- Decisões separadas de discussão.
- Ações sempre com responsável e prazo, quando houver.
- Evitar notas longas sem estrutura.

## Rotina de versionamento (git local)
1. Commit diário curto
- Mensagem sugerida: `msb: fechamento diario AAAA-MM-DD`.

2. Commit de triagem semanal
- Mensagem sugerida: `msb: triagem inbox e consolidacao semanal`.

3. Snapshot antes de mudanças maiores
- Mensagem sugerida: `msb: snapshot pre-reorganizacao`.

## Modelo recomendado no VS Code (custo x benefício)
### Padrão
- Usar GPT-5.3-Codex para tarefas de maior impacto:
  - síntese de semana
  - consolidação de reuniões
  - plano de ação
  - priorização de backlog

### Economia de custo
- Mandar uma tarefa por vez (escopo pequeno).
- Fornecer só os arquivos necessários no contexto.
- Pedir saída já no template final (evita retrabalho).
- Evitar prompts genéricos muito abertos.

## Prompt base (copiar e usar)
Objetivo: organizar conteúdo do MSB com compatibilidade total com Claude CoWork.
Entrada: [cole a nota bruta ou contexto].
Saída:
1. preencher template adequado;
2. listar ações com responsável e prazo;
3. sugerir atualização objetiva no TASKS.
Restrições:
- não criar novas pastas;
- manter estrutura PARA atual;
- manter horários em UTC-3 (Brasília);
- escrever em pt-BR direto e conciso.

## Checklist rápido (fim do dia)
- [ ] Nota diária atualizada
- [ ] Ações novas refletidas em `TASKS.md`
- [ ] Itens do Inbox triados
- [ ] Decisões importantes registradas
- [ ] Commit diário realizado

## Sinais de que você está preservando compatibilidade
- Claude consegue entender e continuar notas sem retrabalho.
- Não existem formatos alternativos fora dos templates.
- `TASKS.md` segue como fonte única de pendências ativas.
- Estrutura de pastas permaneceu estável.

## Quando os créditos do Claude voltarem
- Retomar fluxo normal sem migração.
- Continuar usando os mesmos templates e pastas.
- Pedir ao Claude apenas tarefas de alto valor (síntese, decisão, plano), mantendo captura e triagem sob seu controle.
