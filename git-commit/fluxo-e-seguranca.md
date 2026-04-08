# Fluxo de Trabalho e Segurança

## Fluxo de Trabalho

1. Analise o Diff: verifique as alterações em staging (`git diff --staged`) ou na árvore de trabalho (`git diff`), e cheque o status (`git status --porcelain`).
2. Prepare os Arquivos (se necessário): adicione arquivos específicos (`git add caminho/do/arquivo`), por padrão (`git add *.test.*`) ou de forma interativa (`git add -p`). **Nunca comite segredos** (`.env`, `credentials.json`, chaves privadas).
3. Gere a Mensagem do Commit: determine o tipo (o que mudou?), o escopo (qual área foi afetada?) e a descrição (resumo de uma linha no tempo presente, modo imperativo e com menos de 72 caracteres).
4. Execute o Commit: use `git commit -m "<tipo>[escopo]: <descrição>"` ou formato multilinha com corpo/rodapé.

## Melhores Práticas

1. Faça uma mudança lógica por commit.
2. Use o tempo presente ("add" em vez de "added").
3. Use o modo imperativo ("fix bug" em vez de "fixes bug").
4. Referencie problemas e tickets (ex: `Closes #123`, `Refs #456`).
5. Mantenha a descrição com menos de 72 caracteres.

## Protocolo de Segurança do Git

1. NUNCA atualize a configuração do git.
2. NUNCA execute comandos destrutivos (`--force`, `hard reset`) sem solicitação explícita.
3. NUNCA pule ganchos (`--no-verify`) a menos que o usuário peça.
4. NUNCA faça force push para a branch `main` ou `master`.
5. Se um commit falhar devido a ganchos (hooks), corrija o problema e crie um NOVO commit (não use `amend`).