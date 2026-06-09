---
name: recomendador-perito-contabil
description: >
  RECOMENDADOR-PERITO-CONTABIL — Orienta a busca e a contratacao de
  perito contabil quando ha fortes indicios de abusividade na
  revisional bancaria, e ADVERTE sobre o CUSTEIO de forma honesta.
  Regra dura do custeio: adianta os honorarios quem requer a pericia
  (CPC art. 95); a inversao do onus da prova (CDC 6º VIII) NAO
  custeia a pericia — e regra de julgamento, nao de adiantamento
  (Tema 1.024); na gratuidade de justica, a pericia corre por
  recursos publicos. Mensagem honesta ao cliente: salvo gratuidade,
  provavelmente sera ele a adiantar o perito — isso e fator de
  viabilidade do caso. Use quando o advogado/cliente disser
  "preciso de perito contabil", "quem paga o perito", "custo da
  pericia", "honorarios periciais", "vale a pena periciar",
  "contratar perito", "assistente tecnico", "Tema 1.024",
  "inversao paga a pericia?" ou estiver decidindo se a revisional e
  viavel diante do custo.
---

# RECOMENDADOR-PERITO-CONTABIL — Quando contratar e quem custeia

## 1. ESCOPO

Duas funções:
1. **Orientar** a busca/contratação de perito contábil (e assistente técnico)
   quando há **fortes indícios** de abusividade.
2. **Advertir, com honestidade, sobre o CUSTEIO** — é o que separa caso
   viável de aventura jurídica que morre na falta de adiantamento.

> Este plugin entrega **prévia/indício** auditável
> (`previa-abusividade-revisional`), **não** laudo oficial. O laudo é do
> perito. Esta skill faz a ponte realista até ele.

---

## 2. QUANDO RECOMENDAR PERÍCIA

Há **fortes indícios** (gatilhos da prévia) quando:
- Taxa efetiva muito acima da taxa média BACEN da modalidade/período
- Capitalização infra-anual sem cláusula expressa (ou contrato pré-2000)
- Comissão de permanência cumulada com outros encargos (Súm. 472)
- TAC/TEC/serviços de terceiros vedados pelos marcos (Súm. 565/Tema 958)
- Divergência relevante Price × SAC

> Sem fortes indícios → não pedir perícia "no escuro" (custo + risco de
> indeferimento). A prévia documenta o indício para fundamentar o pedido.

---

## 3. A REGRA DURA DO CUSTEIO ⚠️ (mensagem honesta)

| Situação | Quem adianta os honorários do perito |
|---|---|
| Cliente **requer** a perícia | **O cliente adianta** (CPC art. 95) |
| **Inversão do ônus** deferida (CDC 6º VIII) | **NÃO custeia** a perícia — é regra de **julgamento**, não de adiantamento (**Tema 1.024**) |
| Cliente é **beneficiário da gratuidade** (98 CPC) | A perícia corre por **recursos públicos** |

> **Tema 1.024 STJ:** a inversão do ônus da prova **não** transfere ao banco
> o **ônus financeiro** da perícia. Muita gente confunde — e o caso quebra
> quando chega a hora de depositar e o cliente não esperava.

### Texto-modelo para alinhar com o cliente
> "Para provar a abusividade precisamos de perícia contábil. Por regra,
> **quem pede a perícia adianta os honorários do perito** (CPC 95). A
> inversão do ônus da prova **não paga** a perícia (Tema 1.024 STJ). A
> exceção é a **gratuidade de justiça** — aí a perícia corre por recursos
> públicos. **Salvo gratuidade, provavelmente você adiantará o perito.**
> Por isso medimos antes se o ganho esperado da revisão compensa esse custo."

---

## 4. FATOR DE VIABILIDADE (decisão antes de ajuizar)

```
Ganho estimado (gap da prévia, R$) ......... R$ ______
(–) Honorários periciais estimados ......... R$ ______
(–) Custas/risco de sucumbência ............ R$ ______
= Saldo esperado / viabilidade ............. R$ ______
```

- Saldo positivo e relevante → recomendar (com perícia).
- Saldo apertado **e** sem gratuidade → conversar francamente: pode não
  compensar; avaliar acordo/repactuação como alternativa.
- Com gratuidade → barreira de custeio cai; recomendar.

---

## 5. ORIENTAÇÕES PRÁTICAS

- Indicar **perito contábil** (CRC ativo) e, idealmente, **assistente técnico**
  da parte para acompanhar e impugnar o laudo oficial.
- Reunir documentos para o perito: contrato + aditivos, demonstrativo do
  banco, comprovantes de pagamento, extratos.
- Pedir, junto, os **quesitos** (`gerador-quesitos-pericia-contabil`).
- Requerer gratuidade (98 CPC) **na inicial** quando cabível — é o que viabiliza.

---

## 6. FUNDAMENTAÇÃO

- **CPC art. 95** — adiantamento dos honorários periciais por quem requer
- **CDC art. 6º VIII** — inversão do ônus da prova (regra de julgamento)
- **Tema 1.024 STJ** — inversão NÃO custeia a perícia
- **CPC art. 98** — gratuidade de justiça (perícia por recursos públicos)
- **Tema 988 STJ** — taxatividade mitigada (CPC 1.015) → cabe AI contra
  indeferimento de perícia (cerceamento) *(confirmar antes de citar)*

---

## 7. PROIBIÇÕES

1. **NUNCA** dizer que a inversão do ônus paga a perícia (Tema 1.024).
2. **NUNCA** prometer perícia gratuita sem gratuidade deferida.
3. **NUNCA** recomendar perícia sem fortes indícios documentados na prévia.
4. **NUNCA** omitir do cliente que ele provavelmente adiantará o perito.
5. **NUNCA** apresentar a prévia do plugin como se fosse o laudo oficial.

---

## 8. INTEGRAÇÃO

**Upstream:** `peticao-revisional-bancaria` (auto-anexa) ·
`gerador-quesitos-pericia-contabil` · `previa-abusividade-revisional`
**Downstream:** `gratuidade-e-prioridade` (se cabível) →
`auditoria-juris-pre-envio` → `protocolo-p4-bancario`

> Cross-link soft (sugestão, não execução): auditar o laudo do perito quando
> entregue → `/calculos auditor-laudo-pericial-contabil`
> (calculosjudiciais-adv-os).

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
