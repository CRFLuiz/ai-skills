# Estrutura do Plano e Tarefas

Esta seção descreve a granularidade, o cabeçalho obrigatório e a estrutura de cada tarefa dentro de um plano de implementação.

## Cabeçalho do Plano (Plan Document Header)

Todo plano DEVE começar com o seguinte cabeçalho:

```markdown
# [Feature Name] Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** [Uma frase descrevendo o que será construído]

**Architecture:** [2-3 frases sobre a abordagem]

**Tech Stack:** [Tecnologias e bibliotecas chave]

---
```

## Granularidade das Tarefas (Bite-Sized Task Granularity)

Cada passo deve ser uma única ação que leva de 2 a 5 minutos:

1. **Passo 1:** "Escrever o teste que falha" (Write the failing test)
2. **Passo 2:** "Executá-lo para garantir que falha" (Run it to make sure it fails)
3. **Passo 3:** "Implementar o código mínimo para passar no teste" (Implement the minimal code to make the test pass)
4. **Passo 4:** "Executar os testes e garantir que passam" (Run the tests and make sure they pass)
5. **Passo 5:** "Fazer o commit" (Commit)

## Estrutura da Tarefa (Task Structure)

Cada tarefa deve seguir uma estrutura exata contendo os arquivos afetados e os cinco passos descritos acima com blocos de código completos:

```markdown
### Task N: [Component Name]

**Files:**
- Create: `exact/path/to/file.py`
- Modify: `exact/path/to/existing.py:123-145`
- Test: `tests/exact/path/to/test.py`

- [ ] **Step 1: Write the failing test**

\`\`\`python
def test_specific_behavior():
    result = function(input)
    assert result == expected
\`\`\`

- [ ] **Step 2: Run test to verify it fails**

Run: `pytest tests/path/test.py::test_name -v`
Expected: FAIL with "function not defined"

- [ ] **Step 3: Write minimal implementation**

\`\`\`python
def function(input):
    return expected
\`\`\`

- [ ] **Step 4: Run test to verify it passes**

Run: `pytest tests/path/test.py::test_name -v`
Expected: PASS

- [ ] **Step 5: Commit**

\`\`\`bash
git add tests/path/test.py src/path/file.py
git commit -m "feat: add specific feature"
\`\`\`
```
