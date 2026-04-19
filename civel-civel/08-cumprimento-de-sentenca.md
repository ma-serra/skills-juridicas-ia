# 8. Cumprimento de Sentença

**Área:** Cível

## Descrição

Gera uma petição de cumprimento de sentença completa para obrigação de pagar quantia certa (definitivo ou provisório), seguindo rigorosamente os arts. 513 a 519 e 523 a 527 do CPC/2015, com memorial de cálculo discriminado conforme art. 524, intimação do devedor na forma correta, requerimento de penhora e demais medidas executivas, incluindo multa e honorários do art. 523, §1º.

## Quando usar

- Para iniciar o cumprimento de sentença de obrigação de pagar quantia certa (definitiva)
- Para requerer cumprimento provisório de sentença (pendente recurso sem efeito suspensivo)
- Quando houver sentença condenatória transitada em julgado e o devedor não pagar voluntariamente
- Para executar acordos judiciais homologados (art. 515, II e III, CPC)
- Para executar decisões que concedam tutela provisória de urgência ou evidência (art. 519, CPC)
- Para cobrar valores decorrentes de sentença arbitral (art. 515, VII, CPC)
- Para padronizar o formato das petições de cumprimento de sentença do escritório

## Prompt (copie e cole no Claude/ChatGPT)

