# Skill: Peças Jurídicas HTML — Template Personalizável

## 🚀 Como Instalar e Configurar

Esta skill é uma ferramenta avançada para geração de peças jurídicas diretamente em formato HTML otimizado para exportação em PDF (A4).

### 🤖 Instalação no Claude
1. **Via Projetos (Recomendado):** Crie um "Project" no Claude e faça o upload deste arquivo `.md` na seção **Knowledge**. Nas "Custom Instructions", adicione: *"Consulte o arquivo da skill de peças HTML e aplique as regras visuais e o Wizard sempre que eu pedir para redigir uma peça."*
2. **Uso Direto:** Copie o conteúdo abaixo e cole no chat do Claude, dizendo: *"Aja como meu redator jurídico e adote o seguinte template para a criação de peças:"*

### ⚙️ Instalação no Antigravity (Agente Local)
1. Crie uma pasta chamada `pecas-juridicas-html` dentro de `.agent/skills/`.
2. Salve o conteúdo abaixo em um arquivo chamado `SKILL.md` dentro dessa nova pasta.
3. Certifique-se de que o cabeçalho (Frontmatter) YAML contém `name` e `description` conforme fornecido.

---
*(Conteúdo Oficial da Skill abaixo)*

---
name: pecas-juridicas-html
description: >
  Gera peças jurídicas em HTML otimizado para exportação em PDF via browser, com identidade visual profissional personalizável: faixa lateral colorida, tipografia configurável, paleta de cores customizável, cabeçalho com logo SVG inline + dados de contato do escritório. Na PRIMEIRA execução, a skill conduz um wizard guiado para configurar dados do escritório, fontes, cores e estilo visual. Use SEMPRE que o usuário pedir para gerar, redigir ou exportar qualquer peça jurídica em HTML/PDF — petições, manifestações, recursos, contestações, contrarrazões, impugnações, cumprimentos de sentença, memoriais, ou qualquer documento jurídico com saída em HTML. Acionar também quando o usuário mencionar "timbrada HTML", "PDF da petição", "peça em HTML", "configurar skill de peças" ou similar.
---

# Peças Jurídicas HTML — Template Personalizável

Gera um arquivo `.html` pronto para exportação como PDF via `Ctrl+P → Salvar como PDF → Margens: Padrão → Gráficos de fundo: ativado`.

---

## ⚠ REGRAS CRÍTICAS (ler antes de qualquer execução)

1. **Verificação de viabilidade obrigatória**: antes de gerar, estimar o volume do conteúdo. Se houver risco de supressão por limitação de contexto, informar o usuário antes de executar qualquer função.
2. **Nunca inventar precedentes, súmulas ou fundamentação jurídica.**
3. **Nunca suprimir jurisprudências** — citar exatamente como o usuário apresentar.
4. **Logo SVG sempre inline** — nunca carregar arquivo externo. Copiar o SVG da seção "Logo SVG" abaixo integralmente.
5. **Padding nunca zerado no `@media print`** — exceto `padding-top` do `.doc`, que é substituído pelo `margin-top` do `@page`.
6. **Faixa lateral via `border-left` no `.doc`** — nunca via `position: fixed` ou elemento separado.

### 🔒 REGRA INEGOCIÁVEL — Impressão A4 Dinâmica

O HTML **NUNCA** deve ter altura pré-definida em nenhum contêiner. A quebra de página é controlada exclusivamente pelo browser via `@page` + regras `page-break-*` / `break-*`. Isso é inegociável:

- **PROIBIDO**: `height`, `min-height` ou `max-height` em `.doc` ou qualquer contêiner de layout
- **PROIBIDO**: `position: fixed` ou `position: absolute` para elementos que devem fluir entre páginas
- **OBRIGATÓRIO**: `page-break-inside: avoid` / `break-inside: avoid` em todo elemento atômico (parágrafos, citações, fechamento, itens de lista, linhas de tabela)
- **OBRIGATÓRIO**: `page-break-after: avoid` / `break-after: avoid` em títulos de seção e cabeçalhos
- **OBRIGATÓRIO**: `orphans: 3; widows: 3` em parágrafos longos
- **PERMITIDO**: containers longos (`.box-break`, tabelas grandes) podem quebrar entre páginas — proteção é por item/linha, não pelo container

---

## Fluxo de Trabalho

1. **Verificar se o escritório já foi configurado** — se os dados do escritório não estiverem disponíveis (nem na conversa, nem nas User Preferences), executar o Wizard de Configuração antes de qualquer geração.
2. Verificar viabilidade (tamanho do conteúdo × limite de contexto)
3. Coletar dados: número do processo, partes, vara/juízo, tipo de peça, conteúdo
4. Gerar o HTML completo seguindo a estrutura abaixo
5. Salvar em `/mnt/user-data/outputs/[TipoPeca]_[Parte]_[Réu].html`
6. Apresentar com `present_files`



---

## 🔧 WIZARD DE CONFIGURAÇÃO (primeira execução)

Na primeira vez que o usuário acionar esta skill, ou quando o usuário pedir para "configurar a skill de peças", o Claude deve conduzir um wizard **etapa por etapa**, perguntando uma etapa de cada vez e aguardando a resposta antes de avançar.

### Instruções para o Claude

