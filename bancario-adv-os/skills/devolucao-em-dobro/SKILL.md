---
name: devolucao-em-dobro
description: >
  DEVOLUCAO-EM-DOBRO — Aplica a repeticao de indebito em dobro
  (CDC art. 42, paragrafo unico) sob o Tema 929 STJ. GATE DE MARCO
  TEMPORAL: cobranca indevida APOS 30/03/2021 = dobro independe de
  ma-fe (basta ser contraria a boa-fe objetiva); ANTES = simples
  (exige ma-fe comprovada). Diz quando pedir e como fundamentar.
  Use quando o advogado disser: "devolucao em dobro", "repeticao
  de indebito", "restituicao em dobro", "cobranca indevida",
  "art. 42 CDC", "Tema 929", "cobraram a mais", "desconto
  indevido", "valor cobrado sem causa", "pedir o dobro de volta".
---

# DEVOLUCAO-EM-DOBRO — Repeticao de indebito (CDC 42 §u + Tema 929)

## 1. ESCOPO

Estrutura o pedido de **restituicao em dobro** de valor cobrado
indevidamente do cliente do banco (parcela de emprestimo nao
contratado, desconto fraudulento, encargo abusivo expurgado,
tarifa vedada etc.). Perspectiva: cliente. O fio condutor e o
**marco temporal 30/03/2021** fixado pelo Tema 929.

---

## 2. GATE DE MARCO TEMPORAL ⚠️ (nucleo da skill)

```
Data da COBRANCA indevida ──► 
   APOS 30/03/2021  → DOBRO independe de ma-fe
                       (basta cobranca contraria a boa-fe objetiva)
   ATE  30/03/2021  → DOBRO so com MA-FE comprovada;
                       senao, restituicao SIMPLES
```

- A modulacao foi fixada nos **EAREsp 600.663/RS e 676.608/RS**
  (Corte Especial) e consolidada no **Tema 929 STJ**.
- **Reafirmacao:** EAREsp 1.501.756/SC (Corte Especial,
  21/02/2024, Info 803) — confirmar antes de citar o Info.
- "Contraria a boa-fe objetiva" e criterio **mais amplo** que
  ma-fe subjetiva: cobranca sem causa, desorganizacao do credor,
  encargo nulo cobrado — bastam, no periodo posterior ao marco.
- Marco-chave = a **data da cobranca**, nao a do contrato.

---

## 3. INPUT NECESSARIO

Do contexto + perguntar:

1. **Data(s) da cobranca** indevida (define o gate)
2. Natureza do indebito (parcela nao contratada / desconto
   fraudulento / encargo abusivo / tarifa vedada)
3. Houve **pagamento efetivo** pelo consumidor? (CDC 42 §u exige
   pagamento — valor apenas lancado/em aberto nao gera dobro)
4. Valores e competencias (para liquidacao)
5. Ha indicios de ma-fe? (necessario so se cobranca ate 30/03/2021)

---

## 4. PROCESSAMENTO

1. Confirmar que houve **pagamento** do valor indevido (requisito
   do art. 42 §u — sem pagamento, nao ha repeticao).
2. Aplicar o gate: cobranca apos 30/03/2021 → dobro objetivo;
   ate 30/03/2021 → avaliar ma-fe; se ausente → simples.
3. Afastar "engano justificavel" (unica excludente do dobro):
   erro escusavel real, nao mera alegacao generica do banco.
4. Quantificar: dobro = 2x o valor pago indevidamente, corrigido
   + juros (encaminhar calculo a skill/plugin de calculo).
5. Redigir o pedido com fundamento datado.

---

## 5. OUTPUT — BLOCO DE PEDIDO

```markdown
## Repeticao de indebito em dobro — pedido fundamentado

| Campo | Valor |
|---|---|
| Natureza do indebito | [parcela nao contratada / desconto / encargo] |
| Data(s) da cobranca | [dd/mm/aaaa] |
| Houve pagamento? | [sim — requisito do art. 42 §u] |
| Regime aplicavel | [DOBRO objetivo (pos 30/03/2021) / simples ou dobro c/ ma-fe (ate 30/03/2021)] |
| Valor pago indevidamente | R$ _____ |
| Valor a restituir (dobro) | R$ _____ (+ correcao + juros) |

> Requer a condenacao do banco-reu a restituir EM DOBRO o valor
> indevidamente cobrado e pago, na forma do art. 42, paragrafo
> unico, do CDC, c/c Tema 929 do STJ. As cobrancas ocorreram
> [apos 30/03/2021], de modo que o dobro independe de ma-fe,
> bastando a contrariedade a boa-fe objetiva (modulacao firmada
> nos EAREsp 600.663/RS e 676.608/RS, Corte Especial). Nao se
> configura "engano justificavel" (art. 42 §u, parte final),
> unica excludente cabivel.
```

---

## 6. FUNDAMENTACAO LEGAL

- **CDC art. 42, paragrafo unico** — repeticao em dobro do
  indevidamente cobrado e pago, salvo engano justificavel
- **Tema 929 STJ** — dobro independe de ma-fe; **modulacao para
  cobrancas posteriores a 30/03/2021**
- **EAREsp 600.663/RS + 676.608/RS** (Corte Especial) — origem da
  tese e do marco
- 🟡 **EAREsp 1.501.756/SC** (Corte Especial, 21/02/2024, Info
  803) — reafirmacao (confirmar antes de citar)

---

## 7. PROIBICOES

1. **NUNCA pedir dobro sem pagamento efetivo** do indevido (art.
   42 §u exige pagamento; valor so lancado → afastar dobro).
2. **NUNCA aplicar dobro objetivo a cobranca ate 30/03/2021** sem
   demonstrar ma-fe — fora do gate, e simples.
3. **NUNCA tratar "engano justificavel" como presuncao do banco**
   — o onus de demonstra-lo e do fornecedor.
4. **NUNCA hardcodar valores corrigidos** — encaminhar calculo a
   fonte com indices datados.

---

## 8. INTEGRACAO

**Upstream:** `bancario-master` · skills de fraude/revisional (que
identificam o indebito) · `replica-contestacao`.
**Downstream:** `auditoria-juris-pre-envio` (GATE) ·
`protocolo-p4-bancario`.

## 💡 Proximos passos opcionais
| Proximo passo | Comando | Plugin |
|---|---|---|
| Calcular o dobro corrigido | `/calculos restituicao-dobro-cdc` | calculosjudiciais-adv-os |
| Buscar julgado atual | `/juris buscar` | juris-adv-os |

> Se plugin nao instalado, usar o bloco de pedido acima manualmente.

---

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
