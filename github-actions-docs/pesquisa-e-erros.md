# Pesquisa, Resposta e Erros Comuns

## Formato da Resposta

1. Use uma estrutura compacta, a menos que o usuário peça profundidade.
2. Forneça uma resposta direta.
3. Inclua links de documentação relevantes.
4. Forneça exemplo de YAML ou passos, apenas se necessário.
5. Faça um aviso explícito de inferência, apenas se tiver que conectar várias páginas de documentação.
6. Mantenha as citações próximas à afirmação que elas apoiam.

## Dicas de Pesquisa e Roteamento

1. Para questões conceituais, prefira páginas de visão geral antes das páginas de referência profunda.
2. Para sintaxe, busque páginas de referência de sintaxe, eventos, contextos, variáveis ou expressões.
3. Para segurança, prefira as documentações de uso seguro, segredos, `GITHUB_TOKEN`, OpenID Connect e atestados de artefato.
4. Para implantação, busque ambientes e regras de proteção de implantação antes de exemplos específicos de nuvem.
5. Para migração, comece pelo hub de migração e depois pelo guia específico da plataforma.
6. Se o usuário pedir um tutorial para iniciantes, comece com um guia rápido (quickstart) em vez de uma página de referência crua.

## Erros Comuns a Evitar

1. Responder de memória sem verificar a documentação atual.
2. Linkar a página inicial da documentação do GitHub Actions quando existe uma página mais específica.
3. Confundir fluxos de trabalho reutilizáveis (reusable workflows) com ações compostas (composite actions).
4. Sugerir credenciais de nuvem de longa duração quando OIDC é o caminho mais bem documentado.
5. Tratar a depuração de CI específica de um repositório como uma questão de documentação quando deveria ser encaminhada para `gh-fix-ci`.
6. Deixar domínios adjacentes absorverem a solicitação quando `codeql` ou `dependabot` seriam escolhas mais precisas.