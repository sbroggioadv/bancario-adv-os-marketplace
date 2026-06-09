---
name: recursos-civeis-router
description: >
  RECURSOS-CIVEIS-ROUTER — Escolhe o recurso CIVEL certo por
  juizo: Embargos de Declaracao, Apelacao, Recurso Inominado
  (JEC), Agravo de Instrumento, REsp/RE. Da prazo, fundamento e
  ALERTA DE VIA. BLOQUEIO duro: no JEC NAO cabe Apelacao, REsp nem
  AI (FONAJE 15/63; Sum. 203 STJ); tutela no JEC vai por Mandado
  de Seguranca a Turma (FONAJE 62). Use quando o advogado disser:
  "qual recurso cabe", "vou recorrer", "apelar", "agravo de
  instrumento", "recurso inominado", "embargos de declaracao",
  "REsp", "recurso especial", "RE", "recurso extraordinario",
  "perdi no juizado", "perdi a sentenca", "indeferiram a pericia",
  "negaram a tutela", "prazo do recurso".
---

# RECURSOS-CIVEIS-ROUTER — Recurso certo por juizo

## 1. ESCOPO

Roteia para o recurso civel correto a partir de (a) o **juizo**
(JEC ou Justica Comum) e (b) **o que** se quer atacar (sentenca,
decisao interlocutoria, acordao, omissao). Evita o erro fatal de
interpor recurso incabivel no JEC. Perspectiva: cliente do banco.

---

## 2. INPUT NECESSARIO

Do contexto + perguntar:

1. **Juizo:** Juizado Especial Civel (JEC) ou Justica Comum?
2. **O que ataca:** sentenca de merito / decisao interlocutoria
   (tutela, indeferimento de pericia) / acordao / omissao-
   contradicao-obscuridade
3. Data da intimacao (para contar prazo)
4. Conteudo: foi indeferida pericia? negada tutela? extinto sem
   merito? (define cabimento de AI / MS)

---

## 3. TABELA — RECURSO POR SITUACAO (corpus §6)

| Recurso | Quando cabe | Prazo | Base |
|---|---|---|---|
| Embargos de Declaracao | omissao/contradicao/obscuridade/erro material | **5 dias** | CPC 1.022 |
| Apelacao | sentenca da **Justica Comum** | **15 dias uteis** | CPC 1.009 |
| Recurso Inominado | sentenca do **JEC** | **10 dias** | Lei 9.099 art. 41 |
| Agravo de Instrumento | rol CPC 1.015 (inclui **tutela**, inc. I); cabe contra indeferimento de **pericia** (Tema 988 — taxatividade mitigada) | **15 dias uteis** | CPC 1.015 |
| REsp / RE | acordao (CF 105 III / 102 III); **prequestionamento**; RE exige **repercussao geral** | **15 dias uteis** | CF + CPC 1.029 |

**Contagem:** dias **uteis** na Justica Comum (CPC 219). No JEC,
prazo do Recurso Inominado = **10 dias** (regra propria da Lei
9.099 — conferir contagem conforme orientacao local).

---

## 4. BLOQUEIO DE VIA — JEC ⚠️ (erro fatal)

🔴 **No JEC NAO cabe Apelacao, NAO cabe REsp, NAO cabe Agravo de
Instrumento** (FONAJE 15 e 63; Sumula 203 STJ).

| Situacao no JEC | Via correta |
|---|---|
| Sentenca de merito | **Recurso Inominado** (10 dias) a Turma Recursal |
| Acordao da Turma Recursal | so **Embargos de Declaracao** e **RE** (CF 102 III + repercussao geral) — **nao** cabe REsp |
| Tutela/liminar no JEC | **Mandado de Seguranca** a Turma Recursal (FONAJE 62) — nao cabe AI |
| Decisao interlocutoria comum | em regra **nao** ha agravo no rito da Lei 9.099 |

Se o caso exige pericia contabil (revisional), ele provavelmente
**nao deveria** estar no JEC (FONAJE 70/94) → conferir
`classificador-foro-jec-comum` antes de recorrer.

---

## 5. OUTPUT — RECOMENDACAO

```markdown
## Recurso recomendado

| Campo | Valor |
|---|---|
| Juizo de origem | [JEC / Justica Comum] |
| Ato atacado | [sentenca / interlocutoria / acordao / omissao] |
| **Recurso indicado** | [ED / Apelacao / Inominado / AI / REsp / RE / MS] |
| Prazo | [N dias — uteis ou corridos] |
| Fundamento | [CPC 1.022 / 1.009 / Lei 9.099 41 / 1.015 / CF] |
| ⚠️ Alerta de via | [ex.: JEC — NAO interpor Apelacao/REsp/AI] |

### Requisitos especificos
- ED: apontar exatamente o vicio (omissao/contradicao/obscuridade)
- REsp/RE: prequestionar (se faltou, **opor ED** antes); RE exige
  preliminar formal de repercussao geral
- AI contra indeferimento de pericia: invocar Tema 988
  (taxatividade mitigada) + cerceamento de defesa
- MS no JEC: demonstrar ilegalidade/abuso + direito liquido e
  certo (tutela so via MS, FONAJE 62)
```

---

## 6. FUNDAMENTACAO LEGAL

- **CPC 1.022** (ED) · **1.009** (apelacao) · **1.015** (AI, rol;
  inc. I tutela) · **1.029** (REsp/RE) · **219** (dias uteis)
- **Lei 9.099 art. 41** (recurso inominado) · **art. 3o, I** (teto)
- **CF 105, III** (REsp) · **102, III** (RE)
- **FONAJE 15 e 63** — nao cabe AI no JEC
- **FONAJE 62** — tutela no JEC atacada por MS a Turma
- **Sumula 203 STJ** — nao cabe REsp contra acordao de Turma
  Recursal de JEC
- **Tema 988 STJ** — taxatividade mitigada do art. 1.015 (AI
  contra indeferimento de pericia)

> Estes sao enunciados/normas processuais estaveis. Ainda assim,
> conferir vigencia e adaptacoes locais antes de protocolar.

---

## 7. INTEGRACAO

**Upstream:** `bancario-master` · `classificador-foro-jec-comum`
(define o juizo) · `replica-contestacao`.
**Downstream:** `auditoria-juris-pre-envio` (GATE) ·
`protocolo-p4-bancario`.

## 💡 Proximos passos opcionais
| Proximo passo | Comando | Plugin |
|---|---|---|
| Buscar julgado para o REsp/RE | `/juris buscar` | juris-adv-os |
| Auditoria final com IA | `/ia-combativa suprema-corte-r1-r4` | ia-combativa-adv-os |

> Se plugin nao instalado, usar a recomendacao acima manualmente.

---

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
