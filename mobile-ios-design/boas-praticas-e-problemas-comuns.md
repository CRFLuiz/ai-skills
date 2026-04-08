# Boas Práticas e Problemas Comuns

1. **Boas Práticas**
   1. **Uso de Cores Semânticas:** Sempre utilize cores como `.primary`, `.secondary` e `.background` para suporte automático aos modos claro e escuro.
   2. **Adoção dos Símbolos SF:** Utilize os símbolos do sistema para manter a consistência e garantir acessibilidade automática.
   3. **Suporte ao Dynamic Type:** Utilize fontes semânticas (como `.body`, `.headline`) em vez de tamanhos de fonte fixos.
   4. **Inclusão de Acessibilidade:** Adicione modificadores como `.accessibilityLabel()` e `.accessibilityHint()` para melhorar a experiência de todos os usuários.
   5. **Uso de Áreas Seguras:** Respeite o `safeAreaInset` e evite usar preenchimentos fixos nas bordas da tela.
   6. **Implementação de Restauração de Estado:** Utilize `@SceneStorage` para preservar o estado do usuário entre as sessões.
   7. **Suporte a Multitarefa no iPad:** Projete a interface pensando em visualização dividida (split view) e sobreposição (slide over).
   8. **Testes em Dispositivos Físicos:** Lembre-se de que o simulador não captura a experiência completa de desempenho e resposta tátil.

2. **Problemas Comuns**
   1. **Quebra de Layout:** Evite o uso excessivo do modificador `.fixedSize()`; dê preferência a layouts flexíveis.
   2. **Problemas de Desempenho:** Utilize `LazyVStack` ou `LazyHStack` para listas longas que necessitam de rolagem.
   3. **Erros de Navegação:** Certifique-se de que os valores passados para o `NavigationLink` estejam em conformidade com o protocolo `Hashable`.
   4. **Problemas com o Modo Escuro:** Evite usar cores fixas; prefira cores semânticas ou utilize o catálogo de ativos.
   5. **Falhas de Acessibilidade:** Sempre teste a interface com o recurso VoiceOver ativado.
   6. **Vazamentos de Memória:** Fique atento a ciclos de referência fortes dentro de closures.
