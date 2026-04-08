# Diretrizes Estéticas e Implementação

## Tipografia, Cor e Tema

1. Escolha fontes bonitas e únicas, combinando uma fonte de exibição distinta com uma fonte de corpo refinada.
2. Use uma escala de tipos modular com dimensionamento fluido (`clamp`).
3. Varie os pesos e tamanhos das fontes para criar hierarquia visual clara.
4. Evite fontes excessivamente usadas (Inter, Roboto, Arial) ou tipografia monoespaçada apenas para parecer "técnico".
5. Comprometa-se com uma paleta coesa, usando cores dominantes com contrastes nítidos.
6. Use funções modernas de cor CSS (`oklch`, `color-mix`, `light-dark`).
7. Tinte seus tons neutros com a cor da marca e evite preto puro (`#000`) ou branco puro (`#fff`).
8. Evite a paleta clichê de IA: ciano no escuro, gradientes de roxo para azul, ou texto com gradiente apenas para "impacto".

## Layout, Espaço e Detalhes Visuais

1. Crie ritmo visual por meio de espaçamentos variados, abraçando a assimetria e quebrando o grid intencionalmente para dar ênfase.
2. Use espaçamento fluido com `clamp()` que respire em telas maiores.
3. Evite colocar tudo dentro de cards, aninhar cards ou usar grids de cards idênticos repetidos infinitamente.
4. Evite centralizar tudo; texto alinhado à esquerda com layouts assimétricos parece mais bem desenhado.
5. Use elementos decorativos intencionais que reforcem a marca.
6. Evite o uso excessivo de glassmorfismo, bordas arredondadas com cores grossas de um lado só, ou modais (a menos que não haja alternativa).

## Movimento, Interação e Responsividade

1. Foco em momentos de alto impacto: um carregamento de página bem orquestrado é melhor do que micro-interações espalhadas.
2. Use animação para transmitir mudanças de estado e utilize suavização exponencial (ease-out-quart/quint/expo).
3. Evite animar propriedades de layout (width, height, padding); use apenas `transform` e `opacity`.
4. Faça com que as interações pareçam rápidas, utilizando UI otimista.
5. Use divulgação progressiva: comece simples e revele opções avançadas através da interação.
6. Projete estados vazios (empty states) que ensinem a usar a interface.
7. Use container queries (`@container`) para responsividade no nível do componente e adapte a interface em vez de apenas encolhê-la ou esconder funções críticas.

## UX Writing e o Teste "AI Slop"

1. Faça com que cada palavra justifique sua presença.
2. Não repita informações que os usuários já podem ver.
3. Aplique o teste crítico: se você mostrasse a interface e dissesse que foi feita por IA, a pessoa acreditaria imediatamente? Se sim, há um problema. O design deve fazer as pessoas perguntarem "como isso foi feito?".
4. Combine a complexidade da implementação com a visão estética escolhida, interpretando criativamente e fazendo escolhas inesperadas.