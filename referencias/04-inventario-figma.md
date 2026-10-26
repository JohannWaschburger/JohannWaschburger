# 04 · Inventário do Figma

Arquivo: `Os-4-tempos-do-mercado` (ghilQjlMPNETRzmfL3YaC8). Lido via MCP em 26/10/2026, com variáveis, estilos, metadados, descrições de componente e capturas.
Páginas: DS · Fundamentos (69:2) · DS · Logos e Ícones (55:2) · DS · Componentes (60:2) · KV · logo · CDN · Email · Tela de atualização (77:2) · Ads · Facebook.

**Como os assets foram baixados:** a rede deste ambiente bloqueia `figma.com`, então as URLs de exportação não abrem. As imagens em `/assets` vêm das capturas que o MCP devolve inline (PNG em tamanho real, 1× a 3×), e os logos vêm de `exportAsync(SVG_STRING)`, os vetores originais. As versões Negativo, Mono tinta e Mono papel do logo principal foram geradas trocando o hex dos preenchimentos, conferidos no Figma (Positivo: tinta + laranja · Negativo: papel + laranja · Mono tinta: só tinta · Mono papel: só papel).

## Variáveis

**Primitivos (1 modo)**
- brand: papel #F4F3EF · pedra #E5E3DC · tinta #141619 · laranja #DF4A29 · laranja-sombra #CD4527 · laranja-hover #CF4020 · laranja-ativo #BC391C · laranja-texto #B63518 · laranja-claro #E4583A. Nota do Figma: "a cor da marca é #DF4A29 e não muda; derivados mantêm o matiz 33.9 (OKLCH)".
- neutro: 50 #F4F3EF · 100 #E5E3DC · 150 #D8D6CF · 200 #C9C7C1 · 300 #ADABA5 · 400 #8E8C87 · 500 #74736F · 600 #5E6064 · 700 #45484C · 800 #2E3034 · 900 #1E2124 · 950 #141619.
- sinal: compra #03A14A · compra-claro #7CD591 · venda #D02940 · venda-claro #F49191 · saida #F3C530 · saida-roxo #7544CD · neutro #ADABA5.
- feedback: success #03A14A · success-texto #197037 · danger #D02940 · danger-texto #BE2038.

**Cor (4 modos: Papel, Pedra, Tinta, Laranja)**, iguais às classes `.superficie-*` do código. Papéis por alias (Papel / Pedra / Tinta / Laranja):
- surface: papel / pedra / tinta / laranja · on-surface: tinta / tinta / papel / papel · texto-corpo: neutro-700 / 700 / 150 / papel
- surface-alt: pedra / papel / neutro-900 / pedra · muted: neutro-600 / 600 / 300 / 600 · border: neutro-200 / 200 / 700 / laranja-sombra · border-strong: neutro-500 / 500 / 400 / 500
- primary e accent: laranja (fixo) · primary-hover: laranja-hover · primary-active: laranja-ativo · on-primary: papel · accent-texto: laranja-texto (laranja-claro no modo Tinta)
- surface-inverse: tinta · surface-marca: laranja · fio-rotulo: tinta / tinta / papel / papel · focus: tinta / tinta / papel / tinta · meio-tom: laranja (laranja-sombra no modo Laranja) · success, danger e seus -texto · on-success, on-danger: papel
- Regra do modo Laranja: "só texto grande: ≥24px, ou ≥19px a 700 … (papel/laranja = 3,67:1)".

**Forma e Espaço:** space 1·2·3·4·6·8·12 = 8·16·24·32·48·64·96 · respiro par 8, texto 16, item 24 · grid/gap 24 · radius capsula 999, card 24, midia 32, md 16, sm 8, checkbox 6 · capsula/vao 0,6 · squircle/suavizacao 0,6 · btn-min-h 44, btn-min-h-lg 52, btn-pad-x 28, btn-pad-x-compacto 18, campo-h 52, touch-min 24, etiqueta-h 28, mt-celula 12 · borda fina 1, botao 1,5, foco 2, foco-offset 2 · icone/traco 2 · container max 1200, wide 1440, estreito 720 · breakpoints 640, 768, 1024, 1440 · motion 150, 250, 400 (ms).
Nota: "grid de 8pt · a cápsula (999px) é o DNA da marca: tudo que se toca é cápsula; 24/32px só em card e mídia".

**Responsivo (Mobile → Desktop):** text xs 12 · sm 14 · base 16 · lg 19,3→20 · h4 23,3→25 · h3 28,1→31,25 · h2 33,9→39,06 · h1 40,9→48,83 · display 49,3→61,04 · hero 32,8→64 · hero-eyebrow 21,3→32 · btn/fs-lg 19 · btn/fs 16 · secao-y 65→96 · respiro-bloco 48,5→64 · card-pad 32,5/25→48/48 · gutter 19,5→48 · grid/colunas 4→12.

