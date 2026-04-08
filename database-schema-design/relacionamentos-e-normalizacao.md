# Design de Relacionamentos e Normalização

## Definição de Relacionamentos

1. **Relacionamento 1:1:** Chave Estrangeira + restrição UNIQUE.
2. **Relacionamento 1:N:** Apenas Chave Estrangeira.
3. **Relacionamento N:M:** Criar tabela de junção (Junction table).

## Critérios de Decisão para Normalização

1. **Sistemas OLTP:** Normalizar até a 3ª Forma Normal (3NF) para garantir integridade de dados.
2. **Sistemas OLAP/Analytics:** Desnormalização é permitida para melhorar performance de consultas.
3. **Foco em Leitura:** Minimizar JOINs usando desnormalização parcial.
4. **Foco em Escrita:** Normalização completa para eliminar redundâncias.
