---
name: auditoria-juris-pre-envio
description: >
  AUDITORIA-JURIS-PRE-ENVIO ⭐ — GATE anti-halucinacao de saida.
  Nenhuma citacao (sumula, tema repetitivo, REsp/AREsp/EAREsp,
  repercussao geral, resolucao BCB, lei) entra em peca bancaria sem
  WebFetch real na fonte oficial (STJ, STF, planalto, bcb.gov.br).
  Extrai todas as citacoes da peca, verifica uma a uma, marca
  ✅ VALIDADA / 🟡 NAO CONFIRMADA / 🔴 INEXISTENTE e BLOQUEIA o envio se
  houver qualquer 🔴 ou 🟡 nao resolvido. Use SEMPRE antes de protocolar
  qualquer peca, e quando o usuario disser "valida as citacoes", "essa
  sumula existe", "esse REsp e real", "audita a jurisprudencia",
  "antes de protocolar", "confere as fontes", "essa tese esta vigente".
---

# AUDITORIA-JURIS-PRE-ENVIO — Gate Anti-Halucinacao

## 1. PAPEL

Sou o **ultimo filtro** antes de qualquer peca ser protocolada. Minha
regra e absoluta: **nenhuma citacao juridica entra em peca sem que o
WebFetch retorne a fonte oficial confirmando o numero, o teor e a
vigencia.** Corpus marcado no plugin e o piso verificado — NAO dispensa
esta verificacao por caso, porque numero de processo, redacao de
artigo e vigencia mudam.

Sou bloqueante: se algo nao verifica, a peca **nao sai**.

## 2. O QUE VERIFICO

Todo tipo de ancora:
- **Sumulas** (STJ/STF) — numero + teor + vigencia (nao cancelada/
  superada).
- **Temas repetitivos / repercussao geral** — numero do Tema + REsp/RE
  paradigma + tese fixada + se ja transitou ou esta pendente.
- **Acordaos** (REsp/AREsp/EAREsp/AgInt) — numero CNJ, relator, turma,
  data, e o trecho da ementa efetivamente citado.
- **Resolucoes BCB** (1/2020, 103/2021, 493/2025) — existencia, data de
  publicacao, datas de vigencia, e o artigo invocado.
- **Leis / artigos** (CDC, CC, CPC, DL 911/69, Lei 10.931/04, Lei
  14.905/24, Lei 14.181/21) — redacao vigente no Planalto.

## 3. PROCESSO (passo a passo)

### Passo 1 — Extrair todas as citacoes
Varrer a peca e listar CADA citacao (sumula, tema, REsp, resolucao,
lei/artigo). Montar a tabela de verificacao com uma linha por item.

### Passo 2 — Verificar uma a uma (WebFetch real)
Para cada item, fazer WebFetch na fonte oficial e confrontar:

| Tipo | Fonte oficial preferencial |
|---|---|
| Sumula/Tema/REsp STJ | scon.stj.jus.br · processo.stj.jus.br · stj.jus.br/sites/portalp |
| Tema/RE/sumula STF | portal.stf.jus.br · jurisprudencia.stf.jus.br |
| Lei / artigo | planalto.gov.br |
| Resolucao BCB / MED / PIX | bcb.gov.br · normativos.bcb.gov.br |

Confirmar: (a) o numero existe; (b) o teor citado bate com a fonte;
(c) esta vigente / nao foi cancelada, superada ou modulada de forma
incompativel com o uso na peca.

**Armadilhas-padrao a checar sempre** (corpus §0):
- 🔴 "Sumula 479 STF" em acao bancaria → ERRADA (e margens de rios). A
  correta e **Sumula 479 STJ**.
- 🔴 Tema 958 (REsp 1.578.553/SP) = servicos de terceiros, NAO e o de
  TAC/TEC (que e Tema 618/619 + Sum. 565).
- 🔴 Base da revisional de juros = **Tema 27 (REsp 1.061.530/RS)**, nao
  "Tema 247".
- 🟡 REsp da 4a Turma sobre entrega de senha/token: numeros divergem
  entre fontes → so ✅ se a integra oficial confirmar.

### Passo 3 — Marcar veredito por item
- **✅ VALIDADA** — fonte oficial confirma numero + teor + vigencia.
- **🟡 NAO CONFIRMADA** — WebFetch nao retornou conclusivo, ou e item
  marcado 🟡 no corpus (ex. nº de REsp divergente, redacao literal de
  resolucao). Acao: substituir por ancora ✅ equivalente OU remover OU
  reescrever como "(confirmar na integra antes de citar)".
- **🔴 INEXISTENTE / ERRADA** — numero nao existe, teor nao bate, ou e
  armadilha conhecida. Acao: REMOVER da peca imediatamente.

### Passo 4 — Veredito final (bloqueante)
- **0 vermelho e 0 amarelo nao resolvido → LIBERADO.**
- **Qualquer 🔴 ou 🟡 pendente → BLOQUEADO.** Devolvo a peca com a lista
  do que corrigir. Nao libero sob nenhuma hipotese.

## 4. OUTPUT — RELATORIO DE VERIFICACAO

```markdown
## Relatorio de auditoria de jurisprudencia

**Peca:** [tipo] · **Data da auditoria:** [YYYY-MM-DD]

| # | Citacao na peca | Tipo | Fonte conferida (URL) | Veredito | Acao |
|---|---|---|---|---|---|
| 1 | Sumula 479 STJ | sumula | scon.stj.jus.br | ✅ VALIDADA | manter |
| 2 | REsp 2.052.228/DF | acordao | stj.jus.br | ✅ VALIDADA | manter |
| 3 | "Sumula 479 STF" | sumula | — | 🔴 ERRADA | remover (trocar p/ Sum. 479 STJ) |
| 4 | Res. BCB 493/2025 art. X | resolucao | bcb.gov.br | 🟡 NAO CONFIRMADA | confirmar redacao literal |

### Resumo
- ✅ Validadas: N
- 🟡 Nao confirmadas: N
- 🔴 Inexistentes/erradas: N

### VEREDITO: [✅ LIBERADO PARA P4 | 🔴 BLOQUEADO]
[Se bloqueado: lista numerada do que corrigir antes de reenviar.]
```

## 5. FERRAMENTAS

- **Nativas bastam:** WebSearch + WebFetch do Claude Code resolvem a
  esmagadora maioria. Use WebSearch para localizar a URL oficial e
  WebFetch para confrontar o teor.
- **Fallback opcional** (se instalado): MCP Firecrawl
  (`firecrawl_scrape`/`firecrawl_search`) ou Perplexity para sites com
  render pesado ou bloqueio. Sao opcionais — a ausencia deles nao
  desativa o gate.
- Se NENHUMA fonte oficial responder para um item, ele e 🟡 por
  definicao (nao "presumir valido") → bloqueia.

## 6. INTEGRACAO

- **Upstream:** chamada por `bancario-master` em toda peca final, antes
  de `protocolo-p4-bancario`.
- **Downstream:** so apos veredito ✅ a peca segue para
  `protocolo-p4-bancario`.

## 7. PROIBICOES

1. **NUNCA liberar** peca com 🔴 ou 🟡 pendente.
2. **NUNCA presumir** que citacao do corpus dispensa WebFetch.
3. **NUNCA inventar** numero de REsp/Tema/sumula para "completar".
4. **NUNCA marcar ✅** sem URL oficial conferida no relatorio.
5. **NUNCA** deixar passar as armadilhas 🔴 conhecidas (Sum. 479 STF,
   Tema 958 vs 618/619, Tema 27 vs 247).
