# Boas Práticas e Otimização da Descrição

Após testes, avaliação e feedback do usuário, a skill entra no processo de melhoria contínua e, por fim, em sua otimização.

## Melhorando a Skill (Iteration Loop)

A iteração baseia-se diretamente no feedback recebido.
1. **Generalize a partir do feedback:** Não construa soluções presas aos casos de teste ("overfitting"). Tente usar metáforas, recomendações ou novos padrões de trabalho que resolvam o problema fundamental sem exigir ordens opressoras.
2. **Mantenha o prompt limpo:** Remova partes da instrução que não estão fazendo efeito. Leia as transcrições (não apenas as saídas finais) para identificar se o modelo está perdendo tempo com ações improdutivas.
3. **Explique o "Porquê":** LLMs têm "teoria da mente" (Theory of Mind). Explique as razões por trás das suas regras, para que o modelo as aplique naturalmente.
4. **Procure trabalhos repetitivos:** Se os sub-agentes constantemente recriarem um script em vários testes (ex: `build_chart.py`), crie esse script uma vez na pasta `scripts/` e diga à skill para utilizá-lo. Isso poupa tempo futuro.
5. **Rode novamente:** Aplique as melhorias, rode os testes (numa nova iteração `N+1`) e repita o processo de avaliação até que o usuário esteja totalmente satisfeito ou não haja mais progresso significativo.

## Otimização de Descrição (Description Optimization)

O campo de descrição (no `SKILL.md`) é a engrenagem principal para o Claude ativar uma skill. Como o Claude só ativa skills para tarefas complexas que não resolve sozinho, uma descrição forte é fundamental.

### Passo 1: Gerar Avaliações de Acionamento (Trigger Eval Queries)

Crie 20 queries realistas (textos de usuário) no formato JSON (`{"query": "...", "should_trigger": true}`):
1. **Should-trigger (8-10):** Deve conter diversas formas de falar a mesma intenção (casuais, formais, sem citar diretamente o nome da skill) e casos de uso específicos.
2. **Should-not-trigger (8-10):** Devem ser testes próximos ("near-misses"). Consultas de domínios vizinhos ou onde as palavras-chave combinam, mas outra ferramenta seria mais apropriada. Não faça testes fáceis ou genéricos.

### Passo 2: Revisão com o Usuário

1. Apresente os testes de acionamento ao usuário gerando um template HTML (`assets/eval_review.html`).
2. Substitua os placeholders (`__EVAL_DATA_PLACEHOLDER__`, `__SKILL_NAME_PLACEHOLDER__`, `__SKILL_DESCRIPTION_PLACEHOLDER__`).
3. Peça ao usuário que os valide e exporte (`eval_set.json`).

### Passo 3: Executar o Loop de Otimização

Avise o usuário que o processo levará tempo e execute em segundo plano:
1. Rode o script de loop (`scripts.run_loop`).
2. Isso dividirá os testes (60% treino / 40% teste invisível) e testará a taxa de acionamento rodando 3 vezes cada.
3. O Claude proporá melhorias, re-avaliando-as por até 5 iterações.
4. Ele devolverá um HTML com o progresso e o JSON com a `best_description` (focada no melhor resultado dos 40% de testes invisíveis para evitar overfitting).

### Passo 4: Aplicar o Resultado e Empacotar (Package)

1. Pegue a `best_description` e atualize o cabeçalho `SKILL.md`.
2. Mostre o antes e o depois ao usuário.
3. **Empacotamento:** Se tiver acesso, empacote a skill via `python -m scripts.package_skill <caminho>` e retorne o arquivo `.skill` gerado para o usuário instalar.
