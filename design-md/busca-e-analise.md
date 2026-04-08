# Busca de Dados e Análise

## Pré-requisitos

1. Acesso ao Servidor MCP do Stitch.
2. Um projeto no Stitch com pelo menos uma tela desenhada.
3. Acesso ao Guia de Prompting Efetivo do Stitch.

## Recuperação e Rede (Uso do MCP)

1. Descoberta de namespace: execute `list_tools` para encontrar o prefixo do MCP do Stitch (ex: `mcp_stitch:`).
2. Busca de projeto: use `list_projects` com o filtro `view=owned`, identifique o projeto alvo e extraia o ID numérico.
3. Busca de tela: use `list_screens` com o ID do projeto, identifique a tela (ex: "Home") e extraia o ID da tela.
4. Busca de metadados: use `get_screen` passando os IDs do projeto e da tela para obter o URL de download do HTML/CSS (`htmlCode.downloadUrl`), a imagem da tela (`screenshot.downloadUrl`) e outros detalhes de layout.
5. Download de ativos: use `web_fetch` ou `read_url_content` para baixar o código HTML e analisar as classes Tailwind, CSS personalizado e padrões de componentes.
6. Extração de metadados do projeto: use `get_project` para obter o tema de design (modo de cor, fontes, arredondamentos) e diretrizes de design.

## Instruções de Análise e Síntese

1. Extraia a identidade do projeto (Título e ID).
2. Defina a atmosfera avaliando a captura de tela e a estrutura HTML, usando adjetivos evocativos (ex: "Minimalista", "Utilitário", "Denso").
3. Mapeie a paleta de cores identificando as cores principais. Dê um nome descritivo (ex: "Azul-petróleo profundo"), inclua o código hexadecimal exato entre parênteses e defina sua função (ex: "Usado para ações primárias").
4. Traduza a geometria e formas (CSS/Tailwind) para descrições físicas (ex: `rounded-full` vira "Formato de pílula", `rounded-lg` vira "Cantos sutilmente arredondados").
5. Descreva a profundidade e elevação (sombras), explicando como a interface lida com camadas.