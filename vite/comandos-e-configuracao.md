# Comandos e Configuração Rápida

## Comandos da CLI

1. `vite` - Inicia o servidor de desenvolvimento.
2. `vite build` - Realiza a build de produção.
3. `vite preview` - Visualiza a build de produção.
4. `vite build --ssr` - Realiza a build SSR.

## Configuração Comum

```typescript
import { defineConfig } from 'vite'

export default defineConfig({
  plugins: [],
  resolve: { alias: { '@': '/src' } },
  server: { port: 3000, proxy: { '/api': 'http://localhost:8080' } },
  build: { target: 'esnext', outDir: 'dist' },
})
```

## Plugins Oficiais

1. `@vitejs/plugin-vue` - Suporte a Vue 3 SFC.
2. `@vitejs/plugin-vue-jsx` - Suporte a Vue 3 JSX.
3. `@vitejs/plugin-react` - Suporte a React com Oxc/Babel.
4. `@vitejs/plugin-react-swc` - Suporte a React com SWC.
5. `@vitejs/plugin-legacy` - Suporte a navegadores legados.
