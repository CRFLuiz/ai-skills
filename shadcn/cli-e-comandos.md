# CLI e Comandos Úteis

## Uso Geral do CLI

1. Nunca decodifique ou busque códigos de preset manualmente. Passe-os diretamente para o comando de inicialização ou aplicação.
2. Sempre rode os comandos do CLI dentro do diretório do projeto do usuário.

## Fluxo de Trabalho Recomendado

1. Obtenha o contexto do projeto (via `npx shadcn@latest info --json`).
2. Verifique os componentes já instalados antes de tentar adicionar novos.
3. Encontre componentes buscando com `npx shadcn@latest search`.
4. Obtenha documentação e URLs de exemplos usando `npx shadcn@latest docs <componente>`.
5. Instale ou atualize componentes usando `npx shadcn@latest add`.
6. Corrija importações em componentes de terceiros que não utilizam os alias corretos do seu projeto.
7. Revise os componentes adicionados para garantir que seguem as regras de composição e importação de ícones corretas.
8. Ao atualizar componentes com modificações locais, use as flags `--dry-run` e `--diff` para realizar uma mesclagem inteligente.

## Comandos Rápidos

1. Criar novo projeto: `npx shadcn@latest init --name my-app --preset base-nova`
2. Inicializar projeto existente: `npx shadcn@latest init --preset base-nova`
3. Aplicar preset em projeto existente: `npx shadcn@latest apply --preset a2r6bw`
4. Adicionar componentes: `npx shadcn@latest add button card dialog`
5. Visualizar alterações antes de adicionar/atualizar: `npx shadcn@latest add button --dry-run`
6. Ver diff de um arquivo específico: `npx shadcn@latest add button --diff button.tsx`
7. Buscar nos registros: `npx shadcn@latest search @shadcn -q "sidebar"`