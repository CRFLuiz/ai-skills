# Diretrizes de Performance (As 69 Regras)

A skill **Vercel React Best Practices** está dividida em 8 categorias essenciais, organizadas por nível de impacto e prioridade. Cada regra possui um prefixo exclusivo para fácil referência em ferramentas de automação e CI/CD.

## Categorias de Regras por Prioridade

| Prioridade | Categoria | Impacto | Prefixo |
| --- | --- | --- | --- |
| 1 | **Eliminating Waterfalls** | CRITICAL | `async-` |
| 2 | **Bundle Size Optimization** | CRITICAL | `bundle-` |
| 3 | **Server-Side Performance** | HIGH | `server-` |
| 4 | **Client-Side Data Fetching** | MEDIUM-HIGH | `client-` |
| 5 | **Re-render Optimization** | MEDIUM | `rerender-` |
| 6 | **Rendering Performance** | MEDIUM | `rendering-` |
| 7 | **JavaScript Performance** | LOW-MEDIUM | `js-` |
| 8 | **Advanced Patterns** | LOW | `advanced-` |

---

## Referência Rápida (Quick Reference)

### 1. Eliminating Waterfalls (CRITICAL)
Problemas de "waterfall" ocorrem quando requisições ou processos assíncronos que poderiam rodar em paralelo são executados em série, atrasando o carregamento da página.
1. **`async-cheap-condition-before-await`**: Verifique condições síncronas baratas antes de usar `await` em flags ou valores remotos.
2. **`async-defer-await`**: Mova o `await` para ramificações onde ele é realmente utilizado.
3. **`async-parallel`**: Use `Promise.all()` para operações independentes.
4. **`async-dependencies`**: Use bibliotecas como `better-all` para lidar com dependências parciais.
5. **`async-api-routes`**: Inicie as promises cedo e faça o `await` apenas quando necessário em API Routes.
6. **`async-suspense-boundaries`**: Use `Suspense` para renderizar conteúdo por streaming (streaming content).

### 2. Bundle Size Optimization (CRITICAL)
1. **`bundle-barrel-imports`**: Importe diretamente os arquivos e evite "barrel files" (`index.ts` exportando tudo).
2. **`bundle-dynamic-imports`**: Use `next/dynamic` para componentes pesados.
3. **`bundle-defer-third-party`**: Carregue scripts de analytics/logging apenas após a hidratação (hydration).
4. **`bundle-conditional`**: Carregue módulos apenas quando a feature correspondente estiver ativada.
5. **`bundle-preload`**: Faça preload no `hover` ou `focus` para dar sensação de velocidade instantânea.

### 3. Server-Side Performance (HIGH)
1. **`server-auth-actions`**: Autentique "server actions" (ex: rotas de API).
2. **`server-cache-react`**: Use `React.cache()` para desduplicação (dedup) de requests por requisição.
3. **`server-cache-lru`**: Use cache LRU para cacheamento compartilhado entre requisições.
4. **`server-dedup-props`**: Evite duplicação na serialização das props de RSC (React Server Components).
5. **`server-hoist-static-io`**: "Içe" (hoist) I/O estático (fontes, logos) para o nível do módulo (fora da função principal).
6. **`server-no-shared-module-state`**: Evite estados mutáveis compartilhados no nível de módulo em RSC/SSR.
7. **`server-serialization`**: Minimize os dados que são passados do servidor para os "client components".
8. **`server-parallel-fetching`**: Reestruture componentes para paralelizar requisições de fetch.
9. **`server-parallel-nested-fetching`**: Encadeie requests aninhadas usando `Promise.all` para cada item.
10. **`server-after-nonblocking`**: Use a função `after()` para operações que não devem bloquear o carregamento (non-blocking).

### 4. Client-Side Data Fetching (MEDIUM-HIGH)
1. **`client-swr-dedup`**: Use `SWR` ou React Query para desduplicação automática de requisições.
2. **`client-event-listeners`**: Desduplique "event listeners" globais.
3. **`client-passive-event-listeners`**: Use ouvintes passivos (passive listeners) para eventos de scroll.
4. **`client-localstorage-schema`**: Controle a versão e minimize os dados guardados no `localStorage`.

