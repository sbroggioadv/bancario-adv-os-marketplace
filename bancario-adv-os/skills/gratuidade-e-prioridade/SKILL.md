---
name: gratuidade-e-prioridade
description: >
  GRATUIDADE-E-PRIORIDADE — Gera os requerimentos processuais
  frequentes do cliente do banco para colar na inicial: gratuidade
  da justica (art. 98 CPC, presuncao relativa, juiz pode exigir
  prova), prioridade de tramitacao do idoso (art. 1.048, I, CPC +
  art. 71 Estatuto da Pessoa Idosa) e desinteresse na audiencia de
  conciliacao (art. 334, §5o, CPC). Blocos prontos. Use quando o
  advogado disser: "gratuidade", "justica gratuita", "isencao de
  custas", "cliente nao tem como pagar custas", "prioridade",
  "tramitacao prioritaria", "cliente idoso", "prioridade do
  idoso", "dispensar audiencia de conciliacao", "nao quero
  conciliar", "requerimentos da inicial".
---

# GRATUIDADE-E-PRIORIDADE — Requerimentos da inicial

## 1. ESCOPO

Tres requerimentos processuais que entram na **inicial** (ou em
peticao avulsa) do cliente do banco: gratuidade da justica,
prioridade do idoso e desinteresse na conciliacao. Blocos prontos
para colar. Perspectiva: cliente (autor).

---

## 2. INPUT NECESSARIO

Do contexto + perguntar:

1. Cliente declara **insuficiencia de recursos**? (gratuidade)
2. Cliente e **pessoa juridica**? (PJ precisa **comprovar** —
   presuncao do art. 99 §3o e so para PF)
3. Cliente tem **60 anos ou mais**? (prioridade idoso)
4. Ha doenca grave / PCD? (outras hipoteses do art. 1.048)
5. Quer **dispensar** a audiencia de conciliacao do art. 334?

---

## 3. BLOCOS PRONTOS

### Bloco A — Gratuidade da justica (art. 98 CPC)
> Para **pessoa fisica**, presuncao relativa de veracidade (art.
> 99, §3o). O juiz **pode** exigir prova (art. 99, §2o) antes de
> indeferir — nao indefere sem dar oportunidade. **PJ** deve
> **comprovar** a insuficiencia (Sumula 481 STJ — confirmar antes
> de citar).

```
Requer a concessao dos beneficios da JUSTICA GRATUITA (art. 98 e
seguintes do CPC), por nao dispor de recursos para arcar com as
custas, despesas processuais e honorarios sem prejuizo do proprio
sustento [e de sua familia], declarando, sob as penas da lei, a
veracidade desta afirmacao (art. 99, §3o, CPC — presuncao em favor
da pessoa natural). [Anexa: declaracao de hipossuficiencia /
comprovante de renda, se PJ ou se requerido pelo juizo.]
```

### Bloco B — Prioridade de tramitacao do idoso
> Cabivel a quem tem **60 anos ou mais** (art. 1.048, I, CPC +
> art. 71 do Estatuto da Pessoa Idosa). A partir de **80 anos**, a
> prioridade e **especial** (preferencia sobre os demais idosos —
> art. 71, §5o do Estatuto). Vale tambem a portadores de doenca
> grave (art. 1.048, I, parte final).

```
Requer a concessao de PRIORIDADE NA TRAMITACAO do feito, por ser a
parte autora pessoa idosa (60 anos ou mais), nos termos do art.
1.048, I, do CPC, c/c art. 71 da Lei 10.741/2003 (Estatuto da
Pessoa Idosa). [Se 80+: requer prioridade especial, art. 71, §5o.]
Anexa documento comprobatorio da idade.
```

### Bloco C — Desinteresse na audiencia de conciliacao
> Art. 334, §5o, CPC: o autor manifesta desinteresse **na propria
> peticao inicial**. A audiencia so e dispensada se **ambas** as
> partes manifestarem desinteresse (§4o, I) — ainda assim, e
> faculdade do autor registrar a posicao.

```
Manifesta, desde ja, DESINTERESSE na realizacao da audiencia de
conciliacao ou de mediacao (art. 334, §5o, do CPC), sem prejuizo
de eventual composicao em qualquer fase. [Observacao: a audiencia
so sera dispensada se a parte re tambem manifestar desinteresse,
nos termos do art. 334, §4o, I, do CPC.]
```

---

## 4. OUTPUT

Monta os blocos **selecionados** na ordem de uma inicial
(geralmente: desinteresse na conciliacao no topo dos pedidos;
gratuidade e prioridade nos requerimentos finais), prontos para
colar, com os anexos a juntar listados.

---

## 5. FUNDAMENTACAO LEGAL

- **CPC art. 98** — concessao da gratuidade · **art. 99, §2o** —
  juiz pode exigir prova antes de indeferir · **§3o** — presuncao
  relativa em favor da pessoa natural
- **CPC art. 1.048, I** — prioridade idoso (60+) e doenca grave
- **Lei 10.741/2003 (Estatuto da Pessoa Idosa) art. 71** —
  prioridade; **§5o** — prioridade especial a partir de 80 anos
- **CPC art. 334, §4o, I e §5o** — dispensa/desinteresse na
  audiencia de conciliacao
- 🟡 **Sumula 481 STJ** — PJ deve comprovar insuficiencia
  (confirmar antes de citar)

> Normas processuais estaveis; conferir vigencia/atualizacao do
> Estatuto e adaptacoes locais antes de protocolar.

---

## 6. PROIBICOES

1. **NUNCA afirmar que a gratuidade e automatica para PJ** — PF
   tem presuncao; PJ **comprova**.
2. **NUNCA dizer que a conciliacao foi dispensada** so com o
   desinteresse do autor — depende tambem do reu (art. 334 §4o I).
3. **NUNCA omitir o documento comprobatorio da idade** no pedido
   de prioridade.
4. **NUNCA tratar a presuncao da gratuidade como absoluta** — e
   relativa; o juiz pode exigir prova (art. 99 §2o).

---

## 7. INTEGRACAO

**Upstream:** `bancario-master` · qualquer skill de peticao
inicial da frente · `hipervulneravel-idoso-fraude` (quando idoso).
**Downstream:** `auditoria-juris-pre-envio` (GATE) ·
`protocolo-p4-bancario`.

## 💡 Proximos passos opcionais
| Proximo passo | Comando | Plugin |
|---|---|---|
| Auditoria final com IA | `/ia-combativa suprema-corte-r1-r4` | ia-combativa-adv-os |
| Buscar entendimento local sobre gratuidade | `/juris buscar` | juris-adv-os |

> Se plugin nao instalado, usar os blocos acima manualmente.

---

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
