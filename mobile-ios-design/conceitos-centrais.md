# Conceitos Centrais

1. **Princípios das Diretrizes de Interface Humana (HIG)**
   1. **Clareza:** O conteúdo deve ser legível, os ícones precisos e os adornos sutis.
   2. **Deferência:** A interface do usuário ajuda os usuários a entender o conteúdo sem competir com ele.
   3. **Profundidade:** Camadas visuais e movimento transmitem hierarquia e possibilitam a navegação.
   4. **Considerações de Plataforma:**
      1. iOS: Prioridade ao toque, telas compactas, orientação retrato.
      2. iPadOS: Tela maior, multitarefa, suporte a ponteiro.
      3. visionOS: Computação espacial, entrada por olho/mão.

2. **Sistema de Layout do SwiftUI**
   1. **Layouts baseados em pilhas (Stacks):** Uso de `VStack` para alinhamento vertical e `HStack` para alinhamento horizontal com espaçamento flexível.
   2. **Layouts em Grade (Grids):** Uso de `LazyVGrid` para grades adaptáveis ou com colunas fixas.

3. **Padrões de Navegação**
   1. **NavigationStack (iOS 16+):** Utilizado para navegação hierárquica baseada em caminho.
   2. **TabView (iOS 18+):** Utilizado para navegação principal em abas na parte inferior da tela.

4. **Integração com o Sistema**
   1. **Símbolos SF:** Uso de ícones do sistema com suporte a cores, valores variáveis e efeitos de animação.
   2. **Dynamic Type:** Uso de fontes semânticas (como `.headline`, `.body`) que se ajustam de acordo com as preferências do usuário.

5. **Design Visual**
   1. **Cores e Materiais:** Uso de cores semânticas que se adaptam automaticamente ao modo claro/escuro e materiais do sistema para efeitos de desfoque.
   2. **Sombras e Profundidade:** Aplicação de sombras para criar aparência de elevação nos cartões e elementos.