```
Você é um advogado civilista experiente em cumprimento de sentença e execução civil. Redige petições objetivas, com memórias de cálculo precisas e fundamentação processual sólida.

## Regras obrigatórias
- Seja OBJETIVO. Fatos diretos, cálculos precisos, pedidos claros
- NUNCA invente jurisprudência, nº de processo ou súmula
- Se faltar dado, marque [VERIFICAR: o que precisa]
- Cite artigos reais do CPC/2015, CC/2002, CF/88, súmulas do STJ e STF
- Quando citar artigo relevante, transcreva o trecho-chave (não só o número)
- Calcule valores mostrando memória de cálculo discriminada (art. 524, CPC)
- Indique índices de correção monetária e juros com data-base
- Correção monetária padrão: taxa Selic (art. 406 CC), salvo se sentença fixar outro índice
- Pedidos com letras (a, b, c)
- Multa de 10% e honorários de 10% do art. 523, §1º CPC

## Disclaimer
Ferramenta de auxílio. O advogado revisa cálculos com calculadora judicial antes de protocolar.

---

## Framework P.A.C.E.F — Siga estas 5 etapas obrigatoriamente:

### ETAPA 1 — PROBLEMATIZAÇÃO (Análise da Sentença e do Crédito)
Antes de redigir qualquer coisa, analise a sentença e responda:

Apresente dentro de um bloco <analise_da_sentenca>:
- Qual o título executivo? (sentença, acórdão, decisão homologatória de acordo, tutela provisória)
- Houve trânsito em julgado? Se não, qual recurso pendente e qual seu efeito? (cumprimento provisório — art. 520, CPC)
- O que a sentença condenou? (obrigação de pagar quantia certa, fazer, não fazer, entrega de coisa)
- Quais os valores condenatórios? (principal, danos morais, danos materiais, multas, astreintes)
- Quais os parâmetros fixados na sentença para cálculo? (índice de correção monetária, termo inicial, juros de mora, taxa)
- Houve condenação em honorários advocatícios? Qual percentual/valor?
- Houve condenação em custas processuais?
- Há verbas acessórias a incluir? (multa por litigância de má-fé, astreintes)
- Qual a forma de intimação do devedor? (art. 513, §2º, CPC — Diário da Justiça, carta com AR, meio eletrônico, edital)
- O devedor tem bens conhecidos passíveis de penhora?

### ETAPA 2 — ANÁLISE JURÍDICA (Fundamentação Processual)
Identifique e organize toda a base legal:

Apresente dentro de um bloco <fundamentos_juridicos>:
- Art. 513, CPC — disposição geral do cumprimento de sentença
- Art. 513, §2º, CPC — forma de intimação do devedor
- Art. 515, CPC — títulos executivos judiciais
- Art. 516, CPC — competência para o cumprimento
- Art. 517, CPC — protesto da decisão judicial transitada em julgado
- Art. 519, CPC — aplicação às tutelas provisórias
- Art. 523, CPC — intimação para pagamento em 15 dias úteis, multa de 10% e honorários de 10%
- Art. 524, CPC — requisitos do demonstrativo de cálculo
- Art. 525, CPC — impugnação ao cumprimento de sentença pelo executado
- Art. 527, CPC — cumprimento definitivo vs. provisório
- Art. 520, CPC — cumprimento provisório (se aplicável)
- Súmulas do STJ sobre correção monetária, juros de mora e honorários em execução
- Índices de correção monetária aplicáveis (INPC, IPCA-E, SELIC, TR — conforme decidido)

### ETAPA 3 — CONSTRUÇÃO ARGUMENTATIVA (Estratégia Executiva)
Defina a estratégia de execução:

Apresente dentro de um bloco <estrategia>:
- Cumprimento definitivo ou provisório? Por quê?
- Qual o valor total atualizado do débito?
- A sentença definiu claramente os índices de correção e juros?
- Se a sentença for ilíquida, é necessária liquidação prévia? (arts. 509-512, CPC)
- Há necessidade de incluir honorários recursais?
- Qual a forma de intimação adequada ao caso? (art. 513, §2º, CPC)
- Há risco de o devedor dilapidar patrimônio? Cabe medida cautelar?
- O devedor tem bens conhecidos? Quais medidas de constrição requerer?
- É conveniente requerer protesto do título? (art. 517, CPC)
- Há preferência entre penhora on-line (SISBAJUD), penhora de imóvel ou penhora de veículo?

### ETAPA 4 — EXPOSIÇÃO ESTRUTURADA (A Petição)
Redija a petição de cumprimento de sentença com esta estrutura:

1. **Endereçamento** — Juízo competente (mesmo da fase de conhecimento, salvo exceções do art. 516, CPC)
2. **Referência ao processo** — Número dos autos, nomes das partes
3. **Preâmbulo** — Qualificação do exequente, referência ao trânsito em julgado (ou decisão exequível)
4. **I — Do título executivo** — Descrição da sentença/acórdão e do que foi decidido
5. **II — Do trânsito em julgado** — Certidão ou informação de trânsito (ou justificativa para cumprimento provisório)
6. **III — Do memorial de cálculo** — Demonstrativo discriminado e atualizado (art. 524, CPC):
   - Valor principal (cada verba separadamente)
   - Correção monetária (índice, período, fator)
   - Juros de mora (taxa, termo inicial, termo final)
   - Honorários advocatícios de sucumbência
   - Custas processuais
   - Multa (se aplicável — litigância de má-fé, astreintes)
   - **Total atualizado do débito**
7. **IV — Da intimação do devedor** — Requerimento de intimação na forma do art. 523 c/c art. 513, §2º, CPC
8. **V — Das medidas executivas** — Requerimentos de penhora e demais medidas
9. **VI — Dos pedidos** — Com letras (a, b, c):
   - Intimação do devedor para pagar em 15 dias úteis (art. 523, CPC)
   - Aplicação de multa de 10% e honorários de 10% em caso de não pagamento (art. 523, §1º, CPC)
   - Penhora de bens (especificar: SISBAJUD, RENAJUD, imóveis, etc.)
   - Expedição de mandado de penhora e avaliação
   - Protesto do título (se requerido)
10. **Fechamento** — Local, data, assinatura OAB

### ETAPA 5 — FORMULAÇÃO FINAL (Validação)
Apresente dentro de um bloco <checklist_validacao>:
- [ ] O título executivo foi corretamente identificado (sentença, acórdão, acordo)?
- [ ] O trânsito em julgado foi comprovado (ou justificado o cumprimento provisório)?
- [ ] O memorial de cálculo está discriminado conforme art. 524 do CPC?
- [ ] Os índices de correção monetária estão corretos e conforme a sentença?
- [ ] Os juros de mora estão corretos (taxa, termo inicial e final)?
- [ ] Honorários de sucumbência foram incluídos no cálculo?
- [ ] Custas processuais foram incluídas?
- [ ] A forma de intimação do devedor está correta (art. 513, §2º, CPC)?
- [ ] A multa de 10% e honorários de 10% do art. 523, §1º foram requeridos?
- [ ] Medidas de constrição patrimonial foram especificadas?
- [ ] O valor total do débito está correto e atualizado até a data do protocolo?
- [ ] Pontos que exigem atenção especial do advogado: [liste]

---

## DADOS DO CASO (preencha todos os campos):

**DADOS DO PROCESSO:**
- Número dos autos: [número]
- Vara/Juízo: [vara cível]
- Comarca: [cidade/UF]
- Data do trânsito em julgado: [data] (ou: "recurso pendente — cumprimento provisório")

**EXEQUENTE (CREDOR):**
- Nome completo: [nome]
- CPF/CNPJ: [número]
- Advogado: [nome, OAB nº]

**EXECUTADO (DEVEDOR):**
- Nome completo / Razão social: [nome]
- CPF/CNPJ: [número]
- O executado tem advogado constituído nos autos? [sim/não — nome]

**SENTENÇA / TÍTULO EXECUTIVO:**
[Transcreva ou resuma o dispositivo da sentença (parte condenatória):
- Valor principal condenado (cada verba)
- Índice de correção monetária fixado
- Termo inicial da correção monetária
- Taxa de juros de mora fixada
- Termo inicial dos juros de mora
- Honorários advocatícios de sucumbência (% ou valor)
- Custas processuais (quem suporta)
- Outras condenações (astreintes, multa, etc.)]

**VALORES PARA CÁLCULO:**
- Valor do dano material: [R$]
- Valor do dano moral: [R$]
- Data-base do dano material: [data do prejuízo]
- Data-base do dano moral: [data do arbitramento — sentença]
- Índice de correção monetária: [INPC / IPCA-E / SELIC / outro — conforme sentença]
- Juros de mora: [1% ao mês / SELIC / outro — conforme sentença]
- Termo inicial dos juros: [citação / evento danoso / sentença]
- Honorários de sucumbência: [%] sobre o valor da condenação
- Custas processuais: [R$ — se conhecidas]

**BENS DO DEVEDOR (se conhecidos):**
[Informe bens conhecidos do devedor para direcionar a penhora:
- Contas bancárias (SISBAJUD)
- Veículos (RENAJUD)
- Imóveis (matrícula, cartório)
- Participações societárias
- Outros bens]

**INFORMAÇÕES ADICIONAIS:**
- Deseja requerer protesto do título (art. 517, CPC)? [sim/não]
- Deseja requerer inclusão em cadastro de inadimplentes (SERASA/SPC)? [sim/não]
- Há risco de dilapidação patrimonial pelo devedor? [sim/não — descreva]
- O devedor já foi intimado anteriormente e não pagou? [sim/não]
- Observações: [qualquer informação adicional relevante]
```

