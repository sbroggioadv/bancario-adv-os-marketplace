---
name: prescricao-bancaria
description: >
  PRESCRICAO-BANCARIA — Classifica a pretensao do cliente do banco
  e o prazo prescricional, com alerta de DIVERGENCIA real:
  revisional/repeticao de indebito CONTRATUAL → decenal (CC 205,
  posicao majoritaria STJ); reparacao por FRAUDE/fato do servico →
  5 anos (CDC 27) se sob CDC, ou 3 anos (CC 206 §3o V) se
  responsabilidade civil pura. Define termo inicial e sinaliza a
  divergencia honestamente. Use quando o advogado disser:
  "prescricao", "prescreveu", "qual o prazo", "prazo
  prescricional", "decadencia", "ainda da tempo de entrar",
  "quando comeca a contar", "prescricao revisional", "prescricao
  da fraude", "decenal ou trienal", "5 anos ou 3 anos".
---

# PRESCRICAO-BANCARIA — Prazo por pretensao (com divergencia)

## 1. ESCOPO

Classifica a **pretensao** do cliente do banco e aponta o prazo
prescricional aplicavel + termo inicial. O ponto critico: o prazo
**muda conforme o enquadramento** (contratual vs fato do servico
vs responsabilidade civil pura) e ha **divergencia real** — esta
skill mapeia, nao esconde. Perspectiva: cliente.

---

## 2. TABELA — PRAZO POR PRETENSAO (corpus §6) ⚠️ divergencia

| Pretensao | Prazo | Base | Nota |
|---|---|---|---|
| **Revisional / repeticao de indebito CONTRATUAL** (juros, tarifas, anatocismo expurgado) | **decenal (10 anos)** | CC art. 205 | posicao **majoritaria** do STJ (ausencia de prazo especifico) |
| **Reparacao por FRAUDE / fato do servico** sob CDC | **5 anos** | CDC art. 27 | quando a relacao e de consumo e o pedido e reparacao por defeito do servico |
| **Reparacao civil pura** (responsabilidade extracontratual) | **3 anos** | CC art. 206, §3o, V | quando enquadrada como reparacao civil, fora do microssistema CDC |

> 🟡 **Enquadramento e por caso.** O mesmo fato pode ser lido como
> fato do servico (CDC 27, 5 anos) ou reparacao civil (CC 206 §3o
> V, 3 anos). Sinalizar a divergencia ao advogado e adotar o
> enquadramento mais defensavel/favoravel, fundamentando.

---

## 3. TERMO INICIAL (quando comeca a correr)

- **Revisional/indebito:** em regra, da **celebracao** do contrato
  ou de cada **pagamento** indevido (teoria da actio nata aplicada
  por parcela; conferir orientacao do tribunal competente).
- **Fraude/fato do servico:** do **conhecimento do dano e da
  autoria** (actio nata subjetiva) — em golpe, tipicamente quando
  a vitima percebe a movimentacao/descobre a fraude.
- Causas de **interrupcao/suspensao** (CC 202): notificacao,
  protocolo administrativo, reconhecimento pelo devedor — checar.

---

## 4. INPUT NECESSARIO

Do contexto + perguntar:

1. **Natureza da pretensao:** revisar contrato? repetir indebito?
   reparar dano por fraude/golpe?
2. Relacao de consumo (CDC) ou empresarial (CC)?
3. Data do contrato / de cada cobranca / do conhecimento da fraude
4. Houve notificacao, protocolo administrativo, reconhecimento de
   divida? (interrupcao/suspensao)
5. Ja ha decisao do TJ competente sobre o enquadramento?

---

## 5. OUTPUT — DIAGNOSTICO

```markdown
## Diagnostico de prescricao

| Campo | Valor |
|---|---|
| Pretensao | [revisional / indebito / reparacao por fraude] |
| Regime | [consumo (CDC) / civil (CC)] |
| **Prazo aplicavel** | [10 anos (CC 205) / 5 anos (CDC 27) / 3 anos (CC 206 §3o V)] |
| Termo inicial | [celebracao / cada pagamento / conhecimento do dano] |
| Interrupcao/suspensao | [notificacao / protocolo / nenhuma] |
| Prescreveu? | [nao / sim / risco — depende do enquadramento] |

### ⚠️ Divergencia a sinalizar
[Se fraude/fato do servico: explicar que 5 anos (CDC 27) e 3 anos
(CC 206 §3o V) disputam o enquadramento; indicar a tese adotada e
por que. Se revisional: registrar que o decenal (CC 205) e
majoritario mas conferir entendimento do TJ competente.]
```

---

## 6. FUNDAMENTACAO LEGAL

- **CC art. 205** — prazo geral decenal (revisional/indebito
  contratual, na ausencia de prazo especifico)
- **CC art. 206, §3o, V** — reparacao civil em 3 anos
- **CDC art. 27** — reparacao por fato do produto/servico em 5
  anos (do conhecimento do dano e da autoria)
- **CC art. 202** — causas de interrupcao
- **CDC art. 26** — decadencia (vicio aparente) — distinguir de
  prescricao (fato do servico)

> 🟡 Prazos por pretensao envolvem divergencia jurisprudencial
> real. Conferir o entendimento ATUAL do TJ/STJ competente antes
> de afirmar que prescreveu ou nao.

---

## 7. PROIBICOES

1. **NUNCA afirmar um prazo unico** para "acao bancaria" — depende
   da pretensao e do enquadramento.
2. **NUNCA esconder a divergencia** 5 anos (CDC) × 3 anos (CC) em
   fraude — sinalizar sempre.
3. **NUNCA confundir prescricao com decadencia** (vicio aparente
   CDC 26 × fato do servico CDC 27).
4. **NUNCA ignorar interrupcao/suspensao** (CC 202) — pode salvar
   pretensao aparentemente prescrita.

---

## 8. INTEGRACAO

**Upstream:** `bancario-master` · `triagem-caso-bancario`.
**Downstream:** skill de peticao da frente · `replica-contestacao`
(se o banco arguir prescricao) · `auditoria-juris-pre-envio`
(GATE) · `protocolo-p4-bancario`.

## 💡 Proximos passos opcionais
| Proximo passo | Comando | Plugin |
|---|---|---|
| Buscar entendimento atual do TJ/STJ | `/juris buscar` | juris-adv-os |
| Auditoria final com IA | `/ia-combativa suprema-corte-r1-r4` | ia-combativa-adv-os |

> Se plugin nao instalado, usar o diagnostico acima manualmente.

---

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
