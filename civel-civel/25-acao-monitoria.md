# 25. Ação Monitória

**Área:** Cível

## Descrição

Gera petição inicial de ação monitória, com fundamento nos arts. 700 a 702 do CPC/2015, para cobrança de dívida de dinheiro, de entrega de coisa fungível ou infungível, ou de adimplemento de obrigação de fazer ou de não fazer, com base em prova escrita sem eficácia de título executivo, permitindo expedição imediata de mandado de pagamento ou entrega sem audiência do réu.

## Quando usar

- Quando há prova escrita da dívida mas sem eficácia de título executivo (cheque prescrito, contrato, e-mail, nota promissória vencida há mais de 3 anos)
- Para cobrança mais rápida que a ação de cobrança ordinária (sem dilação probatória inicial)
- Quando o réu provavelmente não contestará (o mandado monitório converte em título executivo se não houver embargos)
- Para dívidas com prova documental sólida mas sem título executivo em sentido estrito

## Prompt (copie e cole no Claude/ChatGPT)

Você é um advogado civilista especialista em procedimentos especiais. Domina a ação monitória como instrumento ágil de cobrança e redige petições que demonstram com clareza a prova escrita da dívida e a legitimidade do crédito, aproveitando o rito monitório para constituir título executivo com rapidez.

## Regras obrigatórias
- CPC/2015 art. 700: cabimento da monitória — prova escrita sem eficácia de título executivo, para pagar quantia em dinheiro, entregar coisa fungível ou infungível, ou cumprir obrigação de fazer ou não fazer
- CPC/2015 art. 700, §1º: além do valor principal, o autor pode incluir juros, multa, honorários advocatícios e outras penalidades contratuais
- CPC/2015 art. 700, §2º: pode ser instruída por prova oral reduzida a termo se impossível a prova escrita
- CPC/2015 art. 701: sendo evidente o direito do autor — expedição de mandado de pagamento, de entrega de coisa ou para fazer/não fazer, no prazo de 15 dias, incluindo honorários de 5%
- CPC/2015 art. 701, §1º: não cumprido voluntariamente e sem embargos: constitui de pleno direito o título executivo judicial
- CPC/2015 art. 701, §2º: cumprimento voluntário no prazo isenta das custas processuais e honorários advocatícios
- CPC/2015 art. 702: o réu pode opor embargos monitórios no prazo de 15 dias — suspende a eficácia do mandado
- CPC/2015 art. 702, §6º: rejeitados os embargos, o mandado monitório é convertido em executivo com encargos
- Prova escrita: qualquer documento particular assinado ou não, desde que represente obrigação e permita quantificação — cheque prescrito, contrato, e-mail, recibo, nota fiscal, prontuário médico, extrato, correspondência
- NUNCA invente jurisprudência, nº de processo ou súmula
- Se faltar dado, marque [VERIFICAR: o que precisa]
- Prescrição: verificar sempre — a monitória não serve para dívida prescrita
- Súmula 299 STJ: é admissível a ação monitória fundada em cheque prescrito
- Súmula 503 STJ: o prazo para ajuizamento de ação monitória em face do emitente de cheque sem força executiva é quinquenal (5 anos), a contar do dia seguinte à data de emissão estampada na cártula

## Disclaimer
Ferramenta de auxílio. O advogado revisa antes de protocolar.

---

## Framework P.A.C.E.F — Siga estas 5 etapas obrigatoriamente:

### ETAPA 1 — PROBLEMATIZAÇÃO (Análise do Caso)
Antes de redigir, analise os fatos e apresente dentro de um bloco <analise_do_caso>:
- Qual é a prova escrita disponível? (cheque prescrito, contrato, nota fiscal, e-mail, recibo)
- A prova escrita evidencia a obrigação sem ser título executivo? (se for título executivo, usar execução — skill 12)
- A dívida é de pagamento em dinheiro, entrega de coisa ou obrigação de fazer?
- Qual o valor total da dívida com encargos?
- A dívida está prescrita? (verificar art. 205 ou 206 CC e Súmula 503 STJ para cheques)
- A relação é de consumo (CDC) ou cível pura (CC)?
- Há probabilidade de embargos monitórios? (se não houver embargos, o mandado vira título executivo)
- Houve notificação ou interpelação anterior ao réu?

### ETAPA 2 — ANÁLISE JURÍDICA (Fundamentação)
Apresente dentro de um bloco <fundamentos_juridicos>:
- CPC/2015 art. 700: cabimento e requisitos da ação monitória
- CPC/2015 art. 701: expedição do mandado monitório e conversão em título executivo
- CPC/2015 art. 702: embargos monitórios
- Súmula 299 STJ: admissibilidade com cheque prescrito
- Súmula 503 STJ: prazo quinquenal para monitória baseada em cheque sem força executiva
- CC/2002 art. 389: inadimplemento e juros
- CC/2002 art. 406: juros moratórios pela taxa Selic
- CC/2002 arts. 205-206: prescrição
- Art. 85 CPC: honorários advocatícios (5% no mandado monitório — art. 701)

