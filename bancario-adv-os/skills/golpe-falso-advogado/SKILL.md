---
name: golpe-falso-advogado
description: >
  GOLPE-FALSO-ADVOGADO — Inicial completa do CLIENTE-vitima contra o banco
  no golpe do falso advogado (estelionatario se passa pelo advogado real,
  usa dados do processo, "voce ganhou a acao, pague taxa pra liberar").
  10 blocos de causa de pedir: relacao de consumo, legitimidade passiva,
  resp. objetiva fortuito interno (Sum. 479 + REsp 2.052.228), falha
  antifraude (movimentacoes atipicas em 24h), hipervulneravel idoso,
  OMISSAO NO MED (Res. BCB 1/2020 art. 39-B + 103/2021 + 493/2025 MED 2.0,
  GATE DE DATA 02/02/2026), banco recebedor (conta-laranja, REsp 2.124.423),
  contratacao irregular de emprestimos + inversao do onus, inercia
  pos-comunicacao / prazo 90 dias abusivo, devolucao em dobro (Tema 929,
  gate 30/03/2021), dano moral, tutela de urgencia (suspender desconto no
  beneficio). Inclui RISCO DA TESE. Use quando: "falso advogado", "ganhei
  acao", "taxa pra liberar valor", "intimacao falsa", "se passou pela minha advogada".
---

# GOLPE-FALSO-ADVOGADO — Inicial completa (10 blocos)

> Perspectiva: cliente-vitima (autor) x banco (reu). Placeholders:
> {{CLIENTE_NOME}}, {{BANCO_REU}}, {{ADV_USURPADO}}, {{COMARCA}}, {{DATA_FRAUDE}}.
> ⚠️ Nenhuma citacao na peca sem `auditoria-juris-pre-envio` (WebFetch real).

## 0. ARMADILHAS
- 🔴 Sumula 479 e do **STJ**, nunca do STF.
- ⏱️ **GATE DE DATA (MED):** fraude **antes** de 02/02/2026 → MED da Res. BCB
  103/2021. Fraude **a partir** de 02/02/2026 → **MED 2.0 (Res. BCB 493/2025)**,
  dever reforcado: rastreio em **ate 5 camadas** + monitoramento **90 dias** +
  bloqueio cautelar 72h. Citar "Res. BCB 1/2020, art. 39-B, c/ redacao da
  Res. BCB 493/2025", mantendo 103/2021 como marco instituidor.
  🟡 Redacao literal de artigos da 493/2025: confirmar antes de citar.
- 🟡 Acordaos de TJ: confirmar n. CNJ + data no inteiro teor.
- ANTES de redigir: `varredura-jurisprudencial-pre-tese` + `classificador-foro-jec-comum`.

## 1. INPUT
1. Como o golpista se apresentou (nome do advogado real {{ADV_USURPADO}}, foto, OAB falsa)
2. Documento falso usado (brasao TJ, logo OAB, "voce ganhou a acao")
3. Cronologia das operacoes (PIX + emprestimos contratados, valores, favorecidos, datas)
4. Data da fraude (→ gate MED) e data da comunicacao ao banco
5. Houve desconto/parcela iniciando no beneficio? Saldo negativo? Negativacao?
6. Cliente idoso? Recuperacao de saude? (agravamento hipervulnerabilidade)
7. Resposta do banco (prazo 90 dias? recusa?)

## 2. ESTRUTURA — ACAO DECLARATORIA DE INEXIGIBILIDADE C/C INDENIZACAO + TUTELA

Enderecamento a uma das Varas Civeis de {{COMARCA}}. **Tramitacao prioritaria**
(idoso): art. 1.048, I, CPC + art. 71 Estatuto do Idoso. **Gratuidade** se for o caso
(art. 98 CPC). Desinteresse na audiencia (334 §5o CPC) — urgencia + verba alimentar.

### FATOS
Narrar: golpista contatou {{CLIENTE_NOME}} se passando pelo advogado real, com
dados do processo; afirmou "acao ganha, pague taxa pra liberar"; documento falso
com brasao TJ/OAB. Sob dominio psicologico, em ate 24h foram contratados N
emprestimos + N PIX a terceiros desconhecidos, todos **aprovados sem bloqueio,
alerta ou autenticacao reforcada**. Conta zerada e/ou saldo negativo. Cliente
contestou na agencia ({{DATA_FRAUDE}}), lavrou BO; banco deu prazo de 90 dias
e nao acionou o MED nem cancelou os emprestimos.

### DIREITO — OS 10 BLOCOS

**1. Relacao de consumo** — art. 2o/3o §2o CDC + **Sum. 297 STJ**.

**2. Legitimidade passiva** — banco gestor da conta autorizou as operacoes sem
verificacao; resp. objetiva (art. 3o §2o + 14 CDC).

**3. Resp. objetiva / fortuito interno** — **Sum. 479 STJ** + **Tema 466** +
art. 14 CDC + **CC 927 p.u.** (risco da atividade). Fraude = fortuito interno.

