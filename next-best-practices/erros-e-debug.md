# Tratamento de Erros e Debug no Next.js

Esta página orienta sobre a manipulação de exceções, falhas de renderização e boas práticas para hospedagem independente.

## Tratamento de Erros (Error Handling)

1. **Uso de `error.tsx` e `global-error.tsx`:** Trate erros de nível de rota usando as convenções corretas. O arquivo `error.tsx` envolve componentes no servidor e cliente para capturar exceções com boundaries React.
2. **Página 404 (not-found.tsx):** Retorne o fallback visual quando a rota ou o recurso dinâmico não for encontrado (acionado pela função `notFound()`).
3. **Redirecionamentos e Autenticação:** Diferencie erros de rotas não autorizadas usando as APIs experimentais/novas `forbidden()` ou `unauthorized()`, além dos utilitários como `redirect` e `permanentRedirect`.
4. **`unstable_rethrow`:** Lembre-se de não silenciar erros do framework (como redirecionamentos) dentro de blocos `try/catch`. Use `unstable_rethrow` se precisar capturá-los.

## Erros de Hidratação (Hydration Errors)

1. **Causas Comuns:** Evite disparidades entre a árvore do Servidor (HTML bruto) e a do Cliente (React Render) decorrentes do uso prematuro de APIs do navegador, datas aleatórias ou marcações HTML inválidas (ex.: `<div>` dentro de `<p>`).
2. **Overlay de Erro:** Utilize as mensagens de aviso do servidor de desenvolvimento que apontam as tags exatas e as propriedades onde as incompatibilidades ocorrem.
3. **Resoluções:** Saiba resolver cada caso aplicando hooks como `useEffect`, checagens de hidratação (como estado `isMounted`) e componentes com o prop `suppressHydrationWarning`.

## Truques de Depuração (Debug Tricks)

1. **Endpoints MCP:** O Next.js fornece suporte para ferramentas AI-assisted, permitindo que os agentes analisem ou ajustem o código do projeto mais rapidamente com contexto completo de tipos e funções.
2. **Rebuild Específico:** Utilize a flag `--debug-build-paths` durante os testes de build de produção (`next build`) para rastrear apenas as rotas e funções específicas.

## Self-Hosting e Implantação Independente

1. **Standalone Output:** Quando não estiver hospedando na Vercel (ex.: Docker), configure `output: 'standalone'` no `next.config.ts` para criar um diretório enxuto e minimizado.
2. **Cache em Múltiplas Instâncias:** Para arquiteturas escaláveis (pods do Kubernetes), implemente ou utilize tratadores de cache customizados para compartilhar o ISR (Incremental Static Regeneration).
3. **Limitações:** Entenda quais otimizações de imagens, caches de borda ou middlewares globais funcionam nativamente no Node e quais precisam de uma configuração de CDN extra ou proxy reverso (como Nginx).