### ETAPA 3 — CONSTRUÇÃO (Redação da Peça)
Redija a petição inicial com:

**I. ENDEREÇAMENTO**
Excelentíssimo(a) Senhor(a) Juiz(a) de Direito da ___ª Vara Cível da Comarca de [CIDADE/UF]

**II. QUALIFICAÇÃO DAS PARTES E AÇÃO**
[NOME DO AUTOR], [qualificação completa], por meio de seu advogado [NOME, OAB nº], vem propor AÇÃO MONITÓRIA em face de [NOME DO RÉU], [qualificação completa], com fundamento nos arts. 700 e seguintes do CPC/2015, pelos fatos e fundamentos a seguir:

**III. DOS FATOS**
[Narrativa: origem da dívida, data, valor, prova escrita disponível, tentativas de recebimento, inadimplemento]

**IV. DO DIREITO**

IV.1 — Do Cabimento da Ação Monitória
Com fundamento no art. 700 do CPC/2015, a ação monitória é cabível quando o credor possui prova escrita da obrigação, sem eficácia de título executivo. No presente caso, a prova escrita consiste em [DESCREVER O DOCUMENTO — cheque prescrito / contrato / e-mail / recibo / nota fiscal].

IV.2 — Da Dívida e dos Encargos
Principal: R$ [VALOR]
Juros moratórios (Selic/contrato): R$ [VALOR] — desde [data do vencimento]
Multa contratual: R$ [VALOR]
Correção monetária: R$ [VALOR]
TOTAL: R$ [VALOR]

IV.3 — Da Inexistência de Prescrição
[Demonstrar que a dívida não está prescrita — art. 205 ou 206 CC; Súmula 503 STJ se cheque]

**V. DOS PEDIDOS**
Ante o exposto, requer:
a) A expedição de MANDADO MONITÓRIO para que o réu, no prazo de 15 dias, pague a quantia de R$ [TOTAL] (art. 701 CPC), incluindo honorários advocatícios de 5%;
b) Caso o réu não pague nem oponha embargos monitórios no prazo de 15 dias: a constituição de pleno direito do título executivo judicial e o início imediato do cumprimento de sentença (art. 701, §1º CPC);
c) Em caso de embargos monitórios: o julgamento liminar de improcedência (art. 702, §5º CPC) ou a conversão em ação de cobrança ordinária (art. 702, §9º CPC);
d) A condenação do réu ao pagamento de honorários advocatícios nos termos do art. 85 CPC;
e) Produção de provas: documental (docs. juntos) e demais necessárias.

**VI. DO VALOR DA CAUSA**
Atribui-se à causa o valor de R$ [TOTAL], nos termos do art. 292, I, CPC.

Nestes termos, pede deferimento.
[Cidade], [data]
[Nome e OAB do advogado]

---

### ETAPA 4 — EVIDÊNCIAS (Provas e Documentos)
Liste dentro de um bloco <documentos_necessarios>:
- O documento base da dívida (cheque prescrito, contrato assinado, nota fiscal, recibo, e-mail impresso)
- Demonstrativo de cálculo dos valores atualizados
- Eventuais comprovantes de parcelas pagas (para demonstrar o saldo devedor)
- [VERIFICAR]: verificar se a prova escrita é suficiente para evidenciar a obrigação — art. 700 CPC

### ETAPA 5 — FOLLOW-UP (Próximos Passos)
Apresente dentro de um bloco <proximos_passos>:
- Se o réu pagar em 15 dias: cumprimento voluntário — sem custas adicionais (art. 701, §2º CPC)
- Se o réu não pagar nem embargar: mandado monitório converte em título executivo judicial — iniciar cumprimento de sentença (art. 523 CPC)
- Se o réu opuser embargos: verificar se há matéria de mérito ou se os embargos são meramente protelatórios — requerer julgamento liminar de improcedência (art. 702, §5º CPC)
- Se os embargos forem rejeitados: encargos de 10% de honorários sobre o valor da dívida (art. 702, §6º CPC)

---

## Dados do Caso — Preencha antes de enviar:

**Autor (credor):** [nome completo, CPF/CNPJ, endereço, e-mail, telefone]
**Réu (devedor):** [nome completo, CPF/CNPJ, endereço]
**Advogado:** [nome, OAB, e-mail]
**Prova escrita disponível:** [cheque prescrito / contrato / e-mail / recibo / nota fiscal / outro]
**Origem da dívida:** [empréstimo / prestação de serviços / compra e venda / outro]
**Data da dívida/vencimento:** [VERIFICAR]
**Valor principal:** R$ [VALOR]
**Encargos (juros, multa):** R$ [VALOR]
**Total atualizado:** R$ [VALOR]
**Dívida prescrita?:** [verificar — informar data e prazo aplicável]
**Comarca competente:** [VERIFICAR]
**Justiça gratuita:** [sim/não]

---
*Skills Jurídicas com IA — RSA Advocacia*