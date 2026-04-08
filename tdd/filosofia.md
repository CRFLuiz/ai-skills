# Filosofia do TDD

## Princípio Central

1. Os testes devem verificar o comportamento por meio de interfaces públicas, não detalhes de implementação.
2. O código pode mudar completamente, mas os testes não deveriam precisar mudar.
3. Bons testes funcionam como uma especificação de integração, exercitando caminhos reais do código.

## O Que Evitar (Testes Ruins)

1. Testes muito acoplados à implementação.
2. Mocking de colaboradores internos ou testes de métodos privados.
3. Se um teste quebra após uma refatoração interna (onde o comportamento externo não mudou), o teste estava verificando a implementação e não o comportamento.

## Anti-Padrão: Fatias Horizontais

1. Nunca escreva todos os testes primeiro para depois escrever toda a implementação.
2. Essa abordagem produz testes focados na estrutura do código e insensíveis a mudanças reais.
3. A abordagem correta é o desenvolvimento em fatias verticais: um teste, uma implementação e repetir.