- Conduzir **uma etapa por vez**. Não despejar todas as perguntas de uma vez.
- Mostrar os valores padrão entre parênteses. Se o usuário responder "ok", "pode ser", "padrão" ou equivalente, usar o padrão.
- Se o usuário disser "usar padrões para o resto", pular as etapas restantes e usar todos os padrões.
- Ao final, gerar um **resumo completo** em formato copiável e pedir confirmação.
- Após confirmação, informar ao usuário que ele pode copiar o resumo para as User Preferences (Settings > Profile) para não precisar repetir a configuração em conversas futuras.

### ETAPA 1 — Dados do Escritório

Texto sugerido para o Claude:

```
Vamos configurar sua skill de peças jurídicas HTML! Vou te guiar passo a passo.

Primeiro, preciso dos dados do seu escritório para o cabeçalho das peças:

1. Nome completo do advogado titular (ex.: João da Silva Santos)
2. OAB (ex.: OAB/SP 123.456)
3. Razão social do escritório (ex.: Silva Santos Sociedade de Advogados)
4. Sigla para o logo — geralmente 2 letras (ex.: SS)
5. Nome curto para o logo (ex.: SILVA SANTOS)
6. OAB da Sociedade, se houver (ex.: OAB/SP 12.345 — ou deixe em branco)
```

### ETAPA 2 — Endereço e Contato

```
Agora os dados de contato que aparecem no cabeçalho:

1. Endereço completo (ex.: Rua das Flores, 100 · Centro · CEP 01.234-000 · São Paulo — SP)
2. Cidade-UF para fechamento das peças (ex.: São Paulo-SP)
3. E-mail de contato (ex.: contato@escritorio.com)
4. Telefone fixo (ex.: (11) 3000-0000 — ou deixe em branco)
5. Telefone celular (ex.: (11) 99000-0000)
```

### ETAPA 3 — Tipografia

```
Agora vamos definir as fontes. A skill usa duas famílias tipográficas:

• Fonte de títulos (cabeçalhos, seções, logo, assinatura)
  Padrão: Space Grotesk — moderna, geométrica, profissional
  Alternativas comuns: Montserrat, Raleway, Poppins, Inter, Roboto Slab

• Fonte do corpo (parágrafos, citações, texto corrido)
  Padrão: DM Sans — limpa, legível, contemporânea
  Alternativas comuns: Source Sans 3, Lato, Noto Sans, Open Sans, Merriweather (serifada)

Quer manter os padrões ou prefere outras fontes?
(Todas devem estar disponíveis no Google Fonts para carregar corretamente)
```

### ETAPA 4 — Tamanhos e Espaçamento

```
Tamanhos de fonte e espaçamento:

• Tamanho do corpo do texto (padrão: 15px ≈ 12pt Word)
• Tamanho das citações jurisprudenciais (padrão: 12.5px ≈ 10pt)
• Espaçamento entre linhas (padrão: 1.65 — equivalente a ~1,5 do Word)
• Recuo da primeira linha dos parágrafos (padrão: 2cm)
• Margem esquerda do documento (padrão: 32mm — inclui respiro da faixa lateral)
• Margem direita (padrão: 20mm)

Quer ajustar algum desses valores ou manter os padrões?
```

### ETAPA 5 — Cores e Identidade Visual

```
Paleta de cores da peça:

• Cor do texto principal (padrão: #1A1714 — preto quente)
• Cor de destaque / faixa lateral (padrão: #B08A4E — dourado)
• Cor de texto secundário (padrão: #6B5E4E — marrom acinzentado)
• Cor das linhas divisórias (padrão: #DDD6C8 — bege claro)
• Largura da faixa lateral (padrão: 6px)

Se você tem as cores do seu escritório em hex, pode informar aqui.
Ou quer manter a paleta padrão?
```

### ETAPA 6 — Estilo das Citações Jurisprudenciais

```
Como você quer que as citações de jurisprudência apareçam?

• Formato sanduíche (padrão): tese → ementa itálica recuada → fonte → aplicação ao caso
• Recuo da citação: esquerda (padrão: 2cm) + direita (padrão: 10px)
• Fonte do julgado — onde aparece a identificação (tribunal, número, relator)?
  - Abaixo da ementa, em linha separada (padrão)
  - Ao final da própria ementa, entre parênteses
• Estilo visual: itálico (padrão) ou entre aspas sem itálico?

Quer manter o padrão ou ajustar?
```

### ETAPA 7 — Regras de Redação

```
Preferências de redação para as peças:

• Pedidos/requerimentos formatados como: a) b) c) (padrão), ou I, II, III, ou 1, 2, 3?
• Valores monetários: sempre número + extenso? (padrão: sim — R$ 10.000,00 (dez mil reais))
• Latim e estrangeirismos em itálico? (padrão: sim)
• Nome do escritório aparece no corpo da petição? (padrão: não — só no cabeçalho)
• Limite de linhas por parágrafo (padrão: 4–5 linhas impressas em A4)
• Construção em blocos ou peça inteira de uma vez? (padrão: blocos — fundamentação, pedidos, fechamento separados, para manter controle e precisão)

Quer ajustar alguma dessas regras?
```

### ETAPA 8 — Confirmação e Resumo

Ao final, o Claude deve gerar um resumo estruturado assim:

