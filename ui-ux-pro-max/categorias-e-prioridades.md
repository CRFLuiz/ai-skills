# Categorias e Prioridades

Para referência de IA ou uso humano, a skill organiza suas diretrizes em uma escala de prioridade de 1 a 10. Você deve focar primeiro nas categorias mais cruciais antes de avançar para os detalhes menores.

## Tabela de Regras (Prioridades 1 a 10)

1. **Accessibility (CRITICAL):**
   - **Foco principal:** Contraste 4.5:1, Alt text, Navegação por teclado, Aria-labels.
   - **Anti-padrões (Evite):** Remover anéis de foco, botões compostos apenas por ícones sem rótulos (labels).
2. **Touch & Interaction (CRITICAL):**
   - **Foco principal:** Tamanho mínimo 44x44px, espaçamento maior que 8px, feedback de carregamento.
   - **Anti-padrões (Evite):** Dependência apenas do *hover* (passar o mouse), mudanças de estado instantâneas (0ms).
3. **Performance (HIGH):**
   - **Foco principal:** WebP/AVIF, Lazy loading, Reservar espaço (CLS < 0.1).
   - **Anti-padrões (Evite):** Layout thrashing, Cumulative Layout Shift (CLS).
4. **Style Selection (HIGH):**
   - **Foco principal:** Corresponder ao tipo de produto, Consistência visual, Ícones SVG (sem emoji).
   - **Anti-padrões (Evite):** Misturar estilos *flat* e *skeuomorphic* aleatoriamente, usar Emojis como ícones oficiais.
5. **Layout & Responsive (HIGH):**
   - **Foco principal:** Breakpoints *mobile-first*, Viewport meta configurado, Sem rolagem horizontal.
   - **Anti-padrões (Evite):** Rolagem horizontal em mobile, larguras de contêiner em pixels fixos, desativar zoom nativo.
6. **Typography & Color (MEDIUM):**
   - **Foco principal:** Fonte base de 16px, Line-height 1.5, Uso de tokens semânticos de cores.
   - **Anti-padrões (Evite):** Texto do corpo menor que 12px, cor cinza sobre fundo cinza, uso de código Hex bruto em componentes em vez de variáveis/tokens.
7. **Animation (MEDIUM):**
   - **Foco principal:** Duração entre 150–300ms, Movimento deve transmitir um significado, Continuidade espacial.
   - **Anti-padrões (Evite):** Animação meramente decorativa, animar atributos caros (width/height), desrespeitar as preferências de *reduced-motion*.
8. **Forms & Feedback (MEDIUM):**
   - **Foco principal:** Rótulos visíveis (labels), Erro posicionado próximo ao campo que gerou o erro, Texto de ajuda (*helper text*), Divulgação progressiva de dados.
   - **Anti-padrões (Evite):** Rótulo contido apenas como *placeholder*, Erros exibidos apenas no topo da tela, Sobrecarregar o usuário logo de cara.
9. **Navigation Patterns (HIGH):**
   - **Foco principal:** Ação de voltar (back) previsível, Navegação inferior contendo até 5 itens, Suporte a *Deep linking*.
   - **Anti-padrões (Evite):** Navegação sobrecarregada, comportamento de voltar quebrado, páginas sem suporte a *deep links*.
10. **Charts & Data (LOW):**
    - **Foco principal:** Legendas claras, Tooltips informativas, Cores com boa acessibilidade.
    - **Anti-padrões (Evite):** Depender apenas da cor para transmitir um significado (daltônicos podem não diferenciar os gráficos).
