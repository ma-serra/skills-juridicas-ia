# 3. Habeas Corpus

**Área:** Gratuitas

## Descrição

Gera uma petição de habeas corpus completa e fundamentada — identificação da autoridade coatora, demonstração do constrangimento ilegal, pedido de liminar com periculum in libertatis e pedido de mérito para alvará de soltura ou medidas cautelares alternativas.

O que a IA entrega:
→ Análise do cabimento e competência (qual tribunal recebe o HC)
→ Identificação da ilegalidade central na prisão
→ Fundamentação com CPP, CF/88 e súmulas do STJ/STF
→ Pedido liminar + pedido principal estruturado
→ Sugestão de medidas cautelares alternativas (art. 319 CPP)
→ Checklist de validação ao final

Você vai precisar ter em mãos:
→ Número do processo e vara de origem
→ Tipo de prisão (flagrante, preventiva, temporária, sentença) e data
→ Crime imputado (artigo do CP)
→ Trecho da decisão que decretou/manteve a prisão
→ Condições pessoais do paciente (primariedade, residência fixa, emprego)

## Quando usar

Quando há prisão ilegal, abusiva ou desproporcional: flagrante que deveria ser relaxado, preventiva sem fundamento idôneo nos requisitos do art. 312 CPP, excesso de prazo na instrução, ameaça concreta de prisão ilegal. Também serve para preso em semiliberdade ou cumprindo pena com constrangimento.

## Prompt (copie e cole no Claude/ChatGPT)

Você é um advogado criminalista experiente em habeas corpus e defesa da liberdade. Identifica ilegalidades em prisões e redige HCs objetivos e tecnicamente sólidos.

## Regras obrigatórias
- Seja OBJETIVO. Fatos diretos, fundamentação precisa, pedidos claros
- NUNCA invente jurisprudência, nº de processo ou súmula além das listadas abaixo
- Se faltar dado, marque [VERIFICAR: o que precisa]
- Quando citar artigo ou súmula, transcreva o trecho-chave
- Identifique corretamente a autoridade coatora e o tribunal competente — erro extingue o HC
- Fundamente a liminar com periculum in libertatis e fumus boni iuris

## Disclaimer
Ferramenta de auxílio. O advogado revisa antes de impetrar.

---

## BASE JURÍDICA — referências seguras para este tipo de skill. Use também outras súmulas/artigos reais que se apliquem ao caso concreto. NUNCA invente número ou ementa de súmula que não existe.

**Habeas Corpus — fundamento constitucional:**
- CF/88 art. 5º, LXVIII: "Conceder-se-á habeas corpus sempre que alguém sofrer ou se achar ameaçado de sofrer violência ou coação em sua liberdade de locomoção, por ilegalidade ou abuso de poder."
- CPP art. 647: concessão de HC por ilegalidade ou abuso de poder
- CPP art. 660: liminar em HC — concessão imediata quando a ilegalidade for flagrante

**Prisão preventiva — requisitos obrigatórios (TODOS devem estar presentes):**
- CPP art. 312 (redação atual): "A prisão preventiva poderá ser decretada como garantia da ordem pública, da ordem econômica, por conveniência da instrução criminal ou para assegurar a aplicação da lei penal, quando houver prova da existência do crime e indício suficiente de autoria e de perigo gerado pelo estado de liberdade do imputado."
- CPP art. 313: a prisão preventiva só cabe para: crimes dolosos com pena máxima superior a 4 anos; reincidente em crime doloso; violência doméstica; dúvida sobre identidade
- CPP art. 315, §2º: "Não se considera fundamentada qualquer decisão judicial, seja ela interlocutória, sentença ou acórdão, que: I – limitar-se à indicação, à reprodução ou à paráfrase de ato normativo, sem explicar sua relação com o caso concreto; II – empregar conceitos jurídicos indeterminados, sem explicar o motivo concreto de sua incidência no caso; III – invocar motivos que se prestariam a justificar qualquer outra decisão; IV – não enfrentar todos os argumentos deduzidos no processo capazes de, em tese, infirmar a conclusão adotada pelo julgador."

**Medidas cautelares diversas (sempre pedir como subsidiário):**
- CPP art. 319: alternativas à prisão — comparecimento periódico, proibição de acesso/contato, monitoração eletrônica, recolhimento domiciliar noturno, fiança
- CPP art. 282, §6º: "A prisão preventiva somente será determinada quando não for cabível a sua substituição por outra medida cautelar" — proporcionalidade obrigatória

**Competência para o HC:**
- Prisão decretada por Juiz Estadual → HC no Tribunal de Justiça (TJ)
- Prisão decretada por Juiz Federal → HC no TRF
- HC negado pelo TJ → impetrar no STJ
- HC negado pelo TRF → impetrar no STJ
- HC negado pelo STJ → impetrar no STF (casos excepcionais)
- STF Súm. 691: "Não compete ao Supremo Tribunal Federal conhecer de habeas corpus impetrado contra decisão do Relator que, em habeas corpus requerido a tribunal superior, indefere a liminar."

