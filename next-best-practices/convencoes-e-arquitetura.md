# Convenções e Arquitetura no Next.js

Esta página detalha as diretrizes de arquitetura, estruturação e convenções do Next.js baseadas na skill **next-best-practices**.

## Convenções de Arquivos (File Conventions)

1. **Estrutura de Projeto e Arquivos Especiais:** Utilize os arquivos nativos do Next.js como `layout.tsx`, `page.tsx`, `loading.tsx`, `error.tsx` etc.
2. **Segmentos de Rota:** Organize rotas dinâmicas `[id]`, catch-all `[...slug]` e grupos de rotas `(group)` conforme as práticas oficiais.
3. **Rotas Paralelas e Interceptação:** Domine padrões de modal com rotas paralelas (`@slot`) e rotas de interceptação (`(.)`). Utilize `default.tsx` para garantir fallback e feche modais corretamente com `router.back()`.
4. **Middleware:** Atenção à mudança de nome no v16, de `middleware` para `proxy`.

## Limites de React Server Components (RSC Boundaries)

1. **Detecção de Padrões Inválidos:** Identifique e corrija padrões que misturam componentes de cliente assíncronos (o que é inválido).
2. **Props Não Serializáveis:** Evite passar dados não serializáveis (como funções ou classes completas) através dos limites do Server para o Client.
3. **Exceções de Server Actions:** Trate adequadamente as Server Actions como pontos de entrada do servidor.

## Padrões Assíncronos (Async Patterns)

1. **APIs Assíncronas (Next.js 15+):** Com as mudanças nas APIs no Next.js 15, `params` e `searchParams` agora são assíncronos.
2. **Funções do Servidor:** `cookies()` e `headers()` também devem ser tratados como assíncronos.
3. **Migração:** Utilize codemods de migração fornecidos pela Vercel para atualizar o código antigo.

## Seleção de Runtime

1. **Padrão:** O Node.js é o runtime padrão e deve ser a escolha principal.
2. **Edge Runtime:** Saiba quando o Edge runtime é apropriado (geralmente para execuções muito rápidas, middlewares ou proxies onde latência global é o foco).

## Diretivas

1. **Diretivas React:** Uso de `'use client'` para componentes de cliente (interatividade, estado) e `'use server'` para ações de servidor.
2. **Diretivas Next.js:** Uso do `'use cache'` para gerenciar armazenamento de cache de dados ou fragmentos no framework.

## Funções Comuns

1. **Hooks de Navegação:** `useRouter`, `usePathname`, `useSearchParams`, `useParams`.
2. **Funções de Servidor:** `cookies`, `headers`, `draftMode`, `after`.
3. **Funções de Geração:** `generateStaticParams` e `generateMetadata` (usadas para SSG e SEO).
