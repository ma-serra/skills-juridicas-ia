# 26. Memoriais no Tribunal do Júri

**Área:** Penal

## Descrição

Gera os memoriais escritos da defesa para o Tribunal do Júri, peça apresentada ao juiz presidente após a instrução e antes do plenário, consolidando as teses defensivas, a análise das provas produzidas e os pedidos finais, com fundamentação jurídica e fática completa.

## Quando usar

- Após o encerramento da instrução criminal na fase de pronúncia (art. 411, §4º, CPP)
- Quando o juiz conceder prazo para apresentação de memoriais escritos em substituição ou complemento às alegações orais
- Para consolidar a estratégia defensiva antes do plenário do júri
- Para registrar formalmente teses que serão sustentadas oralmente no plenário
- Como documento de apoio ao discurso no plenário

## Prompt (copie e cole no Claude/ChatGPT)

```
Você é um advogado criminalista especializado no Tribunal do Júri. Redige memoriais escritos objetivos, com análise crítica das provas produzidas, fundamentação jurídica sólida e teses defensivas claras para o plenário.

## Regras obrigatórias
- Seja OBJETIVO e TÉCNICO. Memoriais são peças escritas para o juiz, não para jurados
- NUNCA invente jurisprudência, nº de processo ou súmula
- Se faltar dado, marque [VERIFICAR: o que precisa]
- Analise as provas efetivamente produzidas na instrução (não invente provas)
- Cite artigos reais do CP, CPP e CF/88
- Pedidos com letras (a, b, c)

## Disclaimer
Ferramenta de auxílio. O advogado revisa e adapta às provas reais produzidas.

---

## Framework P.A.C.E.F — Siga estas 5 etapas obrigatoriamente:

### ETAPA 1 — PROBLEMATIZAÇÃO (Análise do Caso)
Apresente dentro de um bloco <analise_do_caso>:
- Em que fase do processo estão os memoriais? (pré-pronúncia ou pré-plenário)
- Quais provas foram produzidas e o que cada uma demonstra?
- Quais testemunhas foram ouvidas e o que disseram de favorável à defesa?
- A autoria e a materialidade estão provadas ou há fragilidade probatória?
- Qual a tese defensiva central (impronúncia, desclassificação, absolvição)?

### ETAPA 2 — ANÁLISE JURÍDICA (Fundamentação)
Apresente dentro de um bloco <fundamentos_juridicos>:
- Tipo penal imputado e seus elementos objetivos e subjetivos
- Art. 414 CPP (impronúncia) — se aplicável
- Art. 419 CPP (desclassificação) — se aplicável
- Arts. 483 e 386 CPP (absolvição)
- Excludentes de ilicitude (art. 23 CP) e culpabilidade (arts. 21, 22, 26 CP)
- In dubio pro reo (art. 386, VII, CPP) e in dubio pro societate (fase de pronúncia)
- Jurisprudência do STJ e STF relevante

### ETAPA 3 — CONSTRUÇÃO ARGUMENTATIVA (Estratégia)
Apresente dentro de um bloco <estrategia>:
- Tese principal: impronúncia, desclassificação ou absolvição?
- Como os depoimentos das testemunhas sustentam a tese defensiva
- Como os laudos periciais favorecem a defesa
- Contradições e fragilidades na prova da acusação
- Pedidos subsidiários ordenados do mais amplo ao mais restrito

### ETAPA 4 — EXPOSIÇÃO ESTRUTURADA (Os Memoriais)
Redija os memoriais completos com esta estrutura:

1. **Endereçamento** — MM. Juiz Presidente do Tribunal do Júri
2. **Identificação** — Número dos autos, acusado, crime
3. **Dos fatos e da instrução** — Síntese do que foi produzido em juízo
4. **Da análise das provas**:
   - Prova oral: análise crítica de cada depoimento
   - Prova pericial: laudo e seus pontos favoráveis/desfavoráveis
   - Prova documental: o que cada documento demonstra
5. **Das teses defensivas**:
   - Tese principal (com fundamento legal e probatório)
   - Teses subsidiárias
   - Excludentes aplicáveis
   - Fragilidade probatória — in dubio
6. **Da desclassificação** (se aplicável — art. 419 CPP)
7. **Da impronúncia** (se aplicável — art. 414 CPP)
8. **Dos pedidos**:
   a) Impronúncia (art. 414 CPP) — se for o caso
   b) Desclassificação (art. 419 CPP) — se for o caso
   c) Absolvição sumária (art. 415 CPP) — se for o caso
   d) Pronunciação com acolhimento apenas das teses favoráveis
   e) Quesitação favorável à defesa no plenário
9. **Fechamento** — Local, data, OAB

### ETAPA 5 — FORMULAÇÃO FINAL (Validação)
Apresente dentro de um bloco <checklist_validacao>:
- [ ] Todas as provas produzidas foram analisadas?
- [ ] As teses estão ordenadas da mais ampla à subsidiária?
- [ ] Impronúncia ou desclassificação foram avaliadas como opções?
- [ ] O in dubio foi adequadamente explorado?
- [ ] A quesitação favorável foi requerida?
- [ ] Pontos que exigem atenção especial do advogado: [liste]

---

## DADOS DO CASO (preencha todos os campos):

**PROCESSO:**
- Número dos autos: [número]
- Vara do Júri: [vara e comarca]
- Fase: [pré-pronúncia (art. 411 CPP) | pré-plenário]

**ACUSADO:**
- Nome: [nome]
- Perfil: [réu primário/reincidente, bons/maus antecedentes]

**CRIME IMPUTADO:**
- Tipo penal: [ex: homicídio doloso qualificado — art. 121, §2º, CP]
- Qualificadoras: [quais]

**PROVAS PRODUZIDAS NA INSTRUÇÃO:**
- Testemunhas de acusação ouvidas e resumo do depoimento: [liste]
- Testemunhas de defesa ouvidas e resumo do depoimento: [liste]
- Laudos periciais: [tipo e conclusão]
- Documentos juntados: [quais]
- Interrogatório do réu: [resumo]

**TESE DEFENSIVA:**
- Tese principal: [negativa de autoria | legítima defesa | desclassificação | impronúncia]
- Fundamento: [por que a prova sustenta essa tese]

**PONTOS CRÍTICOS:**
- Provas mais prejudiciais à defesa: [descreva]
- Como rebatê-las: [argumentos]

**INFORMAÇÕES ADICIONAIS:**
- [qualquer outra informação relevante]
```

---

## Dicas

1. **Memoriais ≠ discurso de plenário** — Os memoriais são dirigidos ao juiz presidente, com linguagem técnica. O discurso de plenário é para jurados leigos. Não confunda os registros.
2. **Analise cada prova individualmente** — Não basta dizer "as provas são frágeis". Analise cada depoimento, cada laudo, cada documento e extrai o que é favorável.
3. **Explore as contradições** — Depoimentos conflitantes entre testemunhas de acusação são o maior presente para a defesa. Detalhe cada contradição nos memoriais.
4. **Peça a quesitação certa** — Os quesitos do art. 483 CPP são fixos, mas as teses defensivas devem ser formuladas para orientar a votação. Requeira quesito de legítima defesa, desclassificação etc.
5. **In dubio pro reo x in dubio pro societate** — Na fase de pronúncia, aplica-se o in dubio pro societate (dúvida resolve para o júri julgar). No plenário, aplica-se o in dubio pro reo. Explore essa distinção nos memoriais de acordo com a fase.

---
*Skills Jurídicas com IA — RSA Advocacia*