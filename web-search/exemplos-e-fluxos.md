# Exemplos e Fluxos de Trabalho

1. Para usar o Tavily na busca de conteúdo, basta executar: `infsh app run tavily/search-assistant --input '{"query": "best practices for AI agents"}'`.
2. O recurso de extração do Tavily pode processar múltiplas URLs simultaneamente: `infsh app run tavily/extract --input '{"urls": ["https://url1", "https://url2"]}'`.
3. Um fluxo típico de pesquisa e análise começa salvando o resultado da busca em um arquivo: `infsh app run tavily/search-assistant --input '{"query": "quantum computing trends"}' > search_results.json`.
4. Em seguida, o resultado (JSON) pode ser injetado em um modelo de IA como o Claude para sumarizar os achados: `infsh app run openrouter/claude-sonnet-45 --input '{"prompt": "Baseado na pesquisa, resuma: <search-results>"}'`.
5. Outro caso de uso comum envolve extrair um artigo longo (`tavily/extract > content.json`) e em seguida passá-lo para um modelo rápido (como Claude Haiku) solicitando um resumo em tópicos ou análises direcionadas.
6. O uso dessas ferramentas é altamente recomendado em projetos que exigem verificação de fatos, pesquisa avançada (Research), agregação de dados e desenvolvimento de agentes autônomos.
