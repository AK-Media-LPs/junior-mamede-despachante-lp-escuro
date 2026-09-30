# Júnior Mamede Despachante — LP · tema escuro

**Cliente:** Júnior Mamede Despachante — despachante veicular particular, desde 1987
**Cidade:** Franca/SP (atende também Cristais Paulista, Ribeirão Corrente e São José da Bela Vista)
**Objetivo:** levar o visitante ao WhatsApp (16) 99319-4949, com mensagem pré-preenchida por seção

Landing page única, tráfego pago. A versão no tema claro vive em repositório
separado (https://github.com/AK-Media-LPs/junior-mamede-despachante-lp-claro).

## Stack

HTML e CSS puros. Animações com GSAP 3.13 (ScrollTrigger + SplitText) e Lenis.
React 18.3.1, ReactDOM, GSAP e Lenis são servidos pelo próprio site (`vendor/`), com `defer`:
a página não depende de unpkg/jsdelivr no ar.
**Sem framework, sem bundler, sem etapa de build.**

```
index.html      página (design v9 aprovado no Claude Design)
support.js      runtime que renderiza o template do index.html
vercel.json     clean URLs + cache de assets
vendor/         React, ReactDOM, GSAP (+ScrollTrigger, SplitText) e Lenis locais
assets/         logos, símbolo JM, fotos da loja, carros, textura, favicons e og-image.jpg
```

## Deploy — Vercel

1. Importar este repositório no Vercel.
2. Framework Preset: **Other**.
3. Root Directory: **raiz do repositório** (o `index.html` está na raiz).
4. Sem Build Command, sem Install Command, sem Output Directory.

## Edições sobre o exportado

- `<head>` estático (lido por WhatsApp/Google sem rodar JS): title, description, canonical,
  Open Graph (`og:*`, imagem 1200×630 em `assets/og-image.jpg`) e `twitter:card`, favicons.
- Setas/barras dos chats do Parcelamento e do CTA final viraram links reais (44 px, aria-label).
- Placa: aceita colar com hífen/espaço (limpa e corta em 7), botão é um `<a>` com o link já montado
  (sem `window.open`, que falha no navegador do Instagram/Facebook), erro visível + `aria-invalid`.
- Hero: janela some por `mask-image` antes dos carros; sombra de contato única sob as rodas.
- Parcelamento: linhas decorativas escondidas abaixo de 1024 px.
- Rodapé: cada serviço abre a aba correspondente (hover travado durante a rolagem).
- Pílula do WhatsApp limitada a 420 px e centralizada no tablet.
- Card "Quem te atende": "Quem responde no WhatsApp é quem te atende **no balcão**."
- JSON-LD sem `url`/`logo` até existir domínio.

## Pendências sinalizadas na exportação

- **Domínio** com o nome completo → trocar `https://junior-mamede-despachante-lp-escuro.vercel.app/` em `canonical`,
  `og:url`, `og:image` e `twitter:image`, e devolver `url`/`logo` ao JSON-LD (em `componentDidMount`).
- **`assets/carros.png`** veio do pngwing, licença incerta, com logos da Ford: trocar por imagem licenciada antes de anunciar.
- **Copy nova a aprovar:** "Franca e região. Pelo WhatsApp ou no balcão."
- **Pixel da Meta + GA4** (ou GTM): ainda sem IDs. Evento de clique em todo link `wa.me`.
- Horário de funcionamento e CNPJ ficam fora até o cliente enviar.

Última atualização: 29/09/2026 (rodada de correções)
