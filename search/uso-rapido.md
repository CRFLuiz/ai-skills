# Uso Rápido e Exemplos

## Usando o Script Local

1. O script pode ser executado localmente via `./scripts/search.sh '<json>'`.

### Exemplos com o Script

1. **Busca Básica:**
   `./scripts/search.sh '{"query": "python async patterns"}'`
2. **Com opções:**
   `./scripts/search.sh '{"query": "React hooks tutorial", "max_results": 10}'`
3. **Busca avançada com filtros:**
   `./scripts/search.sh '{"query": "AI news", "time_range": "week", "max_results": 10}'`
4. **Busca filtrada por domínio:**
   `./scripts/search.sh '{"query": "machine learning", "include_domains": ["arxiv.org", "github.com"], "search_depth": "advanced"}'`

## Usando a API (cURL)

### Busca Básica

```bash
curl --request POST \
  --url https://api.tavily.com/search \
  --header "Authorization: Bearer $TAVILY_API_KEY" \
  --header 'Content-Type: application/json' \
  --data '{
    "query": "latest developments in quantum computing",
    "max_results": 5
  }'
```

### Busca Avançada e Filtrada

```bash
curl --request POST \
  --url https://api.tavily.com/search \
  --header "Authorization: Bearer $TAVILY_API_KEY" \
  --header 'Content-Type: application/json' \
  --data '{
    "query": "Python async best practices",
    "include_domains": ["docs.python.org", "realpython.com", "github.com"],
    "search_depth": "advanced"
  }'
```
