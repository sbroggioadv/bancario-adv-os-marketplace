---
description: Ponto de entrada do plugin bancario-adv-os. Aciona o orquestrador bancario-master para triagem da frente (fraude/golpe pix/golpe falso advogado/financiamento fraudulento/revisional/juros abusivos/superendividamento/busca e apreensao/embargos/recursos) e roteamento para a skill correta, sempre com varredura jurisprudencial antes de redigir e auditoria anti-halucinacao antes de entregar.
---

# /bancario

Voce acionou o plugin **bancario-adv-os** (acoes bancarias na perspectiva do cliente do banco).

Use a skill **`bancario-master`** (orquestrador) para conduzir o caso. Fluxo padrao:

1. **Triagem** (`triagem-caso-bancario`) — identifica a frente pela conversa.
2. **Varredura jurisprudencial** (`varredura-jurisprudencial-pre-tese`) — valida a tese no TJ/STJ atual ANTES de redigir.
3. **Foro** (`classificador-foro-jec-comum`) — JEC ou Justica Comum.
4. **Peca** da materia (auto-anexa tese + tutela + agravantes).
5. **Auditoria anti-halucinacao** (`auditoria-juris-pre-envio`) — nenhuma citacao sem verificacao real.
6. **P4** (`protocolo-p4-bancario`) — auditoria de excelencia.

Argumento opcional: `/bancario <frente>` (ex.: `/bancario golpe-pix`, `/bancario revisional`, `/bancario superendividamento`).

Se for a primeira vez, rode antes **`/start-bancario`** para configurar advogado, comarca/TJ e tom de voz.
