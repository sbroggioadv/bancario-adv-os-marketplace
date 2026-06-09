---
name: previa-abusividade-revisional
description: >
  PREVIA-ABUSIVIDADE-REVISIONAL — Estimativa/INDICIO auditavel de abusividade
  em contrato bancario do cliente-devedor (financiamento, CCB, cheque especial,
  cartao, leasing). NAO e laudo pericial: e simulacao com premissas declaradas e
  fonte/data dos indices, que apresenta GAP quantificado (encargo contratado x
  recalculado depurando capitalizacao indevida, comissao de permanencia cumulada
  e tarifas vedadas). Base: Tema 27 (REsp 1.061.530/RS) — revisao de juros so com
  abusividade cabalmente demonstrada. Serve para instruir "fortes indicios",
  fundamentar pedido de pericia e tutela (deposito do incontroverso). Use quando
  o advogado disser: "previa de abusividade", "estimativa de revisional",
  "indicio de juros abusivos", "gap do contrato", "quanto da pra revisar",
  "simulacao antes da pericia", "calculo previo bancario", "abusividade do
  financiamento", "vale a pena revisar".
---

# PREVIA-ABUSIVIDADE-REVISIONAL — Indicio auditavel (NAO e laudo)

> ⚠️ Esta skill produz **PREVIA / INDICIO**, jamais laudo pericial. O laudo
> oficial vem da pericia contabil judicial. Aqui geramos uma simulacao
> defensavel que instrui "fortes indicios" + pedido de pericia + tutela.

## 1. PARA QUE SERVE (e o que NAO faz)

**Serve para:**
- Decisao cliente↔advogado: vale a pena ajuizar revisional?
- Instruir a inicial com "fortes indicios" (requisito da pericia — Tema 27).
- Fundamentar pedido de tutela: **deposito/consignacao do valor incontroverso**.

**NAO faz:** nao e laudo, nao fixa valor final, nao substitui o perito,
nao afirma tese como pacificada. Toda saida marca: "**simulacao sujeita a
pericia oficial**".

## 2. BASE JURIDICA (Tema 27)

A tese-mae da revisional e o **Tema 27 (REsp 1.061.530/RS)**: revisao de juros
remuneratorios so em situacao **excepcional**, com abusividade **cabalmente
demonstrada** (CDC art. 51 §1º). A previa existe justamente para construir esse
"cabalmente demonstrada" com numeros, antes da pericia.

🔴 Atencao anti-alucinacao: a base e o **Tema 27**, NAO "Tema 247" (este e
capitalizacao — Sumulas 539/541).

## 3. PREMISSAS A DECLARAR (sempre no topo da saida)

| Premissa | Como obter |
|---|---|
| Tipo de contrato | CCB / financiamento veiculo-imovel / leasing / cartao / cheque especial |
| Natureza | consumo (CDC) ou empresarial (CC — revisao mais restrita) |
| Valor financiado, prazo, N parcelas | contrato |
| Sistema de amortizacao | SAC / Price / misto |
| Taxa mensal e anual contratada | contrato |
| Data do contrato | define marcos (31/03/2000; 30/04/2008; 30/06/2024) |
| Taxa media BACEN da modalidade | **placeholder + link oficial — NUNCA hardcodar** |

**Taxa media BACEN:** consultar
`bcb.gov.br/estatisticas/historicodastaxasdejuros` (SGS) para a modalidade e o
mes do contrato. A skill NAO tem acesso a taxas pos-cutoff → sempre placeholder
`[TAXA_MEDIA_BACEN_%]` + fonte/data de extracao.

## 4. PARAMETRO INDICIARIO (aviso obrigatorio)

O criterio "**taxa contratada > 1,5x / 50% acima da taxa media BACEN**" e
jurisprudencia **estadual/indiciaria**, **NAO tese vinculante do STJ**. Usar
apenas como **indicio de prosseguir/periciar**, jamais como tese fixada.

⚠️ O **Tema 1.378 STJ** (REsp 2.227.276/AL) esta **AFETADO, pendente de
julgamento** — vai decidir se a taxa media BACEN isoladamente basta para aferir
abusividade. Ate la, tratar como **questao em definicao** (confirmar antes de
citar). Avisar o cliente: o parametro nao e seguro como tese.

