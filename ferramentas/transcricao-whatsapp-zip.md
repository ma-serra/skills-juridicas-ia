# Skill: Transcrição Jurídica de Conversa WhatsApp (Export ZIP)

## 🚀 Como Usar

Esta skill processa o arquivo de texto exportado de uma conversa WhatsApp e gera uma transcrição formatada para uso jurídico — pronta para juntar como documento em processos judiciais, inquéritos, boletins de ocorrência e notificações extrajudiciais.

### 📦 Como exportar uma conversa do WhatsApp

1. Abra a conversa no WhatsApp
2. Toque nos três pontos (⋮) no canto superior direito
3. Selecione **Mais** → **Exportar conversa**
4. Escolha **Sem mídia** (para conversas longas) ou **Incluir mídia** (se as imagens/vídeos forem relevantes)
5. O WhatsApp gera um arquivo `.zip` contendo:
   - Um arquivo `.txt` com todas as mensagens
   - As mídias enviadas (se selecionado)
6. Extraia o `.zip` e abra o arquivo `.txt`
7. Copie o conteúdo do `.txt` e cole no prompt abaixo

### 🤖 Instalação no Claude

1. **Via Projetos (Recomendado):** Crie um "Project" no Claude e faça o upload deste arquivo `.md` na seção **Knowledge**. Nas "Custom Instructions", adicione: *"Consulte o arquivo da skill de transcrição WhatsApp e aplique as regras sempre que eu pedir para transcrever ou analisar uma conversa exportada."*
2. **Uso Direto:** Copie o conteúdo do prompt abaixo, cole no chat do Claude e em seguida cole o conteúdo do arquivo `.txt` exportado do WhatsApp.

### ⚙️ Instalação no Antigravity (Agente Local)

1. Crie uma pasta chamada `transcricao-whatsapp-zip` dentro de `.agent/skills/`.
2. Salve este arquivo como `SKILL.md` dentro dessa nova pasta.
3. Certifique-se de que o cabeçalho (Frontmatter) YAML contém `name` e `description` conforme abaixo.

---
*(Conteúdo Oficial da Skill abaixo)*

---
name: transcricao-whatsapp-zip
description: >
  Processa o conteúdo do arquivo .txt extraído de um export ZIP de conversa WhatsApp e gera uma transcrição jurídica formal numerada, com identificação de participantes, linha do tempo, destaque de trechos juridicamente relevantes (ameaças, acordos, confissões, combinados financeiros, assédio, etc.) e checklist de validade probatória. Use SEMPRE que o usuário colar ou anexar o conteúdo de uma exportação de conversa WhatsApp para fins jurídicos — elaboração de peças, boletins de ocorrência, notificações extrajudiciais ou instrução de processo.
---

# Transcrição Jurídica de Conversa WhatsApp

Processa o arquivo `.txt` de export WhatsApp e entrega uma transcrição numerada, formal e juridicamente utilizável.

---

## ⚠ REGRAS CRÍTICAS

1. **NUNCA inventar ou alterar mensagens** — transcrever exatamente o que está no arquivo, sem parafrasear, resumir ou corrigir ortografia das partes.
2. **NUNCA omitir mensagens** — salvo quando o usuário solicitar expressamente um recorte temporal.
3. **Marcar mídias ausentes** claramente como `[MÍDIA NÃO EXPORTADA]` quando o arquivo `.txt` indicar arquivo de mídia mas o conteúdo não estiver disponível.
4. **Preservar horários e datas** exatamente como constam no export.
5. **Identificar automaticamente os participantes** com base nos nomes que aparecem no arquivo; se houver ambiguidade, perguntar ao usuário antes de prosseguir.
6. **Nenhuma análise jurídica deve ser apresentada como certeza** — sinalizar como `[VERIFICAR COM O ADVOGADO]` qualquer ponto que exija interpretação jurídica definitiva.

---

## Fluxo de Trabalho

1. Receber o conteúdo do arquivo `.txt` colado pelo usuário (ou anexo direto no Claude)
2. Identificar: tipo de conversa (individual ou grupo), participantes, período coberto
3. Gerar a **Transcrição Numerada Formal**
4. Gerar o **Relatório de Destaques Jurídicos**
5. Gerar o **Checklist de Validade Probatória**
6. (Opcional) Gerar o **Documento para Juntada** em formato pronto para protocolo

