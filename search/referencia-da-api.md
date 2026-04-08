# Referência da API

## Endpoint

1. **Método:** POST
2. **URL:** `https://api.tavily.com/search`

## Cabeçalhos

1. **Authorization:** `Bearer <TAVILY_API_KEY>`
2. **Content-Type:** `application/json`

## Campos do Corpo da Requisição (Request Body)

1. `query` (string, Obrigatório): Consulta de pesquisa (manter abaixo de 400 caracteres).
2. `max_results` (inteiro, Padrão: 10): Máximo de resultados (0-20).
3. `search_depth` (string, Padrão: "basic"): Níveis disponíveis são `ultra-fast`, `fast`, `basic`, `advanced`.
4. `topic` (string, Padrão: "general"): Tópico de pesquisa (apenas `general`).
5. `time_range` (string, Padrão: null): Opções disponíveis são `day`, `week`, `month`, `year`.
6. `include_domains` (array, Padrão: []): Domínios a serem incluídos (máximo 300).
7. `exclude_domains` (array, Padrão: []): Domínios a serem excluídos (máximo 150).
8. `include_raw_content` (booleano, Padrão: false): Incluir conteúdo completo da página.

## Profundidade de Pesquisa (Search Depth)

1. `ultra-fast`: Latência mais baixa, relevância mais baixa.
2. `fast`: Latência baixa, boa relevância.
3. `basic`: Equilibrado, propósito geral.
4. `advanced`: Maior latência, altíssima precisão (recomendação padrão).