**4. Falha no sistema antifraude / dever de seguranca** ⭐ — **REsp 2.052.228/DF**
(Nancy Andrighi, T3, 12/09/2023): banco deve identificar/obstar movimentacoes
atipicas ao perfil; ausencia = defeito. No caso: multiplos emprestimos +
escoamento via PIX em <24h, fracionados, a terceiros — padrao classico de fraude,
plenamente detectavel. Banco autorizou tudo mecanicamente = facilitador da fraude.

**5. Hipervulneravel idoso** — Estatuto do Idoso (Lei 10.741/2003) + Convencao
Interamericana sobre Protecao dos Direitos Humanos dos Idosos. Banco tinha a idade
no cadastro → dever de cautela redobrado. Agrava resp. e quantum. (REsp 2.052.228
trata expressamente do idoso como hipervulneravel.) → `hipervulneravel-idoso-fraude`.

**6. Omissao no MED** — apos a comunicacao da fraude, cabia ao banco acionar o
**Mecanismo Especial de Devolucao** (instituido pela **Res. BCB 103/2021**;
hoje **art. 39-B da Res. BCB 1/2020 c/ redacao da Res. BCB 493/2025 — MED 2.0**,
obrigatorio desde 02/02/2026). A omissao = perda da chance de recuperacao =
falha autonoma do servico. **Aplicar o GATE DE DATA** (secao 0). → `med-pix-acionamento`.

**7. Banco recebedor (conta-laranja)** — **REsp 2.124.423** (Nancy Andrighi, T3,
27/01/2025): a instituicao recebedora responde se houve **falha de diligencia na
abertura/manutencao** da conta de destino (KYC/PLD). Pedir **exibicao dos
documentos de abertura** das contas favorecidas. 🟡 (confirmar n. na integra).
→ `responsabilidade-banco-recebedor`.

**8. Contratacao irregular de emprestimos + inversao do onus** — a autora jamais
anuiu; vicio de consentimento. **art. 6o VIII CDC**: cabe ao banco provar a
contratacao valida (biometria, logs, geolocalizacao, gravacao). Juntar contrato
digital unilateral NAO basta. → declarar inexigibilidade de todos os contratos.

**9. Inercia pos-comunicacao / prazo de 90 dias abusivo** — dever de mitigar o
dano; prazo de 90 dias e incompativel com a urgencia de fraude com verba alimentar.
Violacao a boa-fe objetiva, cooperacao e eficiencia.

**10. Devolucao em dobro + dano moral**
- **Devolucao em dobro**: **Tema 929 STJ** + **EAREsp 600.663/RS** (Corte
  Especial) — dobro independe de ma-fe, basta cobranca contraria a boa-fe.
  **GATE: modulacao 30/03/2021** — cobrancas anteriores = simples; posteriores = dobro.
  → `devolucao-em-dobro`.
- **Dano moral in re ipsa** + desvio produtivo (tempo perdido, idas a agencia, BO);
  agravado pela hipervulnerabilidade e pela verba alimentar.

### TUTELA DE URGENCIA (art. 300 CPC) — inaudita altera parte
Fumus (extratos, prints do golpe, BO, protocolo) + periculum (parcelas com data
certa de inicio no beneficio = unica fonte de renda alimentar). Pedir:
a) abster-se de descontar as parcelas dos emprestimos fraudulentos no beneficio/conta;
b) suspender a exigibilidade dos contratos;
c) abster-se de negativar (SERASA/SPC);
d) neutralizar o saldo negativo (sem juros/encargos);
e) astreintes (art. 537). Irreversibilidade afastada (banco pode retomar se improceder).
→ minuta detalhada em `tutela-urgencia-bancaria`.

### PEDIDOS
Confirmar tutela; declarar **inexigibilidade** de todos os contratos e do saldo
negativo; **restituir** os PIX (corrigidos do desembolso, juros da citacao) —
em **dobro** se pos 30/03/2021; **dano moral** (quantia certa fundamentada);
inversao do onus; prioridade idoso; custas + honorarios. Valor da causa = material + moral.

## ⚠️ RISCO DA TESE (racha 3a x 4a Turma)
**Pro-cliente (3a Turma)**: dever de seguranca / atipicidade — REsp 2.052.228 /
2.220.333. **Risco (4a Turma)**: entrega voluntaria de senha/token = culpa
exclusiva = fortuito externo (materia NAO pacificada na 2a Secao, jun/2026;
🟡 nao citar n. da 4a Turma sem conferir). **Blindar**: ancorar na **atipicidade
da operacao + omissao no MED + contratacao sem validacao** (defeitos autonomos),
nao em "fui enganado". Avisar o cliente → `monitor-temas-em-definicao` +
`limites-quando-banco-ganha`.

## INTEGRACAO
ANTES: `varredura-jurisprudencial-pre-tese` + `classificador-foro-jec-comum`.
Anexa: `tese-fortuito-interno-sumula-479`, `rebater-culpa-exclusiva-vitima`,
`hipervulneravel-idoso-fraude`, `med-pix-acionamento`, `responsabilidade-banco-recebedor`,
`devolucao-em-dobro`, `tutela-urgencia-bancaria`. Sugere `matriz-protocolos-extrajudiciais`.
DEPOIS: `auditoria-juris-pre-envio` → `protocolo-p4-bancario`.

---
⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
