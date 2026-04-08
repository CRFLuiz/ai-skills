# Estratégia de Indexação

## Passos para Indexação

1. As Chaves Primárias criam índices automaticamente.
2. Adicione índices nas colunas usadas frequentemente em cláusulas WHERE.
3. Adicione índices nas Chaves Estrangeiras usadas em JOINs.
4. Considere índices compostos para consultas como `WHERE col1 = ? AND col2 = ?`.
5. Utilize índices UNIQUE para garantir exclusividade (email, username, etc.).

## Checklist de Verificação

1. Índices presentes em colunas frequentemente consultadas.
2. Índices presentes em colunas de Chave Estrangeira.
3. A ordem do índice composto foi otimizada (colunas de alta seletividade primeiro).
4. Evitou-se o excesso de índices (que degrada o desempenho de INSERT/UPDATE).

## Exemplo em PostgreSQL

```sql
-- Chaves Primárias (indexadas automaticamente)
CREATE TABLE users (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    email VARCHAR(255) UNIQUE NOT NULL,
    username VARCHAR(50) UNIQUE NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT NOW(),
    updated_at TIMESTAMP DEFAULT NOW()
);

-- Chaves Estrangeiras + índices explícitos
CREATE TABLE orders (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    total_amount DECIMAL(10, 2) NOT NULL
);

CREATE INDEX idx_orders_user_id ON orders(user_id);
```