```
Perfeito! Aqui está o resumo da sua configuração:

══════════════════════════════════════
CONFIGURAÇÃO — PEÇAS JURÍDICAS HTML
══════════════════════════════════════

DADOS DO ESCRITÓRIO
• Advogado: [nome]
• OAB: [oab]
• Razão Social: [razão social]
• Sigla: [sigla]  |  Nome curto: [nome curto]
• OAB Sociedade: [oab sociedade ou "—"]

CONTATO
• Endereço: [endereço]
• Cidade-UF: [cidade-uf]
• E-mail: [email]
• Telefones: [tel1] · [tel2]

TIPOGRAFIA
• Títulos: [fonte títulos]
• Corpo: [fonte corpo]
• Tamanho corpo: [fs]  |  Citações: [fs-cita]
• Espaçamento: [line-height]  |  Recuo: [recuo]

CORES
• Texto: [ink]  |  Destaque: [gold]
• Secundário: [muted]  |  Divisórias: [rule]
• Faixa lateral: [largura]

CITAÇÕES
• Formato: [sanduíche / outro]
• Fonte do julgado: [abaixo / inline]
• Estilo: [itálico / aspas]

REDAÇÃO
• Pedidos: [a) b) c) / I, II, III / 1, 2, 3]
• Valores: [número + extenso / só número]
• Parágrafos: [máx linhas]
• Construção: [blocos / inteira]

══════════════════════════════════════

Está tudo certo? Se quiser ajustar algo, me diga qual etapa.

💡 Dica: copie o bloco acima e cole em Settings > Profile > User Preferences.
Assim o Claude já terá seus dados em qualquer conversa futura.
```

---

## Tabela de Placeholders

Após a configuração, o Claude substitui estes placeholders em cada geração:

| Placeholder | Dado | Padrão |
|---|---|---|
| `{{NOME_ADVOGADO}}` | Nome completo do advogado | — (obrigatório) |
| `{{OAB}}` | Número da OAB | — (obrigatório) |
| `{{RAZAO_SOCIAL}}` | Razão social do escritório | — (obrigatório) |
| `{{SIGLA}}` | Sigla do logo (2 letras) | — (obrigatório) |
| `{{NOME_ESCRITORIO_CURTO}}` | Nome curto para o logo | — (obrigatório) |
| `{{OAB_SOCIEDADE}}` | OAB da Sociedade | (em branco se não houver) |
| `{{ENDERECO_COMPLETO}}` | Endereço formatado | — (obrigatório) |
| `{{CIDADE_UF}}` | Cidade-UF para local/data | — (obrigatório) |
| `{{CIDADE}}` | Cidade (para o logo) | extraído de CIDADE_UF |
| `{{UF}}` | Estado por extenso (para o logo) | extraído de CIDADE_UF |
| `{{EMAIL}}` | E-mail de contato | — (obrigatório) |
| `{{TELEFONE_1}}` | Telefone fixo | (em branco se não houver) |
| `{{TELEFONE_2}}` | Telefone celular | — (obrigatório) |

### Variáveis CSS configuráveis

| Variável | Descrição | Padrão |
|---|---|---|
| `--ink` | Cor do texto principal | `#1A1714` |
| `--gold` | Cor de destaque / faixa lateral | `#B08A4E` |
| `--glt` | Cor de destaque clara | `#CFA96A` |
| `--muted` | Cor de texto secundário | `#6B5E4E` |
| `--rule` | Cor das linhas divisórias | `#DDD6C8` |
| `--cream-t` | Fundo sutil de destaque | `rgba(176,138,78,.05)` |
| `--fs` | Tamanho do corpo do texto | `15px` |
| `--fs-cita` | Tamanho das citações | `12.5px` |
| `--font-titulo` | Família tipográfica de títulos | `'Space Grotesk', sans-serif` |
| `--font-corpo` | Família tipográfica do corpo | `'DM Sans', sans-serif` |
| `--line-height` | Espaçamento entre linhas | `1.65` |
| `--recuo` | Recuo da primeira linha | `2cm` |
| `--faixa-width` | Largura da faixa lateral | `6px` |
| `--margin-left` | Margem esquerda do documento | `32mm` |
| `--margin-right` | Margem direita do documento | `20mm` |

---

## Estrutura do HTML

### `<head>` — sempre incluir

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;0,9..40,600;1,9..40,300;1,9..40,400&family=Space+Grotesk:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

### CSS — copiar integralmente

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  /* CORES — substituir conforme Etapa 5 do wizard */
  --ink:     #1A1714;
  --gold:    #B08A4E;
  --glt:     #CFA96A;
  --muted:   #6B5E4E;
  --rule:    #DDD6C8;
  --cream-t: rgba(176,138,78,.05);

  /* TIPOGRAFIA — substituir conforme Etapas 3 e 4 */
  --font-titulo: 'Space Grotesk', sans-serif;
  --font-corpo:  'DM Sans', sans-serif;
  --fs:      15px;       /* equivalente a 12pt Word */
  --fs-cita: 12.5px;    /* citações jurisprudenciais */
  --line-height: 1.65;
  --recuo:   2cm;

  /* LAYOUT — substituir conforme Etapa 4 */
  --faixa-width:  6px;
  --margin-left:  32mm;
  --margin-right: 20mm;
}

html, body {
  margin: 0; padding: 0;
  background: white;
  -webkit-print-color-adjust: exact;
  print-color-adjust: exact;
}

/*
 * @page: controla margens de TODAS as páginas impressas.
 * NUNCA definir height em nenhum contêiner — a altura é sempre dinâmica.
 * margin-left/right = 0 (controlados pelo .doc).
 */
@page {
  size: A4 portrait;
  margin-top:    25mm;
  margin-bottom: 22mm;
  margin-left:   0;
  margin-right:  0;
}