**Tipografia:** font titulo Syne, corpo Inter, mono DM Mono · pesos Bold / Regular / Regular · leading display 1,06, tight 1,15, snug 1,3, normal 1,5.

## Estilos
- **Cor (7):** Branco - 4T #F4F3EF ("fundos") · Segunda cor - 4T #E5E3DC · Preto - 4T #141619 · CTA - 4T #DF4A29 · complementar 2 #182033 · Complementar 3 #A9875A · Complementar 4 #848E8F.
- **Texto (21):** Título/Hero, Display, H1–H4, Eyebrow hero, Item (Syne Bold) · Botão/Grande 19, Padrão 16, Grande (hero) 24 (Syne Bold) · Corpo/Lead 19,3, Base 16, Pequeno 14, Legal 12 (Inter Regular, 150%) · Mono/Rótulo 14, Pequeno 12, Etiqueta 12 em caixa alta +6%, Número 40,9, Preço 40,9 −2%, Preço pequeno 19,3 (DM Mono Regular). Os estilos guardam o tamanho Mobile; o Desktop está na coleção Responsivo.
- **Efeito (4):** Elevação/1 a /4, sombras em tinta com alfa de até 12%. Regra: "Elevação/0 na página; Elevação/3 só no que flutua (nav); Elevação/4 no modal".

## Componentes (página DS · Componentes)
| Componente | Variantes e estados | Regra-chave (descrição no Figma) |
|---|---|---|
| Botão | Tipo Primário, Secundário, Tinta × Estado Repouso, Hover, Foco, Ativo, Desabilitado, Carregando · props Rótulo, Seta | Primário em Syne 700 a 19px, nunca menor. Foco com anel de 2px. Sobre laranja, use o Tinta. |
| Botão com disco | Estilo Tinta, Contorno × 6 estados (Padrão) + Compacto e Grande · prop Ícone | Altura 2,75em, disco 2,15em. Compacto 16px (44), Padrão 19px (52), Grande 24px (66). O disco nunca sai. Não usar junto com o Primário. |
| Botão só de disco | Estilo Laranja, Tinta × Repouso, Hover, Foco, Ativo, Desabilitado | Alvo de 52px; rótulo acessível obrigatório (`.sr-only`). Sobre laranja, o disco vira tinta. |
| Ícones de ação | Seta direita, baixo, cima, cima-direita, Play (24px) | Lucide, traço 2, cor papel. |
| Etiqueta | Contorno, Cheia · props Texto, Marca | Mono 12 em caixa alta; o texto nunca é laranja. Não é botão. |
| Rótulo sobre fio (A2) | Fio Padrão, Laranja | Dado factual em DM Mono, caixa baixa, sobre fio de 1px. Fio laranja só para "a próxima". |
| Compasso (A1) | Ativo Nenhum, 1–4 | Marca posição numa sequência de quatro, nunca importância. |
| Campo | Repouso, Hover, Foco, Erro, Sucesso, Desabilitado | Cápsula de 52px, fonte 16px, borda neutro-500. Erro e sucesso com cor e texto. |
| Escolha | Repouso/Foco × Marcado Sim/Não | Marcada = tinta com check papel. |
| Contador regressivo | Contando, Ao vivo | Dígito DM Mono em célula pedra. |
| FAQ item | Fechado, Aberto | Linhas sobre fio; o "+" gira 45°. |
| Inclusão | Celular, Desktop | 4fr/6fr/2fr no desktop; peso igual entre itens. |
| Garantia | — | "[texto da garantia conforme a OP]". |
| Placeholder de imagem | — | Imagem que falta vira placeholder, nunca imagem inventada. |
| Frase-marca | Faixa Laranja, Tinta | Uma por página, só em texto ≥24px. |
| Retrato do parceiro | — | Recorte sobre laranja, 4 cápsulas em laranja-sombra #CD4527, moldura de 32px. |
| Agenda item | Normal, Próxima | Lives 03/11 19h, 10/11 9h, 18/11 19h. Preço nunca aparece aqui. |
| Plano | Superfície Papel, Tinta | Preço em 000; "o preço é revelado na live 01". |
| Cartão do tempo | Virar, Acelerar, Romper, Voltar | Glifo dimensionado pela largura (48px). Ordem fixa. "Não existe cor por tempo." |
| Nav em cápsula | Celular, Desktop | Papel opaco + Elevação/3. |
| Rodapé Nelogica | Celular, Desktop | Texto legal verbatim; falta razão social e CNPJ. |
| Fundos / Fundos com bolinhas | 5 + 3 modelos | Sem descrição. |

