# CEL — Como Empreender Lucrando — LP V2 (versão final)

**Cliente:** CEL (Felipe Winston)
**Objetivo:** levar ao checkout Hotmart (W94393903V · off=9bv66jk3), com UTMs repassadas

## Stack
HTML + runtime do Claude Design (`support.js`, `image-slot.js`, não editar). React, ReactDOM, Babel e GSAP/ScrollTrigger locais em `vendor/`. Fontes Roboto locais em `assets/fonts/`. Sem build.

## Deploy — Vercel
Import do repo · Framework Preset **Other** · Root Directory na raiz · sem Build/Install Command, sem Output Directory.

## Edições sobre o exportado
- `<head>` estático com título, description, canonical, Open Graph, Twitter e favicon (crawlers não rodam JS); removidos do `<helmet>`, que ficou só com o CSS das fontes.
- React, ReactDOM, Babel (7.29.0, SRI conferido) e GSAP/ScrollTrigger (3.13.0) servidos de `vendor/`, com `defer` antes do `support.js`; `<style>x-dc{display:none}</style>`.
- Removido o marcador amarelo [A VALIDAR] do bônus "Diagnóstico dos 8 pilares" (validado pelo cliente).
- `DEPLOY.md` do export movido para `docs-handoff/DEPLOY-v2.md`; adicionados `vercel.json`, `.gitignore`, `robots.txt` e `favicon.ico`.
- Observação: 404 inofensivo no console (`{{ v.embed }}`) vem do template do export, sem efeito na página.

## Testado localmente (08/10/2026)
Renderiza, sem requisições a CDN, UTMs/`src`/`sck` chegam ao checkout, vídeo de depoimento abre, mobile 390 px sem rolagem horizontal.

## Pendências
- [ ] URL real da Vercel/domínio: trocar `SEU-DOMINIO.com.br` (canonical, og:url, og:image, twitter:image) e fazer segundo commit
- [ ] ID do GTM (não há tag no export): inserir como 1ª coisa do `<head>` + `<noscript>` após `<body>`; Pixel Meta e GA4 dentro do GTM
- [ ] Depoimentos: conferir nome/segmento/pilar (pendência de copy citada no DEPLOY.md)
- [ ] `robots.txt` hoje `Allow: /`; se for só tráfego pago, `Disallow: /` + `noindex` [DECIDIR]

Última atualização: 08/10/2026
