---
name: detector-encargos-abusivos
description: >
  DETECTOR-ENCARGOS-ABUSIVOS — Checklist juridico encargo por encargo de contrato
  bancario do cliente-devedor. Para cada cobranca aplica o teste correto e o
  status jurisprudencial atual: capitalizacao infra-anual (Sum. 539/541 + Tema
  246/247 + MP 2.170-36); Price x SAC (NAO e anatocismo automatico); comissao de
  permanencia cumulada (Sum. 30/294/296/472); TAC/TEC (Sum. 565 + Tema 618/619 —
  so ate 30/04/2008); servicos de terceiros/correspondente (Tema 958 = REsp
  1.578.553/SP — abusivo pos 25/02/2011); juros > 12% por si so nao e abusivo
  (Sum. 382); Sum. 596 STF (bancos fora da Lei de Usura). Devolve tabela
  encargo|teste|status|expurgar. Use quando o advogado disser: "quais encargos
  posso atacar", "checklist de abusividade", "comissao de permanencia",
  "anatocismo Price ou SAC", "TAC TEC abusiva", "tarifa de cadastro",
  "servicos de terceiros", "registro do contrato", "encargos do financiamento".
---

# DETECTOR-ENCARGOS-ABUSIVOS — Checklist encargo por encargo

> Mapeia cada cobranca do contrato ao teste juridico e ao status atual da
> jurisprudencia. Saida = tabela acionavel: o que expurgar e por que.

## 1. INPUT NECESSARIO

- Contrato + aditivos · data do contrato · natureza (CDC/CC) · lista de
  encargos/tarifas cobradas (do contrato e do demonstrativo do banco).
- Marcos de data que mudam o veredito: **31/03/2000** (capitalizacao),
  **30/04/2008** (TAC/TEC), **25/02/2011** (servicos de terceiros),
  **30/06/2024** (Lei 14.905/2024 — taxa legal supletiva).

## 2. TESTES POR ENCARGO (corpus validado)

### a) Capitalizacao infra-anual (anatocismo)
- Teste: `taxa_anual > 12 x taxa_mensal` → ha capitalizacao mensal embutida.
- Licita SE: contrato **pos 31/03/2000** (MP 2.170-36/2001 art. 5º, perene via
  EC 32/2001) **+ clausula expressa**.
- **Sum. 539:** capitalizacao inferior a anual licita = pos 31/03/2000 + clausula
  expressa. **Sum. 541:** taxa anual > duodecuplo da mensal **basta** como
  pactuacao expressa. **Tema 246/247 (REsp 973.827/RS):** repetitivo que gerou
  539/541.
- Sem clausula OU pre-31/03/2000 → **expurgar** (recalcular sem capitalizacao).

### b) Price x SAC
- Price (parcela constante) **NAO e anatocismo automatico**. STJ admite Price com
  clausula expressa + pos-31/03/2000 (Sum. 539). Comparativo formal com SAC
  (amortizacao constante) pode **revelar** excesso, mas Price em si nao expurga.
- Veredito: so atacar se faltar pactuacao expressa de capitalizacao.

### c) Comissao de permanencia
- **Sum. 30:** nao cumula com correcao monetaria. **Sum. 294:** licita pela taxa
  media BACEN, **limitada a taxa do contrato**. **Sum. 296:** juros remuneratorios
  na inadimplencia = taxa media BACEN limitada ao % contratado. **Sum. 472:**
  exclui juros remun./morat. e multa (nao cumula).
- Veredito: licita **isolada**; **expurgar** se cumulada com qualquer outro
  encargo moratorio.

### d) TAC / TEC (tarifa de cadastro / emissao de carne)
- **Sum. 565 + Tema 618/619 (REsp 1.251.331/RS):** validas SO em contratos
  **anteriores a 30/04/2008**; ilicitas apos.
- Veredito: contrato pos 30/04/2008 → **expurgar**.

### e) Servicos de terceiros / comissao de correspondente
- **Tema 958 (REsp 1.578.553/SP):** abusivo **pos 25/02/2011**. Registro do
  contrato e avaliacao do bem licitos se **efetivamente prestados**.
- 🔴 Anti-alucinacao: REsp 1.578.553 = **Tema 958 (servicos de 3os)**, NAO e o
  repetitivo de TAC/TEC. Nao confundir.
- Veredito: servicos de 3os pos 25/02/2011 → **expurgar**; registro/avaliacao →
  depende de prestacao efetiva.

### f) Juros remuneratorios "altos"
- **Sum. 382:** juros > 12% a.a. **por si so** NAO indicam abusividade.
- **Sum. 596 STF:** bancos do SFN **nao** se sujeitam a Lei de Usura (reforcado
  pelo art. 3º da Lei 14.905/2024).
- Veredito: so atacar com **abusividade cabalmente demonstrada** (Tema 27),
  comparando com taxa media BACEN — **placeholder, nunca hardcodar valor**
  (consultar SGS em bcb.gov.br). ⚠️ Tema 1.378 pendente (confirmar antes de citar
  taxa media como criterio isolado).

### g) Multa / encargos moratorios
- Multa moratoria maxima **2%** (CDC art. 52 §1º). Acima → expurgar excesso.

## 3. OUTPUT — TABELA DE DETECCAO

```markdown
## Detector de encargos abusivos
Contrato: [tipo] · data [dd/mm/aaaa] · natureza [CDC|CC]

| Encargo | Teste aplicado | Status jurisprudencial | Expurgar? |
|---|---|---|---|
| Capitalizacao | anual > 12x mensal? clausula expressa? data | Sum. 539/541 + MP 2.170-36 | [sim/nao] |
| Price/SAC | pactuacao expressa? | Sum. 539 (Price nao = anatocismo) | [nao/depende] |
| Comissao permanencia | cumulada? | Sum. 30/294/296/472 | [sim se cumulada] |
| TAC / TEC | data x 30/04/2008 | Sum. 565 + Tema 618/619 | [sim se pos] |
| Servicos de 3os | data x 25/02/2011 | Tema 958 (REsp 1.578.553/SP) | [sim se pos] |
| Registro / avaliacao | prestado de fato? | Tema 958 | [depende] |
| Juros remuneratorios | vs [TAXA_MEDIA_BACEN_%] | Sum. 382/596 + Tema 27 | [so com prova] |
| Multa moratoria | > 2%? | CDC 52 §1º | [excesso] |

> ⚠️ Encargos a periciar para quantificar o expurgo: [lista]. Taxa media BACEN
> nao hardcodada — validar no SGS. Status em definicao: Tema 1.378 (juros) —
> confirmar antes de citar.
```

## 4. PROIBICOES

1. NUNCA expurgar capitalizacao se pos 31/03/2000 + clausula expressa.
2. NUNCA tratar Price como anatocismo automatico.
3. NUNCA invocar Lei de Usura contra banco (Sum. 596 STF).
4. NUNCA confundir Tema 958 (servicos de 3os) com TAC/TEC (Sum. 565/Tema 618/619).
5. NUNCA hardcodar taxa media BACEN.
6. NUNCA cumular expurgo de comissao de permanencia sem provar a cumulacao.

## 5. INTEGRACAO

- **Upstream:** `triagem-caso-bancario`, `previa-abusividade-revisional`.
- **Downstream:** `peticao-revisional-bancaria`, `gerador-quesitos-pericia-contabil`,
  `embargos-execucao-ccb` (mesmos testes para excesso de execucao).

> ⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
