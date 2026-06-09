---
name: triagem-superendividamento
description: >
  TRIAGEM-SUPERENDIVIDAMENTO — Classifica se o caso e
  superendividamento de pessoa fisica de BOA-FE (CDC art. 54-A
  §1º) e separa dividas ELEGIVEIS x EXCLUIDAS antes de repactuar.
  Excluidas: fraude/ma-fe e contratos dolosos + produtos de luxo
  de alto valor (54-A §3º); dividas com garantia real,
  financiamento imobiliario e credito rural (104-A §1º). Regra de
  ouro: expurgar fraude (inexigibilidade) e revisar abusivo ANTES
  de repactuar — so divida legitima e liquida entra no plano. Use
  quando o cliente disser "superendividado", "nao consigo pagar",
  "muitas dividas", "estourei", "vivendo de emprestimo",
  "comprometi tudo", "repactuar dividas", "Lei 14.181",
  "minimo existencial", "boa-fe" ou descrever multiplas dividas
  bancarias/cartao/consignado que nao consegue mais honrar.
---

# TRIAGEM-SUPERENDIVIDAMENTO — Porta de entrada da Lei 14.181/2021

## 1. ESCOPO

Decide DUAS coisas antes de qualquer repactuação:

1. O caso **se enquadra** no superendividamento (CDC 54-A §1º)?
2. **Quais dívidas entram** no plano (elegíveis) e quais ficam de fora (excluídas)?

> ⚠️ **REGRA DE OURO:** primeiro **expurgar fraude** (inexigibilidade do
> empréstimo não contratado) e **revisar o abusivo** — só dívida
> **legítima e líquida** entra no plano. Repactuar dívida fraudada =
> legitimar o golpe; repactuar valor abusivo = perder o que se ganharia
> na revisional.

---

## 2. INPUT NECESSÁRIO

Do contexto + perguntar:

1. **Perfil do devedor:** PF? (PJ e empresário individual NÃO entram)
2. **Renda mensal líquida** + composição do núcleo familiar
3. **Lista de TODAS as dívidas:** credor, tipo, valor, parcela, garantia
4. **Origem das dívidas:** consumo/sustento? ou luxo/jogo/má-fé?
5. **Reconhece todos os contratos?** (algum empréstimo não fez?)
6. **Suspeita de cláusula/juros abusivos** em algum contrato?
7. **Já houve renegociação anterior** que piorou o quadro?

---

## 3. TESTE DE ENQUADRAMENTO (CDC 54-A §1º)

| Requisito | Verificação |
|---|---|
| Pessoa física | sim / não → se não, NÃO se aplica |
| Boa-fé | dívidas de consumo/sustento, sem dolo? |
| Impossibilidade **manifesta** de pagar a totalidade | sim / não |
| Sem comprometer o **mínimo existencial** | renda – dívidas < mínimo? |

**Não basta estar endividado** — tem de ser impossibilidade manifesta de
pagar **sem sacrificar o mínimo existencial** (cálculo na skill
`minimo-existencial-e-sancoes`).

---

## 4. SEPARAÇÃO DÍVIDAS ELEGÍVEIS × EXCLUÍDAS

### Excluídas por MÁ-FÉ / LUXO (CDC 54-A §3º)
- Dívidas contraídas com **fraude ou má-fé**
- Contratos **dolosos** (ex.: contraiu sabendo que não pagaria)
- **Produtos/serviços de luxo de alto valor**

### Excluídas por NATUREZA (CDC 104-A §1º)
- Dívidas com **garantia real** (penhor, alienação fiduciária)
- **Financiamento imobiliário**
- **Crédito rural**

### Elegíveis (entram no plano)
- Cartão de crédito, crédito pessoal, cheque especial
- **Consignado** (entra; e desde abril/2026 conta no mínimo existencial)
- Financiamento de veículo **sem** discussão de garantia real *(confirmar antes de citar — interface garantia real × consumo)*
- Demais dívidas de consumo de boa-fé

> Tabela de triagem por dívida:

| Credor | Tipo | Valor | Garantia? | Origem | **Veredito** |
|---|---|---|---|---|---|
| [banco] | cartão | R$ _ | não | consumo | ELEGÍVEL |
| [banco] | imobiliário | R$ _ | imóvel | moradia | EXCLUÍDA (104-A §1º) |
| [financeira] | empréstimo não feito | R$ _ | — | **fraude** | EXPURGAR (inexigibilidade) |

---

## 5. ROTEAMENTO (cadeia obrigatória ANTES de repactuar)

1. **Há empréstimo que o cliente não fez / fraudado?**
   → chamar `financiamento-emprestimo-fraudulento` PRIMEIRO (ação de
   inexigibilidade). NÃO incluir esse valor no plano.

2. **Há contrato com juros/encargos abusivos?**
   → chamar `previa-abusividade-revisional`. O valor **revisado** (menor)
   é o que entra no plano, não o cobrado pelo banco.

3. Só depois → `repactuacao-104a-104b` com o passivo **líquido e legítimo**.

4. Em paralelo → `minimo-existencial-e-sancoes` (calcula o que pode
   comprometer; R$ 600 + consignado no cômputo, STF abr/2026).

---

## 6. FUNDAMENTAÇÃO

- **CDC art. 54-A** §1º (conceito/boa-fé) e **§3º** (exclui má-fé, dolo,
  luxo de alto valor) — Lei 14.181/2021
- **CDC art. 54-B/54-C/54-D** — dever de informar CET, práticas vedadas,
  crédito responsável
- **CDC art. 104-A §1º** — exclui garantia real, financiamento imobiliário
  e crédito rural da repactuação
- **Vigência:** Lei 14.181/2021 desde 02/07/2021
- ⚠️ Atenção: **CDC 54-E foi VETADO** — não existe texto vigente, não citar.

---

## 7. PROIBIÇÕES

1. **NUNCA repactuar** sem antes expurgar fraude e revisar abusivo.
2. **NUNCA incluir** no plano dívida de garantia real / imobiliário /
   rural (104-A §1º) — exclusão de natureza.
3. **NUNCA tratar PJ/empresário** como superendividado da Lei 14.181.
4. **NUNCA afirmar boa-fé** sem checar origem das dívidas (54-A §3º).
5. **NUNCA citar o art. 54-E** (vetado).

---

## 8. INTEGRAÇÃO

**Upstream:** `bancario-master` (triagem por conversa) · `triagem-caso-bancario`
**Downstream:** `financiamento-emprestimo-fraudulento` → `previa-abusividade-revisional`
→ `repactuacao-104a-104b` → `minimo-existencial-e-sancoes`

> Cross-link soft (sugestão, não execução): cálculo do passivo revisado →
> `/calculos calculo-revisao-bancaria` (calculosjudiciais-adv-os).

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