## Logos e ícones (página DS · Logos e Ícones)
- **Logo/4 Tempos do Mercado:** Positivo, Negativo, Mono tinta, Mono papel. Área livre = largura de uma cápsula nos 4 lados; mínimo de 120px de largura; "nunca esticar, contornar, sombrear nem refazer em Syne".
- **Ícone/4 Tempos do Mercado:** Laranja, Mono tinta, Mono papel; usado como favicon.
- **Logo/Tempo de Virar, Acelerar, Romper, Voltar:** 4 versões cada. **Ícone/Tempo de …:** Laranja, Mono tinta, Mono papel; "dimensione sempre pela LARGURA"; "nunca com eixo, número ou como ilustração de crescimento".

## Tela de atualização (77:2): 3 artes de 1920×1080
Papel + meio-tom laranja + retrato de Suriel Ports (765×1020, x 1119) + logo (444×112, x 118 y 132) + título Syne 700 120px −2,16px + 2 faixas laranja Syne 46px + CTA botão com disco (Syne 44px, disco 92px).
- PT: "Virar, acelerar, / romper, voltar:" · "uma carteira com 4 indicadores / para 4 momentos do mercado." · "Quero minha vaga na live"
- EN: "Turn, accelerate, / break out, revert:" · "a portfolio of 4 indicators / for 4 market moments." · "Save my spot for the live"
- ES: "Girar, acelerar, / romper, volver:" · "una cartera con 4 indicadores / para 4 momentos del mercado." · "Quiero mi lugar en la live"

## Lacunas no Figma
1. **Zip dos tokens em código:** não aparece em nenhuma camada lida pelo MCP. As descrições citam o código (`.superficie-*`, `.sr-only`, "DS 1.2.0", "script da galeria"), mas o zip, se está no arquivo, não é visível para mim.
2. **Chips e caixas de ícone:** não existem com esses nomes. O mais próximo de tag é a Etiqueta; de caixa de ícone, o Botão só de disco e o painel dos Ícones de ação.
3. **Papéis sem nome:** `sinal/saida-roxo` e `sinal/neutro` não têm descrição. Os estilos "complementar 2/3/4" (#182033, #A9875A, #848E8F) não têm papel nem variável.
4. **Tamanhos dos estilos de texto:** guardam o valor Mobile. Quem aplica o estilo no desktop precisa ligar a variável Responsivo.
5. **Logo sem "Os":** o wordmark diz "4 TEMPOS DO MERCADO".

## Cruzamento com a OP (Fase 0)
| Ponto | OP / apoio | Figma | Situação |
|---|---|---|---|
| Nome | "Os 4 Tempos de Ports" | "4 Tempos do Mercado" | Divergente; pendência da Estratégia |
| Tempos | Indicadores 1–4 por nome técnico | Virar/Acelerar/Romper/Voltar + leitura (reversão, impulso, tendência do dia, retorno à média) | Ligação marcada "confirmar" no Figma |
| Cores de sinal | How-To: verde-água comprado, coral vendido, dourado alvo, **fúcsia** stop | sinal/compra verde, venda vermelho, saida amarelo, saida-**roxo** | Fúcsia × roxo a confirmar; os hex do Figma não são verde-água nem coral |
| Lives | 03/11 19h · 10/11 9h · 18/11 19h | Iguais (Agenda item) | Ok |
| Preço | R$ 79,90/mês no Bienal | 000; proibido na página | Coerente com a regra |
| Garantia | Não está na OP | Pede "texto da OP" | Lacuna |
| Público iniciante, 4 com o mesmo peso | OP + Estratégia | "Peso igual", "não existe cor por tempo" | Ok |

## Revisão (Fase 6)
- Render de cada slide em 1920×1080 pelo Playwright (`/apresentacao/revisao/`): sem sobreposição, sem placeholder, imagens nas proporções originais (`object-fit: contain`, sem filtro).
- Cores, fontes e espaçamento do HTML vêm das variáveis acima (`:root` com os nomes do Figma).
- Busca de vocabulário vetado do guia 02 nos textos do HTML: zero ocorrências.
- Corrigido na revisão: transbordo de imagem e legenda nos slides 10, 12, 13, 14 e 15 (imagens reduzidas, sem mudar a proporção); quebra de nome de variável no meio (slide 9); 5 caracteres sem glifo nas fontes da marca (↔, …, ≥, ×, −), que caíam em fonte de sistema no PDF. O PDF final só usa Syne, Inter e DM Mono.
