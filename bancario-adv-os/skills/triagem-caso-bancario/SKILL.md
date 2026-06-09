---
name: triagem-caso-bancario
description: >
  TRIAGEM CASO BANCARIO — Tier 1, porta de entrada de todo caso de
  acao bancaria na perspectiva do CLIENTE do banco (autor/vitima/devedor).
  Triagem-by-conversation: o advogado descreve o caso em linguagem
  natural; a skill faz perguntas direcionadas e classifica em uma das
  9 trilhas (golpe PIX / falso advogado / financiamento fraudulento /
  revisional-juros / busca e apreensao / execucao de CCB /
  superendividado / protocolos extrajudiciais / recurso) e roteia para
  as proximas skills da cadeia. Pergunta se houve transacao atipica,
  se o cliente e idoso, se ha contrato a revisar, se o banco ja foi
  comunicado. Use no inicio de qualquer demanda bancaria, caso novo,
  ou quando o advogado disser: triagem bancaria, analisar caso banco,
  cliente caiu em golpe, golpe pix, juros abusivos, revisional,
  busca e apreensao, fui executado, muitas dividas, superendividado,
  o que protocolar.
---

# TRIAGEM CASO BANCARIO

> Skill **Tier 1** — porta de entrada. Triagem-by-conversation: classifica o caso numa das 9 trilhas, identifica vulnerabilidades, e dispara a cadeia. Perspectiva: SEMPRE o cliente do banco (autor/vitima/devedor), nunca o banco.

---

## 0. ESCOPO E ACIONAMENTO

Primeira skill de produto a rodar. Acionada por `bancario-master`, `/bancario triagem`, ou ao descrever um caso novo. Entrega: frente classificada + polo do cliente + vulnerabilidade + próximas skills da cadeia.

## 1. APRESENTACAO INICIAL

> "Vou te ajudar a classificar o caso e montar a cadeia de trabalho. Este plugin atua **sempre pelo cliente do banco** (vítima de golpe, devedor que quer revisar/se defender, ou superendividado). Me descreve o caso em linguagem natural — o que aconteceu, o que o cliente quer. Eu faço perguntas direcionadas para classificar corretamente."

---

## 2. AS 9 TRILHAS

| # | Trilha | Quando classifica aqui | Roteia para |
|---|--------|------------------------|-------------|
| T1 | Golpe PIX / falso funcionário / falsa central | "golpe pix", "falso gerente", "ligaram do banco", "central de segurança", "estorno", "transferi achando que era o banco" | `fraude-pix-golpe-terceiro` |
| T2 | Golpe do falso advogado | "falso advogado", "ganhei uma ação", "taxa pra liberar valor", "intimação falsa", "pagou pra advogado que não era o dele" | `golpe-falso-advogado` |
| T3 | Financiamento/empréstimo não reconhecido | "empréstimo que não fiz", "financiamento fraudulento", "não reconheço esse contrato", "abriram conta no meu nome" | `financiamento-emprestimo-fraudulento` |
| T4 | Revisional / juros / tarifas | "revisional", "juros abusivos", "anatocismo", "capitalização", "tarifa", "Price", "SAC", "cheque especial", "rotativo" | `previa-abusividade-revisional` → `peticao-revisional-bancaria` |
| T5 | Busca e apreensão | "busca e apreensão", "tomaram meu carro", "vão pegar o veículo", "purgar mora", "alienação fiduciária" | `defesa-busca-apreensao` |
| T6 | Execução de CCB / cédula | "fui executado", "CCB", "cédula de crédito", "embargos", "penhora", "título executivo" | `embargos-execucao-ccb` |
| T7 | Superendividamento | "superendividado", "não consigo pagar", "muitas dívidas", "repactuar", "comprometeu tudo", "efeito bola de neve" | `triagem-superendividamento` |
| T8 | Protocolos extrajudiciais | "o que protocolar", "MED", "devolver o pix", "Registrato", "PROCON", "BACEN", "reclamar antes de processar" | `matriz-protocolos-extrajudiciais` |
| T9 | Recurso / réplica | "recurso", "apelar", "REsp", "agravo", "embargos de declaração", "réplica", "contestação do banco" | `recursos-civeis-router` / `replica-contestacao` |

Trilhas **cumulam**: ex. T7 + T3 (superendividado com empréstimo fraudulento na conta) — expurgar a fraude ANTES de repactuar.

---

## 3. BATERIA DE PERGUNTAS DIRECIONADAS

Após a descrição livre, fazer as perguntas-chave (agrupadas ou uma a uma). Para escolhas de lista fechada, **apresentar como botões via AskUserQuestion**.

### Q1 — Natureza do caso (variável-mãe)
> "O caso do cliente é mais de: (a) **fraude/golpe** (alguém o enganou, ele perdeu dinheiro/contraiu dívida que não reconhece) ou (b) **dívida própria** (ele contraiu o crédito e quer revisar juros, se defender de cobrança/busca e apreensão, ou está superendividado)?"

Fraude → T1/T2/T3. Dívida própria → T4/T5/T6/T7.

### Q2 — Houve transação atípica? **(gatilho dever de segurança)**
> "Houve **movimentação atípica** ao perfil do cliente (valor alto fora do padrão, horário incomum, local diferente, frequência anormal, dispositivo novo)? **O banco deveria ter barrado/sinalizado?** (gatilho REsp 2.052.228 — dever de segurança; reforça a tese de fraude)."

