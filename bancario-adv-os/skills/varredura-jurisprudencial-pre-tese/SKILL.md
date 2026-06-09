---
name: varredura-jurisprudencial-pre-tese
description: >
  VARREDURA JURISPRUDENCIAL PRE-TESE — Tier 1, GATE BLOQUEANTE antes
  de redigir QUALQUER peticao bancaria. Dada a tese escolhida + o TJ
  competente, faz varredura do entendimento ATUAL (TJ local + STJ) via
  WebSearch/WebFetch (e Firecrawl/Perplexity se disponiveis) para
  CONFIRMAR que a tese esta validada por julgado recente (12-24 meses),
  detectar virada de entendimento e sinalizar divergencia (ex.: racha
  3a x 4a Turma STJ na culpa exclusiva da vitima; Tema 1.378 pendente
  na taxa media BACEN). Classifica a tese em FAVORAVEL CONSOLIDADA /
  FAVORAVEL MAJORITARIA COM DIVERGENCIA / EM DISPUTA / DESFAVORAVEL e
  recomenda seguir, ajustar ou reconsiderar. Mitiga improcedencia por
  entendimento desatualizado. Use SEMPRE antes de redigir peticao,
  ou quando o advogado disser: varredura jurisprudencial, essa tese
  ainda vale, como esta o entendimento, virou a jurisprudencia,
  o que o TJ daqui pensa, conferir antes de peticionar.
---

# VARREDURA JURISPRUDENCIAL PRE-TESE ⭐

> Skill **Tier 1** e **GATE BLOQUEANTE**: nenhuma petição é redigida antes desta varredura confirmar que a tese está viva no TJ competente + STJ. Mitiga o pior risco da "petição-fábrica": **improcedência por tese desatualizada**.

---

## 0. POR QUE ESTE GATE EXISTE

O entendimento sobre fraudes e revisional bancária **muda por Turma e por ano**. Redigir com base em julgado vencido = derrota previsível. Esta skill **para o pipeline** até confirmar que a tese está validada por julgado recente do tribunal que vai julgar o caso.

**Diferença para `auditoria-juris-pre-envio`:** aquela valida se a citação **existe** (WebFetch na peça pronta). Esta valida se a tese **ainda vence** (varredura ANTES de redigir). As duas são complementares e ambas bloqueantes.

## 1. INPUT NECESSARIO

1. **Tese central** escolhida (ex.: fortuito interno Súm. 479; revisão de juros Tema 27; abusividade por taxa média BACEN).
2. **TJ competente** (ex.: TJSP, TJMG, TJRS) — vem do `classificador-foro-jec-comum` / triagem.
3. **Tipo de caso** (fraude / revisional / superendividamento / defesa em execução).
4. Período-alvo: **últimos 12-24 meses** (privilegiar 2025-2026).

---

## 2. PROCESSO DE VARREDURA

### Passo 1 — Identificar tese + tribunal
Fixar a tese e o tribunal. Listar as âncoras do corpus que a sustentam (súmula/tema/REsp) — elas guiam a busca.

### Passo 2 — Buscar julgados recentes (TJ + STJ)
Disparar buscas reais. Ordem de ferramentas: **WebSearch/WebFetch nativos primeiro**; Firecrawl/Perplexity **só como fallback** se disponíveis.

Queries-modelo (adaptar à tese):
- `"<TJ> golpe pix banco responsabilidade 2025 fortuito interno"` (jusbrasil/esaj/jurisprudencia oficial)
- `"STJ <tese> <ano>"` + `site:stj.jus.br` quando útil
- Revisional: `"<TJ> revisão contrato bancário juros taxa média BACEN 2025"`
- Pendências: `"STJ Tema 1.378 julgamento taxa média"` / `"STJ culpa exclusiva vítima senha token 3ª 4ª Turma"`

**Coletar para cada julgado relevante:** tribunal/órgão, nº (CNJ ou REsp), data, sentido (favorável/contrário ao cliente), trecho da ementa. **Só registrar o que a busca realmente retornar.**

### Passo 3 — Classificar a tese
| Status | Critério |
|---|---|
| **✅ FAVORÁVEL CONSOLIDADA** | Súmula/repetitivo vigente + julgados recentes do TJ no mesmo sentido, sem divergência interna relevante |
| **🟢 FAVORÁVEL MAJORITÁRIA C/ DIVERGÊNCIA** | Maioria favorável, MAS existe corrente contrária (ex.: 4ª Turma STJ; câmara isolada do TJ) — blindar a peça contra ela |
| **🟡 EM DISPUTA** | Tema afetado/pendente ou racha real entre órgãos — resultado incerto; avisar o cliente |
| **🔴 DESFAVORÁVEL** | TJ/STJ recentes contra a tese; redigir assim = improcedência provável → reconsiderar ângulo |

