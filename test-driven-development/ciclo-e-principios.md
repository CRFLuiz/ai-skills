# Ciclo e Princípios do TDD

## A Regra de Ouro

1. Não escreva código de produção sem antes ter um teste falhando.
2. Se você escreveu código antes do teste, apague-o e comece de novo. Não o guarde como "referência".
3. A única exceção a essa regra é quando se trata de protótipos descartáveis, código gerado automaticamente ou arquivos de configuração (e mesmo assim, pergunte ao parceiro humano).

## O Ciclo Red-Green-Refactor

1. **RED (Escreva um teste que falha):** Escreva um teste mínimo mostrando o que deve acontecer. O teste deve ter um nome claro e focar em apenas um comportamento real (evitando mocks, a menos que seja inevitável).
2. **Verifique o RED:** Execute o teste e confirme que ele falha pelo motivo correto (falta da funcionalidade, e não por um erro de sintaxe ou erro de execução não relacionado).
3. **GREEN (Código Mínimo):** Escreva o código mais simples possível apenas para fazer o teste passar. Não adicione funcionalidades extras nem refatore outras partes do código neste momento.
4. **Verifique o GREEN:** Execute os testes novamente e confirme que o novo teste passa e que nenhum outro teste foi quebrado.
5. **REFACTOR (Limpeza):** Apenas após o teste passar, melhore o código. Remova duplicações, melhore nomes de variáveis e extraia funções auxiliares, garantindo que os testes continuem passando (verdes).

## Por Que a Ordem Importa?

1. Escrever testes depois do código não prova que o teste realmente funciona para capturar falhas.
2. Testes escritos depois são enviesados pela implementação; você testa o que construiu, não o que era exigido.
3. Testes automatizados prévios são sistemáticos e documentam o comportamento esperado, diferentemente de testes manuais ad-hoc.
4. O tempo gasto apagando código não testado não é desperdício; manter código em que você não pode confiar é dívida técnica.