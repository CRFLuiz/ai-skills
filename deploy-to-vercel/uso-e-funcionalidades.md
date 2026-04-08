# Uso e Funcionalidades

1. A skill coleta o estado do projeto antes de qualquer ação para decidir o melhor método de deploy.
2. Verifica a existência de um repositório Git remoto através de `git remote get-url origin`.
3. Verifica se o projeto já está vinculado à Vercel checando os arquivos `.vercel/project.json` ou `.vercel/repo.json`.
4. Confirma se a CLI da Vercel está instalada e autenticada utilizando `vercel whoami`.
5. Lista as equipes disponíveis usando o comando `vercel teams list --format json`.
6. Solicita que o usuário escolha uma equipe caso pertença a várias, passando o valor no parâmetro `--scope`.
7. Se não houver repositório Git, o deploy direto é realizado com `vercel deploy [path] -y --no-wait`.
8. O status de deploys diretos pode ser monitorado pelo comando `vercel inspect <deployment-url>`.
