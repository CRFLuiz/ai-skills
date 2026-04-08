# Tipos de Commit e Formato

## Formato do Conventional Commit

1. A estrutura básica é: `<tipo>[escopo opcional]: <descrição>`.
2. Opcionalmente, pode conter um `[corpo]` e um `[rodapé(s)]`.

## Tipos de Commit

1. `feat`: Nova funcionalidade.
2. `fix`: Correção de bug.
3. `docs`: Apenas documentação.
4. `style`: Formatação/estilo (sem alteração de lógica).
5. `refactor`: Refatoração de código (sem adicionar funcionalidade ou corrigir bug).
6. `perf`: Melhoria de desempenho.
7. `test`: Adição ou atualização de testes.
8. `build`: Sistema de build ou dependências.
9. `ci`: Mudanças de CI/configuração.
10. `chore`: Manutenção ou tarefas diversas.
11. `revert`: Reversão de um commit anterior.

## Breaking Changes (Mudanças Críticas)

1. Podem ser indicadas com um ponto de exclamação após o tipo/escopo (ex: `feat!: remover endpoint obsoleto`).
2. Podem ser indicadas no rodapé com a palavra `BREAKING CHANGE:` seguida da explicação da mudança.