# Boas Práticas e Armadilhas

## Características de Bons Testes

1. O teste deve ser mínimo, validando apenas uma coisa. Se o nome do teste tiver um "e", divida-o em dois testes.
2. O nome do teste deve descrever claramente o comportamento esperado.
3. O teste deve demonstrar a API desejada, revelando a intenção de como o código deve ser usado.

## Bandeiras Vermelhas (Pare e Comece de Novo)

1. Código escrito antes do teste.
2. Teste escrito após a implementação.
3. O teste passa imediatamente na primeira execução.
4. Não conseguir explicar por que o teste falhou.
5. Testes adicionados "mais tarde" ou usar a desculpa de "só desta vez".
6. Acreditar que "testes manuais são suficientes" ou que "testes depois alcançam o mesmo objetivo".
7. Guardar o código existente como "referência" ou tentar "adaptá-lo" em vez de recomeçar.

## Checklist de Verificação

1. Toda nova função/método tem um teste.
2. Você assistiu cada teste falhar antes de implementar o código.
3. Cada teste falhou pelo motivo esperado (funcionalidade ausente).
4. Escreveu-se o código mínimo necessário para passar no teste.
5. Todos os testes estão passando.
6. A saída do terminal está limpa (sem erros ou avisos).
7. Os testes usam código real (mocks apenas se inevitáveis).
8. Casos extremos e erros estão cobertos.

## O Que Fazer Quando Estiver Travado

1. Se não souber como testar: escreva a API que você gostaria que existisse, escreva a asserção primeiro e peça ajuda ao parceiro humano.
2. Se o teste estiver muito complicado: isso indica que o design está muito complexo; simplifique a interface.
3. Se precisar "mockar" tudo: o código está muito acoplado; use injeção de dependência.
4. Se a configuração do teste for enorme: extraia funções auxiliares. Se continuar complexo, simplifique o design.