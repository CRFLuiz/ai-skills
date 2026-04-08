# Guia de Referência Rápida

## 1. Performance de Listas (CRÍTICO)

1. Use o FlashList para listas grandes.
2. Memorize (memoize) os componentes de itens da lista.
3. Estabilize referências de callbacks.
4. Evite objetos de estilo inline.
5. Extraia funções para fora da renderização.
6. Otimize imagens em listas.
7. Mova trabalhos custosos para fora dos itens.
8. Use tipos de itens para listas heterogêneas.

## 2. Animação (ALTO)

1. Anime apenas propriedades de transformação e opacidade.
2. Use `useDerivedValue` para animações computadas.
3. Use `Gesture.Tap` em vez de Pressable.

## 3. Navegação (ALTO)

1. Use navegadores de pilha nativa e abas nativas em vez de navegadores JS.

## 4. Padrões de UI (ALTO)

1. Use `expo-image` para todas as imagens.
2. Use Galeria para lightboxes de imagens.
3. Use Pressable em vez de TouchableOpacity.
4. Trate áreas seguras em ScrollViews.
5. Use `contentInset` para cabeçalhos.
6. Use menus de contexto nativos.
7. Use modais nativos quando possível.
8. Use `onLayout` para medir visualizações, não `measure()`.
9. Use `StyleSheet.create` ou Nativewind para estilização.

## 5. Gerenciamento de Estado (MÉDIO)

1. Minimize assinaturas de estado.
2. Use o padrão dispatcher para callbacks.
3. Mostre fallback na primeira renderização.
4. Desestruture para o React Compiler.
5. Trate valores compartilhados do reanimated com o compiler.

## 6. Renderização (MÉDIO)

1. Envolva texto em componentes Text.
2. Evite o uso de `&&` com valores "falsy" para renderização condicional.

## 7. Monorepo (MÉDIO)

1. Mantenha as dependências nativas no pacote do aplicativo.
2. Use versões únicas em todos os pacotes.

## 8. Configuração (BAIXO)

1. Use plugins de configuração para fontes personalizadas.
2. Organize as importações do design system.
3. Faça hoist na criação do objeto Intl.