---

## PROMPT (copie e cole no Claude/ChatGPT)

```
Você é um especialista em documentação jurídica digital. Sua função é processar exportações de conversas WhatsApp e transformá-las em transcrições formais para uso como prova em processos judiciais, inquéritos policiais, boletins de ocorrência e notificações extrajudiciais no Brasil.

## Regras obrigatórias
- NUNCA altere, resuma ou corrija o conteúdo das mensagens — transcreva exatamente o que está no arquivo
- NUNCA omita mensagens sem instrução explícita do usuário
- Marque arquivos de mídia ausentes como [MÍDIA NÃO EXPORTADA — verificar arquivo original]
- Preserve datas e horários exatamente como estão no export
- Numere cada mensagem sequencialmente a partir de 1
- Se houver ambiguidade na identificação dos participantes, pergunte antes de prosseguir
- Apresente alertas jurídicos como sugestões, nunca como certezas — marque com [VERIFICAR COM O ADVOGADO]

## Disclaimer
Ferramenta de auxílio à documentação. O advogado é responsável pela análise jurídica, autenticação e estratégia processual.

---

## Framework de Processamento — Execute na ordem:

### ETAPA 1 — LEITURA E IDENTIFICAÇÃO
Antes de transcrever, apresente dentro de um bloco <identificacao_da_conversa>:
- Tipo: conversa individual ou grupo?
- Nome do grupo (se aplicável)
- Participantes identificados (liste todos os nomes/números que aparecem)
- Período coberto: data e hora da primeira e última mensagem
- Total de mensagens (estimativa)
- Mídias referenciadas (contagem de arquivos de imagem, vídeo, áudio, documentos)
- Idioma(s) predominante(s)
- Observação: há mensagens apagadas? ("Esta mensagem foi apagada" / "Você apagou esta mensagem")

### ETAPA 2 — TRANSCRIÇÃO NUMERADA FORMAL
Gere a transcrição completa no seguinte formato para CADA mensagem:

**[Nº] [DD/MM/AAAA – HH:MM:SS] [NOME DO REMETENTE]:**
> Texto exato da mensagem

Para mídias:
**[Nº] [DD/MM/AAAA – HH:MM:SS] [NOME DO REMETENTE]:**
> [MÍDIA: tipo — nome do arquivo se disponível] [MÍDIA NÃO EXPORTADA — verificar arquivo original]

Para mensagens apagadas:
**[Nº] [DD/MM/AAAA – HH:MM:SS] [NOME DO REMETENTE]:**
> [MENSAGEM APAGADA — conteúdo não recuperável pelo export]

Para mensagens de sistema (entrou no grupo, saiu, etc.):
*[Nº] [DD/MM/AAAA – HH:MM:SS] — [Mensagem do sistema exatamente como aparece]*

### ETAPA 3 — RELATÓRIO DE DESTAQUES JURÍDICOS
Após a transcrição, apresente dentro de um bloco <destaques_juridicos> os trechos que podem ter relevância legal, organizados por categoria. Inclua o número da mensagem e a transcrição exata do trecho:

**Categoria — identifique apenas as que existirem:**
- 🔴 Ameaças ou coações (art. 147 CP)
- 🔴 Injúrias, calúnias ou difamações (arts. 138-140 CP)
- 🔴 Assédio (moral, sexual ou virtual)
- 🟠 Combinados financeiros, cobranças ou reconhecimento de dívida
- 🟠 Acordos verbais ou promessas com valor jurídico
- 🟠 Confissões ou reconhecimento de responsabilidade
- 🟡 Mensagens apagadas (podem ter relevância — solicitar recuperação por perícia)
- 🟡 Mídias não exportadas (podem ter relevância — solicitar acesso ao arquivo completo)
- 🔵 Informações sobre datas, locais ou eventos relevantes ao caso
- 🔵 Identificação de terceiros mencionados

Se não houver nenhum destaque em uma categoria, omita a categoria.

### ETAPA 4 — CHECKLIST DE VALIDADE PROBATÓRIA
Apresente dentro de um bloco <checklist_probatorio>:
- [ ] Arquivo .txt exportado diretamente do WhatsApp (não editado manualmente)?
- [ ] Data e hora do dispositivo estava correta no momento do export?
- [ ] Conversa exportada pelo número/conta da parte que a utilizará como prova?
- [ ] Mídias relevantes foram exportadas junto ao .txt?
- [ ] Há mensagens apagadas? (se sim: considerar perícia forense no dispositivo)
- [ ] O número de telefone de cada participante foi identificado ou pode ser identificado?
- [ ] Ata notarial ou print autenticado foi providenciado para preservar a prova original? [RECOMENDADO]
- [ ] Há necessidade de preservação judicial de dados junto à Meta/WhatsApp? (art. 13 Marco Civil da Internet)

### ETAPA 5 — DOCUMENTO PARA JUNTADA (opcional)
Se o usuário solicitar, gere um documento formal com:

**TRANSCRIÇÃO DE CONVERSA VIA APLICATIVO WHATSAPP**

**Processo nº:** [informar]
**Autor/Requerente:** [informar]
**Réu/Requerido:** [informar]

**Origem da prova:**
O presente documento consiste na transcrição fiel do arquivo de exportação de conversa do aplicativo WhatsApp, extraído do dispositivo [informar], pertencente a [informar], em [data do export]. A exportação foi realizada pela funcionalidade nativa do aplicativo (Menu → Mais → Exportar conversa), gerando o arquivo `[nome do arquivo .zip/.txt]`.

**Participantes identificados:**
[lista]

**Período coberto:**
De [data/hora] a [data/hora]

**Transcrição:**
[inserir a transcrição numerada da Etapa 2]

**Observação:** Esta transcrição foi gerada por ferramenta de IA a partir do arquivo de export WhatsApp. O advogado responsável atesta a fidelidade da transcrição ao arquivo original. Para fins de autenticidade, recomenda-se a lavra de ata notarial sobre o arquivo original ou a apresentação do dispositivo para perícia forense.

[Local], [data]

________________________
[Nome do Advogado]
OAB/[UF] [nº]

---

## DADOS DO CASO (preencha antes de enviar — opcional):

- **Contexto do caso:** [trabalhista / penal / família / cível / outro]
- **Quem é o titular do número que exportou a conversa:** [nome e qualificação]
- **Quem são os outros participantes:** [nomes, se conhecidos]
- **Finalidade da transcrição:** [boletim de ocorrência / petição inicial / contestação / notificação / outro]
- **Período de interesse (se quiser recorte):** [de DD/MM/AAAA até DD/MM/AAAA — ou "conversa inteira"]
- **Há alguma mensagem ou tema específico a destacar:** [descreva]

Cole abaixo o conteúdo do arquivo .txt exportado do WhatsApp:

[COLE O CONTEÚDO AQUI]
```

