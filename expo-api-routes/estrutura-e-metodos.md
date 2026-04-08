# Estrutura e Métodos HTTP

## Estrutura de Arquivos

As rotas de API vivem no diretório `app` com o sufixo `+api.ts`:

1. `app/api/hello+api.ts` → GET `/api/hello`
2. `app/api/users+api.ts` → `/api/users`
3. `app/api/users/[id]+api.ts` → `/api/users/:id`

## Rota de API Básica

Exemplo de como exportar uma função nomeada para lidar com requisições HTTP:

```typescript
// app/api/hello+api.ts
export function GET(request: Request) {
  return Response.json({ message: "Hello from Expo!" });
}
```

## Métodos HTTP

Exporte funções nomeadas para cada método HTTP desejado:

```typescript
// app/api/items+api.ts
export function GET(request: Request) {
  return Response.json({ items: [] });
}

export async function POST(request: Request) {
  const body = await request.json();
  return Response.json({ created: body }, { status: 201 });
}

export async function PUT(request: Request) {
  const body = await request.json();
  return Response.json({ updated: body });
}

export async function DELETE(request: Request) {
  return new Response(null, { status: 204 });
}
```

## Rotas Dinâmicas

Para criar rotas com parâmetros dinâmicos, use colchetes no nome do arquivo:

```typescript
// app/api/users/[id]+api.ts
export function GET(request: Request, { id }: { id: string }) {
  return Response.json({ userId: id });
}
```
