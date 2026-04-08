# Princípios e Configuração do Projeto

## Princípios Básicos

1. O `shadcn/ui` não é uma biblioteca tradicional de componentes, é uma coleção de códigos reutilizáveis que você copia para o seu projeto.
2. Vantagens: propriedade total (código vive no seu repositório), customização completa, sem travamento de versão e com zero sobrecarga em tempo de execução.

## Descoberta e Instalação

1. Use as ferramentas MCP para listar (`list_components`), obter metadados (`get_component_metadata`) e ver demonstrações (`get_component_demo`).
2. Instalação direta (Recomendada): execute `npx shadcn@latest add [nome-do-componente]`. Isso baixa o código, instala as dependências necessárias e atualiza o arquivo `components.json`.
3. Instalação manual: recupere o código fonte usando `get_component`, crie o arquivo manualmente em `components/ui/` e instale as dependências (peer dependencies).
4. Para trabalhar com registros personalizados, use os comandos `get_project_registries` ou `list_items_in_registries`.

## Configuração do Projeto

1. Para novos projetos: `npx shadcn@latest create`.
2. Para inicializar em projetos existentes: `npx shadcn@latest init`. Isso cria o arquivo `components.json` onde você define o estilo (`default`, `new-york`, `vega`, etc.), cor base, variáveis CSS, caminhos do Tailwind e diretivas RSC.
3. Dependências necessárias: React (18+), Tailwind CSS (3.0+), Radix UI ou Base UI, `class-variance-authority`, `clsx` e `tailwind-merge`.

## Arquitetura de Componentes

1. Os componentes base do shadcn ficam na pasta `src/components/ui/`. Seus componentes compostos ficam na pasta `src/components/`.
2. O utilitário `cn()` (em `lib/utils.ts`) é usado por todos os componentes do shadcn para mesclar classes (`twMerge(clsx(inputs))`), permitindo sobrescrever estilos, aplicar classes condicionais e resolver conflitos no Tailwind de forma inteligente.