/*
 * .doc: único contêiner de layout. SEM height, SEM min-height, SEM max-height.
 * border-left = faixa lateral (cor via --gold, largura via --faixa-width).
 * padding-top: zerado no print; @page assume.
 */
.doc {
  font-family: var(--font-corpo);
  font-size: var(--fs);
  color: var(--ink);
  background: white;
  width: 210mm;
  margin: 0 auto;
  padding-top:    25mm;   /* tela apenas */
  padding-bottom: 0;
  padding-right:  var(--margin-right);
  padding-left:   var(--margin-left);
  border-left: var(--faixa-width) solid var(--gold);
  -webkit-print-color-adjust: exact;
  print-color-adjust: exact;
}

@media print {
  .doc { padding-top: 0; margin: 0; }
}

/* HEADER */
.hdr {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  padding-bottom: 12px;
  border-bottom: 2px solid var(--gold);
  margin-bottom: 26px;
  gap: 20px;
  page-break-after: avoid;
  break-after: avoid;
}

.hdr-right { text-align: right; }

.hdr-right .escritorio-nome {
  font-family: var(--font-titulo);
  font-size: 8.5px; font-weight: 700;
  letter-spacing: 2px; text-transform: uppercase;
  color: var(--muted); margin-bottom: 5px;
}

.hdr-right .contato { font-size: 9px; color: var(--ink); line-height: 1.7; }
.hdr-right .contato .sep   { color: var(--gold); margin: 0 4px; }
.hdr-right .contato .email { color: var(--muted); font-size: 8.5px; }

/* ENDEREÇAMENTO — sempre caixa alta */
.enderecamento {
  font-size: var(--fs);
  font-weight: 700;
  text-transform: uppercase;
  color: var(--ink);
  text-align: justify;
  line-height: var(--line-height);
  page-break-after: avoid;
  break-after: avoid;
}

/* ESPAÇADOR 3 linhas */
.gap3 {
  height: calc(var(--fs) * 1.65 * 2.2);
  page-break-inside: avoid;
  break-inside: avoid;
}

/* DADOS DO PROCESSO */
.dados-processo {
  font-size: var(--fs); color: var(--ink); line-height: var(--line-height);
  page-break-inside: avoid; break-inside: avoid;
  page-break-after: avoid; break-after: avoid;
}
.dados-processo span { display: block; }

/* PREÂMBULO */
.abertura {
  font-size: var(--fs); color: var(--ink);
  line-height: var(--line-height); text-align: justify; text-indent: var(--recuo);
  page-break-inside: avoid; break-inside: avoid;
  orphans: 3; widows: 3;
}

/* Nome do cliente e nome da ação: bold 14pt ≈ 18px */
.nome-cliente, .nome-acao { font-size: 18px; font-weight: 700; }

/* TÍTULO DE SEÇÃO — recuo 2cm em todas as linhas */
.sec-titulo {
  font-family: var(--font-titulo);
  font-size: var(--fs); font-weight: 700;
  text-transform: uppercase; color: var(--ink);
  line-height: 1.5; margin: 20px 0 8px var(--recuo);
  page-break-after: avoid; break-after: avoid;
  page-break-inside: avoid; break-inside: avoid;
}

/* PARÁGRAFO */
.par {
  font-size: var(--fs); color: var(--ink);
  line-height: var(--line-height); text-align: justify; text-indent: var(--recuo);
  margin-bottom: 20px; orphans: 3; widows: 3;
}

/* VALORES E DATAS — sempre negrito */
.val, .dt { font-weight: 700; }

/* CITAÇÃO JURISPRUDENCIAL */
.cita {
  font-size: var(--fs-cita); color: var(--ink);
  line-height: 1.6; text-align: justify; font-style: italic;
  margin: 12px 10px 0 var(--recuo);
  page-break-inside: avoid; break-inside: avoid;
}

.cita-fonte {
  font-size: var(--fs-cita); color: var(--muted);
  font-style: italic; margin: 3px 10px 12px var(--recuo);
  page-break-before: avoid; break-before: avoid;
}

/* INTRO PEDIDOS */
.pedido-intro {
  font-size: var(--fs); color: var(--ink);
  line-height: var(--line-height); text-align: justify; text-indent: var(--recuo);
  margin-bottom: 6px;
  page-break-after: avoid; break-after: avoid;
}

/* BLOCO DE ITENS (agrupa intro + itens — evita quebra entre eles) */
.bloco-itens { page-break-inside: avoid; break-inside: avoid; }

/* ITEM a) b) c) — letra sempre em negrito, recuo 2cm */
.item-lista {
  font-size: var(--fs); color: var(--ink);
  line-height: var(--line-height); text-align: justify;
  margin-left: var(--recuo); margin-bottom: 7px;
  page-break-inside: avoid; break-inside: avoid;
  orphans: 3; widows: 3;
}
.item-lista .letra { font-weight: 700; }

/*
 * CAIXA QUEBRÁVEL (box-break pattern)
 * Usar quando o conteúdo é longo e deve fluir entre páginas sem espaço vazio.
 * Princípio: a caixa quebra livremente entre páginas; cada item interno é
 * protegido individualmente de ser cortado ao meio.
 *
 * Estrutura obrigatória:
 *   .box-break           → container (sem page-break-inside)
 *   .box-break-titulo    → cabeçalho da caixa
 *   .box-break-item      → cada linha/entrada (tem page-break-inside: avoid)
 *
 * Divisor visual entre itens via border-top em .box-break-item;
 * primeiro item sem border-top via :first-of-type.
 */
