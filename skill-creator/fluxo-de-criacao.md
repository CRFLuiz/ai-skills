# O Fluxo de Criação (Lifecycle)

A criação de uma skill com o **Skill Creator** envolve um ciclo de vida estruturado, pensado para produzir instruções robustas que o Claude consiga executar repetidamente com sucesso.

## Visão Geral do Processo

1. **Decisão:** Defina o que você deseja que a skill faça e como ela deve operar.
2. **Rascunho:** Escreva uma versão inicial da skill.
3. **Casos de Teste:** Crie alguns prompts de teste e execute-os com o Claude (usando o acesso à nova skill).
4. **Avaliação Inicial:** Ajude o usuário a avaliar os resultados de forma qualitativa e quantitativa.
5. **Avaliações Quantitativas:** Enquanto as execuções de teste rodam no fundo, rascunhe as avaliações quantitativas (se não houverem) e as explique.
6. **Revisão:** Utilize o script de visualização (`eval-viewer/generate_review.py`) para que o usuário analise as saídas e as métricas.
7. **Iteração:** Reescreva e aprimore a skill com base no feedback e em eventuais falhas identificadas nos benchmarks.
8. **Repetição:** Repita o processo até obter satisfação com o resultado.
9. **Expansão:** Amplie o conjunto de testes para validar a skill em maior escala.

## Etapa 1: Capturando a Intenção (Capture Intent)

Antes de escrever qualquer código, é crucial entender a intenção:
1. Extraia o máximo de informações do histórico da conversa.
2. Pergunte: "O que esta skill deve permitir que o Claude faça?"
3. Pergunte: "Quando esta skill deve ser acionada?" (Quais frases ou contextos do usuário).
4. Defina o formato de saída esperado.
5. Decida sobre casos de teste: Skills com saídas objetivas (transformação de arquivos, extração de dados) exigem testes; skills subjetivas (estilo de escrita) podem não precisar.

## Etapa 2: Entrevista e Pesquisa

1. Faça perguntas ativamente sobre casos extremos (edge cases), formatos, arquivos de exemplo, critérios de sucesso e dependências.
2. Se necessário, pesquise na documentação ou busque habilidades similares como referência para não onerar o usuário.

## Etapa 3: Escrevendo o SKILL.md

Com base nas respostas, preencha os componentes obrigatórios do frontmatter (cabeçalho YAML):
1. **name:** Identificador da skill.
2. **description:** Deve incluir o que a skill faz e os contextos específicos de quando usá-la. Seja incisivo ("pushy") na descrição para garantir que a skill seja ativada quando necessário.

### Anatomia de uma Skill
1. `SKILL.md` (obrigatório): Contém o frontmatter YAML e as instruções em Markdown. O ideal é manter sob 500 linhas.
2. `scripts/` (opcional): Código executável para tarefas repetitivas ou determinísticas.
3. `references/` (opcional): Documentações carregadas no contexto apenas quando necessário.
4. `assets/` (opcional): Arquivos usados na saída (como templates, fontes).

### Estilo de Escrita
1. Prefira usar o formato imperativo nas instruções.
2. Defina os formatos de saída de forma clara (usando marcações de cabeçalhos `#`, por exemplo).
3. Inclua exemplos (Input / Output) para clarear o comportamento esperado.
4. Explique o "porquê" por trás das instruções. Em vez de regras rígidas e engessadas (como "SEMPRE" ou "NUNCA"), faça o modelo entender a razão pela qual a instrução é importante.
