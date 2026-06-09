---
name: embargos-execucao-ccb
description: >
  EMBARGOS-EXECUCAO-CCB — Embargos a execucao de Cedula de Credito Bancario (CCB)
  na perspectiva do cliente-devedor executado. CCB e titulo executivo
  extrajudicial (Lei 10.931/2004, arts. 26-45), mas admite discussao de encargos
  abusivos. Teses: excesso de execucao por encargos abusivos; ataque a
  liquidez/certeza do titulo (encargos ilegais retiram a liquidez); CDC aplicavel
  (Sum. 297) + Sum. 286 (renegociacao nao impede revisao); necessidade de pericia
  contabil. Estrutura completa dos embargos. Use quando o advogado disser:
  "embargos a execucao", "executaram a CCB", "cedula de credito bancario",
  "excesso de execucao", "titulo sem liquidez", "defesa em execucao bancaria",
  "embargos do devedor banco", "fui executado pelo banco".
---

# EMBARGOS-EXECUCAO-CCB — Cliente-devedor executado

> Embargos a execucao de CCB. A CCB e titulo executivo (Lei 10.931/2004), mas o
> excesso de execucao e o ataque a liquidez (via encargos abusivos) sao as portas
> de defesa.

## 1. NATUREZA DO TITULO

- **Lei 10.931/2004, arts. 26-45:** a CCB e **titulo executivo extrajudicial**.
- Mesmo sendo titulo, **admite discussao de abusividade** dos encargos em embargos
  (**Sum. 286** + **Sum. 297** — CDC aplicavel a instituicoes financeiras).
- Estrategia: encargos ilegais **retiram a liquidez/certeza** do titulo →
  excesso de execucao → necessidade de pericia para apurar o valor correto.

## 2. INPUT NECESSARIO

- CCB + aditivos + demonstrativo do debito do banco (memoria do exequente).
- Data da CCB (marcos: 31/03/2000; 30/04/2008; 25/02/2011; 30/06/2024).
- Encargos cobrados na memoria executiva.
- Prazo: embargos em **15 dias** (CPC 915) contados conforme a regra de cada caso.

## 3. TESES (corpus validado)

### a) Excesso de execucao (eixo central)
- O banco cobra valor superior ao devido por embutir encargos abusivos.
- Aplicar `detector-encargos-abusivos`: capitalizacao (Sum. 539/541 + MP
  2.170-36), comissao de permanencia cumulada (Sum. 30/294/296/472), TAC/TEC
  (Sum. 565 + Tema 618/619), servicos de 3os pos 25/02/2011 (Tema 958 = REsp
  1.578.553/SP), multa > 2% (CDC 52 §1º).
- **Obrigatorio (CPC 917 §3º/§4º):** ao alegar excesso, **declarar o valor que
  entende correto** e juntar memoria/demonstrativo — sob pena de rejeicao dos
  embargos. Puxar da `previa-abusividade-revisional`.

### b) Ataque a liquidez e certeza do titulo
- Encargos ilegais tornam o valor **iliquido/incerto**. Sem liquidez, falta
  requisito do titulo executivo → questionar a propria exequibilidade naquele
  montante. Nao e nulidade automatica da CCB, mas reducao/iliquidez do excesso.

### c) Revisao de juros (com cautela — Tema 27)
- Juros remuneratorios revisados so em situacao excepcional, abusividade
  **cabalmente demonstrada** (Tema 27 = REsp 1.061.530/RS). 🔴 base = Tema 27,
  NAO "Tema 247". Sum. 382 (juros > 12% por si so nao e abusivo); Sum. 596 STF
  (bancos fora da Usura).

### d) Renegociacao nao sana (Sum. 286)
- Se houve confissao/renegociacao, **Sum. 286**: nao impede revisar ilegalidades
  anteriores incorporadas a CCB.

### e) Pericia contabil
- Requerer pericia para apurar o quantum correto; quesitos via
  `gerador-quesitos-pericia-contabil`. Custeio: adianta quem requer (CPC 95);
  inversao nao custeia (Tema 1.024); gratuidade se cabe.

## 4. EFEITO SUSPENSIVO

- Embargos **nao** tem efeito suspensivo automatico. Requerer atribuicao (CPC
  919 §1º): garantia do juizo + fumus (encargos abusivos demonstrados na previa)
  + periculum (dano grave da execucao). Sem garantia, o efeito suspensivo e
  excepcional.

## 5. ESTRUTURA DOS EMBARGOS

1. Enderecamento ao juizo da execucao (em apenso).
2. Qualificacao embargante (devedor) x embargado (banco exequente).
3. Tempestividade (15 dias — CPC 915) e, se for o caso, garantia do juizo.
4. **Do excesso de execucao** — encargos abusivos item a item (detector) +
   **valor correto declarado** + memoria (CPC 917 §3º/§4º).
5. **Da iliquidez/incerteza** do titulo pelos encargos ilegais.
6. **Da revisao** — Sum. 286/297; Tema 27 para juros (com prova).
7. **Da pericia** — requerimento + quesitos anexos.
8. **Do efeito suspensivo** (CPC 919 §1º) — se garantido o juizo.
9. Pedidos — reduzir a execucao ao valor correto; declarar nulos os encargos
   abusivos; pericia; honorarios; gratuidade/prioridade idoso se cabe.
10. Provas e valor da causa.

## 6. PROIBICOES

1. NUNCA alegar excesso sem declarar o valor correto + memoria (CPC 917 §3º).
2. NUNCA prometer suspensao automatica da execucao (depende de garantia + CPC 919).
3. NUNCA afirmar abusividade de juros como certa sem demonstrar (Tema 27).
4. NUNCA hardcodar taxa media BACEN.
5. NUNCA confundir Tema 958 (servicos de 3os) com TAC/TEC (Sum. 565/Tema 618/619).
6. NUNCA citar Sum. 479 do STF (e do STJ).

## 7. INTEGRACAO

- **Upstream:** `triagem-caso-bancario`, `detector-encargos-abusivos`,
  `previa-abusividade-revisional`.
- **Downstream:** `gerador-quesitos-pericia-contabil`, `recomendador-perito-contabil`,
  `recursos-civeis-router`, `protocolo-p4-bancario`.

## 💡 Proximos passos opcionais

| Proximo passo | Comando | Plugin necessario |
|---|---|---|
| Calcular o excesso / auditar memoria do banco | `/calculos calculo-revisao-bancaria` | `calculosjudiciais-adv-os` |
| Embargos/defesa em execucao correlata | `/execucao embargos-execucao` | `execucao-adv-os` |
| Buscar julgado do TJ sobre excesso na CCB | `/juris buscar` | `juris-adv-os` |

> Se plugin nao instalado, usar a estrutura acima manualmente.

> ⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
