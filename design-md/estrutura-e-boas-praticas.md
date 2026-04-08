# Estrutura do Documento e Melhores Práticas

## Diretrizes de Saída

1. Linguagem: use terminologia de design descritiva e linguagem natural.
2. Formato: gere um arquivo Markdown limpo seguindo a estrutura padrão.
3. Precisão: inclua códigos hexadecimais exatos para cores, mas sempre acompanhados de nomes descritivos.
4. Contexto: explique o "porquê" das decisões de design, não apenas o "o quê".

## Formato de Saída (Estrutura do DESIGN.md)

1. **Título:** `# Design System: [Título do Projeto]` e `**Project ID:** [ID]`.
2. **Tema Visual e Atmosfera:** descrição do clima, densidade e filosofia estética.
3. **Paleta de Cores e Funções:** lista de cores por Nome Descritivo + Código Hexadecimal + Função.
4. **Regras de Tipografia:** descrição da família de fontes, uso de pesos para cabeçalhos vs corpo, e espaçamento de letras.
5. **Estilos de Componentes:**
   - Botões: forma, cor, comportamento.
   - Cards/Containers: arredondamento de cantos, cor de fundo, profundidade de sombra.
   - Inputs/Formulários: estilo de borda, fundo.
6. **Princípios de Layout:** estratégia de espaços em branco, margens e alinhamento de grade.

## Melhores Práticas e Erros Comuns

1. Seja descritivo: evite termos genéricos como "azul" ou "arredondado". Use "Azul Cerúleo Profundo (#0077B6)" ou "Bordas suavemente curvas".
2. Seja funcional: sempre explique para que serve cada elemento de design.
3. Seja consistente: use a mesma terminologia em todo o documento.
4. Pense semanticamente: nomeie cores pelo propósito, não apenas pela aparência.
5. **NÃO USE** jargões técnicos sem tradução (ex: escrever apenas `rounded-xl` em vez de "cantos generosamente arredondados").
6. **NÃO OMITA** códigos de cores hexadecimais ou explique os papéis funcionais.