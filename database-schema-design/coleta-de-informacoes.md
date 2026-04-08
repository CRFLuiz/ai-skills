# Coleta de Informações

## Informações Obrigatórias

Antes de iniciar o design, colete:

1. **Tipo de Banco de Dados:** PostgreSQL, MySQL, MongoDB, SQLite, etc.
2. **Descrição do Domínio:** O que será armazenado (ex: e-commerce, blog, rede social).
3. **Entidades Principais:** Objetos de dados centrais (ex: Usuário, Produto, Pedido).

## Informações Opcionais

1. **Volume de Dados Esperado:** Pequeno (<10K linhas), Médio (10K-1M), Grande (>1M). O padrão é Médio.
2. **Proporção de Leitura/Escrita:** Foco em leitura, foco em escrita ou balanceado. O padrão é balanceado.
3. **Requisitos de Transação:** Se ACID é obrigatório. O padrão é verdadeiro.
4. **Sharding/Particionamento:** Se será necessária distribuição de dados em larga escala. O padrão é falso.
