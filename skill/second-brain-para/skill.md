---
name: "second-brain-para"
description: "Ajuda a escrever, atualizar e manter um \"Second Brain\" pessoal organizado pelo método PARA (Projects, Areas, Resources, Archive) com Inbox de captura rápida e camada de memória (pessoas, projetos, termos). Use SEMPRE que o usuário disser algo como \"adiciona isso no meu segundo cérebro\", \"cria uma nota no inbox\", \"resume minha semana\", \"cria um plano de ação pra X\", \"registra esse insight\", \"triagem do inbox\", \"arquiva esse projeto\", \"atualiza minha memória/CLAUDE.md\", \"faz um backup do segundo cérebro\", \"condensa essa nota\", \"resume esse projeto antigo\", ou qualquer pedido de capturar, organizar, resumir, condensar ou arquivar conhecimento pessoal/profissional em notas markdown. Também acionar para dúvidas sobre a estrutura de pastas (0-Inbox, 1-Projetos, 2-Areas, 3-Recursos, 4-Arquivo, memory/, templates/) ou sobre o fluxo de captura → triagem → distill → insight → plano de ação."
---
 
---
name: second-brain-para
description: Ajuda a escrever, atualizar e manter um "Second Brain" pessoal organizado pelo método PARA (Projects, Areas, Resources, Archive) com Inbox de captura rápida e camada de memória (pessoas, projetos, termos). Use SEMPRE que o usuário disser algo como "adiciona isso no meu segundo cérebro", "cria uma nota no inbox", "resume minha semana", "cria um plano de ação pra X", "registra esse insight", "triagem do inbox", "arquiva esse projeto", "atualiza minha memória/CLAUDE.md", "faz um backup do segundo cérebro", "condensa essa nota", "resume esse projeto antigo", ou qualquer pedido de capturar, organizar, resumir, condensar ou arquivar conhecimento pessoal/profissional em notas markdown. Também acionar para dúvidas sobre a estrutura de pastas (0-Inbox, 1-Projetos, 2-Areas, 3-Recursos, 4-Arquivo, memory/, templates/) ou sobre o fluxo de captura → triagem → distill → insight → plano de ação.
---
 
# Second Brain (PARA)
 
Skill para operar o "Second Brain" pessoal do usuário: um repositório local (git) de notas markdown organizado pelo método **PARA**, com um Inbox de captura rápida e uma camada de `memory/` que guarda contexto recorrente (pessoas, projetos, termos/siglas). O fluxo de trabalho também incorpora, de forma leve, a ideia de **Distill** do método CODE (Capture, Organize, Distill, Express, de Tiago Forte) — ver seção 5.7.
 
Esta skill NUNCA deve conter ou introduzir dados pessoais do usuário (nomes reais, empresas, projetos específicos) no próprio SKILL.md ou em qualquer arquivo bundled. Esses dados vivem exclusivamente dentro do vault do usuário (`memory/`, notas, etc.), nunca na skill.
 
## 1. Localizar o vault
 
O vault não tem caminho fixo. Antes de qualquer ação, localize a pasta raiz procurando por esta assinatura (todas ou a maioria destes itens no mesmo diretório):
 
- Pastas: `0-Inbox/`, `1-Projetos/`, `2-Areas/`, `3-Recursos/`, `4-Arquivo/`
- Arquivos/pastas: `templates/`, `memory/`, `TASKS.md`, `CLAUDE.md`
- Repositório git local (`.git/` presente)
Ordem de busca sugerida:
1. Diretório de trabalho atual e seus pais.
2. Locais comuns como `~/segundo-cerebro`, `~/second-brain`, `~/Documents/*segundo*`, `~/Documents/*second-brain*` (case-insensitive, aceitar variações de nome).
3. Se não encontrar, pergunte ao usuário o caminho — não assuma nem crie uma estrutura nova sem confirmação.
Depois de localizado, guarde o caminho mentalmente para o resto da conversa (não precisa perguntar de novo na mesma sessão).
 
## 2. Estrutura de pastas (referência rápida)
 