## 5. PROCESSAMENTO (o que a previa testa)

1. **Anatocismo (Sum. 539/541):** se `taxa_anual > 12 x taxa_mensal` → ha
   capitalizacao mensal embutida. Licita SO se contrato pos 31/03/2000
   (MP 2.170-36/2001 art. 5º) + clausula **expressa**. Sem clausula → recalcular
   sem capitalizacao indevida. Sum. 541: taxa anual > duodecuplo da mensal basta
   como pactuacao expressa.
2. **Comissao de permanencia (Sum. 30/294/296/472):** licita isolada; **abusiva
   se cumulada** com correcao, juros moratorios ou multa.
3. **Tarifas vedadas:** TAC/TEC so ate 30/04/2008 (Sum. 565); servicos de
   terceiros/correspondente abusivos pos 25/02/2011 (Tema 958 = REsp
   1.578.553/SP). 🔴 Tema 958 e servicos de terceiros, NAO TAC/TEC.
4. **Juros vs taxa media:** comparar contratada x `[TAXA_MEDIA_BACEN_%]`. Sum.
   382: juros > 12% a.a. por si so NAO indicam abusividade. Sum. 596 STF: bancos
   fora da Lei de Usura.
5. **GAP:** somar expurgos → diferenca entre valor cobrado e valor recalculado.

## 6. OUTPUT — PREVIA AUDITAVEL

```markdown
## Previa de abusividade — INDICIO (simulacao sujeita a pericia oficial)

### Premissas declaradas
| Campo | Valor |
|---|---|
| Tipo / natureza | [___] / [CDC|CC] |
| Valor financiado | R$ [___] |
| Data contrato | [dd/mm/aaaa] |
| Sistema | [SAC|Price|misto] |
| Taxa mensal / anual | [X%] / [Y%] |
| Taxa media BACEN (modalidade/mes) | [TAXA_MEDIA_BACEN_%] — fonte: bcb.gov.br/SGS, extracao [data] |

### Indicios apurados
| Encargo | Teste | Indicio | Valor estimado a expurgar |
|---|---|---|---|
| Capitalizacao | anual > 12x mensal? clausula expressa? | [sim/nao] | R$ [___] |
| Comissao permanencia | cumulada? | [sim/nao] | R$ [___] |
| Tarifas (TAC/TEC/3os) | epoca/vedacao | [sim/nao] | R$ [___] |
| Juros vs taxa media | contratada x [TAXA_MEDIA_BACEN_%] | [indicio] | (instruir pericia) |

### GAP estimado
| Item | Cobrado pelo banco | Recalculado (previa) | Diferenca |
|---|---|---|---|
| Saldo / total | R$ [___] | R$ [___] | **R$ [___]** |

### Valor incontroverso (para deposito/consignacao na tutela)
R$ [___] — parcela que o cliente reconhece dever mesmo na hipotese pro-banco.

> ⚠️ SIMULACAO — NAO E LAUDO. Submeter a pericia contabil oficial. Taxa media
> BACEN nao hardcodada: validar no SGS para modalidade/mes do contrato.
```

## 7. PROIBICOES

1. NUNCA chamar de "laudo" nem fixar valor como definitivo.
2. NUNCA hardcodar taxa media BACEN — placeholder + link SGS sempre.
3. NUNCA afirmar "1,5x = abusivo" como tese fixada (e indiciario; Tema 1.378
   pendente — confirmar antes de citar).
4. NUNCA expurgar capitalizacao se pos 31/03/2000 + clausula expressa (Sum. 539).
5. NUNCA invocar Lei de Usura contra banco (Sum. 596 STF).
6. NUNCA confundir Tema 958 (servicos de 3os) com TAC/TEC (Sum. 565 + Tema 618/619).

## 8. INTEGRACAO

- **Downstream:** `peticao-revisional-bancaria` (a previa instrui os "fortes
  indicios" + o pedido de tutela/deposito), `gerador-quesitos-pericia-contabil`.
- **Auditoria:** toda citacao passa por `auditoria-juris-pre-envio`.

> ⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
