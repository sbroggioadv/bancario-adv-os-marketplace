---
name: replica-contestacao
description: >
  REPLICA-CONTESTACAO — Monta a replica (CPC 350/351, 15 dias
  uteis) que rebate as defesas TIPICAS do banco em acao bancaria:
  culpa exclusiva da vitima, novacao/confissao de divida (Sum.
  286 STJ), "operacao validada por token/senha", "taxa dentro da
  media" (Sum. 382), ilegitimidade passiva. Estrutura da replica
  + blocos prontos por defesa. Use quando o advogado disser:
  "replica", "replicar a contestacao", "o banco contestou",
  "rebater a defesa do banco", "responder a contestacao", "o
  banco alegou culpa da vitima", "banco disse que a operacao foi
  validada", "banco alegou novacao", "banco diz que a taxa esta
  na media", "banco arguiu ilegitimidade".
---

# REPLICA-CONTESTACAO — Resposta as defesas tipicas do banco

## 1. ESCOPO

Replica do autor (CPC 350/351) quando o banco-reu, na contestacao,
alega fato impeditivo/modificativo/extintivo ou preliminares.
Cobre as 5 defesas que o banco repete em quase toda acao bancaria
do cliente. Perspectiva: **sempre o cliente** (vitima/devedor).

- **Prazo:** 15 dias uteis (CPC 350/351 + 219).
- Combina blocos por defesa alegada → texto unico coerente.

---

## 2. INPUT NECESSARIO

Do contexto + perguntar:

1. Frente (fraude / revisional / busca e apreensao / superendiv.)
2. **Quais defesas o banco alegou?** (marcar): culpa exclusiva,
   novacao/confissao, validacao por token/senha, taxa na media,
   ilegitimidade passiva, fortuito externo, outras
3. Documentos novos juntados pelo banco (contrato, logs, KYC?)
4. Pedidos formulados na inicial (para reforcar)
5. Houve idoso/hipervulneravel? (eleva o dever do banco)

---

## 3. ESTRUTURA DA REPLICA

```
EXCELENTISSIMO(A) ... [Juizo da inicial]
Autos n. ___ — REPLICA

I.   Sintese da contestacao
II.  Preliminares arguidas (rebate cada uma)
III. Merito — refutacao ponto a ponto das defesas tipicas
IV.  Documentos novos do banco (impugnacao especifica)
V.   Reiteracao dos pedidos + provas a produzir
VI.  Requerimentos finais (julgamento procedente)
```

Regra: impugnar especificamente cada fato (CPC 341) — silencio
sobre alegacao do banco pode gerar presuncao indevida.

---

## 4. BLOCOS PRONTOS POR DEFESA

### Bloco A — "Culpa exclusiva da vitima"
> Remete a logica de `rebater-culpa-exclusiva-vitima` (skill irma).

A excludente do art. 14, §3o, II, CDC exige culpa **exclusiva** —
e o onus de prova-la e do banco (Sum. 479 STJ; responsabilidade
objetiva por fortuito interno). **Qualquer falha do banco quebra a
exclusividade** (concausa): nao barrar movimentacao atipica ao
perfil (REsp 2.052.228/DF — confirmar antes de citar), nao acionar
o MED, dado vazado internamente. O dever de seguranca e
**autonomo** (REsp 2.222.059/SP — confirmar antes de citar): a
questao nao e "quem digitou a senha", e "o sistema deveria ter
parado a operacao atipica". Falha de seguranca **afasta** culpa
concorrente em engenharia social (REsp 2.220.333 — confirmar antes
de citar).

### Bloco B — Novacao / Confissao de divida (Sum. 286 STJ)
A renegociacao ou o termo de confissao de divida **nao impede a
revisao** das ilegalidades dos contratos anteriores (Sumula 286
STJ). A novacao nao convalida encargo abusivo nem clausula nula de
pleno direito (CDC 51, IV; nulidade e materia de ordem publica,
conhecivel de oficio). O saldo confessado carrega os mesmos vicios
que se quer expurgar.