| Pasta | Conteúdo |
|---|---|
| `0-Inbox/` | Captura rápida: reuniões, ideias soltas, links. Tudo entra aqui primeiro. |
| `1-Projetos/` | Iniciativas com início/fim definidos. |
| `2-Areas/` | Responsabilidades contínuas, sem prazo final. |
| `3-Recursos/` | Material de referência reutilizável (padrões, glossários, comunidades). |
| `4-Arquivo/` | Projetos/áreas encerrados, mantidos só por histórico. |
| `templates/` | Modelos: nota diária, nota de reunião, insight, plano de ação. |
| `memory/` | Memória de trabalho: pessoas, projetos, termos/siglas. |
| `TASKS.md` | Lista de tarefas ativas. |
| `CLAUDE.md` | Memória de trabalho resumida (visão geral rápida). |
 
Sempre releia `CLAUDE.md` e os arquivos relevantes de `memory/` no início de uma tarefa para pegar o jargão e o contexto atual antes de escrever qualquer coisa nova — isso evita criar entradas duplicadas ou usar termos errados.
 
## 3. Convenção de nomes de arquivo
 
Notas dentro de `0-Inbox/`, `1-Projetos/`, `2-Areas/`, `3-Recursos/` seguem o padrão:
 
```
AAAA-MM-DD-titulo-curto-em-kebab-case.md
```
 
Use a data do dia da captura (não a data de um evento futuro/passado citado na nota, a menos que o usuário peça o contrário). Se já existir uma nota com o mesmo nome no mesmo dia, acrescente um sufixo `-2`, `-3`, etc., em vez de sobrescrever.
 
## 4. Templates
 
Os templates reais ficam em `templates/` dentro do vault do usuário (ex: `templates/nota-diaria.md`, `templates/nota-reuniao.md`, `templates/insight.md`, `templates/action-plan.md` — os nomes exatos podem variar, então liste o diretório antes de assumir).
 
**Sempre leia o template correspondente do disco antes de criar uma nota desse tipo.** Não invente uma estrutura própria nem assuma o conteúdo do template de memória — o layout real do usuário prevalece sempre. Se o template pedido não existir ainda, avise o usuário e pergunte se quer que você crie um novo (não crie silenciosamente).
 
## 5. Fluxos de trabalho
 
### 5.1 Captura (Inbox)
Qualquer coisa nova e ainda não organizada (reunião, ideia, aprendizado, link) vira uma nota em `0-Inbox/` com o nome no padrão da seção 3. Não tente classificar automaticamente em Projeto/Área nesse momento — a captura é deliberadamente "suja"; a triagem acontece depois.
 
### 5.2 Triagem
Quando o usuário pedir para triar o Inbox (ou periodicamente, se pedido "organiza meu inbox"):
1. Liste os arquivos em `0-Inbox/`.
2. Para cada um, proponha o destino (`1-Projetos/`, `2-Areas/` ou `3-Recursos/`) com base no conteúdo e no que `memory/` e `CLAUDE.md` já sabem sobre projetos/áreas existentes.
3. Confirme com o usuário antes de mover em lote — pode mostrar a lista completa de propostas de uma vez para aprovação rápida, não precisa perguntar nota por nota se o usuário preferir revisar tudo junto.
4. Mova (não copie) o arquivo para o destino aprovado, preservando o conteúdo original.
### 5.3 Insight
Quando um padrão ou conclusão importante aparece, registre usando o template `insight.md`, salvo dentro da Área/Projeto relevante (não no Inbox).
 
### 5.4 Plano de ação
Quando um insight ou problema pede execução, gere um plano com o template `action-plan.md`, estruturado nos horizontes: imediato / 30 dias / 90 dias / 180 dias. Salve dentro do Projeto/Área relevante.
 
### 5.5 Resumos e buscas ("resume minha semana", "o que sei sobre X")
Para responder, busque contexto em:
- As pastas do vault relevantes ao pedido (`0-Inbox/`, `1-Projetos/`, `2-Areas/`, conforme o escopo).
- `memory/` (pessoas, projetos, termos citados).
- `TASKS.md` (tarefas ativas relacionadas).
Combine essas fontes num resumo direto; não é necessário ler o vault inteiro se o pedido é claramente restrito a um projeto/área específico.
 
### 5.6 Manutenção geral
 
**Git**: o vault é um repositório git local. Depois de criar, mover ou editar notas de forma relevante, faça um commit descritivo (ex: `git add -A && git commit -m "triagem: move 3 notas do inbox"`). Não configure nem altere remotes (`git remote add`, `git push`) sem o usuário pedir explicitamente — isso é mudança de configuração persistente.
 
