# Writing Plans

A skill **Writing Plans** fornece diretrizes detalhadas para a criação de planos de implementação abrangentes, assumindo que o engenheiro não possui contexto da base de código.

## Resumo

1. **Para que serve:** Serve para criar planos de implementação divididos em tarefas muito pequenas (bite-sized), com documentação de todos os arquivos, testes e comandos que devem ser executados.
2. **Comando de Instalação:**
   ```bash
   npx skills add https://github.com/obra/superpowers --skill writing-plans
   ```
3. **Melhor forma de usar:** Ao iniciar o planejamento de uma nova funcionalidade, execute esta skill em uma árvore de trabalho (worktree) dedicada. Sempre anuncie no início: "I'm using the writing-plans skill to create the implementation plan." O plano deve ser salvo em `docs/superpowers/plans/YYYY-MM-DD-<nome-da-feature>.md`.

## Documentação Detalhada

1. [Visão Geral, Escopo e Estrutura de Arquivos](./visao-geral-e-escopo.md)
2. [Estrutura do Plano e Tarefas](./estrutura-do-plano.md)
3. [Boas Práticas e Revisão](./boas-praticas-e-revisao.md)