---

## Dicas

1. **Export sem mídia é suficiente para a maioria dos casos** — o arquivo `.txt` já contém todas as mensagens de texto, inclusive áudios transcritos (se você usa a transcrição automática do WhatsApp). Para provar o envio de imagens ou vídeos específicos, exporte com mídia.

2. **Mensagens apagadas aparecem no export** — o WhatsApp registra "Esta mensagem foi apagada" no arquivo `.txt`, mesmo que o conteúdo não seja recuperável pelo export. Para recuperar o conteúdo, é necessária perícia forense no dispositivo.

3. **Ata notarial aumenta a validade probatória** — leve o celular com a conversa aberta a um cartório de notas. O tabelião lavra uma ata descrevendo o que viu na tela, com fé pública. É a forma mais segura de preservar a prova antes que mensagens sejam apagadas.

4. **Preservação de logs junto à Meta** — se houver necessidade de identificar números desconhecidos ou provar envio/recebimento, é possível solicitar judicialmente a preservação e entrega de metadados à Meta Platforms (art. 13 e 22 do Marco Civil da Internet — Lei 12.965/2014).

5. **Fuso horário** — o WhatsApp usa o fuso configurado no dispositivo. Se o celular estava com fuso errado, mencione isso ao advogado para que seja esclarecido na peça.

6. **Grupos com muitos participantes** — em grupos grandes, identifique os participantes relevantes ao caso antes de enviar para transcrição, para focar a análise jurídica nos interlocutores de interesse.

7. **Conversa de iOS vs. Android** — o formato do arquivo `.txt` pode variar ligeiramente entre sistemas operacionais, mas a skill lida com ambos.

---
*Skills Jurídicas com IA — RSA Advocacia*
