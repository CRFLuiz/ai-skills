# Visão Geral, Escopo e Estrutura de Arquivos

Esta página descreve os princípios fundamentais de como iniciar e estruturar um plano de implementação.

## Visão Geral (Overview)

1. **Abordagem Fundamental:** Escreva planos assumindo que o engenheiro tem zero contexto do projeto e possui "gosto questionável". Ele é um bom desenvolvedor, mas desconhece suas ferramentas e seu domínio.
2. **Nível de Detalhe:** Documente exatamente quais arquivos tocar, quais códigos escrever e quais testes criar para cada tarefa.
3. **Metodologia:** Siga os princípios DRY (Don't Repeat Yourself), YAGNI (You Aren't Gonna Need It) e TDD (Test-Driven Development). Faça commits frequentes.
4. **Anúncio e Contexto:** Sempre comece dizendo: "I'm using the writing-plans skill to create the implementation plan." E execute este plano em uma *worktree* dedicada.

## Checagem de Escopo (Scope Check)

1. **Divisão de Subsistemas:** Se a especificação cobrir múltiplos subsistemas independentes, ela deveria ter sido dividida antes. Se não foi, divida em planos separados (um por subsistema).
2. **Independência:** Cada plano deve produzir software que funcione e possa ser testado de forma independente.

## Estrutura de Arquivos (File Structure)

1. **Mapeamento Prévio:** Antes de definir as tarefas, mapeie quais arquivos serão criados ou modificados e a responsabilidade de cada um. É aqui que as decisões de decomposição são travadas.
2. **Limites Claros:** Desenhe unidades com limites definidos e interfaces claras. Cada arquivo deve ter apenas uma responsabilidade clara.
3. **Foco e Tamanho:** Prefira arquivos menores e focados em vez de arquivos grandes que fazem demais. Edições são mais confiáveis em arquivos focados.
4. **Coesão:** Arquivos que mudam juntos devem viver juntos. Divida por responsabilidade, não por camada técnica.
5. **Padrões Existentes:** Siga os padrões do repositório. Se a base usar arquivos grandes, não reestruture unilateralmente, mas se um arquivo for incontrolável, é razoável incluir uma divisão no plano.
