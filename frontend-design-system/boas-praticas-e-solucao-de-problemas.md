# Boas Práticas e Solução de Problemas

1. **Boas Práticas**
   1. **Comece pela hierarquia de conteúdo:** A interface deve seguir a prioridade do conteúdo.
   2. **Escala de espaçamento consistente:** Utilize o sistema baseado em múltiplos de 8px e evite espaçamentos aleatórios (ad-hoc).
   3. **Animação com intenção:** Aplique animações apenas para transições significativas.
   4. **Teste no mobile:** Verifique a integridade do layout nas menores telas primeiro.
   5. **Acessibilidade em primeiro lugar:** Considere os requisitos de acessibilidade desde a fase de design.

2. **Problemas Comuns e Armadilhas**
   1. **Uso excessivo de efeitos e gradientes:** Mantenha o design limpo e simples.
   2. **Escala de tipografia inconsistente:** Siga sempre a escala definida nos tokens.
   3. **Ignorar a acessibilidade:** Sempre cheque o contraste de cores e a navegação por teclado.

3. **Solução de Problemas Frequentes**
   1. **Problema:** A interface parece genérica.
      **Causa:** Falta de direção visual ou tokens não definidos.
      **Solução:** Forneça referências de estilo e uma paleta de cores consistente.
   2. **Problema:** O layout quebra no mobile.
      **Causa:** Falta de regras definidas de grade responsiva.
      **Solução:** Defina os pontos de quebra (breakpoints) e o comportamento de empilhamento (stacking) dos elementos.
   3. **Problema:** Componentes inconsistentes.
      **Causa:** Os tokens de design não estão sendo aplicados.
      **Solução:** Referencie todos os valores estritamente a partir dos design tokens.
