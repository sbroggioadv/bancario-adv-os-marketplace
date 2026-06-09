---
name: gerador-quesitos-pericia-contabil
description: >
  GERADOR-QUESITOS-PERICIA-CONTABIL — Emite os 8 quesitos
  essenciais ao perito contabil na revisional bancaria,
  parametrizados pelo tipo de contrato (CCB, financiamento de
  veiculo/imovel, leasing, cartao, cheque especial). Cobre: taxa
  efetiva x taxa media BACEN; capitalizacao infra-anual e se
  pactuada (Sum. 539/541); Price x SAC e anatocismo nao pactuado;
  comissao de permanencia cumulada (Sum. 30/296/472); TAC/TEC e
  servicos de terceiros vedados (Sum. 565 / Tema 618 / Tema 958);
  recalculo depurando ilegais + indebito simples/dobro (Tema 929);
  indices supletivos por epoca (multa max. 2% CDC 52; taxa legal
  Lei 14.905/2024); valor incontroverso x controvertido. Use
  quando o advogado disser "quesitos para o perito", "quesitos
  contabeis", "pericia contabil bancaria", "perguntas ao perito",
  "quesitos da revisional", "perito vai calcular", "rol de
  quesitos" ou estiver instruindo prova pericial em acao revisional.
---

# GERADOR-QUESITOS-PERICIA-CONTABIL — 8 quesitos essenciais

## 1. ESCOPO

Gera os **8 quesitos nucleares** para a perícia contábil na revisional
bancária, ajustados ao **tipo de contrato**. Quesitos bem formulados =
laudo que prova a tese; quesitos genéricos = laudo inútil.

> Estes 8 são o **núcleo**. Acrescentar quesitos específicos do caso
> (ex.: seguro com venda casada, IOF financiado) conforme a inicial.

---

## 2. INPUT NECESSÁRIO

1. **Tipo de contrato** (parametriza os quesitos relevantes)
2. **Data do contrato** (define marcos: 31/03/2000, 30/04/2008,
   25/02/2011, 30/03/2021, ~30/08/2024)
3. Sistema de amortização declarado (Price/SAC/misto), se houver
4. Encargos cobrados (tarifas, comissão de permanência, seguro)
5. Polo do cliente (consumidor CDC × empresarial CC)

---

## 3. OS 8 QUESITOS (modelo)

```
QUESITO 1 — Taxa efetiva × taxa média de mercado
Qual a taxa de juros remuneratórios EFETIVA do contrato (mensal e
anual)? Como ela se compara à TAXA MÉDIA divulgada pelo BACEN para a
mesma modalidade e período (fonte/data)? Há discrepância relevante?

QUESITO 2 — Capitalização infra-anual e pactuação (Súm. 539/541)
Há capitalização de juros em período inferior ao anual? Em caso
positivo, ela está EXPRESSAMENTE pactuada (cláusula) E o contrato é
posterior a 31/03/2000? A taxa anual contratada supera o duodécuplo
(12×) da mensal (Súm. 541)?

QUESITO 3 — Sistema de amortização e anatocismo (Price × SAC)
Qual o sistema adotado (Price, SAC, misto)? Recalcule pelo SAC e
demonstre a diferença de juros totais. Há incidência de juros sobre
juros não autorizada por cláusula expressa?

QUESITO 4 — Comissão de permanência cumulada (Súm. 30/296/472)
Houve cobrança de comissão de permanência? Foi cumulada com correção
monetária (Súm. 30), juros remuneratórios/moratórios ou multa
contratual (Súm. 472)? Excedeu a taxa do contrato (Súm. 294/296)?

QUESITO 5 — TAC/TEC e serviços de terceiros (Súm. 565 / T.618 / T.958)
Foram cobradas TAC/TEC? O contrato é anterior a 30/04/2008 (Súm.
565)? Houve cobrança de "serviços de terceiros"/comissão de
correspondente posterior a 25/02/2011 (Tema 958)? Registro/avaliação
foram efetivamente prestados?

QUESITO 6 — Recálculo depurado + indébito (Tema 929)
Refaça o cálculo expurgando TODOS os encargos reputados ilegais.
Apure a diferença a restituir e indique se a repetição é simples ou
em dobro (Tema 929; modulação para cobranças após 30/03/2021).

QUESITO 7 — Índices supletivos por época
Ao decotar encargo abusivo, quais índices supletivos incidem por
período? Multa moratória respeita o teto de 2% (CDC art. 52 §1º)?
Para o período pós Lei 14.905/2024 (~30/08/2024) aplicou-se a taxa
legal do CC art. 406 (Selic − IPCA, piso zero)?

QUESITO 8 — Valor incontroverso × controvertido
Aponte o valor INCONTROVERSO (que o cliente reconhece dever, para
consignação/depósito) e o valor CONTROVERTIDO (objeto da revisão).
```