.box-break {
  border: 1.5px solid var(--gold);
  border-radius: 4px;
  padding: 14px 16px;
  margin: 10px 0;
  background: var(--cream-t);
  /* SEM page-break-inside: avoid — quebra é permitida entre itens */
}
.box-break-titulo {
  font-family: var(--font-titulo);
  font-size: 10px; font-weight: 700;
  letter-spacing: 2px; text-transform: uppercase;
  color: var(--gold);
  display: block;
  margin-bottom: 10px;
}
.box-break-item {
  font-size: 13px; color: var(--ink);
  line-height: 1.6; text-align: justify;
  padding: 9px 0;
  border-top: 1px solid var(--rule);
  page-break-inside: avoid; break-inside: avoid;
}
.box-break-item:first-of-type { border-top: none; padding-top: 0; }
.box-break-item:last-child     { padding-bottom: 0; }
.box-break-label {
  font-weight: 700; color: var(--muted);
  font-family: var(--font-titulo);
  font-size: 10px; letter-spacing: 1px;
  text-transform: uppercase;
  display: block;
  margin-bottom: 3px;
}

/* TABELA — sem recuo (margin-left: 0), largura total */
.tabela-wrap {
  margin: 14px 0 4px 0; width: 100%;
  page-break-inside: avoid; break-inside: avoid;
}

.tabela-wrap table { width: 100%; border-collapse: collapse; font-size: 12px; }

.tabela-wrap thead { display: table-header-group; }
.tabela-wrap thead tr { background: var(--ink); color: white; }
.tabela-wrap thead th {
  font-family: var(--font-titulo);
  font-size: 8.5px; font-weight: 600;
  letter-spacing: 1.5px; text-transform: uppercase;
  padding: 7px 9px; text-align: left;
}
.tabela-wrap thead th.num { text-align: right; }

.tabela-wrap tbody tr {
  border-bottom: 1px solid var(--rule);
  page-break-inside: avoid; break-inside: avoid;
}
.tabela-wrap tbody tr:last-child { border-bottom: none; }
.tabela-wrap tbody tr:nth-child(even) { background: var(--cream-t); }
.tabela-wrap tbody td { padding: 6px 9px; color: var(--ink); vertical-align: middle; }
.tabela-wrap tbody td.num  { text-align: right; font-weight: 700; white-space: nowrap; }
.tabela-wrap tbody td.dt-cell { font-weight: 700; white-space: nowrap; }

.tabela-wrap tfoot { display: table-footer-group; }
.tabela-wrap tfoot tr {
  background: rgba(176,138,78,.08); border-top: 2px solid var(--gold);
  page-break-inside: avoid; break-inside: avoid;
}
.tabela-wrap tfoot td {
  padding: 7px 9px;
  font-family: var(--font-titulo);
  font-size: 11px; font-weight: 700; color: var(--ink);
}
.tabela-wrap tfoot td.num { text-align: right; color: var(--gold); font-size: 12px; white-space: nowrap; }

.tabela-nota {
  font-size: 10px; color: var(--muted); font-style: italic;
  margin: 4px 0 12px 0;
  page-break-before: avoid; break-before: avoid;
}

/* FECHAMENTO */
.fechamento { page-break-inside: avoid; break-inside: avoid; margin-top: 20px; }
.termos { font-size: var(--fs); color: var(--ink); line-height: var(--line-height); text-indent: var(--recuo); margin-bottom: 4px; }
.pede   { font-size: var(--fs); color: var(--ink); line-height: var(--line-height); text-indent: var(--recuo); margin-bottom: 30px; }

.local-data {
  font-size: var(--fs); color: var(--ink);
  text-align: left; text-indent: var(--recuo); margin-bottom: 40px;
}

.assinatura {
  font-family: var(--font-titulo);
  font-size: var(--fs); font-weight: 500;
  color: var(--ink); text-align: center; line-height: 1.7;
}
.assinatura .oab { font-size: 13px; font-weight: 400; color: var(--muted); }

/* RODAPÉ */
.doc-footer {
  margin-top: 32px; padding-top: 12px;
  border-top: 1px solid var(--rule);
  display: flex; justify-content: space-between; align-items: center;
  font-family: var(--font-titulo);
  font-size: 8px; color: var(--muted); letter-spacing: 1px;
  page-break-inside: avoid; break-inside: avoid;
}
.doc-footer .pgn { color: var(--gold); font-weight: 600; font-size: 9px; }
```

---

## Logo SVG (copiar integralmente — nunca alterar)

```html
<svg width="220" height="56" viewBox="0 0 340 88" xmlns="http://www.w3.org/2000/svg">
  <text x="0" y="56" font-family="'Space Grotesk',sans-serif" font-size="64" font-weight="700" fill="var(--ink,#1A1714)">{{SIGLA}}</text>
  <text x="82" y="28" font-family="'Space Grotesk',sans-serif" font-size="15" font-weight="700" fill="var(--ink,#1A1714)" letter-spacing="3">{{NOME_ESCRITORIO_CURTO}}</text>
  <text x="82" y="46" font-family="'Space Grotesk',sans-serif" font-size="10" font-weight="400" fill="#B08A4E" letter-spacing="5">ADVOCACIA</text>
  <rect x="82" y="52" width="250" height="1" fill="#DDD6C8"/>
  <text x="82" y="66" font-family="'DM Sans',sans-serif" font-size="8.5" font-weight="300" fill="#6B5E4E" letter-spacing="1">{{CIDADE}} · {{UF}} · {{OAB_SOCIEDADE}}</text>
