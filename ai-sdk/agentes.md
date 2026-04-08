# Criação e Consumo de Agentes

1. Para criação de agentes, sempre utilize o padrão arquitetural `ToolLoopAgent`. Pesquise a documentação local atualizada para visualizar as APIs de criação.
2. Siga as convenções de arquivo descritas em `type-safe-agents.md` para saber onde e como salvar corretamente seus agentes e ferramentas (tools).
3. Para segurança de tipagem (Type Safety), ao consumir agentes com o `useChat`, sempre utilize a inferência `InferAgentUIMessage<typeof agent>`. Isso garante que os resultados retornados pelas ferramentas estejam devidamente tipados.
4. Antes de implementar o consumo de um agente no lado do cliente (Client-side), verifique o arquivo `package.json` para descobrir qual é o framework/stack do projeto.
5. Pesquise no guia de início rápido (quickstart) as abordagens recomendadas daquele framework para lidar com "streaming", criação de "API routes" e a integração final com os componentes do cliente.
