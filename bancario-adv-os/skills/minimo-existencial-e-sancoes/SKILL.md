---
name: minimo-existencial-e-sancoes
description: >
  MINIMO-EXISTENCIAL-E-SANCOES — Duas frentes do superendividamento.
  (a) Calcula o comprometimento de renda x minimo existencial = R$
  600,00 (Decreto 11.567/2023), JA COMPUTANDO o consignado (STF
  ADPFs 1005/1006/1097, concluido 23/04/2026: consignado integra o
  computo + CMN revisa anualmente). (b) Define as sancoes ao
  credor: FALTAR a audiencia pune (suspensao da exigibilidade +
  interrupcao dos encargos + sujeicao compulsoria — CDC 104-A §2º +
  REsp 2.168.199, inclusive na fase administrativa); COMPARECER e
  nao propor acordo NAO pune (REsp 2.188.689) → vai ao plano
  compulsorio 104-B. Use quando o cliente/advogado disser "minimo
  existencial", "R$ 600", "quanto posso comprometer", "consignado
  conta", "margem consignavel", "credor faltou na audiencia",
  "sancao ao credor", "104-A §2º", "credor nao propos acordo" ou
  precisar dimensionar a parcela e a estrategia da audiencia.
---

# MINIMO-EXISTENCIAL-E-SANCOES — Cálculo + estratégia de audiência

## PARTE A — MÍNIMO EXISTENCIAL (quanto pode comprometer)

### 1. Valor vigente
- **Mínimo existencial = R$ 600,00** (Decreto 11.567/2023, de 19/06/2023;
  valor vigente jun/2026). Substituiu o Decreto 11.150/2022 (que era 25%
  do salário mínimo).
- **STF — ADPFs 1005/1006/1097 (concluído 23/04/2026):**
  - (unânime) o **CMN deve revisar anualmente** o mínimo existencial;
  - (maioria) o **consignado INTEGRA o cômputo** do mínimo — não pode
    comprometê-lo;
  - **não** declarou inconstitucional o valor de R$ 600.

> ⚠️ Mudança de jogo: antes muitos tribunais somavam consignado **por fora**.
> Agora o consignado entra na conta — o que **reduz** a margem disponível e
> **reforça** a tese de superendividamento de quem já tem consignado pesado.

### 2. Cálculo do comprometimento

```
Renda líquida mensal .................. R$ ______
(–) Mínimo existencial (R$ 600,00) .... R$  600,00
(–) Consignado já existente ........... R$ ______   ← AGORA conta (STF abr/2026)
= Margem disponível para o plano ...... R$ ______
```

| Item | Valor |
|---|---|
| Renda líquida | R$ _____ |
| Mínimo existencial | R$ 600,00 |
| Consignado em curso | R$ _____ (integra o cômputo) |
| **Margem para repactuação** | **R$ _____** |

**Leitura:** se a margem é zero ou negativa, há impossibilidade manifesta de
pagar sem sacrificar o mínimo — confirma o enquadramento (54-A §1º) e baliza
o teto da parcela do plano (`repactuacao-104a-104b`).

> Validar o valor de R$ 600 antes de protocolar (CMN revisa anualmente —
> pode ter sido atualizado). Citar a fonte oficial e a data.

---

## PARTE B — SANÇÕES AO CREDOR (a diferença que decide a estratégia)

### 3. Faltar × comparecer-sem-propor

| Conduta do credor | Sanção? | Base | Efeito |
|---|---|---|---|
| **FALTA** à audiência | **SIM** | CDC 104-A §2º + REsp 2.168.199 | Suspensão da exigibilidade + interrupção dos encargos + **sujeição compulsória** ao plano |
| **COMPARECE e não propõe acordo** | **NÃO** | REsp 2.188.689 | Sem punição — a obrigação de propor o plano é do **devedor**; segue para o **plano compulsório (104-B)** |

### 4. Detalhe dos precedentes
- **REsp 2.168.199 (T3, j. 26/02/2025):** o credor que **falta** à
  audiência conciliatória sofre as sanções do 104-A §2º — e isso vale
  **inclusive na fase administrativa** (Procon/SNDC), não só na judicial.
- **REsp 2.188.689 (T4, j. 23/06/2025):** o credor que **comparece mas não
  propõe acordo NÃO é sancionado** — o dever de apresentar o plano é do
  devedor; a recusa leva ao plano compulsório, não à punição do credor.

### 5. Consequência prática na audiência
- Por isso a intimação **com poderes especiais para transigir** + advertência
  do §2º é load-bearing (ver `repactuacao-104a-104b`): força presença útil.
- Se o credor **faltar** → pleitear de imediato as três sanções do §2º.
- Se o credor **comparecer e travar** → não pedir sanção (perde-se
  credibilidade); requerer a conversão em **plano compulsório (104-B)**.

---

## 6. FUNDAMENTAÇÃO

- **Decreto 11.567/2023** — mínimo existencial R$ 600,00
- **STF ADPFs 1005/1006/1097** (concluído 23/04/2026) — CMN revisa
  anualmente + consignado integra o cômputo
- **CDC 104-A §2º** — sanções por não comparecimento
- **REsp 2.168.199** (T3) — falta pune (inclusive fase administrativa)
- **REsp 2.188.689** (T4) — comparecer sem propor NÃO pune → 104-B
- **CDC 54-A §1º** — mínimo existencial como núcleo do conceito

---

## 7. PROIBIÇÕES

1. **NUNCA** somar consignado "por fora" do mínimo (STF abr/2026: integra).
2. **NUNCA** hardcodar R$ 600 sem checar atualização anual do CMN.
3. **NUNCA** pedir sanção contra credor que **compareceu** (REsp 2.188.689).
4. **NUNCA** propor parcela que invada o mínimo existencial.
5. **NUNCA** afirmar que a sanção do §2º depende de má-fé — basta a falta.

---

## 8. INTEGRAÇÃO

**Upstream:** `triagem-superendividamento` · `repactuacao-104a-104b`
**Downstream:** alimenta o teto de parcela do plano em `repactuacao-104a-104b`;
peça final → `auditoria-juris-pre-envio` → `protocolo-p4-bancario`

> Cross-link soft (sugestão, não execução): memória de cálculo da margem →
> `/calculos` (calculosjudiciais-adv-os).

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
