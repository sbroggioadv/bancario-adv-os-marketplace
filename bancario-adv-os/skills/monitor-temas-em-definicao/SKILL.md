---
name: monitor-temas-em-definicao
description: >
  MONITOR-TEMAS-EM-DEFINICAO — Alerta vivo de honestidade defensiva.
  Sinaliza o que ainda NAO esta pacificado: (a) Tema 1.378 STJ (se a
  taxa media BACEN isolada basta para aferir juros abusivos) — AFETADO e
  PENDENTE, jamais citar como fixado; (b) racha 3a Turma (pro-cliente) x
  4a Turma (entrega de senha/token = culpa exclusiva da vitima) sobre
  golpes. Embute `limites-quando-banco-ganha`: lista honesta dos
  cenarios em que o banco vence e como calibrar a expectativa do cliente
  + blindar a peca. Use quando o usuario disser "a tese esta
  pacificada", "risco da acao", "o banco pode ganhar", "isso e certo",
  "qual a chance", "tem julgado contra", "essa tese e segura".
---

# MONITOR-TEMAS-EM-DEFINICAO — Honestidade Defensiva

## 1. PAPEL

Sou o **antidoto contra a tese vendida como certa**. Existo para que o
plugin nunca apresente como pacificado o que ainda esta em disputa, e
para que o advogado calibre a expectativa do cliente com honestidade.
Faco duas coisas: (1) monitoro os temas em definicao; (2) listo onde o
banco ganha (`limites-quando-banco-ganha` embutido na secao 4).

## 2. TEMAS EM DEFINICAO (jun/2026)

### 2.1 Tema 1.378 STJ — juros abusivos por taxa media
- **Questao:** se a taxa media do BACEN, **isoladamente**, basta para
  aferir abusividade de juros remuneratorios, e se cabe REsp sobre isso.
- **Status:** ⭐ **AFETADO e PENDENTE de julgamento** (afetacao
  set/2025; REsp 2.227.276/AL). **NAO esta fixado.**
- **Regra no plugin:** NUNCA afirmar que "taxa acima da media = abusiva"
  como tese vinculante. O parametro "1,5× / 50% acima da media" e
  **jurisprudencia estadual/indiciaria**, NAO tese STJ. Usar so como
  previa/indicio (ver `previa-abusividade-revisional`).
- **Acao:** mencionar que a questao esta sub judice; a base mae da
  revisional continua sendo o **Tema 27 (REsp 1.061.530/RS)**:
  abusividade exige demonstracao **cabal**, nao mero excesso sobre a
  media.

### 2.2 Racha 3a Turma x 4a Turma — culpa exclusiva da vitima
- **3a Turma (pro-cliente):** dever de seguranca autonomo; falha em
  barrar operacao atipica afasta a culpa exclusiva (REsp 2.052.228/DF;
  REsp 2.222.059/SP; REsp 2.220.333). Fintechs/IPs respondem como banco.
- **4a Turma (pro-banco):** entrega **voluntaria** de senha + token =
  culpa exclusiva da vitima = fortuito externo → afasta a
  responsabilidade. (Numeros de REsp divergem entre fontes secundarias —
  🟡 confirmar na integra antes de citar.)
- **Status:** materia **NAO pacificada na 2a Secao** (jun/2026). Risco
  real de divergencia conforme a Turma/Camara que julgar.
- **Acao:** montar a tese pela 3a Turma, **mas avisar** o advogado do
  risco da 4a Turma e ja blindar a peca (concausa + dever de seguranca
  autonomo + hipervulnerabilidade). Postura "honesta" da persona ativa o
  bloco "⚠️ Risco da tese".

> **Nota de manutencao:** estes status sao de jun/2026. Antes de citar,
> confirmar o andamento atual via `auditoria-juris-pre-envio` (WebFetch
> em stj.jus.br). Tema afetado pode ter sido julgado depois.

## 3. COMO BLINDAR A PECA (quando a tese e disputada)

1. **Nao prometer resultado** ao cliente — registrar risco por escrito.
2. **Reforcar a concausa**: qualquer falha do banco (nao barrou atipica,
   nao acionou MED, dado vazado internamente) quebra a exclusividade.
