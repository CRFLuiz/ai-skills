# Fluxo de Trabalho

## 1. Planejamento

1. Confirme as mudanças de interface necessárias e quais comportamentos testar.
2. Projete interfaces visando testabilidade.
3. Liste os comportamentos a testar e foque nos caminhos críticos, não em cada caso extremo possível.

## 2. A Bala Rastreadora (Tracer Bullet)

1. Escreva um teste que confirme um comportamento do sistema (Fase Vermelha).
2. Escreva o código mínimo necessário para fazer esse teste passar (Fase Verde).
3. Isso prova que o caminho funciona de ponta a ponta.

## 3. Loop Incremental

1. Para cada comportamento restante, escreva o próximo teste e veja-o falhar.
2. Escreva o código mínimo para passar.
3. Trabalhe com um teste por vez, sem antecipar funcionalidades futuras.

## 4. Refatoração

1. Após todos os testes passarem, procure oportunidades de refatoração.
2. Extraia duplicações e simplifique a complexidade mantendo interfaces simples.
3. Execute os testes após cada pequeno passo de refatoração.
4. Nunca refatore enquanto os testes estiverem falhando.
