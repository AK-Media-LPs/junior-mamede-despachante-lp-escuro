# Júnior Mamede Despachante — LP · tema escuro

**Cliente:** Júnior Mamede Despachante — despachante veicular particular, desde 1987
**Cidade:** Franca/SP (atende também Cristais Paulista, Ribeirão Corrente e São José da Bela Vista)
**Objetivo:** levar o visitante ao WhatsApp (16) 99319-4949, com mensagem pré-preenchida por seção

Landing page única, tráfego pago. A versão no tema claro vive em repositório
separado (https://github.com/AK-Media-LPs/junior-mamede-despachante-lp-claro).

## Stack

HTML e CSS puros. Animações com GSAP 3.13 (ScrollTrigger + SplitText) e Lenis, via CDN.
**Sem framework, sem bundler, sem etapa de build.**

```
index.html      página (design v9 aprovado no Claude Design)
support.js      runtime que renderiza o template do index.html
vercel.json     clean URLs + cache de assets
assets/         logos, símbolo JM, fotos da loja, carros, textura e favicons
```

## Deploy — Vercel

1. Importar este repositório no Vercel.
2. Framework Preset: **Other**.
3. Root Directory: **raiz do repositório** (o `index.html` está na raiz).
4. Sem Build Command, sem Install Command, sem Output Directory.

## Única edição sobre o exportado

No `<helmet>`: `<title>` estático, favicons PNG (32/180/512) e `theme-color`.
No `<html>`: `lang="pt-BR"`. Copy e layout intactos.

## Pendências sinalizadas na exportação

- **Domínio** com o nome completo → trocar `https://DOMINIO` no JSON-LD (`url` e `logo`) e adicionar Open Graph (1200×630).
- **`assets/carros.png`** veio do pngwing, licença incerta, com logos da Ford: trocar por imagem licenciada antes de anunciar.
- **Copy nova a aprovar:** "Franca e região. Pelo WhatsApp ou no balcão."
- **Pixel da Meta + GA4** (ou GTM): ainda sem IDs. Evento de clique em todo link `wa.me`.
- Horário de funcionamento e CNPJ ficam fora até o cliente enviar.

Última atualização: 29/09/2026
