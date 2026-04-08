# Quando Usar e Quando Evitar

## Quando Usar API Routes

Você deve usar rotas de API quando precisar de:

1. **Segredos do lado do servidor:** Chaves de API, credenciais de banco de dados ou tokens que nunca devem chegar ao cliente.
2. **Operações de banco de dados:** Consultas diretas ao banco de dados que não devem ser expostas.
3. **Proxies de API de terceiros:** Ocultar chaves de API ao chamar serviços externos (OpenAI, Stripe, etc.).
4. **Validação no servidor:** Validar dados antes de realizar gravações no banco de dados.
5. **Endpoints de Webhook:** Receber callbacks de serviços como Stripe ou GitHub.
6. **Limitação de taxa (Rate limiting):** Controlar o acesso no nível do servidor.
7. **Computação pesada:** Descarregar processamento que seria lento em dispositivos móveis.

## Quando NÃO Usar API Routes

Evite usar rotas de API quando:

1. **Os dados já são públicos:** Use `fetch` direto para APIs públicas em vez disso.
2. **Não são necessários segredos:** Dados estáticos ou operações seguras para o cliente.
3. **Atualizações em tempo real são necessárias:** Use WebSockets ou serviços como Supabase Realtime.
4. **CRUD Simples:** Considere Firebase, Supabase ou Convex para backends gerenciados.
5. **Uploads de arquivos:** Use uploads diretos para o armazenamento (URLs pré-assinadas do S3, Cloudflare R2).
6. **Apenas autenticação:** Use Clerk, Auth0 ou Firebase Auth em vez disso.
