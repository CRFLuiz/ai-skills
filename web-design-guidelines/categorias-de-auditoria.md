# Categorias de Auditoria (As Regras)

A ferramenta verifica seu código contra mais de 100 regras da Vercel. Embora a lista exata seja trazida dinamicamente no momento da execução, as categorias abrangidas na auditoria incluem:

1. **Accessibility (Acessibilidade):** Avalia rótulos `aria-labels`, HTML semântico e manipuladores de eventos de teclado (keyboard handlers).
2. **Focus States (Estados de Foco):** Exige que os focos sejam visíveis e usa os padrões adequados de `focus-visible`.
3. **Forms (Formulários):** Verifica a presença de `autocomplete`, validações de inputs e tratamento correto de mensagens de erro.
4. **Animation (Animações):** Respeita as preferências de usuário para menos movimento (`prefers-reduced-motion`) e usa transformações amigáveis ao "compositor" (para performance em animações).
5. **Typography (Tipografia):** Cuida de detalhes como aspas curvadas (curly quotes), elipses (reticências), e o uso de `tabular-nums` para números.
6. **Images (Imagens):** Confere as dimensões declaradas, a presença de carregamento preguiçoso (`lazy loading`) e textos alternativos (`alt text`).
7. **Performance:** Avalia o uso de "virtualization" para listas, evita layout thrashing (re-cálculo massivo de layout da página) e aplica `preconnect` para origens externas.
8. **Navigation & State (Navegação & Estado):** Assegura que a URL reflete o estado atual e dá suporte ao "deep-linking" (navegação direta para sub-seções).
9. **Dark Mode & Theming (Modo Escuro e Temas):** Observa as regras de `color-scheme` e a meta tag `theme-color`.
10. **Touch & Interaction (Toque e Interação):** Ajusta o uso de `touch-action` e a aparência de cliques de destaque (`tap-highlight`).
11. **Locale & i18n (Internacionalização):** Avalia a aplicação das formatações padrão da plataforma como `Intl.DateTimeFormat` e `Intl.NumberFormat`.
