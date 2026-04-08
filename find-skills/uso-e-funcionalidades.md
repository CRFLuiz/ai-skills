# Uso e Funcionalidades: Find Skills

A skill **Find Skills** atua como uma interface para o CLI `npx skills`, que é o gerenciador de pacotes para o ecossistema aberto de skills para agentes.

## O que é a CLI de Skills?

Skills são pacotes modulares que estendem as capacidades do seu agente adicionando conhecimentos especializados, fluxos de trabalho e ferramentas. 

### Comandos Principais

1. `npx skills find [query]`: Pesquisa interativamente ou por palavra-chave.
2. `npx skills add <package>`: Instala uma skill do GitHub ou de outras fontes.
3. `npx skills check`: Verifica se há atualizações para as skills instaladas.
4. `npx skills update`: Atualiza todas as skills instaladas.

*Nota: Você também pode explorar skills pelo site [skills.sh](https://skills.sh/).*

## Como Ajudar a Encontrar Skills

O processo de busca ideal segue estas etapas:

### Passo 1: Entender a Necessidade
Identifique o **domínio** (ex: React, testes, design, deploy) e a **tarefa específica** (ex: escrever testes, revisar PRs). Verifique se a tarefa é comum o suficiente para já existir uma skill dedicada.

### Passo 2: Checar o Leaderboard
Antes de fazer uma pesquisa no CLI, verifique os destaques e as skills mais baixadas no site `skills.sh`. Skills com grande número de instalações são as opções mais testadas e confiáveis.
1. Exemplo para Web: `vercel-labs/agent-skills` (React, Next.js, web design) e `anthropics/skills`.

### Passo 3: Pesquisar por Skills
Se o leaderboard não cobrir o que você precisa, execute a pesquisa:
```bash
npx skills find [query]
```
Exemplos de uso:
1. "como faço meu app React ficar mais rápido?" → `npx skills find react performance`
2. "preciso criar um changelog" → `npx skills find changelog`

### Passo 4: Oferecer a Instalação
Se a skill for encontrada e validada (veja a página de [Pesquisa e Melhores Práticas](./pesquisa-e-boas-praticas.md)), você pode instalá-la diretamente:
```bash
npx skills add <owner/repo@skill> -g -y
```
1. `-g`: Instala globalmente.
2. `-y`: Pula os prompts de confirmação.

---

### Quando Nenhuma Skill For Encontrada
Se a busca não retornar resultados:
1. Reconheça que não há uma skill pronta.
2. Ofereça-se para ajudar com a tarefa usando suas capacidades gerais.
3. Sugira que uma nova skill pode ser criada usando `npx skills init nome-da-skill`.