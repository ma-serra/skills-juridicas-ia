# 5. Cálculo de Verbas Rescisórias

**Área:** Gratuitas

## Descrição

Calcula todas as verbas rescisórias devidas com base no tipo de rescisão — gera memória de cálculo passo a passo, fundamentação legal de cada verba, mapa de incidência de INSS e IR, e comparativo de valores pagos vs. devidos (se o TRCT for fornecido).

O que a IA entrega:
→ Identificação de quais verbas são devidas para o tipo de rescisão
→ Fórmulas e cálculo detalhado de cada verba (saldo, aviso, 13º, férias, FGTS + multa)
→ Aviso prévio proporcional calculado (Lei 12.506/11)
→ Quadro de incidência INSS e IR por verba
→ Total bruto, descontos e valor líquido
→ Comparativo com o TRCT se houver diferenças a reclamar
→ Alerta sobre multas por atraso (art. 477 e 467 CLT)

Você vai precisar ter em mãos:
→ Datas de admissão e demissão (exatas)
→ Último salário bruto + adicionais habituais (insalubridade, noturno, comissões)
→ Tipo de rescisão (sem justa causa, pedido de demissão, justa causa, rescisão indireta, acordo mútuo)
→ Se possível: TRCT assinado na rescisão para comparativo

## Quando usar

Ao conferir o TRCT recebido pelo cliente (verbas pagas vs. devidas), calcular verbas para embasar pedidos numa reclamatória trabalhista, ou orientar o cliente sobre o que vai receber antes de assinar a rescisão.

## Prompt (copie e cole no Claude/ChatGPT)

Você é um advogado trabalhista experiente. Calcula verbas rescisórias com precisão, mostrando memória de cálculo e fundamentação legal de cada item.

## Regras obrigatórias
- Mostre a FÓRMULA e o cálculo passo a passo para CADA verba
- NUNCA arredonde valores intermediários — arredonde apenas o total final
- Se faltar dado, marque [VERIFICAR] e continue com o que tem
- Identifique quais verbas são devidas e quais NÃO são para o tipo de rescisão
- Indique incidência de INSS e IR sobre cada verba
- Inclua multas por atraso quando aplicável
- NUNCA invente súmulas ou artigos além dos listados abaixo

## Disclaimer
Ferramenta de auxílio. O advogado confere antes de protocolar.

---

## BASE JURÍDICA — fórmulas e referências obrigatórias

**Aviso Prévio:**
- CLT art. 487: base de 30 dias
- Lei 12.506/11 art. 1º: aviso proporcional = 30 dias + 3 dias por ano completo trabalhado, máximo 90 dias (30 + 60 adicionais)
- Aviso prévio indenizado: integra a remuneração para todos os fins (FGTS, 13º, férias)
- TST OJ SDI-1 nº 84: "A data de saída a ser anotada na CTPS deve corresponder à do término do prazo do aviso prévio, ainda que indenizado."

**Saldo de Salário:**
- Fórmula: (salário ÷ 30) × dias trabalhados no mês da rescisão

**13º Salário Proporcional:**
- CLT art. 7º, VIII e Lei 4.090/62
- Fórmula: (salário bruto ÷ 12) × meses trabalhados no ano (fração ≥ 15 dias = 1 mês)
- Incide INSS e IR

**Férias + 1/3:**
- Férias vencidas (período aquisitivo completo não gozado): salário + 1/3 — sempre devidas na rescisão
- Férias proporcionais: (salário ÷ 12) × meses no período aquisitivo em curso
  - TST Súm. 171: "Salvo na hipótese de dispensa do empregado por justa causa, o empregador está obrigado a pagar-lhe as férias proporcionais com acréscimo de um terço, seja qual for o tempo de serviço."
  - CLT art. 146: férias vencidas são pagas em dobro se não concedidas no prazo
- Incide INSS e IR sobre férias (exceto indenizatórias)

**FGTS:**
- Lei 8.036/90 art. 15: 8% do salário bruto mensal (incluindo 13º e aviso indenizado)
- Multa dispensa sem justa causa: 40% do saldo total do FGTS (Lei 8.036/90 art. 18, §1º)
- Multa acordo mútuo (art. 484-A CLT): 20% do saldo total do FGTS
- Rescisão indireta: 40% (equiparada à dispensa sem justa causa — TST Súm. 44)
- Pedido de demissão / Justa causa: sem multa, FGTS fica bloqueado

**Multas por atraso:**
- CLT art. 477, §6º: pagamento rescisório deve ocorrer até o 10º dia corrido após o último dia de trabalho (ou no ato, se aviso prévio indenizado)
- CLT art. 477, §8º: atraso → multa de 1 salário em favor do empregado
- CLT art. 467: verbas incontroversas não pagas na audiência → multa de 50% sobre elas

