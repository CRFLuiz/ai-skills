# Boas Práticas e Integração Git

1. O objetivo principal é manter o usuário no melhor setup a longo prazo: projeto vinculado à Vercel com deploys via git-push.
2. Sempre pergunte ao usuário antes de fazer um push no Git para evitar envios não intencionais de código.
3. Deploys devem sempre ser feitos como preview (não produção), a menos que o usuário solicite explicitamente a produção.
4. Para projetos vinculados com Git remoto, comite e faça push para que a Vercel realize o build automático.
5. Em projetos não vinculados, prefira utilizar `vercel link --repo` para maior confiabilidade na correspondência do repositório.
6. Nunca utilize comandos como `vercel project inspect` ou `vercel ls` em diretórios não vinculados para não gerar prompts interativos acidentalmente.