</svg>
```

---

## Dados Fixos do Escritório (cabeçalho direito)

```html
<div class="hdr-right">
  <div class="escritorio-nome">{{RAZAO_SOCIAL}}</div>
  <div class="contato">
    {{ENDERECO_COMPLETO}}<br>
    <span class="email">{{EMAIL}}</span><span class="sep">|</span>{{TELEFONE_1}}<span class="sep">·</span>{{TELEFONE_2}}
  </div>
</div>
```

---

## Estrutura HTML da Peça

```html
<body>
<div class="doc">

  <!-- HEADER -->
  <div class="hdr">
    [Logo SVG]
    [Dados do escritório]
  </div>

  <!-- ENDEREÇAMENTO: caixa alta via CSS, justificado -->
  <div class="enderecamento">
    Excelentíssimo Senhor Doutor Juiz de Direito da [Vara] da [Comarca] — Estado do [UF]
  </div>

  <div class="gap3"></div>

  <!-- DADOS DO PROCESSO -->
  <div class="dados-processo">
    <span>Autos nº [número]</span>
    <span>[Polo Ativo]: [Nome]</span>
    <span>[Polo Passivo]: [Nome]</span>
  </div>

  <div class="gap3"></div>

  <!-- PREÂMBULO -->
  <p class="abertura">
    <span class="nome-cliente">NOME DO CLIENTE EM MAIÚSCULAS</span>,
    já qualificado(a) nos autos em epígrafe, por seu advogado infra-assinado,
    vem, respeitosamente, à presença de Vossa Excelência, [...] apresentar
    <span class="nome-acao">NOME DA PEÇA EM MAIÚSCULAS</span>
    em face de <strong>NOME DA PARTE CONTRÁRIA</strong>,
    pelas razões e fundamentos a seguir expostos.
  </p>

  <!-- SEÇÃO (repetir para cada tópico) -->
  <div class="sec-titulo">N. Título da Seção</div>

  <p class="par">Texto do parágrafo com recuo automático...</p>

  <!-- ITENS a) b) c) — sempre dentro de .bloco-itens -->
  <p class="pedido-intro">Ante o exposto, requer:</p>
  <div class="bloco-itens">
    <div class="item-lista"><span class="letra">a)</span> texto do item;</div>
    <div class="item-lista"><span class="letra">b)</span> texto do item; e</div>
    <div class="item-lista"><span class="letra">c)</span> texto do item.</div>
  </div>

  <!-- FECHAMENTO -->
  <div class="fechamento">
    <p class="termos">Termos em que,</p>
    <p class="pede">Pede deferimento.</p>
    <div class="local-data"><span class="dt">{{CIDADE_UF}}, DD de mês de AAAA.</span></div>
    <div class="assinatura">
      {{NOME_ADVOGADO}}<br>
      <span class="oab">{{OAB}}</span>
    </div>
  </div>

  <!-- RODAPÉ -->
  <div class="doc-footer">
    <span>Documento Confidencial</span>
    <span class="pgn">N / N</span>
  </div>

</div>
</body>
```

---

## Caixa Quebrável (box-break pattern)

Usar para listas estruturadas longas — fatos incontroversos, quadros comparativos, relação de documentos, pontos de análise — que precisam fluir entre páginas sem gerar espaço vazio.

**Regra central:** a caixa (`.box-break`) não tem `page-break-inside: avoid`; cada item interno (`.box-break-item`) tem. A quebra de página ocorre *entre* itens, nunca *dentro* de um item.

```html
<div class="box-break">
  <span class="box-break-titulo">Título da caixa — rótulo opcional</span>

  <div class="box-break-item">
    <span class="box-break-label">Rótulo 1</span>
    Texto descritivo do primeiro item, podendo ocupar múltiplas linhas
    sem risco de corte ao meio na quebra de página.
  </div>

  <div class="box-break-item">
    <span class="box-break-label">Rótulo 2</span>
    Texto do segundo item.
  </div>

  <div class="box-break-item">
    <span class="box-break-label">Rótulo 3</span>
    Texto do terceiro item.
  </div>
</div>
```

**Notas:**
- Sem recuo (`margin-left: 0`) — ocupa toda a largura disponível
- O primeiro `.box-break-item` não tem `border-top` (via `:first-of-type`)
- `.box-break-label` é opcional — omitir quando não houver rótulo por item
- Não usar `.box-break` para blocos curtos (≤ 3 itens pequenos) — nesses casos `.bloco-itens` com `page-break-inside: avoid` é suficiente

---

## Citação Jurisprudencial — técnica sanduíche

```html
<!-- 1. Tese em parágrafo normal -->
<p class="par">Sobre o tema, o Superior Tribunal de Justiça firmou entendimento no sentido de que...</p>

<!-- 2. Ementa — itálico, recuado, fonte menor -->
<div class="cita">EMENTA: [texto integral exatamente como fornecido pelo usuário]</div>

<!-- 3. Fonte do julgado -->
<div class="cita-fonte">(STJ, REsp nº 0.000.000/PR, Rel. Min. Fulano, j. 00/00/0000, DJe 00/00/0000)</div>

