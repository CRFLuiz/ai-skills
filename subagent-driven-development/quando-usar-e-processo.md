# Quando Usar e Processo

## Quando Usar

1. Use quando tiver um plano de implementação e as tarefas forem em sua maioria independentes.
2. Certifique-se de que a execução permanecerá na sessão atual (se for uma sessão paralela, use `executing-plans`).
3. O princípio central é: subagente novo por tarefa + revisão em duas etapas (especificação e depois qualidade) = alta qualidade e iteração rápida.
4. Por que usar subagentes: ao delegar tarefas com instruções precisas e contexto isolado, você garante o foco e o sucesso da tarefa, evitando que o subagente herde o histórico da sessão e protegendo seu próprio contexto para a coordenação.

## O Processo

1. Leia o plano, extraia todas as tarefas com texto completo, anote o contexto e crie um `TodoWrite`.
2. Para cada tarefa, despache um subagente implementador (usando o prompt apropriado).
3. Responda a quaisquer perguntas do subagente implementador e forneça contexto adicional.
4. O subagente implementador cria o código, os testes, faz os commits e auto-revisa o trabalho.
5. Despache o subagente revisor de especificações para confirmar se o código atende aos requisitos. Se não, o implementador deve corrigir as lacunas.
6. Em seguida, despache o subagente revisor de qualidade de código. Se houver problemas, o implementador os corrige.
7. Após aprovação de qualidade, marque a tarefa como concluída no `TodoWrite`.
8. Se houver mais tarefas, repita o ciclo com um novo subagente implementador.
9. Quando todas as tarefas terminarem, despache o subagente de revisão final para a implementação inteira e use a skill `finishing-a-development-branch`.