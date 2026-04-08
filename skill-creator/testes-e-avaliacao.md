# Testes, Avaliação e Benchmark

Depois que o rascunho de uma skill é concluído, o **Skill Creator** entra na fase de testar e mensurar o seu desempenho. Esta etapa é composta de uma sequência ininterrupta para garantir resultados precisos.

## Casos de Teste Iniciais

1. Após rascunhar a skill, gere 2 ou 3 casos de teste realistas baseados na forma como um usuário final solicitaria a tarefa.
2. Apresente os casos de teste para revisão. (ex: "Aqui estão alguns testes. Estão corretos? Quer adicionar mais?")
3. Salve esses casos no arquivo `evals/evals.json` (apenas os prompts por enquanto; asserções serão definidas mais tarde).

## O Processo Contínuo de Avaliação

### 1. Iniciar Execuções Paralelas (Spawn Runs)

Para cada caso de teste, crie **dois sub-agentes no mesmo turno**:
1. **Com a Skill:** Executa a tarefa apontando o caminho da nova skill. Os resultados vão para `<workspace>/iteration-N/eval-<ID>/with_skill/outputs/`.
2. **Sem a Skill (Baseline):** Usa o mesmo prompt. Se for criar uma skill nova, execute sem skill alguma (salvo em `without_skill/outputs/`). Se for atualizar uma existente, execute a versão anterior como baseline (salvo em `old_skill/outputs/`).

*(Nota: É fundamental iniciar todas as execuções simultaneamente para que finalizem na mesma janela de tempo).*

### 2. Rascunhar Asserções (Draft Assertions)

1. Enquanto as execuções acontecem no plano de fundo, crie asserções (avaliações quantitativas objetivas) para cada teste.
2. Atualize os arquivos `eval_metadata.json` e `evals/evals.json` com as asserções.
3. Explique ao usuário o que essas métricas irão testar (se a skill for subjetiva, prefira avaliação qualitativa/humana).

### 3. Capturar Dados de Tempo e Tokens

1. Quando a execução de um sub-agente é concluída, ele emite uma notificação com o `total_tokens` e o `duration_ms`.
2. Salve imediatamente esses dados no arquivo `timing.json` dentro do diretório de execução, pois não há outra forma de persistir isso posteriormente.

### 4. Avaliar, Agregar e Lançar o Visualizador (Viewer)

1. **Grade (Avaliar):** Gere um sub-agente (ou use scripts) que leia `agents/grader.md` e valide cada asserção contra as saídas. O resultado deve ir para `grading.json`.
2. **Aggregate (Agregar):** Rode o script de agregação (`scripts.aggregate_benchmark`) para produzir o `benchmark.json` e o `benchmark.md`, trazendo taxas de sucesso, tempo e tokens.
3. **Analyst Pass (Análise Humana):** Leia o benchmark para identificar padrões (asserções que sempre passam, variação muito alta de falhas, etc.).
4. **Viewer (Visualizador HTML):** Inicie a interface via `eval-viewer/generate_review.py` (ou com a flag `--static` para criar um HTML local em ambientes como o Cowork). Este visualizador terá abas com as saídas qualitativas e os dados quantitativos para o usuário analisar e preencher seu feedback.

### 5. Analisar o Feedback

1. Assim que o usuário clicar em "Submit All Reviews", leia o arquivo gerado (`feedback.json`).
2. Se o feedback estiver vazio, significa que os resultados estão satisfatórios. Caso contrário, foque em consertar as queixas específicas apontadas.
3. Finalize/Mate (Kill) o processo do servidor do viewer se aplicável.

> **Importante para Cowork:** Nunca se esqueça de rodar o `generate_review.py` para gerar o visualizador antes de analisar as entradas por conta própria. O humano precisa ver os resultados primeiro.
