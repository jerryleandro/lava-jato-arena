# Lava Jato Arena — site

Site estático (HTML + CSS, sem build). Basta abrir `index.html` ou publicar a pasta.

## Arquivos

```
site/
├── index.html      página completa (todo o CSS e JS estão dentro dela)
├── styles.css      tokens da marca (cores, tipografia, componentes base)
├── assets/
│   └── logo-lava-jato-arena.png
├── .nojekyll       necessário no GitHub Pages
└── README.md
```

## Publicar no GitHub Pages

1. Crie um repositório e envie o conteúdo desta pasta na raiz (`index.html` na raiz do repo).
2. Repositório → **Settings → Pages** → Source: `Deploy from a branch` → Branch: `main` / `/ (root)` → Save.
3. O site sai em `https://<usuario>.github.io/<repo>/` em ~1 minuto.

Sem passo de build: nada de npm, nada de compilar.

## O que editar

**WhatsApp e telefone** — no fim do `index.html`:

```js
const WHATSAPP_NUMBER = '558494561446'; // internacional, só dígitos
const PHONE_DISPLAY = '(84) 9456-1446';
const WHATSAPP_MESSAGE = 'Olá! Vim pelo site do Lava Jato Arena…';
```

Alterar aí atualiza os 5 botões de WhatsApp e o telefone do topo de uma vez.

**Fotos** — hoje são fotos temporárias de banco (Unsplash), carregadas por URL. Para usar fotos próprias: coloque os arquivos em `assets/` e troque o `src` de cada `<img>` (procure por `images.unsplash.com`). Ordem em que aparecem: hero, sobre, 4 serviços, antes, depois, box/fachada. Ao trocar todas, remova a linha de créditos no rodapé.

**Preços** — tabela em `<table class="spec">`. Cada linha tem os 4 valores (Hatch, Sedan, SUV, Caminhonete) na ordem das colunas; os "a partir de" dos cards de serviço são editados à parte.

**Pendências antes de publicar**

- 3 depoimentos reais (hoje há placeholders visíveis no lugar).
- Formas de pagamento e política de agendamento (2 respostas do FAQ).
- Política de Privacidade / LGPD (link no rodapé ainda não existe).

## Dependências externas

- Google Fonts (Barlow / Barlow Condensed) — via `styles.css`.
- Ícones Lucide — via CDN unpkg (versão fixa 0.454.0).
- Mapa da Arena das Dunas — iframe do Google Maps.

Tudo funciona por HTTPS sem chave de API. Sem internet, a página ainda carrega, mas sem fontes, ícones e mapa.