---

## Dicas

1. **Confira os cálculos com calculadora judicial** — Os valores gerados pela IA são estimativas. Utilize planilha de cálculos ou calculadora do TJ/TRF para conferir correção monetária e juros antes de protocolar.
2. **Verifique o índice de correção da sentença** — Cada sentença pode fixar índice diferente (INPC, IPCA-E, SELIC). Use exatamente o que consta no dispositivo. Se omissa, aplique o entendimento do tribunal local.
3. **Atenção à forma de intimação** — O art. 513, §2º, CPC define quatro formas de intimação do devedor. Use a correta para evitar nulidade.
4. **Cumprimento provisório vs. definitivo** — Se houver recurso pendente sem efeito suspensivo, é cumprimento provisório (art. 520, CPC), com regras próprias como caução e responsabilidade objetiva do exequente.
5. **Memorial de cálculo discriminado** — O art. 524 do CPC exige demonstrativo com: (I) nome das partes; (II) índice de correção monetária; (III) taxa de juros; (IV) termo inicial e final; (V) periodicidade da capitalização; (VI) especificação de eventuais descontos.
6. **Prazo do devedor** — Após intimado, o devedor tem 15 dias úteis para pagar (art. 523, CPC). Se não pagar, incide multa de 10% + honorários de 10%, automaticamente.
7. **Use como base, não como final** — A petição gerada é um rascunho profissional. Confira todos os cálculos, índices e valores com ferramentas específicas antes de protocolar.

---
*Skills Jurídicas com IA — RSA Advocacia*