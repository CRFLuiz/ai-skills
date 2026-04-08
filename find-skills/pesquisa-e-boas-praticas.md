# Pesquisa e Melhores Práticas

A skill **Find Skills** não apenas ajuda a encontrar outras habilidades, mas define um padrão de segurança e eficácia ao recomendar pacotes.

## Como Verificar a Qualidade (Passo 4)

Antes de sugerir ou instalar uma skill encontrada com `npx skills find`, certifique-se da sua qualidade:

1. **Quantidade de Instalações:** Dê preferência a skills com mais de 1K instalações. Desconfie daquelas com menos de 100.
2. **Reputação da Fonte:** Fontes oficiais (como `vercel-labs`, `anthropics`, `microsoft`) são mais confiáveis do que autores desconhecidos.
3. **Estrelas no GitHub:** Verifique o repositório de origem. Repositórios com menos de 100 estrelas devem ser tratados com ceticismo.

## Apresentando as Opções (Passo 5)

Quando você encontrar skills relevantes, apresente-as sempre com as seguintes informações:
1. Nome da skill e descrição do que ela faz.
2. Quantidade de instalações e fonte (quem criou).
3. Comando de instalação.
4. Um link para o repositório ou página no [skills.sh](https://skills.sh/).

**Exemplo de Resposta:**
> "Encontrei uma skill que pode ajudar! A 'react-best-practices' fornece diretrizes de otimização de performance em React e Next.js pela Engenharia da Vercel (185K instalações).
> Para instalá-la, execute: `npx skills add vercel-labs/agent-skills@react-best-practices`
> Saiba mais: https://skills.sh/vercel-labs/agent-skills/react-best-practices"

---

## Dicas para Pesquisas Efetivas

1. **Seja Específico:** Use "react testing" em vez de apenas "testing".
2. **Termos Alternativos:** Se "deploy" não funcionar, tente "deployment" ou "ci-cd".
3. **Fontes Populares:** Verifique repositórios conhecidos, como `vercel-labs/agent-skills` ou `ComposioHQ/awesome-claude-skills`.

## Categorias Comuns de Skills

Ao buscar por skills, considere estas categorias e suas palavras-chave:

| Categoria | Palavras-chave Exemplo |
| --- | --- |
| **Web Development** | `react`, `nextjs`, `typescript`, `css`, `tailwind` |
| **Testing** | `testing`, `jest`, `playwright`, `e2e` |
| **DevOps** | `deploy`, `docker`, `kubernetes`, `ci-cd` |
| **Documentation** | `docs`, `readme`, `changelog`, `api-docs` |
| **Code Quality** | `review`, `lint`, `refactor`, `best-practices` |
| **Design** | `ui`, `ux`, `design-system`, `accessibility` |
| **Productivity** | `workflow`, `automation`, `git` |