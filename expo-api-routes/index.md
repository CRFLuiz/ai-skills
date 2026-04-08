# Expo API Routes

Uma skill para criar rotas de API no Expo, permitindo executar código no lado do servidor com segurança e eficiência.

## Resumo

1. **Para que serve:** Permite a criação de endpoints de API diretamente no seu aplicativo Expo, ideal para ocultar segredos do servidor, acessar bancos de dados, criar webhooks e validar dados antes de salvar.
2. **Comando de instalação:** `npx skills add expo/skills/expo-api-routes`
3. **Melhor forma de usar:** Utilizar para operações que não devem ser expostas no cliente, mantendo as chaves de API seguras e processando validações no backend, criando arquivos com o sufixo `+api.ts` dentro do diretório `app/api/`.

## Documentação Detalhada

1. [Quando Usar e Quando Evitar](./quando-usar-e-evitar.md)
2. [Estrutura e Métodos HTTP](./estrutura-e-metodos.md)
3. [Manipulação de Requisições](./manipulacao-de-requisicoes.md)
4. [Testes e Deploy](./testes-e-deploy.md)
