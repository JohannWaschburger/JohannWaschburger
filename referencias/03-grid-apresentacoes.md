# 03 · Grid para slides de 1920×1080

## Base
- **Müller-Brockmann:** margens consistentes e iguais, colunas separadas por calha (gutter) fixa, o campo modular como unidade. ([Grid Systems in Graphic Design](https://thamesandhudson.com.au/?p=93182), [resumo](https://madegooddesigns.com/grid-systems/))
- **Material:** layout em grid de 8, tipo em 4; colunas fluidas, calha e margem fixas. ([m2.material.io/design/layout](https://m2.material.io/design/layout))
- **Safe area:** a SMPTE ST 2046-1 define o *title safe* em 90% do quadro, o que em 1920×1080 dá 96px de cada lado e 54px em cima e embaixo. ([SMPTE ST 2046-1](https://pub.smpte.org/doc/st2046-1/20091123-pub/st2046-1-2009.pdf))
- **Escala da marca (Figma, coleção Forma e Espaço):** 8 · 16 · 24 · 32 · 48 · 64 · 96, `grid/colunas` 12 (Desktop), `space/gutter` 48 (Desktop), `grid/gap` 24.

## Decisões

| Item | Valor | Origem |
|---|---|---|
| Unidade base | 8px | `space/1` |
| Margem lateral | 96px | `space/12`, coincide com o title safe |
| Margem superior e inferior | 64px | `space/8`. **Ajuste:** o title safe pede 54px, que não existe na escala; subi para 64, o próximo valor da marca. |
| Colunas | 12 de 100px | `grid/colunas` Desktop |
| Calha (gutter) | 48px | `space/gutter` Desktop |
| Área útil | 1728 × 952px | 12·100 + 11·48 = 1728 |
| Linhas | 4 de 202px, calha de 48px | 4·202 + 3·48 = 952. Quatro linhas, como os quatro tempos. |
| Respiro entre blocos | 48 (bloco) · 24 (item) · 16 (texto) · 8 (par) | `respiro/*` |

**Bordas das colunas (x):** col 1 = 96 · 2 = 244 · 3 = 392 · 4 = 540 · 5 = 688 · 6 = 836 · 7 = 984 · 8 = 1132 · 9 = 1280 · 10 = 1428 · 11 = 1576 · 12 = 1724 (fim 1824).
**Bordas das linhas (y):** L1 64–266 · L2 314–516 · L3 564–766 · L4 814–1016.

## Hierarquia tipográfica por slide
A escala do Figma é modular, razão 1,25 sobre 16px (16 · 20 · 25 · 31,25 · 39,06 · 48,83 · 61,04 no Desktop). Para a tela de 1920 continuei a mesma razão até 120px, o tamanho do título nas artes de 1920×1080 do próprio Figma (16 × 1,25⁹ ≈ 119).

| Papel no slide | Estilo | Tamanho / entrelinha | Token de entrelinha |
|---|---|---|---|
| Título de capa | Syne 700, -1,8% | 120 / 1,06 | `leading/display` |
| Título de slide | Syne 700, -1% | 61,04 / 1,15 | `leading/tight` |
| Subtítulo e lead | Inter 400 | 31,25 / 1,3 | `leading/snug` |
| Corpo | Inter 400 | 25 / 1,5 | `leading/normal` |
| Rótulo sobre fio (A2) | DM Mono 400, caixa baixa | 20 / 1,3 | Mono/Rótulo |
| Legenda e valor de token | DM Mono 400 | 16 / 1,3 | Mono/Pequeno escalado |

**Densidade:** um título, no máximo 60 palavras de texto corrido e uma imagem ou grade por slide. Pelo menos uma linha do grid fica vazia nos slides de texto.

## Layouts-tipo (posições em colunas e linhas)

1. **Capa:** fundo `brand/papel`. Logo principal Positivo em col 1–4, topo de L1. Título 120px em col 1–9, de L2 a L3. Rótulo sobre fio em col 1–12, na base de L4 (y 976–1016). Ícone principal em col 10–12, de L1 a L4.
2. **Divisor de seção:** fundo `brand/tinta`, modo Tinta. Número da seção (DM Mono) em col 1–2 L1; título 120px em col 1–10, L3; compasso com a posição em col 11–12, L1. (No deck as seções entram pelo rótulo do topo, então este layout não foi usado: ver ajuste no fim.)
3. **Texto + imagem:** rótulo sobre fio em col 1–12, y 64. Título em col 1–5, L1. Texto em col 1–5, L2–L4. Imagem em col 7–12, L1–L4, raio `radius/midia` 32.
4. **Grade de componentes:** rótulo e título em col 1–12, L1. Componentes em L2–L4, em 2, 3 ou 4 módulos (6, 4 ou 3 colunas cada). Legenda mono 16px a 16px (`respiro/texto`) abaixo de cada módulo.
5. **Tabela de tokens:** título em col 1–4, L1–L2, com a regra em corpo. Tabela em col 5–12, L1–L4: amostra 48px · nome · valor · papel, linhas sobre fio de 1px, altura de linha 56 (7×8).
6. **Imagem cheia:** imagem de 1920×1080 sem margem, ou reduzida dentro da área útil com legenda no fio de rodapé. Usado nas artes da tela de atualização (1 grande em col 1–8 e 2 menores em col 9–12).

Sobreposição do grid: tecla **G** no HTML mostra as 12 colunas, as 4 linhas e as margens.

**Ajuste registrado:** o divisor de seção (layout 2) ficou fora. Com 16 slides, cada divisor tiraria um slide de conteúdo, e a seção já aparece no rótulo do topo de cada slide.
