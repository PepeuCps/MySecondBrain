# MSB (My Second Brain) — Segundo Cérebro para Gestão de Tarefas

## O problema
No dia a dia, a informação relevante fica espalhada: reunião aqui, mensagem de Teams ali, e-mail de fornecedor, documentos no SharePoint. Quando várias frentes correm em paralelo, é fácil perder o fio — quem decidiu o quê, qual o próximo passo, e por que aquilo foi decidido daquele jeito.

## O que é o MSB
Uma pasta pessoal de organização de conhecimento, estruturada pelo método **PARA** (Projetos, Áreas, Recursos, Arquivo) — do livro *Building a Second Brain* (Tiago Forte, 2022) — mais um Inbox de captura rápida, versionada em **git local** — nada se perde, tudo tem histórico. O diferencial é que o Claude mantém isso vivo comigo: lê calendário, e-mail e Teams quando eu peço, escreve e atualiza as notas certas, cruza pessoas/projetos/decisões, e me avisa quando algo está em aberto.

## Como funciona no dia a dia
Tudo novo entra no Inbox e é triado para o lugar certo — um projeto com início/fim (ex: incidente, teste de carga), uma área contínua (ex: acompanhamento de KPIs), ou um recurso de referência (ex: glossário de siglas). Uma lista única de tarefas ativas (`TASKS.md`) e uma camada de memória de pessoas/termos garantem que eu (e o Claude) entendemos o contexto rápido, mesmo depois de dias fora do assunto — por exemplo, voltar de uma sala de guerra e conseguir reconstruir o que aconteceu nas reuniões que perdi.

## Por que isso importa
- **Retomada rápida de contexto** depois de imprevistos (incidentes, viagens, sobrecarga de agenda).
- **Rastreabilidade de decisões** — quem decidiu o quê e quando, sem depender de memória.
- **Menos retrabalho**: informação que já foi levantada uma vez não precisa ser levantada de novo.
- **Onboarding mais rápido** em temas novos (ex: entrar numa frente já com o histórico organizado).

## Sobre dados e segurança
Tudo fica local, versionado em git (sem depender de nuvem de terceiros para existir), permitindo quando necessário subir o repositório para um remoto.

## Se alguém quiser montar o próprio
Essa forma de trabalhar segue também, mesmo sem eu ter parado pra nomear assim, o outro método do mesmo Tiago Forte: o **CODE** (Capture, Organize, Distill, Express). Capturo tudo no Inbox, organizo pelo PARA, de tempos em tempos condenso notas antigas pra não perder o essencial no meio do histórico, e expresso o que aprendo em insights, planos de ação e materiais como este.

Empacotei essa forma de trabalhar como uma **Skill** ("second-brain-para"), que outras pessoas podem instalar para começar o próprio segundo cérebro com a mesma estrutura — sem precisar copiar minhas notas. Mas vale mais ainda ir direto na fonte: o livro *Building a Second Brain* dá o método completo pra cada um adaptar do seu próprio jeito, em vez de replicar o que eu fiz aqui ao pé da letra.