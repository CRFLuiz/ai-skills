# Otimização e Assets no Next.js

Esta página aborda as regras para manipulação de mídias, metadados, agrupamento (bundling) e uso correto de scripts de terceiros.

## Otimização de Imagens (Image Optimization)

1. **Uso do `next/image`:** Sempre dê preferência ao componente `<Image />` em vez de tags `<img>` nativas para aproveitar redimensionamento, formato WebP/AVIF e *lazy loading*.
2. **Configuração Remota:** Imagens externas devem ser configuradas corretamente no `next.config.ts` no array `remotePatterns`.
3. **Tamanhos Responsivos:** Use os atributos `sizes` adequados para economizar banda do usuário, dependendo dos breakpoints de layout.
4. **Placeholders de Desfoque (Blur):** Empregue placeholders para melhorar o layout *Cumulative Layout Shift* (CLS) enquanto a imagem carrega.
5. **Prioridade LCP:** Use a prop `priority` nas imagens críticas (maiores imagens da viewport visível inicial) para carregar e renderizar mais rápido.

## Otimização de Fontes (Font Optimization)

1. **Configuração com `next/font`:** O Next.js otimiza automaticamente fontes com fallback adequado e redução de tamanho.
2. **Fontes Google e Locais:** É possível otimizar fontes externas do Google Fonts ou fontes locais em seu projeto.
3. **Integração com Tailwind CSS:** O `next/font` pode injetar a fonte diretamente nas classes do Tailwind.
4. **Preloading de Subsets:** Reduza o tamanho precarregando apenas os caracteres (subsets) usados, como `latin`.

## Metadados e Imagens OG (Metadata & OG Images)

1. **Metadados Estáticos e Dinâmicos:** Utilize objetos estáticos de `metadata` ou funções dinâmicas como `generateMetadata`.
2. **Geração de Imagens OG:** O pacote `@vercel/og` e a API `ImageResponse` permitem gerar imagens de Open Graph dinâmicas baseadas em React/JSX no Edge.
3. **Convenções de Arquivo:** Utilize arquivos nativos do Next.js baseados em convenção, como `favicon.ico`, `opengraph-image.png` e `robots.txt` diretamente nas pastas de rotas.

## Agrupamento (Bundling)

1. **Pacotes Incompatíveis:** Lide com bibliotecas Node que não são compatíveis com ambientes de servidor ou Edge.
2. **Importações de CSS:** Entenda como o Next.js lida com importações CSS (não use tags de link manuais).
3. **Polyfills:** O framework já inclui os necessários; não importe duplicados.
4. **ESM / CommonJS:** Evite os problemas clássicos de conflito de módulos utilizando as diretivas e os `transpilePackages` no Next Config, se necessário.
5. **Análise de Bundle:** Ferramentas e comandos de build que ajudam a analisar o peso do JavaScript no cliente.

## Scripts de Terceiros

1. **`next/script`:** Use este componente em vez da tag `<script>` tradicional para otimizar o carregamento de JavaScript externo sem afetar o desempenho da página.
2. **Identificação:** Lembre-se que scripts inline precisam de um atributo `id` único.
3. **Estratégias de Carregamento:** Defina as estratégias `beforeInteractive`, `afterInteractive`, ou `lazyOnload` conforme o impacto daquele script.
4. **Google Analytics:** Utilize as integrações nativas recomendadas, como o pacote `@next/third-parties/google`.
