# Conexões e Drivers

1. O Neon suporta múltiplos métodos de conexão, adequando-se às necessidades do ambiente (TCP, HTTP, WebSocket, edge, serverless ou long-running).
2. O **Serverless Driver** (`@neondatabase/serverless`) é altamente recomendado para aplicações em nuvem, utilizando consultas HTTP e transações baseadas em WebSocket, trazendo otimizações específicas de tempo de execução.
3. Para fluxos que combinam Autenticação Neon + API de Dados com consultas estilo PostgREST, o **Neon JS SDK** oferece uma configuração de cliente tipada.
4. Para o setup inicial, é fundamental selecionar a organização/projeto corretos, as strings de conexão e instalar o driver de acordo com a linguagem, framework ou ORM utilizados (compatibilidade total com Postgres).