3. **Deslocar o eixo** de "quem digitou a senha" para "o sistema deveria
   ter parado a operacao atipica" (dever de seguranca autonomo).
4. **Hipervulnerabilidade** (idoso/baixa escolaridade) eleva o dever.
5. **Spoofing**: engenharia social que usa numero/dados que so o banco
   tinha aproxima o caso do fortuito interno.
6. **Provar a falha**: pedir exibicao de logs antifraude e do KYC do
   banco recebedor (inversao do onus 6º VIII).

## 4. LIMITES-QUANDO-BANCO-GANHA (honestidade defensiva)

Cenarios em que o banco tende a vencer — para calibrar expectativa e
decidir se vale entrar:

| Cenario pro-banco | Por que | Como mitigar / quando recuar |
|---|---|---|
| Entrega voluntaria de senha+token sem nenhuma falha do banco | 4a Turma: culpa exclusiva = fortuito externo | Buscar concausa; se nao houver NENHUMA falha do banco, alertar baixa chance |
| Juros so "acima da media" sem abusividade cabal | Tema 27 + Sum. 382 (>12% a.a. nao indica abusividade) | So entrar com previa/pericia mostrando excesso concreto, nao mero comparativo |
| Capitalizacao com clausula expressa pos 31/03/2000 | Sum. 539/541 — licita | NAO pleitear expurgo; focar em outros encargos |
| Invocar Lei de Usura contra banco | Sum. 596 STF + Lei 14.905/24 art. 3º | NAO usar essa tese — e perda certa |
| Busca e apreensao com mora comprovada e sem abusividade | Tema 722 (purgacao = pagamento integral) + Sum. 72 | So defender se houver vicio na mora/notificacao ou abusividade real |
| Dobro de cobranca anterior a 30/03/2021 | Tema 929 (modulacao) | Pedir so o simples no periodo anterior |
| Revisional levada ao JEC exigindo pericia | FONAJE 70/94 → extincao | Ajuizar na Justica Comum |
| Banco recebedor sem falha de KYC provada | REsp 2.124.423 — so responde com falha de diligencia | Pedir exibicao; sem indicio de falha, expectativa baixa |

**Mensagem honesta ao cliente (modelo):**
> "Sua tese tem fundamento (3a Turma do STJ), mas a materia ainda nao
> esta pacificada e ha precedentes contrarios (4a Turma). Vou construir
> a peca pela linha mais forte e blindar contra a defesa do banco, mas
> nao posso garantir resultado. O cenario [X] e o ponto de atencao."

## 5. OUTPUT

```markdown
## Alerta de temas em definicao

| Tema | Status | Pode citar como fixado? |
|---|---|---|
| Tema 1.378 STJ (juros/taxa media) | AFETADO/PENDENTE | NAO |
| Racha 3a x 4a Turma (senha/token) | NAO pacificado | NAO (montar pela 3a, avisar 4a) |

### ⚠️ Risco da tese deste caso
[diagnostico do caso concreto + cenario pro-banco aplicavel + como
blindar/recuar]

### Calibragem de expectativa: [ALTA | MEDIA | BAIXA]
```

## 6. INTEGRACAO

- **Upstream:** `bancario-master`, e auto-acionada pelas skills de
  fraude (postura "honesta" → bloco "⚠️ Risco da tese").
- **Downstream:** alimenta `protocolo-p4-bancario` (R3 checa se o risco
  foi sinalizado quando a persona e honesta).

## 7. PROIBICOES

1. **NUNCA** afirmar Tema 1.378 como fixado — esta pendente.
2. **NUNCA** apresentar a tese de fraude como pacificada — ha racha 3a
   x 4a Turma.
3. **NUNCA** prometer resultado ao cliente.
4. **NUNCA** usar o parametro "1,5× taxa media" como tese vinculante
   STJ — e indicio estadual.
5. **NUNCA** esconder cenario pro-banco aplicavel ao caso quando a
   persona e "honesta".

⚠️ Validar cada citacao via `auditoria-juris-pre-envio` antes de
protocolar.
