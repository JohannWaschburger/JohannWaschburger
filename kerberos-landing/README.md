# KERBEROS — Landing Page de Lançamento

Landing page de captura para a live de lançamento do indicador KERBEROS
(Edgard Matos). Dois arquivos HTML autocontidos, sem dependências externas
além de fontes de fallback via Google Fonts.

- `index.html` — página principal (10 dobras + barra de countdown)
- `obrigado.html` — página de confirmação pós-formulário

## Como abrir

Abra `index.html` direto no navegador, ou sirva a pasta com qualquer
servidor estático (`python3 -m http.server`, Vercel, Netlify).

## Ativos já aplicados

| Ativo | Arquivo | Nota |
|---|---|---|
| 3 moedas (técnica / correlação / fluxo) | `assets/images/moeda-*.webp` | Recortadas do material original, redimensionadas e comprimidas (480×480, WebP q85) |
| Foto de Edgard Matos | `assets/images/edgard-matos.webp` | Recorte original vinha com bloco laranja + faixa "Edgard Matos" embutidos; removi os dois via chroma-key (mantendo só o cutout do Edgard, fundo transparente) porque o bloco/nome não seguia o sistema tipográfico e de cor do projeto. O "bloco de cor atrás" pedido no briefing agora é a própria seção `bg-ocre` — funciona porque o cutout foi tratado especificamente para essa cor de fundo. **Se essa foto for reaproveitada em outra seção/fundo, gerar um novo recorte a partir do original** (o cutout atual pode mostrar uma leve franja/halo em fundos escuros). |

## Ativos pendentes (marcados com `<!-- ATIVO REAL: ... -->` no código)

| Ativo | Onde entra |
|---|---|
| Fonte BD Plakatbau (.woff2) | `assets/fonts/bd-plakatbau-black.woff2` — `@font-face` no `<head>` de ambos os arquivos |
| Fonte Salo (.woff2, regular + medium) | `assets/fonts/salo-regular.woff2` e `salo-medium.woff2` |
| Mockup Profit + KERBEROS (hero) | `.hero-media` — 1ª dobra |
| Comparativo de entrada em duas camadas | 2ª dobra, seção "O problema" |
| Esquema estático das três leituras | `.mechanism-image` — 3ª dobra |
| Numeral fundido em bronze (72%) | `.bronze-num` — 6ª dobra, e os números 1/2/3 em `obrigado.html` |
| Mosaico de prints do KERBEROS (WIN/WDO) | `.proof-mosaic` — 6ª dobra |
| Logo Nelogica | `.nelogica-logo` — rodapé de ambas as páginas |
| Formulário | `#lead-form` envia hoje para `obrigado.html` via JS; trocar por integração real (CRM/webhook) |
| Contador de inscritos | simulado a partir de 500 em `index.html`; trocar pelo valor real do backend |
| Link do grupo do WhatsApp | `#community-link` em `obrigado.html` |
| Metodologia do backtest | texto entre colchetes na 6ª dobra (ativo, período, tempo gráfico, critério de entrada/saída) |

## Mecânica de scroll (3ª dobra)

A convergência das três moedas é ligada à posição de scroll dentro de
`#coin-stage-wrap` (250vh) via `requestAnimationFrame`, sem bibliotecas
externas. Funciona em desktop e mobile porque depende apenas de
`window.scrollY`. Respeita `prefers-reduced-motion`.
