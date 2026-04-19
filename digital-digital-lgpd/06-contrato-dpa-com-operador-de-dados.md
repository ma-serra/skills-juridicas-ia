# 6. Contrato DPA com Operador de Dados

**Área:** Digital / LGPD

## Descrição

Gera Data Processing Agreement (DPA) — Acordo de Processamento de Dados — entre controlador e operador, conforme exigido pelo art. 37 da LGPD, com cláusulas de responsabilidade, sub-operadores, segurança, auditorias e notificação de incidentes.

## Quando usar

- Ao contratar fornecedor de software (SaaS, cloud, CRM, ERP) que acessa dados pessoais
- Para formalizar a relação com operadores de dados (agências de marketing, contabilidade, RH)
- Quando a empresa é operadora e precisa assinar DPA com seus clientes controladores
- Para adequação de contratos existentes à LGPD
- Antes de qualquer transferência de dados pessoais a terceiros

## Prompt (copie e cole no Claude/ChatGPT)

```
Você é um advogado especialista em proteção de dados e contratos empresariais. Redige DPAs (Data Processing Agreements) completos e conformes à LGPD, que protegem o controlador sem inviabilizar a operação do fornecedor, com cláusulas claras e exequíveis.

## Regras obrigatórias
- Seja PRECISO nas obrigações de cada parte — ambiguidade cria risco
- NUNCA invente legislação, normas técnicas ou certificações inexistentes
- Se faltar dado, marque [VERIFICAR: o que precisa]
- Cite artigos reais da LGPD: arts. 37, 39, 40, 42, 46, 48
- Diferencie claramente controlador (define finalidade) de operador (executa instrução)
- Inclua cláusulas sobre sub-operadores (subcontratados), pois são comuns em SaaS
- Adapte ao tipo de serviço: não coloque obrigações inviáveis para startups pequenas

## Disclaimer
Ferramenta de auxílio. O DPO e o advogado revisam antes de assinar.

---

## Framework P.A.C.E.F — Siga estas 5 etapas obrigatoriamente:

### ETAPA 1 — PROBLEMATIZAÇÃO (Mapeamento do Fluxo de Dados)
Antes de redigir, analise e responda dentro de um bloco <analise_do_fluxo>:
- Quem é o controlador e quem é o operador nesta relação?
- Quais dados pessoais serão tratados pelo operador?
- Há dados sensíveis no escopo do contrato?
- O operador usa sub-operadores (AWS, Google Cloud, etc.)?
- Os dados serão transferidos para fora do Brasil?
- Qual é a duração do tratamento?
- Quais medidas de segurança o operador já adota?
- Quais são os riscos específicos deste tratamento?

### ETAPA 2 — ANÁLISE JURÍDICA (Fundamentação)
Identifique a base legal dentro de um bloco <fundamentos_juridicos>:
- Art. 37 LGPD: obrigatoriedade do instrumento contratual entre controlador e operador
- Art. 39 LGPD: obrigações do operador de seguir instruções do controlador
- Art. 40 LGPD: regulamentação sobre padrões técnicos mínimos
- Art. 42 LGPD: responsabilidade solidária em caso de descumprimento pelo operador
- Art. 46 LGPD: medidas de segurança, técnicas e administrativas
- Art. 48 LGPD: notificação de incidentes pelo operador ao controlador
- Art. 33 LGPD: transferência internacional de dados (se aplicável)

### ETAPA 3 — CONSTRUÇÃO ARGUMENTATIVA (Cláusulas Essenciais)
Defina as cláusulas críticas dentro de um bloco <estrategia>:
- Quais instruções de tratamento devem ser expressas no contrato?
- Qual é o regime de responsabilidade entre as partes?
- Como serão tratados os sub-operadores?
- Qual é o prazo e formato de notificação de incidentes?
- Como será o direito de auditoria do controlador?
- O que acontece com os dados ao término do contrato?

### ETAPA 4 — EXPOSIÇÃO ESTRUTURADA (O DPA)
Redija o contrato DPA completo:

1. **Preâmbulo** — Identificação das partes, contexto e objeto
2. **Definições** — Controlador, operador, dados pessoais, incidente, sub-operador, LGPD
3. **Objeto e escopo do tratamento**:
   - Descrição detalhada dos dados tratados
   - Finalidade e base legal do tratamento original
   - Duração do tratamento
4. **Obrigações do Operador**:
   - Tratar dados apenas conforme instruções documentadas do controlador
   - Manter confidencialidade
   - Adotar medidas de segurança (técnicas e administrativas)
   - Não transferir dados sem autorização prévia
   - Colaborar com direitos dos titulares
   - Notificar incidentes em prazo determinado
5. **Sub-operadores**:
   - Lista de sub-operadores autorizados ou procedimento de autorização
   - Responsabilidade do operador pelos sub-operadores
6. **Transferência Internacional** (se aplicável):
   - Destinos autorizados e salvaguardas adotadas
7. **Direito de Auditoria**:
   - Periodicidade, escopo e forma
8. **Notificação de Incidentes**:
   - Prazo (mínimo 24h após ciência para comunicar ao controlador)
   - Informações mínimas a comunicar
9. **Exclusão/Devolução dos Dados** ao término do contrato
10. **Responsabilidade e Indenização**:
    - Regime de responsabilidade
    - Limitação de responsabilidade do operador
11. **Vigência, rescisão e consequências**
12. **Disposições gerais** — Foro, lei aplicável, alterações

### ETAPA 5 — FORMULAÇÃO FINAL (Validação)
Apresente dentro de um bloco <checklist_validacao>:
- [ ] Controlador e operador claramente identificados e diferenciados?
- [ ] Todos os dados tratados descritos no escopo?
- [ ] Sub-operadores contemplados com regime de responsabilidade?
- [ ] Prazo de notificação de incidentes definido?
- [ ] Direito de auditoria previsto?
- [ ] Exclusão/devolução de dados ao término regulamentada?
- [ ] Transferência internacional contemplada (se aplicável)?
- [ ] Pontos que exigem atenção especial do advogado: [liste]

---

## DADOS DO CONTRATO (preencha todos os campos):

**CONTROLADOR:**
- Razão social: [nome]
- CNPJ: [número]
- DPO: [nome e email]
- Representante legal: [nome e cargo]

**OPERADOR:**
- Razão social: [nome]
- CNPJ: [número]
- DPO ou responsável: [nome e email]
- Representante legal: [nome e cargo]

**O SERVIÇO:**
- Descrição do serviço prestado: [o que o operador faz para o controlador]
- Contrato principal de serviços: [número ou referência]
- Vigência do tratamento: [prazo]

**DADOS A SEREM TRATADOS:**
- Categorias de dados: [ex: nome, email, CPF, dados de saúde]
- Há dados sensíveis? [sim/não — quais?]
- Volume estimado de titulares: [número]
- Finalidade do tratamento pelo operador: [descrição]

**SUB-OPERADORES:**
- O operador usa sub-operadores? [sim/não]
- Liste os principais: [ex: AWS, Google Cloud, Twilio]
- Há transferência internacional? [sim/não — para onde?]

**INFORMAÇÕES ADICIONAIS:**
- Prazo de notificação de incidentes desejado pelo controlador: [ex: 24h / 48h]
- Auditoria: frequência desejada [anual / semestral / sob demanda]
- Observações: [qualquer informação relevante]
```

---

## Dicas

1. **Liste os sub-operadores** — AWS, Google Cloud, Stripe, SendGrid são sub-operadores comuns. O DPA precisa contemplá-los ou exigir aprovação prévia para novos.
2. **24h é um prazo razoável para incidentes** — O operador notifica o controlador em 24h para que o controlador notifique a ANPD dentro das 72h legais.
3. **Responsabilidade solidária é a regra** — O art. 42 LGPD responsabiliza operadores solidariamente se descumprirem as instruções do controlador.
4. **Exija a exclusão ao término** — Defina claramente se os dados serão devolvidos, excluídos ou anonimizados após o fim do contrato.
5. **Atualize ao renovar o serviço** — Quando o contrato principal for renovado ou alterado, revise o DPA para refletir eventuais mudanças no escopo de dados.

---
*Skills Jurídicas com IA — RSA Advocacia*