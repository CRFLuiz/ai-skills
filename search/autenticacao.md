# Autenticação e Configuração Inicial

## Autenticação OAuth (Padrão)

1. O script usa OAuth através do servidor MCP da Tavily.
2. Não é necessária configuração manual inicial.
3. Na primeira execução, o sistema verificará a existência de tokens em `~/.mcp-auth/`.
4. Caso nenhum token seja encontrado, o navegador será aberto automaticamente para a autenticação OAuth.
5. **Nota:** Você deve ter uma conta existente na Tavily (`tavily.com`), pois o fluxo suporta apenas login, não criação de conta.

## Alternativa: Chave de API

1. Se preferir usar uma chave de API, obtenha uma em `https://tavily.com`.
2. Adicione a chave ao arquivo `~/.claude/settings.json` conforme o exemplo abaixo:

```json
{
  "env": {
    "TAVILY_API_KEY": "tvly-sua-chave-de-api-aqui"
  }
}
```
