# Padrões de Dados e Estado no Next.js

Esta página aborda as melhores práticas relacionadas à manipulação de dados, Route Handlers e limites do Suspense no Next.js.

## Padrões de Dados (Data Patterns)

1. **Escolha a Estratégia Certa:** Entenda claramente a diferença entre Server Components, Server Actions e Route Handlers e quando utilizá-los para buscar ou mutar dados.
2. **Evite Cascatas de Dados (Data Waterfalls):** Use `Promise.all`, limites do `Suspense` ou funções de `preload` para evitar que requisições de rede travem outras (carregamento paralelo de dados).
3. **Client Component Data Fetching:** Quando for inevitável buscar dados no cliente (Client Components), siga os padrões recomendados de SWR ou React Query em conjunto com a nova API React 19.

## Route Handlers

1. **O Básico do `route.ts`:** Entenda como criar e responder a requisições com os métodos HTTP padrão (`GET`, `POST`, `PUT`, `DELETE`).
2. **Conflito de `GET`:** Não use um Route Handler `GET` e um `page.tsx` no mesmo segmento de rota.
3. **Comportamento do Ambiente:** Route Handlers não possuem o React DOM (não retornam UI e sim JSON, XML ou fluxos de dados).
4. **Quando Usar:** Use Server Actions para mutações vindas da interface, mas prefira Route Handlers para webhooks ou integrações externas.

## Limites de Suspense (Suspense Boundaries)

1. **Evitar o "CSR Bailout":** Entenda como os hooks de cliente `useSearchParams` e `usePathname` podem causar um "CSR bailout" (renderização inteiramente no cliente) se não estiverem envolvidos corretamente por um `Suspense`.
2. **Quais Hooks Requerem Suspense:** Aprenda os padrões em que um hook específico exige um Suspense em uma camada superior para manter o SSR/SSG parcial.
