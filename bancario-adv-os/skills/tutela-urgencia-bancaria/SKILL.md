---
name: tutela-urgencia-bancaria
description: >
  TUTELA-URGENCIA-BANCARIA — Minuta reutilizavel de tutela provisoria de
  urgencia (art. 300 CPC) para acoes bancarias do CLIENTE contra o banco.
  Monta os requisitos (fumus boni iuris + periculum in mora), pedido
  inaudita altera parte, ressalva do §3o (irreversibilidade) e astreintes
  (art. 537). Modalidades de pedido: suspender desconto de emprestimo
  fraudulento no beneficio/conta; suspender exigibilidade dos contratos;
  abster de negativar (SERASA/SPC); neutralizar saldo negativo. Inclui
  alerta JEC (tutela no JEC atacada por MS a Turma — FONAJE 62) + template
  de pedido pronto pra colar. Use quando: "tutela de urgencia", "liminar",
  "suspender desconto", "tirar do SERASA", "abster de negativar", "neutralizar
  saldo negativo", "parar cobranca de emprestimo fraudulento", "astreintes".
---

# TUTELA-URGENCIA-BANCARIA — Minuta de tutela de urgencia (art. 300 CPC)

> Modulo transversal: chamado por `golpe-falso-advogado`,
> `financiamento-emprestimo-fraudulento`, `fraude-pix-golpe-terceiro` e demais.
> Placeholders: {{CLIENTE_NOME}}, {{BANCO_REU}}, {{CONTRATOS}}, {{DATAS_PARCELAS}},
> {{VALOR_ASTREINTE}}.
> ⚠️ Nenhuma citacao na peca sem `auditoria-juris-pre-envio` (WebFetch real).

## 0. BASE LEGAL (corpus verificado)
- **art. 300 CPC** — tutela de urgencia: fumus + periculum.
- **art. 300 §2o** — pode ser concedida liminarmente / inaudita altera parte.
- **art. 300 §3o** — vedada quando houver perigo de irreversibilidade (sempre
  enderecar/afastar este ponto).
- **art. 537 CPC** — multa (astreintes) por descumprimento.
- (consumidor) CDC 6o VIII (inversao) + Sum. 479 STJ reforcam a verossimilhanca.

## 1. QUANDO CABE (cheque rapido)
- [ ] Ha desconto iminente/em curso no beneficio ou conta (verba alimentar)?
- [ ] Ha contratos fraudulentos gerando exigibilidade/parcelas?
- [ ] Ha negativacao em curso ou iminente (SERASA/SPC)?
- [ ] Ha saldo negativo gerando juros/encargos crescentes?
Qualquer "sim" → cabe o respectivo pedido abaixo.

## 2. MONTAGEM DOS REQUISITOS

### Fumus boni iuris (probabilidade do direito)
- Prova documental: extratos, prints do golpe, BO, protocolo de contestacao no banco.
- Direito: relacao de consumo (Sum. 297) + resp. objetiva por fortuito interno
  (**Sum. 479 STJ** + art. 14 CDC) + dever de seguranca (**REsp 2.052.228/DF**).
  A verossimilhanca decorre das operacoes atipicas ao perfil + falha do banco.

### Periculum in mora (perigo de dano) — datar e concretizar
- Parcelas com **data certa de inicio** ({{DATAS_PARCELAS}}) incidindo sobre
  **beneficio previdenciario / unica fonte de renda de natureza alimentar**.
- Comprometimento de subsistencia (alimentacao, medicamentos, moradia).
- Saldo negativo gerando juros/encargos continuos → prejuizo crescente.
- Negativacao → abalo de credito imediato.
> NAO usar periculum abstrato. Sempre ancorar em datas/valores concretos.

### Afastar irreversibilidade (§3o)
"Nao ha perigo de irreversibilidade: em caso de improcedencia, o banco podera
retomar as cobrancas — a medida e plenamente reversivel."

## 3. MODALIDADES DE PEDIDO (combinar conforme o caso)