### Bloco C — "Operacao validada por token/senha"
A validacao por senha/token **nao e salvo-conduto**: o dever de
seguranca do banco e autonomo e abrange detectar e obstar
movimentacao atipica (valor, horario, local, frequencia
incompativeis com o perfil) ainda que a credencial tenha sido
inserida. Em engenharia social a vitima e induzida por **spoofing
do proprio banco** (numero/dados que so o banco detinha). A
existencia de log de autenticacao apenas comprova que o sistema
**nao parou** uma operacao que deveria ter parado — confirma o
defeito (CDC 14), nao o afasta.

### Bloco D — "Taxa dentro da media" (Sum. 382 nao basta)
A Sumula 382 STJ tem **mao dupla**: se juros acima de 12% a.a. nao
indicam abusividade por si so, taxa "na media" **tambem nao afasta**
a abusividade por si so. Abusividade e **multifatorial** (Tema 27 /
REsp 1.061.530/RS): exige analise do encargo concreto —
capitalizacao nao pactuada, comissao de permanencia cumulada (Sum.
30/296/472), tarifas vedadas (Sum. 565; Tema 618/619; Tema 958),
spread em relacao a media (parametro **indiciario**, nao tese
vinculante). Atencao: o **Tema 1.378 STJ esta afetado e pendente**
sobre se a taxa media basta para aferir abusividade — materia em
definicao (confirmar antes de citar). O banco nao se desincumbe so
exibindo a media BACEN.

### Bloco E — Ilegitimidade passiva
O banco e parte legitima: e o fornecedor do servico defeituoso
(CDC 14; Sum. 297) e, em fraude, o gestor do risco da atividade
(Sum. 479; CC 927, p.u.). Em golpe via PIX, tanto o banco do
cliente (dever de seguranca) quanto o **banco recebedor**
(conta-laranja) podem responder — este ultimo se houver falha de
diligencia na abertura/manutencao da conta (KYC/PLD; REsp
2.124.423 — confirmar antes de citar). Instituicoes de
pagamento/fintechs respondem **como bancos** (REsp 2.222.059/SP —
confirmar antes de citar). Requerer, se preciso, exibicao dos docs
de abertura da conta recebedora.

---

## 5. FUNDAMENTACAO LEGAL

- **CPC 350/351** — replica a contestacao com fato impeditivo/
  modificativo/extintivo ou preliminares; **CPC 341** — onus de
  impugnacao especifica; **CPC 219** — prazo em dias uteis
- **CDC 14 + §3o** — responsabilidade objetiva; excludentes
- **CDC 51, IV** — nulidade de clausula abusiva (ordem publica)
- **Sum. 479 STJ** — fortuito interno (responsabilidade objetiva)
- **Sum. 297 STJ** — CDC aplicavel a bancos
- **Sum. 286 STJ** — confissao/novacao nao impede revisao
- **Sum. 382 STJ** — juros >12% a.a. nao indicam abusividade por si
- **Tema 27 (REsp 1.061.530/RS)** — abusividade exige demonstracao
  cabal (base da revisional)
- 🟡 **REsp 2.052.228/DF · 2.222.059/SP · 2.220.333 · 2.124.423** —
  (confirmar antes de citar)
- 🟡 **Tema 1.378 STJ** — afetado/pendente (confirmar antes de citar)

---

## 6. INTEGRACAO

**Upstream:** `bancario-master`; a peca inicial da frente.
**Downstream:** `recursos-civeis-router` (se houver decisao a
recorrer) · `devolucao-em-dobro` · `auditoria-juris-pre-envio`
(GATE — antes de protocolar) · `protocolo-p4-bancario`.

## 💡 Proximos passos opcionais
| Proximo passo | Comando | Plugin |
|---|---|---|
| Buscar julgado atual do TJ/STJ | `/juris buscar` | juris-adv-os |
| Auditoria final com IA | `/ia-combativa suprema-corte-r1-r4` | ia-combativa-adv-os |

> Se plugin nao instalado, usar a replica acima manualmente.

---

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
