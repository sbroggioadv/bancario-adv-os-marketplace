---
name: classificador-foro-jec-comum
description: >
  CLASSIFICADOR FORO JEC x COMUM — Tier 1, gate pre-peticao que decide
  se a acao bancaria vai ao Juizado Especial Civel (JEC) ou a Justica
  Comum. Aplica as regras do FONAJE: teto JEC = 40 salarios minimos
  (Lei 9.099 art. 3o I; FONAJE 133); complexidade aferida pelo OBJETO
  DA PROVA, nao pelo direito material (FONAJE 54); revisional ou
  qualquer causa que EXIJA PERICIA CONTABIL vai a Justica Comum mesmo
  abaixo de 40 SM (FONAJE 70 e 94); dano moral com valor certo SOMA ao
  material na alcada (FONAJE 170). Alerta critico: revisional com
  pericia ajuizada no JEC = extincao sem resolucao de merito. Output:
  juizo recomendado + fundamento + alerta + tabela materia -> juizo.
  Use antes de redigir qualquer peticao inicial bancaria, ou quando o
  advogado disser: JEC ou justica comum, juizado especial, qual vara,
  cabe no juizado, teto do juizado, vai precisar de pericia.
---

# CLASSIFICADOR FORO JEC × COMUM

> Skill **Tier 1** e gate pré-petição: decide **JEC** ou **Justiça Comum** ANTES de redigir a inicial. Erro aqui custa caro — revisional com perícia no JEC é extinta sem mérito (perde-se prazo, custas e, às vezes, prescrição).

---

## 0. ESCOPO E ACIONAMENTO

Roda sempre antes de toda petição inicial bancária (auto-chain bloqueante junto com `varredura-jurisprudencial-pre-tese`). Acionada por `bancario-master`, `triagem-caso-bancario` ou `/bancario foro`. Base: FONAJE (literal) + Lei 9.099/95 art. 3º.

## 1. AS REGRAS (FONAJE — corpus §6)

| Regra | Conteúdo |
|---|---|
| **Teto JEC** | 40 salários mínimos (Lei 9.099 art. 3º I; **FONAJE 133**). Acima de 40 SM → Justiça Comum (no JEC, > 20 SM exige advogado; > 40 SM não cabe). |
| **FONAJE 54** | Complexidade é aferida pelo **objeto da prova**, NÃO pelo direito material. Tese difícil ≠ causa complexa; prova difícil = causa complexa. |
| **FONAJE 70** | Ilegalidade de juros **não** é complexa — **EXCETO quando exigir perícia contábil**. |
| **FONAJE 94** | Revisão de contrato **cabe no JEC** — **EXCETO quando exigir perícia contábil**. |
| **FONAJE 170** | Dano moral com **valor certo SOMA** ao valor material para alçada/custas. |

**Consequência operacional:**
- **Revisional / qualquer causa que EXIJA perícia contábil → Justiça Comum** (mesmo abaixo de 40 SM). A perícia é prova complexa (FONAJE 54/70/94).
- **Fraude simples (PIX + dano moral documental, sem perícia) → JEC** é opção válida do autor (até 40 SM), com vantagem de celeridade e isenção de custas em 1º grau.

---

## 2. PROCESSO DE DECISAO

### Passo 1 — A causa exige perícia contábil?
- Revisional de juros/anatocismo/Price×SAC, recálculo de saldo, comissão de permanência cumulada, tarifas a expurgar → **exige perícia → Justiça Comum**. Encerra aqui.
- Fraude com prova **documental** (extrato, comprovante PIX, contrato não reconhecido, print da conversa) → **não exige perícia** → segue.

### Passo 2 — Calcular o valor da causa
- Material (valor desviado / contrato / saldo discutido) **+** dano moral com valor certo (FONAJE 170).
- ≤ 40 SM → JEC possível. > 40 SM → Justiça Comum.

### Passo 3 — Há outro fator de complexidade probatória?
- Necessidade de exibição judicial de documentos de terceiro (KYC do banco recebedor), prova pericial técnica, instrução extensa com muitas testemunhas → tende à **Justiça Comum** (FONAJE 54).

