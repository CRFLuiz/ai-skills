# Seleção de Modelo e Princípios

## Seleção de Modelo

1. Use o modelo menos poderoso que conseguir lidar com cada função, com o objetivo de conservar os limites de contexto para a sessão principal.
2. Agente Coordenador (você): deve usar um modelo capaz de alto raciocínio (ex: Claude 3.5 Sonnet ou GPT-4o) devido ao contexto longo e tomada de decisão complexa.
3. Subagente Implementador: dependendo da complexidade da tarefa, use um modelo rápido/barato (ex: Claude 3.5 Haiku, GPT-4o-mini) para tarefas simples, ou um modelo de raciocínio (Sonnet, GPT-4o) para lógica complexa.
4. Subagentes Revisores (Especificação e Qualidade): devem usar um modelo rápido e focado (Haiku ou equivalente), pois as tarefas de revisão são focadas em fornecer feedback pontual e não exigem grandes contextos.
5. Se uma tarefa falhar repetidamente com um modelo menor, escale a tarefa despachando um novo subagente com um modelo mais capaz, mas apenas após duas tentativas falhas.

## Princípios Adicionais

1. Cada subagente deve ser despachado fresco e focado estritamente na tarefa atribuída, sem distrações com históricos passados.
2. A revisão em duas etapas (primeiro se atende à especificação, depois a qualidade do código) é inegociável e assegura o alinhamento com as expectativas.
3. A comunicação com o usuário humano só deve ocorrer caso haja dúvidas não resolvidas ou decisões arquiteturais importantes, garantindo o fluxo autônomo na maior parte do tempo.