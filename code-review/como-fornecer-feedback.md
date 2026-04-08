# Como Fornecer Feedback

## 1. Seja Construtivo

1. Forneça sugestões de como melhorar em vez de apenas apontar o erro.
2. Exemplo bom: "Considere extrair esta lógica para uma função separada para melhor testabilidade e reutilização. Isso tornaria mais fácil de testar em toda a base de código."
3. Exemplo ruim: "Isto está errado. Reescreva."

## 2. Seja Específico

1. Aponte a linha ou a função exata e explique o motivo técnico.
2. Exemplo bom: "Na linha 45, esta consulta pode causar o problema N+1. Considere usar `.select_related('author')` para buscar os objetos relacionados em uma única consulta."
3. Exemplo ruim: "Problemas de performance aqui."

## 3. Priorize Problemas

1. **Crítico:** Falhas de segurança, perda de dados, bugs graves.
2. **Importante:** Problemas de performance, problemas de manutenção.
3. **Agradável de ter (Nice-to-have):** Estilo de código, pequenas melhorias.

## 4. Reconheça um Bom Trabalho

1. Sempre que encontrar soluções elegantes ou um bom design, elogie.
2. Exemplo: "Belo uso do padrão strategy aqui! Isso torna muito fácil adicionar novos métodos de pagamento no futuro."