### Passo 4 — Decidir e fundamentar
Emitir juízo recomendado + fundamento FONAJE + alerta.

---

## 3. TABELA MATÉRIA → JUÍZO

| Matéria | Juízo recomendado | Fundamento |
|---|---|---|
| Revisional de contrato (juros/anatocismo/tarifas) | **Justiça Comum** | FONAJE 70/94 (perícia contábil) |
| Golpe PIX / falso funcionário (prova documental, ≤ 40 SM) | **JEC** (opção do autor) | FONAJE 54 (prova documental) + teto |
| Golpe falso advogado (prova documental, ≤ 40 SM) | **JEC** (opção) | FONAJE 54 + teto |
| Financiamento/empréstimo fraudulento — declaratória (documental) | **JEC** se ≤ 40 SM e sem perícia | FONAJE 54 + teto |
| Financiamento fraudulento exigindo exibição de KYC do banco recebedor | **Justiça Comum** | FONAJE 54 (prova complexa) |
| Defesa em busca e apreensão (DL 911/69) | **Justiça Comum** | rito próprio — não é JEC |
| Embargos à execução de CCB | **Justiça Comum** | execução de título — não é JEC |
| Superendividamento / repactuação 104-A/B | **Justiça Comum** | conciliação em bloco c/ todos credores — não é JEC |
| Causa > 40 SM (qualquer) | **Justiça Comum** | FONAJE 133 (teto) |
| Devolução em dobro isolada, valor certo, documental, ≤ 40 SM | **JEC** | teto + prova documental |

> Quando a tese for forte mas o valor exceder 40 SM, **não** fracionar artificialmente o pedido só para caber no JEC — é vedado e gera extinção.

---

## 4. OUTPUT

```
CLASSIFICAÇÃO DE FORO

Matéria: <ex: revisional de contrato de financiamento>
Exige perícia contábil? <SIM / NÃO>
Valor da causa: material R$ ___ + dano moral certo R$ ___ = R$ ___ (___ SM)
Outros fatores de complexidade probatória: <exibição KYC / nenhum>

JUÍZO RECOMENDADO: <JEC / JUSTIÇA COMUM>
FUNDAMENTO: <FONAJE 54/70/94/133/170 + Lei 9.099 art. 3º I>

⚠️ ALERTA: <ex: "Revisional com perícia ajuizada no JEC = extinção sem
resolução de mérito (FONAJE 70/94). Ajuizar na Justiça Comum.">

IMPACTO RECURSAL: <JEC → Recurso Inominado (10d), NÃO cabe Apelação/REsp/AI
(FONAJE 15/63, Súm. 203 STJ) | Comum → Apelação 15d, AI, REsp>
```

> O **impacto recursal** é load-bearing: escolher JEC fecha a porta para Apelação, REsp e Agravo de Instrumento. Em causa que provavelmente vai a tribunais superiores, isso pesa contra o JEC.

---

## 5. VEDACOES

1. **Nunca** mandar revisional (ou causa com perícia contábil) ao JEC — FONAJE 70/94. Extinção certa.
2. **Nunca** fracionar pedido para forçar o enquadramento ≤ 40 SM.
3. **Nunca** esquecer de somar o dano moral com valor certo ao material (FONAJE 170) — pode estourar o teto.
4. **Nunca** propor JEC em busca e apreensão, execução de CCB ou superendividamento (ritos próprios, fora do JEC).
5. **Sempre** sinalizar o impacto recursal da escolha (porta fechada para Apelação/REsp no JEC).

## 6. INTEGRACAO

Acionada por: `bancario-master`, `triagem-caso-bancario`, `/bancario foro`. Auto-chain com `varredura-jurisprudencial-pre-tese` antes de toda inicial. Fornece o **juízo/TJ** que a varredura usa para mirar a busca. Downstream: a skill de petição da trilha redige no juízo confirmado.

---

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
