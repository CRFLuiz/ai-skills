# Referência Rápida (Acessibilidade e Interação)

Esta é a lista rápida das regras para as duas prioridades críticas (CRITICAL) avaliadas pela skill.

## 1. Acessibilidade (Accessibility)

1. **color-contrast:** Proporção mínima de 4.5:1 para texto normal (e 3:1 para texto grande), seguindo as diretrizes do Material Design.
2. **focus-states:** Anéis de foco claramente visíveis em elementos interativos (2–4px), alinhado com Apple HIG e Material Design.
3. **alt-text:** Texto alternativo descritivo para imagens significativas.
4. **aria-labels:** Uso de `aria-label` para botões formados apenas por ícones; equivalente a `accessibilityLabel` em nativo.
5. **keyboard-nav:** A ordem de tabulação (Tab) deve corresponder à ordem visual; suporte total a teclado (Apple HIG).
6. **form-labels:** Utilize sempre a tag `label` contendo o atributo `for`.
7. **skip-links:** Forneça atalhos para "pular para o conteúdo principal" para usuários de teclado.
8. **heading-hierarchy:** Use sequências lógicas de cabeçalhos (de `h1` a `h6`), sem pular níveis hierárquicos.
9. **color-not-only:** Não transmita informações dependendo exclusivamente da cor (adicione um ícone ou texto de apoio).
10. **dynamic-type:** Dê suporte ao escalonamento de texto do sistema operacional; evite que o texto seja truncado/cortado conforme ele cresce (Apple Dynamic Type, MD).
11. **reduced-motion:** Respeite a preferência de acessibilidade `prefers-reduced-motion`; reduza ou desative animações quando solicitado.
12. **voiceover-sr:** Forneça `accessibilityLabel` e `accessibilityHint` significativos, e mantenha uma ordem de leitura lógica para leitores de tela como o VoiceOver.
13. **escape-routes:** Forneça rotas de fuga claras (botões de Cancelar/Voltar) em modais e fluxos de várias etapas.
14. **keyboard-shortcuts:** Preserve os atalhos do sistema e de acessibilidade; ofereça alternativas via teclado para interações complexas (como drag-and-drop).

## 2. Toque e Interação (Touch & Interaction)

1. **touch-target-size:** O tamanho mínimo da área de toque deve ser 44x44pt (Apple) ou 48x48dp (Material); estenda a área de clique invisível se o visual do botão for menor que isso.
2. **touch-spacing:** Espaçamento mínimo de 8px (ou 8dp) entre alvos de toque, prevenindo toques acidentais.
3. **hover-vs-tap:** Utilize clique/toque para interações primárias; não baseie interações críticas apenas no *hover* (passar o cursor do mouse), pois isso exclui usuários mobile.
4. **loading-buttons:** Desative o botão durante operações assíncronas para evitar cliques duplicados; mostre um spinner ou barra de progresso em seu interior.
5. **error-feedback:** Exiba mensagens de erro claras, colocadas estrategicamente o mais próximo possível do local do problema.