<!-- 4. Aplicação ao caso concreto -->
<p class="par">No caso vertente, a situação descrita se amolda ao entendimento consolidado...</p>
```

**ATENÇÃO:** Reproduzir a jurisprudência exatamente como fornecida. Nunca abreviar, suprimir ou inventar trechos.

---

## Tabelas

Usar quando houver múltiplos valores, datas de vencimento, contratos ou documentos a discriminar.

**Regras:**
- Sem recuo (`margin-left: 0`) — ocupam toda a largura disponível
- `thead` escuro, `tbody` com linhas alternadas, `tfoot` com totais em dourado
- Colunas numéricas: classe `.num` (alinhamento direita + negrito)
- Colunas de data: classe `.dt-cell` (negrito + `white-space: nowrap`)
- Nota de rodapé: classe `.tabela-nota` (sem recuo)

```html
<div class="tabela-wrap">
  <table>
    <thead>
      <tr>
        <th>Coluna 1</th>
        <th>Coluna 2</th>
        <th class="num">Valor</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Dado</td>
        <td class="dt-cell">jan/2024</td>
        <td class="num">R$ 1.000,00</td>
      </tr>
    </tbody>
    <tfoot>
      <tr>
        <td colspan="2">Total</td>
        <td class="num">R$ 1.000,00</td>
      </tr>
    </tfoot>
  </table>
</div>
<p class="tabela-nota">* Nota explicativa se necessário.</p>
```

---

## Regras de Marcação Semântica

| Elemento | Classe / Tag | Regra |
|---|---|---|
| Valores monetários | `<span class="val">` | Sempre negrito |
| Datas | `<span class="dt">` | Sempre negrito |
| Nome do cliente | `<span class="nome-cliente">` | Bold 18px, no preâmbulo |
| Nome da peça | `<span class="nome-acao">` | Bold 18px, no preâmbulo |
| Letra do item | `<span class="letra">` | Sempre negrito |
| Texto itálico (latim, citação) | `font-style: italic` via `.cita` | Só em blocos de citação |

---

## Regras de Redação

- Texto corrido em parágrafos — sem bullets ou listas no corpo
- Não mencionar nome do escritório no corpo da peça
- Valores: sempre número + extenso — `R$ 10.000,00 (dez mil reais)`
- Latim e estrangeirismos: itálico
- Trechos extraídos de decisões: itálico via `.cita`
- Jurisprudência: sanduíche — tese → `.cita` → `.cita-fonte` → aplicação
- Itens a) b) c): sempre dentro de `.bloco-itens`; letra em `.letra` (negrito)
- Endereçamento: sempre caixa alta (garantido via `text-transform: uppercase`)

### Disciplina de parágrafos (regra obrigatória)

Cada parágrafo `.par` deve ter no máximo 4 a 5 linhas impressas em A4. Esta é uma regra de qualidade — parágrafos longos prejudicam a leitura e o visual da peça.

**Como aplicar:**
- Ao redigir, contar mentalmente as linhas. Se um parágrafo ultrapassar 5 linhas, quebrá-lo em dois.
- Cada parágrafo deve conter uma unidade de raciocínio: premissa, desenvolvimento OU conclusão — nunca os três juntos.
- A quebra deve ser feita no ponto em que o raciocínio naturalmente respira, não no meio de um período.
- O `margin-bottom: 20px` já garante o espaço visual entre parágrafos — não usar `<br>` para criar espaçamento artificial.

**Exemplos de quebra correta:**

❌ Errado — parágrafo único com 7+ linhas:
```html
<p class="par">A sentença fixou honorários em 20% para a Recorrida e 10% para a Recorrente, desconsiderando o trabalho realizado. Com efeito, a petição inicial da Recorrida era padronizada e de baixa complexidade, ao passo que a defesa da Recorrente exigiu análise contábil aprofundada, elaboração de demonstrativos e confronto técnico com os extratos da administradora — trabalho que resultou no reconhecimento da obrigação de restituição de valores. Tal resultado afronta o art. 85, § 2º, do CPC.</p>
```

✅ Correto — mesma ideia em dois parágrafos respirados:
```html
<p class="par">A sentença fixou honorários em 20% para a Recorrida e apenas 10% para a Recorrente, desconsiderando inteiramente a diferença qualitativa entre os trabalhos realizados por cada patrono.</p>

