# Testes e Deploy

## Testando Localmente

1. Inicie o servidor de desenvolvimento com suporte a rotas de API executando o comando:
   `npx expo serve`
2. Isso inicia um servidor local em `http://localhost:8081` com suporte completo a rotas de API.
3. Teste usando `curl` com os comandos abaixo:
   `curl http://localhost:8081/api/hello`
   `curl -X POST http://localhost:8081/api/users -H "Content-Type: application/json" -d '{"name":"Test"}'`

## Deploy para EAS Hosting

1. Instale o EAS CLI globalmente com o comando:
   `npm install -g eas-cli`
2. Faça login na sua conta Expo usando o comando:
   `eas login`
3. Execute o comando de deploy para compilar e enviar suas rotas de API para o EAS Hosting (Cloudflare Workers):
   `eas deploy`

## Variáveis de Ambiente para Produção

1. Para criar um segredo via terminal, use:
   `eas env:create --name OPENAI_API_KEY --value sk-xxx --environment production`
2. Como alternativa, você pode usar o painel do Expo para configurar suas variáveis.

## Domínio Personalizado

1. Configure domínios personalizados diretamente no arquivo `eas.json`.
2. Como alternativa, use o painel do Expo para configurar domínios.

## Runtime do EAS Hosting

1. As rotas de API são executadas no Cloudflare Workers, portanto, operam em um ambiente Edge.