---

## 4. PARAMETRIZAÇÃO POR TIPO DE CONTRATO

| Contrato | Quesitos com peso reforçado |
|---|---|
| **CCB / crédito pessoal** | 1, 2, 5, 6 |
| **Financiamento de veículo** | 2, 3, 5 (TAC/registro/avaliação), 6 |
| **Financiamento imobiliário** | 3 (Price×SAC, TR), 7 |
| **Leasing** | 3, 5, 7 |
| **Cartão / rotativo** | 1, 2, 4, 6 |
| **Cheque especial** | 1, 4, 6 |

> ⚠️ Marcos temporais decidem quesitos: capitalização (pós 31/03/2000),
> TAC/TEC (até 30/04/2008), serviços de terceiros (pós 25/02/2011),
> dobro (pós 30/03/2021), taxa legal CC 406 (pós ~30/08/2024).

---

## 5. FUNDAMENTAÇÃO

- **Súm. 539/541 STJ** — capitalização infra-anual (expressa + pós
  31/03/2000; taxa anual > 12× mensal)
- **Súm. 30/294/296/472 STJ** — comissão de permanência (não cumula;
  limitada à taxa do contrato)
- **Súm. 565 STJ / Tema 618 (REsp 1.251.331)** — TAC/TEC até 30/04/2008
- **Tema 958 (REsp 1.578.553)** — serviços de terceiros abusivos pós
  25/02/2011 *(corpus: este é o Tema 958, NÃO o de TAC/TEC)*
- **Tema 929** — devolução em dobro (modulação 30/03/2021)
- **Tema 27 (REsp 1.061.530)** — base da revisão de juros remuneratórios
- **CDC art. 52 §1º** — multa moratória máx. 2%
- **Lei 14.905/2024** — taxa legal CC 406 (Selic − IPCA) pós ~30/08/2024

---

## 6. PROIBIÇÕES

1. **NUNCA** hardcodar taxa média BACEN — quesito pede ao perito consultar
   a fonte oficial por modalidade/período.
2. **NUNCA** confundir Tema 958 (serviços de terceiros) com TAC/TEC
   (Tema 618/Súm. 565).
3. **NUNCA** assumir Price = anatocismo automático (pedir comparativo,
   não conclusão pronta).
4. **NUNCA** formular quesito que peça ao perito **decidir tese jurídica**
   (perito apura fatos contábeis; o direito é do juiz).
5. **NUNCA** omitir o quesito do valor incontroverso (instrui depósito).

---

## 7. INTEGRAÇÃO

**Upstream:** `peticao-revisional-bancaria` (auto-anexa) · `detector-encargos-abusivos`
**Downstream:** `recomendador-perito-contabil` (custeio/contratação) →
`auditoria-juris-pre-envio` → `protocolo-p4-bancario`

> Cross-link soft (sugestão, não execução): auditar o laudo entregue pelo
> perito → `/calculos auditor-laudo-pericial-contabil` (calculosjudiciais-adv-os).

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