### 5. Re-render Optimization (MEDIUM)
1. **`rerender-defer-reads`**: Não se inscreva em estados que são usados apenas dentro de callbacks.
2. **`rerender-memo`**: Extraia lógicas "caras" (pesadas) para componentes memorizados.
3. **`rerender-memo-with-default-value`**: "Içe" valores padrão de props não primitivas (como arrays vazios).
4. **`rerender-dependencies`**: Use dependências primitivas (`string`, `number`) no array do `useEffect`.
5. **`rerender-derived-state`**: Inscreva-se em booleanos derivados (ex: `hasItems`), e não no valor bruto (`items`).
6. **`rerender-derived-state-no-effect`**: Derive estado diretamente no render, e não usando `useEffect`.
7. **`rerender-functional-setstate`**: Use o callback funcional no `setState` (`setState(prev => ...)`).
8. **`rerender-lazy-state-init`**: Passe uma função para o `useState` caso a inicialização do estado seja pesada.
9. **`rerender-simple-expression-in-memo`**: Evite usar `useMemo` para expressões simples ou valores primitivos.
10. **`rerender-split-combined-hooks`**: Separe hooks que têm dependências independentes em múltiplos hooks.
11. **`rerender-move-effect-to-event`**: Coloque lógicas de interação dentro de "event handlers" em vez de em `useEffect`.
12. **`rerender-transitions`**: Use `startTransition` para atualizações de interface que não são urgentes.
13. **`rerender-use-deferred-value`**: Atrase renderizações caras usando `useDeferredValue` para manter inputs responsivos.
14. **`rerender-use-ref-transient-values`**: Use `useRef` para valores transientes que mudam frequentemente.
15. **`rerender-no-inline-components`**: Nunca defina um componente React dentro de outro componente.

### 6. Rendering Performance (MEDIUM)
1. **`rendering-animate-svg-wrapper`**: Anime o contêiner `div`, não o elemento `SVG` diretamente.
2. **`rendering-content-visibility`**: Use a regra CSS `content-visibility` para listas muito longas.
3. **`rendering-hoist-jsx`**: Extraia código JSX estático para fora dos componentes.
4. **`rendering-svg-precision`**: Reduza a precisão de coordenadas em SVGs.
5. **`rendering-hydration-no-flicker`**: Use scripts inline para dados que pertencem apenas ao client.
6. **`rendering-hydration-suppress-warning`**: Suprima avisos para "mismatches" esperados de hidratação.
7. **`rendering-activity`**: Use o componente `<Activity>` para esconder/mostrar conteúdos (React 19).
8. **`rendering-conditional-render`**: Prefira usar o operador ternário em vez de `&&` para condicionais.
9. **`rendering-usetransition-loading`**: Prefira `useTransition` para indicar estado de "carregando" (loading).
10. **`rendering-resource-hints`**: Use dicas do React DOM para fazer preload/prefetching de recursos.
11. **`rendering-script-defer-async`**: Utilize `defer` ou `async` nas tags `<script>`.

### 7. JavaScript Performance (LOW-MEDIUM)
1. **`js-batch-dom-css`**: Agrupe mudanças de CSS alterando classes ou via `cssText`.
2. **`js-index-maps`**: Crie mapas (Map/Record) para buscas que se repetem.
3. **`js-cache-property-access`**: Coloque em cache acessos a propriedades de objetos dentro de loops.
4. **`js-cache-function-results`**: Faça cache de resultados de funções num mapa no nível do módulo.
5. **`js-cache-storage`**: Faça cache em memória de leituras vindas de `localStorage` e `sessionStorage`.
6. **`js-combine-iterations`**: Combine múltiplos `filter` e `map` num único loop.
7. **`js-length-check-first`**: Verifique o `length` (tamanho) do array antes de fazer comparações "caras".
8. **`js-early-exit`**: Retorne mais cedo (early return) nas funções, evitando if/else aninhados.
9. **`js-hoist-regexp`**: "Içe" a criação de RegExp para fora de loops.
10. **`js-min-max-loop`**: Utilize loops em vez de `sort()` para descobrir o valor mínimo ou máximo.
11. **`js-set-map-lookups`**: Use `Set` ou `Map` para pesquisas rápidas (complexidade O(1)).
12. **`js-tosorted-immutable`**: Use `toSorted()` ao invés de `sort()` para evitar mutação do array.
13. **`js-flatmap-filter`**: Use `flatMap` para mapear e filtrar em uma única passagem.
14. **`js-request-idle-callback`**: Atrase tarefas não críticas para quando o navegador estiver ocioso (idle time).

### 8. Advanced Patterns (LOW)
1. **`advanced-effect-event-deps`**: Não coloque os resultados de `useEffectEvent` na lista de dependências de um `useEffect`.
2. **`advanced-event-handler-refs`**: Armazene referências para manipuladores de eventos (event handlers) usando refs.
3. **`advanced-init-once`**: Inicialize lógicas do app apenas uma vez durante o seu carregamento (load).
4. **`advanced-use-latest`**: Use o padrão `useLatest` (com `useRef`) para estabilizar callbacks.