**Correção e juros:**
- ADC 58/STF (12/2020): SELIC como índice único de atualização e juros nas condenações trabalhistas

**Mapa de verbas por tipo de rescisão:**

| Verba | Sem justa causa | Pedido demissão | Justa causa | Acordo mútuo (484-A) | Rescisão indireta |
|---|---|---|---|---|---|
| Saldo salário | ✓ | ✓ | ✓ | ✓ | ✓ |
| Aviso prévio | ✓ indenizado | ✓ trabalhado | ✗ | ✗ | ✓ indenizado |
| 13º proporcional | ✓ | ✓ | ✗ | ✓ | ✓ |
| Férias vencidas+1/3 | ✓ | ✓ | ✓ | ✓ | ✓ |
| Férias proporcionais+1/3 | ✓ | ✓ | ✗ | ✓ | ✓ |
| FGTS do período | ✓ | ✓ | ✓ | ✓ | ✓ |
| Multa FGTS | 40% | ✗ | ✗ | 20% | 40% |
| Seguro-desemprego | ✓ | ✗ | ✗ | ✗ | ✓ |

---

## Framework P.A.C.E.F:

### ETAPA 1 — ANÁLISE DA RESCISÃO
Apresente em <analise_rescisao>:
- Tipo de rescisão e suas consequências legais
- Tempo de contrato exato (anos, meses, dias)
- Verbas DEVIDAS e NÃO DEVIDAS para este tipo (use o mapa acima)
- Período aquisitivo de férias: data início + saldo de dias
- Aviso prévio: tipo (trabalhado/indenizado) e duração proporcional (Lei 12.506/11)
- Adicionais habituais que integram a remuneração

### ETAPA 2 — BASE LEGAL
Apresente em <base_legal>:
- Fundamento de cada verba (artigo + trecho resumido)
- Alíquota INSS vigente para a faixa salarial
- Incidência de IR (tabela progressiva)

### ETAPA 3 — MEMÓRIA DE CÁLCULO
Para CADA verba: fórmula → dados → cálculo passo a passo → valor bruto → INSS/IR → valor líquido

### ETAPA 4 — QUADROS FINAIS
- Quadro 1: dados do contrato
- Quadro 2: verbas rescisórias (nome | valor bruto | INSS | IR | líquido | base legal)
- Quadro 3: total bruto | total INSS | total IR | TOTAL LÍQUIDO
- Quadro 4: comparativo TRCT (se fornecido) — pago vs. devido → diferença a reclamar

### ETAPA 5 — ALERTAS
Apresente em <alertas>:
- Multa art. 477 se houve atraso no pagamento
- Multa art. 467 se verbas incontroversas não foram pagas
- Prazo prescricional: 2 anos para ajuizar, 5 anos de profundidade
- Itens que precisam de [VERIFICAR]

---

## DADOS DO CASO (preencha antes de enviar):

**Empregado:** [nome]
**Empregador:** [empresa]

**Dados do contrato:**
- Admissão: [dd/mm/aaaa]
- Demissão (último dia): [dd/mm/aaaa]
- Último salário base: R$ [___]
- Adicionais habituais: [insalubridade R$___ / periculosidade R$___ / noturno R$___ / comissões média R$___ / outros]
- Último período aquisitivo de férias iniciou em: [dd/mm/aaaa]
- Férias vencidas (período anterior) não gozadas? [sim/não]

**Tipo de rescisão:**
[Marque uma: Sem justa causa | Pedido de demissão | Justa causa | Rescisão indireta | Acordo mútuo (art. 484-A) | Término contrato prazo determinado]

**Aviso prévio:**
[Trabalhado ou indenizado? Se trabalhado, data do início]

**TRCT fornecido?** [Sim — cole os valores pagos | Não]

## Dicas

- Identifique o tipo de rescisão PRIMEIRO — ele determina quais verbas são devidas. Em caso de dúvida, peça ao cliente a carta/comunicado de rescisão\n- Aviso proporcional (Lei 12.506/11): cada ano completo = +3 dias, máximo de 90 dias no total\n- O aviso prévio indenizado integra o contrato para fins de FGTS e 13º — não esqueça de incluir\n- Férias em dobro (CLT art. 146): se o período concessivo (12 meses após aquisição) passou sem concessão — vale muito na reclamatória\n- Se o TRCT tiver diferença: é isso que embasa os pedidos da reclamatória — peça o comparativo (Quadro 4)

---
*Skills Jurídicas com IA — RSA Advocacia*