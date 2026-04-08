# Padrões Avançados e Inferência

## Padrões de Projeto com Segurança de Tipos

1. **Emissor de Eventos Tipado:** Usar genéricos para garantir que o payload emitido corresponda ao evento (ex: `TypedEventEmitter<EventMap>`).
2. **Cliente de API Tipado:** Garantir que os métodos HTTP, caminhos e corpos da requisição estejam corretos baseados em uma configuração de endpoints.
3. **Padrão Builder:** Usar tipos utilitários para garantir que o método `.build()` só possa ser chamado quando todos os campos obrigatórios forem preenchidos.
4. **Readonly/Partial Profundo:** Tipos recursivos para aplicar regras a objetos aninhados.
5. **Validação de Formulários:** Associar regras de validação estritamente às chaves do formulário.
6. **Unions Discriminadas:** Usar uma propriedade comum (ex: `status: "success" | "error"`) para criar máquinas de estado seguras.

## Técnicas de Inferência e Proteção

1. **A palavra-chave `infer`:** Útil para extrair o tipo de elementos de arrays, retorno de Promises ou parâmetros de funções.
2. **Type Guards:** Funções que retornam `value is Type` para ajudar o TypeScript a afunilar tipos em blocos condicionais.
3. **Assertion Functions:** Funções que garantem que um valor é de determinado tipo, lançando erros em tempo de execução se não for.

## Melhores Práticas e Armadilhas

1. Use `unknown` em vez de `any`.
2. Prefira `interface` para formas de objetos e `type` para uniões complexas.
3. Use `const` assertions para preservar tipos literais.
4. Evite asseverações de tipo (type assertions) excessivas; prefira type guards.
5. Armadilhas: usar muito `any`, ignorar checagens estritas de nulo, tipos aninhados excessivamente complexos (afeta performance de compilação) e referências circulares.