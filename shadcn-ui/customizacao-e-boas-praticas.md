# Customização e Boas Práticas

## Customização e Variantes

1. Customização de Tema: edite a configuração do Tailwind e as variáveis CSS no arquivo global (ex: `app/globals.css`). Defina as variáveis no `@layer base` para o modo claro (`:root`) e modo escuro (`.dark`).
2. Variantes de Componentes: utilize a biblioteca `class-variance-authority` (cva) para organizar a lógica de variantes de botões, inputs, etc., combinando com as variantes padrão (defaultVariants).
3. Estendendo Componentes: para adicionar lógica ou criar variações, crie um wrapper dentro de `components/` (ex: `custom-button.tsx`) e não modifique os arquivos dentro de `components/ui/` diretamente, a menos que seja necessário alterar a aparência global.

## Blocos e Componentes Complexos

1. O `shadcn/ui` oferece blocos completos de UI (ex: formulários de login, dashboards, calendários).
2. Utilize `list_blocks` e `get_block` para visualizar a lista e obter o código fonte dos blocos.

## Acessibilidade e Solução de Problemas

1. Acessibilidade nativa: os componentes construídos sobre Radix UI já incluem suporte completo para teclado, atributos ARIA adequados e gerenciamento lógico de foco. Ao customizar, certifique-se de manter os atributos ARIA e os manipuladores de teclado.
2. Erros de Importação: verifique o `components.json` e garanta que o arquivo `tsconfig.json` inclui o alias de caminho (ex: `"@/*": ["./src/*"]`).
3. Conflitos de Estilo: confirme que o `globals.css` está importado no layout raiz e que as variáveis CSS batem com o tema configurado no Tailwind.
4. Validação de Qualidade: antes de commitar, execute verificação de tipos TypeScript (`tsc --noEmit`), linter e testes de acessibilidade (ex: axe DevTools). Verifique a visualização nos modos claro e escuro e a responsividade em diversos tamanhos de tela.