### Q3 — Cliente é idoso ou hipervulnerável? **(gatilho hipervulnerabilidade)**
> "O cliente é **idoso (60+)**, tem baixa escolaridade, deficiência ou outra condição de vulnerabilidade agravada? (gatilho `hipervulneravel-idoso-fraude` + prioridade processual art. 1.048 CPC + Estatuto do Idoso)."

### Q4 — Há contrato bancário a revisar? **(gatilho perícia → foro)**
> "Existe um **contrato bancário** no centro do caso (CCB, financiamento de veículo/imóvel, leasing, cartão, cheque especial)? Você tem o contrato e os aditivos? **A análise vai exigir perícia contábil?** (gatilho `classificador-foro-jec-comum`: revisional com perícia vai à Justiça Comum, NÃO ao JEC)."

### Q5 — O banco já foi comunicado? **(gatilho protocolos + mora)**
> "O banco já foi **comunicado formalmente** (MED, reclamação no app, RDR/BACEN, PROCON, notificação extrajudicial, BO)? Há resposta? **A comunicação prévia NÃO é requisito de procedência (CF 5º XXXV), mas vale como prova** de boa-fé e omissão (gatilho `matriz-protocolos-extrajudiciais`)."

### Q6 — Polo processual e fase
> "O cliente é **autor** (vai propor a ação) ou **réu/executado** (precisa se defender de busca e apreensão, execução, monitória)? Já existe processo? Número CNJ, vara, fase, prazo correndo?"

### Q7 — Urgência hoje? **(gatilho tutela)**
> "Há **urgência imediata**? Desconto/débito em curso na conta, nome no SERASA/SPC, saldo negativo crescente, veículo na iminência de apreensão? (gatilho `tutela-urgencia-bancaria` — art. 300 CPC)."

### Q8 — Data do fato (fraude PIX) **(gatilho MED 2.0)**
> "Se for golpe PIX: **qual a data da transação**? (gatilho de marco: antes de 02/02/2026 → MED Res. 103/2021; a partir de 02/02/2026 → MED 2.0, Res. 493/2025, rastreio em 5 camadas)."

---

## 4. CLASSIFICACAO E CADEIA

Após as respostas, classificar em uma ou mais trilhas e montar a cadeia. Lembrar as **auto-chains bloqueantes**:

- Toda trilha que gera **petição** → ANTES roda `varredura-jurisprudencial-pre-tese` (⭐ gate bloqueante) + `classificador-foro-jec-comum`.
- Toda **fraude** (T1/T2/T3) → auto-anexa `tese-fortuito-interno-sumula-479` + `rebater-culpa-exclusiva-vitima` + `tutela-urgencia-bancaria` + (se idoso) `hipervulneravel-idoso-fraude`; e sugere `matriz-protocolos-extrajudiciais`.
- T7 superendividamento → se houver empréstimo fraudulento, chama `financiamento-emprestimo-fraudulento` (expurgar) ANTES de `repactuacao-104a-104b`.
- T4 revisional → auto-anexa `gerador-quesitos-pericia-contabil` + `recomendador-perito-contabil`.
- Toda peça final → `auditoria-juris-pre-envio` → `protocolo-p4-bancario`.

---

## 5. OUTPUT — CHECKPOINT DE TRIAGEM

```
TRIAGEM CONCLUIDA

Frente(s): <T1 golpe PIX / T4 revisional / ...>
Polo do cliente: <autor / réu / executado>
Natureza: <fraude / dívida própria / superendividamento>
Transação atípica: <sim — o banco deveria ter barrado / não / N/A>
Vulnerabilidade: <idoso 60+ / baixa escolaridade / PCD / nenhuma>
Contrato a revisar: <sim — exige perícia? / não>
Banco comunicado: <sim — qual canal / não>
Urgência hoje: <sim — qual / não>
Data do fato (PIX): <dd/mm/aaaa → MED 103 ou MED 2.0 / N/A>

PRÓXIMAS SKILLS DA CADEIA:
1. <ex: varredura-jurisprudencial-pre-tese (gate)>
2. <ex: classificador-foro-jec-comum>
3. <ex: fraude-pix-golpe-terceiro + tese-fortuito-interno-sumula-479 + tutela-urgencia-bancaria>
4. <ex: matriz-protocolos-extrajudiciais (fortalecimento probatório)>
5. <ex: auditoria-juris-pre-envio → protocolo-p4-bancario>

Confirma estes dados para eu avançar na cadeia?
```

---

## 6. VEDACOES

1. **Nunca** prosseguir sem polo do cliente definido (ou explicitamente "a definir").
2. **Nunca** mandar revisional/qualquer caso que exija perícia ao JEC — passar por `classificador-foro-jec-comum` (extinção no JEC = risco real).
3. **Nunca** prometer que protocolo extrajudicial é obrigatório — é probatório/estratégico, não requisito (CF 5º XXXV).
4. **Nunca** afirmar tese de fraude como pacificada — há racha 3ª×4ª Turma STJ (entrega de senha/token); sinalizar via `monitor-temas-em-definicao`.

## 7. INTEGRACAO

Acionada por: `bancario-master`, `/bancario triagem`. Entrega para: `varredura-jurisprudencial-pre-tese` + `classificador-foro-jec-comum` (gates), depois a skill temática da trilha.

---

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
