# Boas Práticas e Solução de Problemas

1. **Boas Práticas Recomendadas**
   1. Sempre salve capturas de tela antes de fazer qualquer correção.
   2. Corrija um problema de cada vez e verifique cada um.
   3. Siga o estilo de código já existente no projeto.
   4. Confirme com o usuário antes de fazer grandes mudanças.
   5. Documente os detalhes da correção cuidadosamente.

2. **O Que Não Fazer**
   1. Não faça grandes refatorações sem confirmação prévia.
   2. Não ignore sistemas de design ou diretrizes de marca.
   3. Não faça correções que prejudiquem a performance do site.
   4. Não corrija vários problemas ao mesmo tempo, pois isso dificulta a verificação.

3. **Solução de Problemas**
   1. **Arquivos de estilo não encontrados:** Verifique as dependências no `package.json`, considere a possibilidade de uso de CSS-in-JS ou geração em tempo de build, e pergunte ao usuário se necessário.
   2. **Correções não refletidas no navegador:** Verifique se o HMR (Hot Module Replacement) do servidor de desenvolvimento está funcionando, limpe o cache do navegador, recompile o projeto ou verifique problemas de especificidade do CSS.
   3. **Correções afetando outras áreas:** Reverta as mudanças, utilize seletores CSS mais específicos, considere o uso de CSS Modules ou estilos com escopo e consulte o usuário para confirmar o impacto.