### Passo 4 — Recomendar
Saída: **seguir** (consolidada) / **ajustar** (blindar contra divergência, mudar fundamento) / **reconsiderar** (tese desfavorável — propor ângulo alternativo do corpus).

---

## 3. PONTOS QUENTES A SEMPRE CHECAR (jun/2026)

> Sinalizar SEMPRE que a tese tocar nestes temas — são os pontos em movimento (corpus §1 e §3):

- **Racha 3ª × 4ª Turma STJ — culpa exclusiva da vítima** (entrega voluntária de senha/token). 3ª Turma: dever de segurança autônomo afasta a exclusividade. 4ª Turma (dez/2025–jan/2026): entrega voluntária = fortuito externo. **Não pacificado na 2ª Seção.** Números divergem entre fontes → 🟡 confirmar na íntegra. Blindar com concausa + dever autônomo (REsp 2.052.228 / 2.222.059 / 2.220.333).
- **Tema 1.378 STJ (REsp 2.227.276/AL)** — **AFETADO, pendente**: vai decidir se a **taxa média BACEN isolada basta** para aferir abusividade. **A questão mais quente da revisional.** Não afirmar como fixado.
- **Parâmetro "1,5× / 50% acima da taxa média"** = jurisprudência **estadual/indiciária**, NÃO tese vinculante STJ. Usar só como prévia/indício.
- **MED 2.0 (Res. BCB 493/2025)** — obrigatório desde **02/02/2026**: a tese de dever de rastreio reforçado só vale para fatos a partir dessa data.

---

## 4. OUTPUT — RELATORIO DE VARREDURA

```
RELATÓRIO DE VARREDURA JURISPRUDENCIAL — GATE PRÉ-TESE

Tese analisada: <ex: fortuito interno — banco responde por golpe PIX>
Tribunal competente: <ex: TJSP>
Período varrido: <ex: 06/2024 a 06/2026>
Ferramentas usadas: <WebSearch / WebFetch / Firecrawl / Perplexity>

JULGADOS ENCONTRADOS (só o que a busca confirmou):
| Órgão | Nº | Data | Sentido | Trecho |
|---|---|---|---|---|
| <TJSP nª Câmara> | <CNJ> | <data> | favorável | "<ementa>" |
| <STJ T3> | <REsp> | <data> | favorável | "<ementa>" |
| <STJ T4> | <REsp> | <data> | contrário | "<ementa>" |

CLASSIFICAÇÃO: <✅ CONSOLIDADA / 🟢 MAJORITÁRIA C/ DIVERGÊNCIA / 🟡 EM DISPUTA / 🔴 DESFAVORÁVEL>

DIVERGÊNCIA DETECTADA: <ex: 4ª Turma STJ entende culpa exclusiva — blindar>
TEMA PENDENTE RELEVANTE: <ex: Tema 1.378 pode mudar o cenário>

RECOMENDAÇÃO ESTRATÉGICA: <SEGUIR / AJUSTAR / RECONSIDERAR>
→ <se AJUSTAR: como blindar / que fundamento reforçar>
→ <se RECONSIDERAR: ângulo alternativo do corpus>

DECISÃO DO GATE: <LIBERADO para redigir / RETIDO até ajuste>
```

---

## 5. REGRA ANTI-HALUCINACAO

1. **Nunca inventar julgado, número de processo ou ementa.** Só reportar o que o WebFetch/WebSearch realmente retornou.
2. Julgado de TJ → confirmar nº CNJ + data abrindo o inteiro teor (corpus §0 🟡).
3. Se a busca **não retornar** julgado recente do TJ → registrar "sem julgado recente localizado no TJ; apoiar em STJ + sinalizar risco" — NÃO preencher com julgado presumido.
4. Esta skill **não dispensa** `auditoria-juris-pre-envio` na peça pronta.

## 6. INTEGRACAO

Acionada por: `bancario-master` (auto, antes de toda petição) e por `triagem-caso-bancario`. Upstream: `classificador-foro-jec-comum` (fornece o TJ). Downstream: libera (ou retém) a skill de petição da trilha. Cross-link soft: `juris-adv-os` (busca/validação avançada) — sugestão de comando, nunca execução.

---

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
