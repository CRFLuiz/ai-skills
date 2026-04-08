# Passo a Passo do Layout

## Abordagem Mobile-First

1. Projete a partir de telas pequenas e expanda progressivamente.
2. O código padrão deve focar em Mobile (exemplo: a partir de 320px).
3. Utilize media queries com `min-width` para telas maiores (Tablet, Desktop, Tela Grande).

## Layout com Flexbox e Grid

1. **Flexbox:** Ideal para layouts unidimensionais (como barras de navegação ou listas de cartões).
2. Use `display: flex` com `flex-wrap` e ajuste as larguras baseadas em media queries.
3. **CSS Grid:** Ideal para layouts bidimensionais (como dashboards).
4. Use `grid-template-areas` para reorganizar as seções de acordo com o tamanho da tela.

## Container Queries

1. Aplique estilos com base no tamanho do contêiner pai, não apenas na tela.
2. Defina o contêiner com `container-type` e `container-name`.
3. Use a regra `@container` para aplicar as mudanças de layout quando o contêiner atingir larguras específicas.
