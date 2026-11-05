# Prime Licitações – site estático (Vercel)

## Deploy
1. Suba esta pasta para um repositório (GitHub) e importe em vercel.com/new, ou rode `npx vercel --prod`.
2. Framework Preset: **Other** · Build Command: vazio · Output Directory: vazio (raiz).
3. `styles.css` já vem compilado. Se mudar classes no `index.html`: `npm i && npm run build:css`.

## Rate limit (configurar no painel)
Projeto > Firewall > Configure > Add Rule:
- Nome: `rate-limit-geral` · If: Request Path *matches* `/` (ou Host existe)
- Then: **Rate Limit** · janela 60s · 100 requisições por IP · ação Challenge/Deny.
Também ative **Attack Challenge Mode** apenas se sofrer ataque. A mitigação de DDoS (L3/L4/L7) da Vercel já é automática.

## Antes de publicar
- Domínio próprio: adicione em Settings > Domains (HTTPS e HSTS ativos).
- Opcional: envie o domínio a hstspreload.org (o header já tem `preload`).
- Teste os headers em securityheaders.com e observatory.mozilla.org.
