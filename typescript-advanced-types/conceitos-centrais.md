# Conceitos Centrais

## 1. Genéricos (Generics)

1. **Propósito:** Criar componentes flexíveis e reutilizáveis mantendo a segurança de tipos.
2. É possível restringir os tipos genéricos usando `extends` (ex: `<T extends HasLength>`).
3. Pode-se usar múltiplos parâmetros de tipo (ex: `<T, U>`).

## 2. Tipos Condicionais (Conditional Types)

1. **Propósito:** Criar tipos que dependem de condições (`T extends U ? X : Y`).
2. Útil para extrair tipos de retorno (ex: `ReturnType<T>`).
3. Permite condições distributivas (ex: `T extends any ? T[] : never`) e condições aninhadas para mapeamento complexo.

## 3. Tipos Mapeados (Mapped Types)

1. **Propósito:** Transformar tipos existentes iterando sobre suas propriedades.
2. Exemplos: `Readonly<T>` (torna tudo somente leitura), `Partial<T>` (torna tudo opcional).
3. Permite remapeamento de chaves usando `as` e filtragem de propriedades condicionais.

## 4. Tipos Literais de Template (Template Literal Types)

1. **Propósito:** Criar tipos baseados em strings com correspondência e transformação de padrões.
2. Permite manipular strings (ex: `Uppercase<T>`, `Capitalize<T>`).
3. Útil para construir caminhos de objetos dinamicamente (ex: `"server.host"`).

## 5. Tipos Utilitários (Utility Types)

1. TypeScript possui utilitários integrados como: `Partial`, `Required`, `Readonly`, `Pick`, `Omit`, `Exclude`, `Extract`, `NonNullable` e `Record`.