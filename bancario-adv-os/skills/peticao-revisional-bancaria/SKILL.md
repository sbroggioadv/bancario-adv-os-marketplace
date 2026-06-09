---
name: peticao-revisional-bancaria
description: >
  PETICAO-REVISIONAL-BANCARIA — Monta a inicial de acao revisional de contrato
  bancario na perspectiva do cliente-devedor, para a JUSTICA COMUM (revisional com
  pericia contabil vai a Comum, NAO ao JEC — FONAJE 70/94). Estrutura: relacao de
  consumo (Sum. 297); juros revisados so em situacao excepcional com abusividade
  cabalmente demonstrada (Tema 27); pedido de PERICIA contabil fundado em fortes
  indicios (a previa entra aqui); deposito/consignacao do incontroverso; repeticao
  em dobro (Tema 929 — gate 30/03/2021); Sum. 286 (renegociacao nao impede
  revisao). Auto-anexa gerador-quesitos-pericia-contabil + recomendador-perito.
  Use quando o advogado disser: "acao revisional", "peticao revisional bancaria",
  "inicial de revisao de contrato", "revisar financiamento", "revisional de juros",
  "redigir revisional", "pedir pericia no contrato bancario".
---

# PETICAO-REVISIONAL-BANCARIA — Inicial (Justica Comum)

> Inicial de revisional do contrato bancario. **Sempre Justica Comum** quando
> houver pericia contabil (FONAJE 70/94). A previa de abusividade instrui os
> "fortes indicios" e o pedido de tutela.

## 1. GATES ANTES DE REDIGIR (bloqueantes)

1. `varredura-jurisprudencial-pre-tese` — confirmar entendimento atual do TJ
   competente + STJ para a tese escolhida (mitiga improcedencia por tese
   desatualizada). ⚠️ **bloqueante**.
2. `classificador-foro-jec-comum` — revisional **com pericia → Justica Comum**
   (FONAJE 70: ilegalidade de juros nao e complexa **exceto** quando exige
   pericia contabil; FONAJE 94: revisao de contrato cabe no JEC **exceto** quando
   exige pericia). Sem pericia e < 40 SM → pode JEC (opcao do autor).

## 2. BASE JURIDICA NUCLEAR

- **Sum. 297 STJ:** CDC aplicavel a instituicoes financeiras → relacao de consumo.
- **Tema 27 (REsp 1.061.530/RS):** revisao de juros remuneratorios so em situacao
  **excepcional**, com abusividade **cabalmente demonstrada** (CDC 51 §1º). Por
  isso a inicial pede **pericia** — nao afirma o numero, demonstra indicio.
  🔴 base = Tema 27, NAO "Tema 247".
- **Sum. 286 STJ:** renegociacao/confissao de divida **nao impede** revisao de
  ilegalidades anteriores.
- **Sum. 382/596:** juros altos por si so nao sao abusivos; bancos fora da Usura.
- **Tema 1.024:** inversao do onus (CDC 6º VIII) **nao** transfere ao banco o
  **onus financeiro** da pericia → o autor (ou a gratuidade) adianta.

## 3. ESTRUTURA DA INICIAL

1. **Enderecamento** — Vara Civel da comarca [CIDADE/UF].
2. **Qualificacao** — autor (cliente-devedor) x banco reu.
3. **Dos fatos** — contrato [tipo], valor, parcelas, encargos cobrados, situacao
   atual (adimplente/inadimplente).
4. **Do direito de consumidor** — Sum. 297; inversao do onus (CDC 6º VIII);
   Sum. 286 (renegociacao nao impede revisao).
5. **Dos encargos questionados** — puxar de `detector-encargos-abusivos`:
   capitalizacao (Sum. 539/541), comissao de permanencia (Sum. 472), TAC/TEC
   (Sum. 565), servicos de 3os (Tema 958), multa > 2% (CDC 52 §1º).
6. **Da abusividade cabalmente demonstrada (Tema 27)** — anexar a **previa de
   abusividade** como fortes indicios; comparar taxa contratada x taxa media
   BACEN `[TAXA_MEDIA_BACEN_%]` (placeholder + link SGS).
7. **Da pericia contabil** — requerer pericia fundada em fortes indicios; quesitos
   anexos (auto-anexa `gerador-quesitos-pericia-contabil`).
8. **Da tutela de urgencia (CPC 300)** — **deposito/consignacao do valor
   incontroverso**, abstencao de negativacao/SERASA, manutencao na posse do bem;
   §537 astreintes. ⚠️ NAO pedir suspensao integral de pagamento sem incontroverso.
9. **Da repeticao em dobro** — se houver cobranca indevida, CDC 42 §ú + **Tema
   929**, com **gate 30/03/2021** (antes desse marco = simples). Ver
   `devolucao-em-dobro`.
10. **Dos pedidos** — declarar nulidade dos encargos abusivos; recalcular o saldo;
    repetir indebito (simples/dobro conforme gate); honorarios; gratuidade se cabe.
11. **Valor da causa, provas, gratuidade.**

## 4. CLAUSULAS DE SEGURANCA (postura honesta)

- A inicial **pede pericia** porque NAO afirma o numero final (Tema 27 exige
  prova). Nao prometer percentual de exito.
- Avisar o cliente: salvo gratuidade, **provavelmente adianta o perito** (CPC 95
  + Tema 1.024).
- Sinalizar que o **parametro "1,5x taxa media"** e indiciario, nao tese fixada
  (Tema 1.378 pendente — confirmar antes de citar).

## 5. AUTO-CHAINS

- ANTES: `varredura-jurisprudencial-pre-tese` + `classificador-foro-jec-comum`.
- Anexa: `previa-abusividade-revisional` (fortes indicios) +
  `gerador-quesitos-pericia-contabil` + `recomendador-perito-contabil`.
- DEPOIS (peca final): `auditoria-juris-pre-envio` → `protocolo-p4-bancario`.

## 6. PROIBICOES

1. NUNCA ajuizar revisional **com pericia no JEC** (extincao — FONAJE 70/94).
2. NUNCA afirmar percentual/valor final sem pericia (Tema 27).
3. NUNCA pedir suspensao integral de pagamento sem deposito do incontroverso.
4. NUNCA hardcodar taxa media BACEN.
5. NUNCA citar Sum. 479 do **STF** em acao bancaria (e do STJ — Sum. 479 STJ).
6. NUNCA aplicar dobro a cobranca anterior a 30/03/2021 (Tema 929).

## 7. INTEGRACAO

- **Upstream:** `previa-abusividade-revisional`, `detector-encargos-abusivos`,
  `varredura-jurisprudencial-pre-tese`, `classificador-foro-jec-comum`.
- **Downstream:** `replica-contestacao`, `recursos-civeis-router`,
  `devolucao-em-dobro`, `protocolo-p4-bancario`.

## 💡 Proximos passos opcionais

| Proximo passo | Comando | Plugin necessario |
|---|---|---|
| Calcular o gap / auditar laudo PJE-CALC | `/calculos calculo-revisao-bancaria` | `calculosjudiciais-adv-os` |
| Buscar julgado atualizado do TJ | `/juris buscar` | `juris-adv-os` |
| Auditoria final R1-R4 | `/ia-combativa suprema-corte-r1-r4` | `ia-combativa-adv-os` |

> Se plugin nao instalado, copiar a estrutura acima e usar manualmente.

> ⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