**Backup/zip**: quando o usuário pedir um "backup" ou "snapshot", gere um `.zip` da pasta raiz do vault (pode excluir `.git/` se o usuário só quiser o conteúdo atual, ou incluir se quiser o histórico completo — pergunte se não estiver claro) e entregue o arquivo para download.
 
**Arquivamento**: nunca mova algo para `4-Arquivo/` automaticamente sem avisar. Se perceber sinais de que um projeto/área foi encerrado (ex: nota dizendo "projeto finalizado", ausência de atividade recente combinada com indicação explícita de encerramento), **sugira** o arquivamento e só mova depois de confirmação do usuário.
 
### 5.7 Distill (condensação proativa)
 
Inspirado no "D" de CODE (Capture, Organize, Distill, Express), este passo cobre uma lacuna natural do fluxo PARA: notas de `1-Projetos/` e `2-Areas/` tendem a crescer por acréscimo (cada atualização adiciona uma seção nova, com data), e depois de várias rodadas o "estado atual" fica diluído no meio de um histórico longo de atualizações já superadas.
 
**Quando sugerir:** sempre que, ao editar ou revisar uma nota existente em `1-Projetos/` ou `2-Areas/`, você perceber sinais como: a nota já acumulou várias seções datadas de atualização; parte do conteúdo descreve um estado que já foi substituído por uma atualização mais recente (ex.: um "risco em aberto" que já foi resolvido, mas a seção antiga continua lá); ou a nota ficou longa o suficiente para que encontrar "o que importa agora" exija ler várias rodadas de histórico.
 
**Como sugerir:** proponha ao usuário — nunca condense silenciosamente. Explique brevemente por que (ex.: "essa nota já tem várias atualizações acumuladas e o estado atual ficou diluído — quer que eu condense, mantendo só um resumo do histórico?"). Só condense após confirmação.
 
**Como condensar (quando aprovado):**
1. Mantenha uma seção clara de estado/situação atual no topo, refletindo só o que vale agora.
2. Comprima as atualizações antigas e já superadas em uma seção curta de histórico (ex.: uma linha por data com o essencial), em vez de manter cada atualização como uma seção completa.
3. Não delete informação relevante que ainda não tenha virado consenso ou que possa ser referenciada depois — o objetivo é comprimir o que já é puramente histórico, não apagar contexto vivo.
4. Lembre (a si mesmo e ao usuário, se relevante) que nada se perde de verdade: o conteúdo original completo continua acessível no histórico do git, então condensar a versão "ativa" da nota é seguro.
5. Faça o commit da condensação separado de outras mudanças, com mensagem clara (ex.: `git commit -m "distill: condensa histórico de <nota>"`).
Esse é um cuidado de manutenção, não uma etapa obrigatória a cada edição — sugira quando notar o sinal, mas não insista repetidamente se o usuário preferir deixar a nota como está.
 
## 6. Memória (`memory/`) — abordagem híbrida
 
- **Leitura**: sempre leia os arquivos relevantes de `memory/` (pessoas, projetos, termos) antes de escrever notas, resumos ou planos — isso garante que você usa o jargão e contexto certos.
- **Escrita**: nunca escreva em `memory/` silenciosamente. Quando perceber uma pessoa, projeto ou termo novo relevante que ainda não está registrado, **proponha** a atualização ao usuário (ex: "encontrei uma pessoa nova nesta nota — quer que eu adicione em `memory/pessoas.md`?") e só escreva após confirmação explícita.
- O mesmo vale para `CLAUDE.md`: é memória de trabalho resumida: sugerir atualização, não sobrescrever sem aprovação.

## 7. Boas práticas gerais
 
- Prefira mover/editar arquivos existentes a duplicar conteúdo.
- Nunca delete notas permanentemente — mover para `4-Arquivo/` é a forma correta de "encerrar" algo.
- Ao criar múltiplas notas de uma vez (ex: importar contexto de várias reuniões), mostre um resumo do que foi criado/movido ao final, não apenas durante o processo.
- Se o vault não tiver algum dos itens esperados (ex: falta `memory/`), não crie a estrutura sozinho sem perguntar — pode ser uma variação intencional do usuário.
- Ao editar uma nota já existente em `1-Projetos/` ou `2-Areas/`, aproveite o momento para avaliar se ela também é candidata a Distill (seção 5.7) — não é preciso fazer isso toda vez, mas vale checar quando a nota já estiver visivelmente longa.