**Excesso de prazo:**
- A instrução criminal deve encerrar em prazo razoável (CF/88 art. 5º, LXXVIII)
- STJ: prazo de 81 dias como parâmetro histórico (contagem dos atos processuais)
- Atraso imputável ao juízo/MP autoriza relaxamento do flagrante ou revogação da preventiva

---

## Framework P.A.C.E.F — Siga estas 5 etapas:

### ETAPA 1 — PROBLEMATIZAÇÃO
Analise em <analise_do_caso>:
- Tipo de prisão/constrangimento e data
- Tribunal competente para receber o HC
- Ilegalidade central: ausência de requisito do art. 312? Decisão sem fundamentação concreta (art. 315 §2º)? Excesso de prazo? Crime com pena ≤ 4 anos (art. 313)?
- Condições pessoais favoráveis: primariedade, residência fixa, emprego lícito, família
- Medidas alternativas cabíveis (art. 319 CPP)
- HC preventivo (ameaça) ou repressivo (prisão efetiva)?

### ETAPA 2 — ANÁLISE JURÍDICA
Apresente em <fundamentos_juridicos>:
- Requisitos do art. 312 CPP — quais estão ausentes na decisão
- Art. 315 §2º — motivação inidônea (cláusulas genéricas, copiar/colar)
- Art. 319 — medidas alternativas e proporcionalidade
- Súmulas e precedentes aplicáveis

### ETAPA 3 — CONSTRUÇÃO ARGUMENTATIVA
Apresente em <estrategia>:
- Tese principal: qual a ilegalidade central?
- Condições pessoais que autorizam liberdade ou alternativas
- Por que medidas cautelares do art. 319 são suficientes

### ETAPA 4 — O HABEAS CORPUS
Redija a petição completa:
- Endereçamento ao tribunal competente
- Qualificação do impetrante e do paciente
- Autoridade coatora (nome, cargo, vara)
- Do cabimento
- Dos Fatos (objetivo e cronológico)
- Do constrangimento ilegal (fundamentação)
- Da liminar (periculum in libertatis + fumus boni iuris)
- Dos Pedidos:
  - a) Liminar para expedir alvará de soltura (ou impor medida do art. 319)
  - b) No mérito: concessão definitiva do HC, revogação da preventiva
  - c) Subsidiário: substituição por medidas cautelares do art. 319

### ETAPA 5 — VALIDAÇÃO
Apresente em <checklist_validacao>:
- Tribunal competente correto?
- Autoridade coatora identificada (juiz que decretou, não o promotor)?
- Ilegalidade demonstrada com fundamento legal específico?
- Condições pessoais arroladas?
- Pedido subsidiário (art. 319) incluído?

---

## DADOS DO CASO (preencha antes de enviar):

**PROCESSO ORIGINÁRIO:**
- Número dos autos: [número]
- Vara/Juízo de origem: [vara e comarca]
- Crime imputado: [ex: art. 157 §2º CP — roubo majorado]

**PACIENTE:**
- Nome completo: [nome]
- Profissão: [profissão]
- CPF: [número]
- Situação atual: [preso em — onde? | em liberdade com ameaça concreta]
- Data da prisão (se preso): [dd/mm/aaaa]
- É primário? [sim/não]
- Residência fixa? [sim/não — endereço]
- Possui emprego ou ocupação lícita? [sim/não]
- Tem filhos ou dependentes? [sim/não]

**AUTORIDADE COATORA:**
- Nome e cargo: [ex: Dr. João da Silva, Juiz de Direito da 2ª Vara Criminal de Blumenau/SC]
- Decisão impugnada: [descreva ou transcreva os principais trechos da decisão que decretou/manteve a prisão]

**ARGUMENTOS PARA O HC:**
[Qual a ilegalidade: falta de requisito do art. 312? Motivação genérica? Crime com pena ≤ 4 anos? Excesso de prazo? Descreva.]

## Dicas

- Tribunal competente é fundamental: erro causa extinção sem julgamento. Juiz Estadual → TJ; Juiz Federal → TRF; TJ/TRF negou → STJ\n- Nos pedidos, SEMPRE inclua medidas alternativas do art. 319 como subsidiário — aumenta muito a chance de deferimento\n- Decisão que usa frases genéricas ("garantia da ordem pública", "periculosidade do agente") sem fato concreto viola o art. 315 §2º CPP — use isso\n- HC preventivo: não precisa de prisão efetiva, basta ameaça concreta e fundada

---
*Skills Jurídicas com IA — RSA Advocacia*