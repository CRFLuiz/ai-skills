# Passo a Passo da Revisão

## 1. Entenda o Contexto

1. Leia a descrição do PR.
2. Identifique qual é o objetivo desta mudança.
3. Verifique quais problemas ela resolve.
4. Confirme se há considerações especiais.
5. Verifique o escopo: quantidade de arquivos alterados, tipo de mudança (feature, bugfix, refatoração) e se os testes estão incluídos.

## 2. Revisão de Alto Nível

1. **Arquitetura e design:** Avalie se a abordagem faz sentido, se é consistente com os padrões existentes, se existem alternativas mais simples e se o código está no lugar certo.
2. **Organização do código:** Verifique a separação clara de responsabilidades, os níveis de abstração apropriados e a estrutura lógica de arquivos e pastas.

## 3. Revisão Detalhada do Código

1. **Nomenclatura:** Variáveis devem ter nomes descritivos, funções devem ser baseadas em verbos, classes devem ser baseadas em substantivos, e constantes em MAIÚSCULAS. Evite abreviações.
2. **Funções:** Devem ter responsabilidade única, tamanho razoável (idealmente menor que 50 linhas), entradas e saídas claras, efeitos colaterais mínimos e tratamento de erros adequado.
3. **Classes e objetos:** Siga os princípios SOLID (Responsabilidade única, Aberto/Fechado, Substituição de Liskov, Segregação de Interface e Inversão de Dependência).
4. **Tratamento de erros:** Todos os erros devem ser capturados e tratados com mensagens significativas e logs adequados. Evite falhas silenciosas.
5. **Qualidade do código:** Não deve haver código duplicado (DRY), código morto, código comentado, nem números mágicos. A formatação deve ser consistente.

## 4. Revisão de Segurança

1. **Validação de entrada:** Todas as entradas de usuário devem ser validadas (tipos, intervalos, formatos).
2. **Autenticação e Autorização:** Verificações adequadas para operações sensíveis, gerenciamento de sessão e tratamento seguro de senhas.
3. **Proteção de dados:** Sem segredos embutidos no código, dados sensíveis devem ser criptografados, previna injeção de SQL, XSS e CSRF.
4. **Dependências:** Não utilize pacotes vulneráveis e mantenha as dependências atualizadas.

## 5. Revisão de Performance

1. **Algoritmos:** Escolha apropriada do algoritmo, complexidade razoável de tempo e espaço, sem loops desnecessários.
2. **Banco de Dados:** Consultas eficientes, indexação adequada, prevenção de consultas N+1 e uso de pool de conexões.
3. **Cache:** Estratégia apropriada de cache com tratamento para invalidação.
4. **Gerenciamento de recursos:** Arquivos devidamente fechados, conexões liberadas e prevenção de vazamentos de memória.

## 6. Revisão de Testes

1. **Cobertura de testes:** Testes unitários para código novo, testes de integração se necessário e casos extremos cobertos.
2. **Qualidade do teste:** Os testes devem ser legíveis, sustentáveis, determinísticos e sem interdependências.
3. **Nomenclatura:** Use nomes descritivos como `test_user_creation_with_valid_data_succeeds()`.

## 7. Revisão de Documentação

1. **Comentários de código:** Lógica complexa deve ser explicada. Não faça comentários óbvios. TODOs devem ter tickets associados.
2. **Documentação de função:** Inclua argumentos, retornos e exceções lançadas.
3. **README e Docs:** Atualize os guias e as documentações de API se houver alterações de quebra (breaking changes).