<p class="par">A petição inicial da Recorrida era peça padronizada e de baixa complexidade. A defesa da Recorrente, em contraste, exigiu análise contábil aprofundada, elaboração de demonstrativos próprios e confronto técnico com os extratos da administradora — trabalho que resultou no reconhecimento judicial da obrigação de restituição de valores pela Recorrida.</p>
```

---

## Exportação para PDF

```
Ctrl+P → Salvar como PDF
Margens: Padrão
Gráficos de fundo: ATIVADO  ← obrigatório para faixa e fundos da tabela
Escala: 100%
```

---

## Verificação de Viabilidade (obrigatória antes de gerar)

Antes de executar:
1. Estimar volume: contar seções, parágrafos, jurisprudências, tabelas
2. Peças simples (até 5 seções, sem jurisprudência extensa): **viável**
3. Peças médias (5–12 seções, 1–3 jurisprudências): **viável com atenção**
4. Peças longas (12+ seções, múltiplas jurisprudências extensas): **alertar o usuário antes de gerar**
5. Se inviável sem supressões: informar e propor alternativa (geração em blocos, .docx via skill `pecas-juridicas`)

---

## Assinatura Padrão

```
{{CIDADE_UF}}, DD de mês por extenso de AAAA.
{{NOME_ADVOGADO}}
{{OAB}}
```

---

## Recurso de Apelação — Padrão do Escritório

O recurso de apelação é gerado em **um único arquivo HTML** contendo dois documentos separados por quebra de página: primeiro a Petição de Interposição, depois as Razões de Apelação.

### Regras absolutas

- Partes são sempre **Recorrente** e **Recorrido(a)** — NUNCA "Apelante" ou "Apelada".
- Email do cabeçalho: sempre em `<span class="email">` puro, **sem** `href` nem `mailto:` (Cloudflare obfusca links de e-mail).
- Os dois documentos ficam dentro do **mesmo `<div class="doc">`** — não criar dois `.doc` separados.

### CSS adicional obrigatório

Adicionar ao bloco `<style>` junto com o CSS padrão:

```css
.quebra-doc { page-break-after: always; break-after: page; height: 0; margin: 0; padding: 0; }
```

### Estrutura dos dois documentos

```
[HEADER — logo + dados escritório]
[ENDEREÇAMENTO → juízo a quo, caixa alta]
[GAP3]
[DADOS DO PROCESSO]
[GAP3]
[PREÂMBULO .abertura — qualificação + nome-acao "RECURSO DE APELAÇÃO"]
[parágrafos .par — tempestividade, preparo, remessa das razões, pedido de remessa ao tribunal]
[FECHAMENTO — "Aguarda deferimento." + data + assinatura]
[RODAPÉ .doc-footer]
[<div class="quebra-doc">]   ← quebra de página

[HEADER — logo + dados escritório]
[TÍTULO .enderecamento centralizado, font-size: var(--fs) → "RAZÕES DE RECURSO DE APELAÇÃO"]
[GAP3]
[ENDEREÇAMENTO centralizado → EGRÉGIO TRIBUNAL / COLENDA CÂMARA / EMÉRITOS JULGADORES]
[GAP3]
[PREÂMBULO .abertura — qualificação + nome-acao "RECURSO DE APELAÇÃO"]
[Razões (seções numeradas, parágrafos, citações)]
[PEDIDOS E REQUERIMENTOS FINAIS]
[FECHAMENTO — "Pede deferimento." + data + assinatura]
[RODAPÉ .doc-footer]
```

### Petição de Interposição — regras

- Endereçada ao **juízo a quo** (vara de origem), não ao tribunal.
- Identifica a decisão recorrida apenas por: número do evento/fl. e data. Sem dispositivo, sem teses.
- Trata exclusivamente de: tempestividade, preparo (ou sua dispensa), e remessa das razões.
- Fecha com **"Aguarda deferimento."** — nunca "Pede deferimento."
- Não contém nenhum argumento de mérito.

Modelo de preâmbulo da interposição:

```html
<p class="abertura">
  <span class="nome-cliente">NOME DO CLIENTE EM MAIÚSCULAS</span>,
  já qualificado(a) nos autos em epígrafe, por seu advogado infra-assinado,
  vem, respeitosamente, à presença de Vossa Excelência, com fundamento no
  artigo 1.009 do Código de Processo Civil, interpor o presente
  <span class="nome-acao">RECURSO DE APELAÇÃO</span>
  em face da sentença proferida em <span class="dt">DD de mês de AAAA</span>,
  constante do Evento N dos presentes autos, que [dispositivo mínimo].
</p>
```

### Razões de Apelação — regras de abertura

O bloco de abertura das razões segue esta sequência fixa, após o cabeçalho:

```html
<!-- TÍTULO DAS RAZÕES — mesmo tamanho da fonte padrão (var(--fs)), centralizado -->
<div class="enderecamento" style="text-align:center;">
  RAZÕES DE RECURSO DE APELAÇÃO
</div>

<div class="gap3"></div>

<!-- ENDEREÇAMENTO — centralizado, caixa alta via .enderecamento -->
<div class="enderecamento" style="text-align:center;">
  EGRÉGIO TRIBUNAL REGIONAL FEDERAL DA [N]ª REGIÃO<br>
  COLENDA CÂMARA DE JULGAMENTO<br>
  EMÉRITOS JULGADORES
</div>

<div class="gap3"></div>

<!-- PREÂMBULO — qualificação completa + nome da peça -->
<p class="abertura">
  <span class="nome-cliente">NOME DO CLIENTE</span>, já qualificado(a)
  nos autos em epígrafe, por seu advogado infra-assinado, vem,
  respeitosamente, à presença de Vossa Excelência, apresentar as presentes
  <span class="nome-acao">RAZÕES DE RECURSO DE APELAÇÃO</span>
  em face de <strong>NOME DA PARTE CONTRÁRIA</strong>,
  pelas razões e fundamentos a seguir expostos.
</p>
```

> **Importante:** o título "RAZÕES DE RECURSO DE APELAÇÃO" usa **`font-size: var(--fs)`** — a mesma fonte padrão da peça — apenas centralizado. Não aplicar `font-size` diferente.

### Fechamento diferenciado por documento

| Documento | Fecho |
|---|---|
| Petição de Interposição | `Aguarda deferimento.` |
| Razões de Apelação | `Pede deferimento.` |

### Exemplo de quebra de página entre os dois documentos

```html
  <!-- Final da Petição de Interposição -->
  <div class="doc-footer">...</div>

  <div class="quebra-doc"></div>

  <!-- Início das Razões — novo cabeçalho logo após -->
  <div class="hdr">...</div>
```
