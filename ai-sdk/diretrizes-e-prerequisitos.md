# Diretrizes de Uso e Pré-requisitos

1. Antes de iniciar qualquer busca em documentação, verifique se a pasta `node_modules/ai/docs/` existe. Caso contrário, instale apenas o pacote `ai` usando o gerenciador do projeto.
2. Não instale outros pacotes (como `@ai-sdk/openai` ou `@ai-sdk/react`) antecipadamente; deixe para instalá-los somente quando a necessidade surgir no projeto.
3. É extremamente crítico não confiar no conhecimento interno (dados de treinamento) sobre o AI SDK, pois as APIs mudam frequentemente e padrões antigos podem gerar erros graves (exemplo: a função `useChat` sofreu mudanças drásticas).
4. Para a versão 6.0.34 ou superior, pesquise a documentação empacotada usando `grep "termo" node_modules/ai/docs/` e o código fonte usando `grep "termo" node_modules/ai/src/`.
5. Os pacotes de provedores possuem documentação própria no diretório `node_modules/@ai-sdk/<provider>/docs/`.
6. Para versões mais antigas ou caso não encontre localmente, pesquise na web através do endereço oficial `ai-sdk.dev/api/search-docs`.
