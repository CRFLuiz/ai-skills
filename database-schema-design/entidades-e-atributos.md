# Definição de Entidades e Atributos

## Passos para Definição

1. Extraia os substantivos dos requisitos de negócio para transformá-los em entidades.
2. Liste os atributos (colunas) para cada entidade.
3. Determine os tipos de dados apropriados (VARCHAR, INTEGER, TIMESTAMP, JSON, etc.).
4. Designe as Chaves Primárias (UUID vs ID Auto-incremento).

## Exemplo de Entidades (E-commerce)

1. **Users:**
   - `id`: UUID PRIMARY KEY
   - `email`: VARCHAR(255) UNIQUE NOT NULL
   - `username`: VARCHAR(50) UNIQUE NOT NULL
   - `password_hash`: VARCHAR(255) NOT NULL
   - `created_at`: TIMESTAMP DEFAULT NOW()
   - `updated_at`: TIMESTAMP DEFAULT NOW()

2. **Products:**
   - `id`: UUID PRIMARY KEY
   - `name`: VARCHAR(255) NOT NULL
   - `description`: TEXT
   - `price`: DECIMAL(10, 2) NOT NULL
   - `stock`: INTEGER DEFAULT 0
   - `category_id`: UUID REFERENCES Categories(id)
   - `created_at`: TIMESTAMP DEFAULT NOW()
