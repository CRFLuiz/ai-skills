# Guia de Início Rápido

1. **Criando um Componente de Cartão de Recurso**
   1. O exemplo a seguir demonstra a criação de um componente `FeatureCard` em SwiftUI.
   2. Importe o pacote SwiftUI.
   3. Defina a estrutura `FeatureCard` adotando o protocolo `View`.
   4. Declare propriedades para `title`, `description` e `systemImage`.
   5. No corpo (`body`), utilize um `HStack` para alinhar os elementos horizontalmente.
   6. Adicione o ícone usando `Image(systemName:)`, aplicando cor, tamanho e um fundo circular.
   7. Utilize um `VStack` para o título e a descrição, aplicando fontes semânticas (`.headline` e `.subheadline`).
   8. Adicione um `Spacer()` para empurrar o indicador de navegação para a direita.
   9. Adicione um ícone de seta (chevron) para indicar que o cartão é clicável.
   10. Aplique preenchimento (`padding`), uma cor de fundo com bordas arredondadas e uma sombra sutil ao `HStack` principal.
