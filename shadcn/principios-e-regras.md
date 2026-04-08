# Princípios e Regras Críticas

## Princípios Básicos

1. Use componentes existentes primeiro. Verifique os registros oficiais e da comunidade antes de escrever uma UI personalizada.
2. Componha, não reinvente. Uma página de configurações é formada por Tabs + Card + controles de formulário.
3. Use variantes integradas antes de criar estilos personalizados (ex: `variant="outline"`, `size="sm"`).
4. Use cores semânticas (`bg-primary`, `text-muted-foreground`) em vez de cores estáticas (`bg-blue-500`).

## Estilização e Tailwind

1. Use `className` para layout, não para alterar o estilo base dos componentes.
2. Evite `space-x-*` ou `space-y-*`. Use `flex` com `gap-*` (ex: `flex flex-col gap-4`).
3. Use `size-*` quando largura e altura forem iguais (ex: `size-10` em vez de `w-10 h-10`).
4. Use o atalho `truncate` em vez de classes manuais longas.
5. Não faça sobreposições manuais de cores escuras (`dark:`).
6. Use `cn()` para classes condicionais em vez de literais de template manuais.
7. Não aplique `z-index` manual em componentes de sobreposição (Dialog, Sheet, Popover gerenciam seu próprio empilhamento).

## Formulários e Inputs

1. Formulários usam `FieldGroup` + `Field`. Nunca use divs cruas com margens para layout de formulário.
2. `InputGroup` utiliza `InputGroupInput` ou `InputGroupTextarea`.
3. Botões dentro de inputs usam `InputGroup` + `InputGroupAddon`.
4. Conjuntos de opções (2 a 7 escolhas) devem usar `ToggleGroup`.
5. Agrupe checkboxes e radios relacionados com `FieldSet` + `FieldLegend`.
6. Validação de campos usa `data-invalid` + `aria-invalid`.

## Estrutura de Componentes

1. Itens sempre devem ficar dentro de seu grupo (ex: `SelectItem` dentro de `SelectGroup`).
2. Modais (Dialog, Sheet, Drawer) sempre precisam de um título para acessibilidade. Use `className="sr-only"` se precisar esconder visualmente.
3. Use a composição completa do `Card` (Header, Title, Description, Content, Footer) em vez de jogar tudo no Content.
4. Botões não possuem estados nativos de carregamento; componha-os com Spinner, `data-icon` e `disabled`.
5. `Avatar` sempre precisa de um `AvatarFallback` caso a imagem falhe ao carregar.

## Ícones

1. Ícones em botões usam o atributo `data-icon` (ex: `data-icon="inline-start"`).
2. Não aplique classes de tamanho em ícones dentro de componentes.
3. Passe ícones como objetos e não como strings (`icon={CheckIcon}`).