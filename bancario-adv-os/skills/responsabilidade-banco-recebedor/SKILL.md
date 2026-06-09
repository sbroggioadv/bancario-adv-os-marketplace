---
name: responsabilidade-banco-recebedor
description: >
  RESPONSABILIDADE-BANCO-RECEBEDOR — Tese contra o banco RECEBEDOR
  (onde o golpista abriu a conta-laranja). Ancora: REsp 2.124.423
  STJ (recebedor responde SO se falha de diligencia na
  abertura/manutencao — KYC/PLD) + art. 39-B da Res. BCB 1/2020
  (bloqueio cautelar sob fundada suspeita). Estrategia: incluir o
  recebedor no polo passivo (litisconsorcio) + pedir EXIBICAO dos
  documentos de abertura da conta (KYC/CCS). Texto pronto +
  criterio de quando vale a pena litigar contra o recebedor. Use
  quando: "banco recebedor", "conta laranja", "conta de destino do
  pix", "incluir o outro banco", "polo passivo recebedor", "KYC",
  "PLD", "exibicao de documentos de abertura", "REsp 2.124.423",
  "art. 39-B", "bloqueio cautelar da conta destino".
---

# RESPONSABILIDADE-BANCO-RECEBEDOR — Réu Certo + Exibição de KYC

## 0. ⚠️ ARMADILHA ANTI-ALUCINAÇÃO

- 🟡 `REsp 2.124.423` (STJ, T3, Nancy Andrighi, 27/01/2025) — confirmar nº/teor na íntegra antes de citar.
- ✅ `art. 39-B` é da **Resolução BCB nº 1/2020** (regulamento-base do PIX), com reforço da Res. BCB 493/2025 (MED 2.0).
- 🔴 Súmula da resp. objetiva = **479 STJ** (não STF).

---

## 1. O QUE É E QUANDO USAR

Bloco para **trazer ao polo passivo o banco RECEBEDOR** — aquele onde o golpista abriu a conta de destino do PIX/TED ("conta-laranja"). O recebedor **não responde automaticamente**, mas responde **se falhou na diligência** de abertura/manutenção da conta (KYC — *Know Your Customer* / PLD — Prevenção à Lavagem de Dinheiro) ou se omitiu o bloqueio cautelar do art. 39-B.

**Quando usar:** valor relevante, conta-laranja identificável, e há indício de cadastro irregular (conta nova, dados falsos, alto giro atípico). Combina com pedido de **exibição dos documentos de abertura**.

> **Atenção ao regime distinto:** o banco do **pagador** (onde a vítima é cliente) responde por dever de segurança amplo (Súm. 479). O **recebedor** responde por regime PRÓPRIO e mais estreito — só se provada falha de diligência. **Não misturar** os fundamentos.

---

## 2. QUANDO VALE A PENA LITIGAR CONTRA O RECEBEDOR

| Sinal a favor | Sinal contra |
|---|---|
| Conta-laranja identificada (nome/CPF/CNPJ do destinatário) | Destinatário desconhecido / não identificável |
| Conta recém-aberta com dados suspeitos | Conta antiga e regular |
| Valor alto que justifica o custo de mais um réu | Valor baixo (custo > benefício) |
| Recebedor é instituição diversa do banco do autor | Mesmo banco como pagador e recebedor (1 réu só) |
| Indício de inércia no art. 39-B (sem bloqueio cautelar) | MED acionado e bloqueio feito a tempo |

**Decisão honesta:** se não há identificação da conta-laranja nem indício de falha cadastral, **focar no banco do pagador** e usar a exibição apenas para tentar localizar o destino. Não inflar o polo passivo sem lastro (risco de sucumbência contra o recebedor).

---

## 3. TEXTO PRONTO — RESPONSABILIDADE DO RECEBEDOR

```markdown
DA RESPONSABILIDADE DO BANCO RECEBEDOR — FALHA NO DEVER DE
DILIGÊNCIA (KYC/PLD) E NO BLOQUEIO CAUTELAR (ART. 39-B DA RES. BCB
1/2020)

A par da responsabilidade do banco do pagador, deve responder
também [banco recebedor], instituição em que o estelionatário abriu
e manteve a conta de destino dos valores fraudulentos.

O Superior Tribunal de Justiça firmou que a instituição RECEBEDORA
responde quando demonstrada FALHA DE DILIGÊNCIA na abertura ou
manutenção da conta utilizada para o escoamento do produto da
fraude — isto é, descumprimento dos deveres de conhecimento do
cliente (KYC) e de prevenção à lavagem de dinheiro (PLD) (REsp
2.124.423).

A regulação do PIX impõe, ainda, ao prestador de serviço de
pagamento recebedor o dever de BLOQUEIO CAUTELAR dos valores sob
fundada suspeita de fraude, nos termos do art. 39-B da Resolução
BCB nº 1/2020. A omissão nesse bloqueio configura falha autônoma,
que viabilizou a pulverização dos recursos.

Há fortes indícios de que [banco recebedor] descumpriu tais
deveres: [ex.: conta aberta poucos dias antes; titularidade
incompatível; alto giro atípico; ausência de bloqueio mesmo após
acionamento]. Tais elementos, cujo esclarecimento depende da
documentação em poder exclusivo do réu, impõem sua inclusão no polo
passivo e a apuração de sua responsabilidade.
```

---

## 4. TEXTO PRONTO — PEDIDO DE EXIBIÇÃO (KYC)

```markdown
DA EXIBIÇÃO DOS DOCUMENTOS DE ABERTURA DA CONTA DE DESTINO

Requer-se, com fundamento nos arts. 396 a 400 do CPC e no art. 6º,
VIII, do CDC, que [banco recebedor] seja intimado a EXIBIR:
  (a) ficha cadastral e documentos de abertura da conta de destino
      (RG/CPF/CNPJ, comprovantes, biometria, geolocalização, IP);
  (b) data de abertura e histórico de movimentação no período;
  (c) registros do procedimento de KYC/PLD adotado;
  (d) comprovação de eventual bloqueio cautelar (art. 39-B) e de
      acionamento/resposta ao Mecanismo Especial de Devolução (MED).

A recusa injustificada autoriza a presunção de veracidade dos fatos
alegados (art. 400 do CPC).
```

> Frente complementar de prova: a skill `registrato-extracao-prova` (CCS/SCR do BCB) ajuda a identificar a conta-laranja e a instituição recebedora antes de incluí-la no polo.

---

## 5. PROIBIÇÕES

1. **NUNCA aplicar a Súmula 479 ao recebedor** como se fosse o mesmo regime do banco do pagador — o recebedor responde por regime PRÓPRIO (falha de diligência), mais estreito.
2. **NUNCA incluir** o recebedor no polo passivo sem indício mínimo de falha cadastral ou de bloqueio (risco de sucumbência).
3. **NUNCA citar** REsp 2.124.423 sem confirmação na íntegra (🟡 → `auditoria-juris-pre-envio`).
4. **NUNCA confundir** art. 39-B (Res. BCB 1/2020) com a Resolução do MED (103/2021 ou 493/2025).

---

## 6. INTEGRAÇÃO

**Upstream:** `bancario-master` · skills de petição de fraude (quando há conta-laranja identificável).
**Co-anexar:** `tese-fortuito-interno-sumula-479` (mérito contra o pagador) · `med-pix-acionamento` (gate de data MED) · `registrato-extracao-prova` (identificar destino).
**Downstream:** `auditoria-juris-pre-envio` → `protocolo-p4-bancario`.

---

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