**A) Suspender desconto de emprestimo fraudulento no beneficio/conta**
Abster-se de efetuar/autorizar quaisquer descontos referentes a {{CONTRATOS}} ou a
outros contratados fraudulentamente, na conta ou no beneficio previdenciario.

**B) Suspender exigibilidade dos contratos**
Suspender a exigibilidade de {{CONTRATOS}}, bloqueando cobranca, debito automatico
ou encargo deles decorrente, ate decisao final.

**C) Abster de negativar (SERASA/SPC)**
Abster-se de inserir/manter o nome de {{CLIENTE_NOME}} em cadastros de inadimplentes
em razao dos contratos impugnados ou do saldo negativo.

**D) Neutralizar saldo negativo**
Suspender a exigibilidade e **neutralizar o saldo negativo** decorrente das operacoes
fraudulentas, impedindo a incidencia de juros, encargos, multas e tarifas.

**E) Astreintes (art. 537)**
Multa diaria de {{VALOR_ASTREINTE}} (ex.: R$ 500,00) por descumprimento — patamar
adequado, sem enriquecimento sem causa.

## 4. TEMPLATE DE PEDIDO (colar na inicial)

```
DA TUTELA PROVISORIA DE URGENCIA (art. 300 do CPC)
Presentes o fumus boni iuris [extratos, prints, BO, protocolo] e o periculum in
mora [parcelas com inicio em {{DATAS_PARCELAS}} sobre verba alimentar], requer-se a
concessao da tutela de urgencia, em carater LIMINAR e INAUDITA ALTERA PARTE, para
determinar que o {{BANCO_REU}}:
 a) SUSPENDA imediatamente qualquer desconto/cobranca, na conta ou no beneficio da
    autora, relativo aos contratos {{CONTRATOS}} e a quaisquer outros celebrados
    fraudulentamente a partir de [data];
 b) SUSPENDA A EXIGIBILIDADE dos referidos contratos, bloqueando debito automatico
    e encargos, ate decisao final;
 c) ABSTENHA-SE de inserir/manter o nome da autora em cadastros de inadimplentes
    em razao dos contratos ou do saldo negativo;
 d) NEUTRALIZE o saldo negativo da conta, impedindo juros, encargos e tarifas;
 e) sob pena de MULTA DIARIA de {{VALOR_ASTREINTE}} (art. 537 do CPC).
Nao ha irreversibilidade (§3o): improcedente a acao, o banco retoma as cobrancas.
```

## 5. ⚠️ ALERTA JEC (foro errado pode derrubar a liminar)
No **Juizado Especial Civel NAO cabe Agravo de Instrumento**. Decisao que concede/
nega tutela no JEC e atacada por **Mandado de Seguranca a Turma Recursal**
(**FONAJE 62**). Implicacoes:
- Se a acao correr no JEC, a tutela existe, mas a via recursal contra ela muda (MS).
- Se o caso exigir pericia (ex.: revisional, discutir encargos), o foro correto e a
  **Justica Comum** (FONAJE 70/94) — la cabe AI (CPC 1.015, I). Conferir com
  `classificador-foro-jec-comum` ANTES de protocolar.

## INTEGRACAO
- Chamada por: `golpe-falso-advogado`, `financiamento-emprestimo-fraudulento`,
  `fraude-pix-golpe-terceiro` (e demais frentes com desconto/negativacao).
- ANTES de definir foro: `classificador-foro-jec-comum`.
- DEPOIS (peca final): `auditoria-juris-pre-envio` → `protocolo-p4-bancario`.
- Cross-link soft: se for descumprida, AI na Justica Comum → `recursos-civeis-router`.

## PROIBICOES
1. NUNCA usar periculum abstrato — sempre data/valor concreto.
2. NUNCA omitir o afastamento do §3o (irreversibilidade).
3. NUNCA pedir AI de tutela no JEC (so MS a Turma — FONAJE 62).
4. NUNCA citar Sumula 479 como sendo do STF (e do STJ).

---
⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
