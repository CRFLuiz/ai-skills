# Boas Práticas e Revisão de Planos

Esta página descreve o que não deve ser feito e as etapas de auto-revisão para garantir a qualidade de um plano de implementação.

## O Que Evitar (No Placeholders)

Todo passo deve conter o conteúdo exato de que um engenheiro precisa. Nunca escreva:

1. **"TBD", "TODO", "implementar depois", "preencher detalhes".**
2. **"Adicionar tratamento de erro apropriado", "adicionar validação", "tratar edge cases".**
3. **"Escrever testes para o acima" (sem fornecer o código de teste).**
4. **"Similar à Tarefa N" (repita o código, pois o engenheiro pode estar lendo as tarefas fora de ordem).**
5. **Passos que dizem o que fazer sem mostrar como (blocos de código são obrigatórios).**
6. **Referências a tipos, funções ou métodos que não foram definidos em nenhuma tarefa.**

## Lembretes Principais (Remember)

Sempre tenha em mente estas quatro regras de ouro:

1. **Caminhos de arquivo exatos sempre.**
2. **Código completo em todo passo:** Se um passo altera um código, mostre-o.
3. **Comandos exatos com a saída esperada.**
4. **Mantenha os princípios:** DRY, YAGNI, TDD e Commits Frequentes.

## Auto-Revisão (Self-Review)

Após concluir o plano, revise a especificação e verifique:

1. **Cobertura da Especificação:** Percorra cada requisito. Você pode apontar uma tarefa que o implementa? Liste as lacunas.
2. **Varredura de Placeholders:** Busque seu plano por bandeiras vermelhas (itens listados em "O Que Evitar"). Corrija-os.
3. **Consistência de Tipos:** Os tipos, assinaturas de método e nomes de propriedades em tarefas posteriores batem com o que foi definido nas anteriores? Um erro aqui é considerado um "bug".
4. **Correções Inline:** Corrija os problemas diretamente no plano sem precisar de uma nova revisão completa.

## Entrega de Execução (Execution Handoff)

1. **Salvar o Plano:** Após concluir a revisão, o plano deve ser salvo no caminho correto.
2. **Oferecer Opções:** Após salvar, ofereça opções de execução para quem vai utilizar o plano.
