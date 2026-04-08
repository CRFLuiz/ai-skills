# Visão Geral e Fluxo de Trabalho

1. **Formato da Skill**
   1. A skill segue um formato híbrido para consulta rápida e compreensão profunda:
   2. **Padrão Rápido:** Trechos de código incorretos/corretos para correspondência imediata de padrões.
   3. **Comando Rápido:** Comandos shell para processos e medições.
   4. **Configuração Rápida:** Trechos de configuração para definições.
   5. **Referência Rápida:** Tabelas de resumo para conceitos.
   6. **Aprofundamento:** Contexto completo com informações sobre quando usar, pré-requisitos, passo a passo e problemas comuns.
   7. **Avaliações de Impacto:** CRÍTICO (corrigir imediatamente), ALTO (melhoria significativa) e MÉDIO (otimização que vale a pena).

2. **Quando Aplicar**
   1. Para depurar interfaces ou animações lentas/travadas.
   2. Para investigar vazamentos de memória (no JavaScript ou nativo).
   3. Para otimizar o tempo de inicialização do aplicativo (TTI).
   4. Para reduzir o tamanho do pacote (bundle) ou do aplicativo.
   5. Ao escrever módulos nativos (Turbo Modules).
   6. Para criar perfis de desempenho em React Native.
   7. Ao revisar o código React Native com foco em desempenho.

3. **Notas de Segurança**
   1. Trate os comandos shell nestas referências como operações de desenvolvedor local. Revise-os antes de executar e evite enviar scripts remotos diretamente para o shell.
   2. Trate bibliotecas e plugins de terceiros como dependências que requerem controles padrão de cadeia de suprimentos (fixar versões, verificar origem e revisar).
   3. Trate o code splitting do Re.Pack como entrega primária. Chunks remotos devem vir de origens HTTPS confiáveis.

4. **Fluxo de Trabalho de Otimização**
   1. **Medir:** Capture métricas de linha de base (FPS, TTI, tamanho do bundle) antes das alterações.
   2. **Otimizar:** Aplique a correção direcionada a partir da referência correspondente.
   3. **Medir novamente:** Execute a mesma medição para obter métricas atualizadas.
   4. **Validar:** Confirme a melhoria (ex: FPS de 45 para 60, TTI de 3.2s para 1.8s, bundle de 2.1MB para 1.6MB). Se as métricas não melhorarem, reverta e tente a próxima correção.
