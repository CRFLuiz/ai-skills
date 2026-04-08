# Fluxo de Trabalho

1. **Fase 1: Coleta de Informações**
   1. **Confirmação da URL:** Caso a URL não seja fornecida, o sistema solicitará.
   2. **Compreensão da Estrutura:** Será identificado o framework utilizado, o método de estilização, a localização dos arquivos e o escopo da revisão.
   3. **Detecção Automática:** O sistema tentará detectar a estrutura automaticamente através de arquivos como `package.json`, `tailwind.config`, entre outros.
   4. **Identificação da Estilização:** Serão procurados padrões como CSS Puro, SCSS, CSS Modules, Tailwind CSS, styled-components, etc.

2. **Fase 2: Inspeção Visual**
   1. **Navegação na Página:** O navegador acessa a URL, tira capturas de tela e obtém o DOM.
   2. **Itens de Inspeção de Layout:** Identificação de transbordamento de elementos, sobreposição, problemas de alinhamento e espaçamentos inconsistentes.
   3. **Itens de Inspeção Responsiva:** Testes em larguras para Mobile (375px), Tablet (768px), Desktop (1280px) e Wide (1920px) para achar falhas de quebra de layout ou alvos de toque pequenos.
   4. **Itens de Inspeção de Acessibilidade:** Verificação de contraste insuficiente, falta de estado de foco e ausência de texto alternativo em imagens.
   5. **Itens de Consistência Visual:** Checagem de mistura de fontes, cores não padronizadas e espaçamentos não uniformes.

3. **Fase 3: Correção de Problemas**
   1. **Priorização de Problemas:** Problemas de layout que afetam a funcionalidade são classificados como P1 (Corrigir Imediatamente). Problemas visuais que degradam a UX são P2 (Corrigir Depois). Inconsistências menores são P3 (Corrigir se Possível).
   2. **Identificação dos Arquivos Fonte:** Realizada através de pesquisa por seletores, pesquisa baseada em componentes ou filtragem por padrão de arquivos.
   3. **Aplicação das Correções:** Seguindo princípios de mudanças mínimas, respeito aos padrões existentes, evitar mudanças drásticas que quebrem o código e adição de comentários explicativos.

4. **Fase 4: Re-verificação**
   1. **Confirmação Pós-correção:** Recarregar o navegador, capturar novas telas e comparar o antes e depois.
   2. **Testes de Regressão:** Verificar se as correções não afetaram outras áreas ou a exibição responsiva.
   3. **Decisão de Iteração:** Se ainda houver problemas, retorna-se à Fase 2. Se não houver, prossegue-se para o Relatório de Conclusão. O limite é de 3 tentativas de correção por problema antes de consultar o usuário.
