# Imagens e Tipografia

## Imagens Responsivas

1. Forneça imagens adequadas ao tamanho do dispositivo para otimizar o desempenho.
2. Use o atributo `srcset` e `sizes` na tag de imagem para diferentes resoluções.
3. Use o elemento `picture` para direção de arte (exemplo: imagens em formato retrato para mobile e paisagem para desktop).
4. No CSS, utilize media queries para alterar imagens de fundo (background images) ou use a função `image-set()`.

## Tipografia Responsiva

1. Ajuste o tamanho do texto com base no tamanho da tela.
2. A função `clamp()` é ideal para dimensionamento fluido (definindo valor mínimo, preferencial e máximo).
3. Alternativamente, use a abordagem de media queries para redefinir o tamanho da fonte em diferentes pontos de interrupção.
