# KERBEROS — Landing Page de Lançamento

Landing page de captura para a live de lançamento do indicador KERBEROS
(Edgard Matos). Dois arquivos HTML autocontidos, sem dependências externas
além de fontes de fallback via Google Fonts.

- `index.html` — página principal (10 dobras + barra de countdown)
- `obrigado.html` — página de confirmação pós-formulário

## Como abrir

Abra `index.html` direto no navegador, ou sirva a pasta com qualquer
servidor estático (`python3 -m http.server`, Vercel, Netlify).

## Ativos pendentes (marcados com `<!-- ATIVO REAL: ... -->` no código)

| Ativo | Onde entra |
|---|---|
| Fonte BD Plakatbau (.woff2) | `assets/fonts/bd-plakatbau-black.woff2` — `@font-face` no `<head>` de ambos os arquivos |
| Fonte Salo (.woff2, regular + medium) | `assets/fonts/salo-regular.woff2` e `salo-medium.woff2` |
| Mockup Profit + KERBEROS (hero) | `.hero-media` — 1ª dobra |
| Comparativo de entrada em duas camadas | 2ª dobra, seção "O problema" |
| 3 moedas (técnica / correlação / fluxo) | `.coin` dentro de `#coin-field` — 3ª dobra. Hoje são círculos com sigla mono (AT / COR / FI); substituir mantendo `data-coin` para não quebrar a animação de scroll |
| Esquema estático das três leituras | `.mechanism-image` — 3ª dobra |
| Foto de Edgard Matos | `.authority-photo` — 5ª dobra |
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
