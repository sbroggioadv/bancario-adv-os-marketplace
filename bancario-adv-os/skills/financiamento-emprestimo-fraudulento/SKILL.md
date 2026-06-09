---
name: financiamento-emprestimo-fraudulento
description: >
  FINANCIAMENTO-EMPRESTIMO-FRAUDULENTO — Acao declaratoria de
  inexigibilidade de debito (emprestimo/financiamento/consignado/cartao
  contratado por golpista em nome do cliente) c/c restituicao + danos,
  na perspectiva do CLIENTE que NUNCA anuiu. Foco: vicio de consentimento
  (inexistencia do negocio juridico); inversao do onus (banco prova a
  contratacao valida — biometria/logs/geolocalizacao — art. 6o VIII CDC +
  Sum. 479 + REsp 2.052.228); declaracao de inexigibilidade + cancelamento
  dos contratos; restituicao em dobro (Tema 929, gate 30/03/2021); se houver
  desconto em beneficio/conta ou negativacao, tutela de urgencia. Inclui
  RISCO DA TESE. Use quando: "emprestimo que nao fiz", "financiamento
  fraudulento", "nao reconheco esse contrato", "consignado fraudulento",
  "cartao que nao contratei", "cancelar emprestimo fraudulento", "biometria fraudada".
---

# FINANCIAMENTO-EMPRESTIMO-FRAUDULENTO — Declaratoria de inexigibilidade

> Perspectiva: cliente (autor) x banco (reu). Placeholders: {{CLIENTE_NOME}},
> {{BANCO_REU}}, {{COMARCA}}, {{CONTRATOS}}, {{VALOR_DEBITO}}.
> ⚠️ Nenhuma citacao na peca sem `auditoria-juris-pre-envio` (WebFetch real).
> Diferenca para fraude-pix: aqui o nucleo e a **INEXISTENCIA do contrato**
> (cliente nunca contratou), nao apenas a transferencia indevida.

## 0. ARMADILHAS
- 🔴 Sumula 479 e do **STJ**, nunca do STF.
- 🟡 Acordaos de TJ: confirmar n. CNJ + data no inteiro teor antes de citar.
- ⏱️ Devolucao em dobro: **gate 30/03/2021** (Tema 929). Antes = simples.
- Foro: se o caso exigir pericia (ex.: discutir encargos do contrato), → Justica
  Comum (FONAJE 70/94). Inexigibilidade simples + dano documental → JEC possivel.
- ANTES de redigir: `varredura-jurisprudencial-pre-tese` + `classificador-foro-jec-comum`.

## 1. INPUT
1. Tipo de contrato fraudulento: emprestimo pessoal, financiamento, consignado, cartao
2. Numero(s) do(s) contrato(s) {{CONTRATOS}}, valor, n. de parcelas, data
3. Como o cliente descobriu (desconto no beneficio, fatura, Registrato/SCR)
4. Canal alegado de contratacao pelo banco (app, biometria, internet banking)
5. Ha desconto em beneficio/conta? Negativacao? (→ tutela)
6. Cliente idoso/hipervulneravel?
7. Houve golpe associado (falso funcionario/advogado) ou contratacao "fria" por terceiro?

## 2. ESTRUTURA — ACAO DECLARATORIA DE INEXIGIBILIDADE DE DEBITO C/C RESTITUICAO E DANOS

Enderecamento a uma das Varas Civeis de {{COMARCA}}. Prioridade idoso (1.048 I CPC +
71 Estatuto) e gratuidade (98 CPC) se cabivel. Desinteresse na audiencia (334 §5o).

### I — DOS FATOS
{{CLIENTE_NOME}} **jamais contratou** os emprestimos/financiamentos {{CONTRATOS}}.
Tomou ciencia por [desconto no beneficio / fatura / extrato Registrato]. Os valores
foram liberados e imediatamente escoados a terceiros, em padrao incompativel com seu
perfil. Comunicou o banco, que se recusou a cancelar / impos prazo abusivo.
> Frase-ancora: "A autora nunca anuiu com a contratacao; sua suposta autorizacao e
> fruto de acao fraudulenta de terceiro — vicio que compromete a propria existencia
> do negocio juridico."

### II — DO DIREITO

**II.1 Relacao de consumo** — art. 2o/3o §2o CDC + **Sum. 297 STJ**.

**II.2 Inexistencia/nulidade do negocio juridico** — a validade pressupoe
manifestacao de vontade livre e inequivoca (CC). Contratacao por terceiro fraudador
→ **vicio absoluto** → inexigibilidade de todos os debitos decorrentes.

**II.3 Responsabilidade objetiva / fortuito interno** — **Sum. 479 STJ** + Tema 466
+ art. 14 CDC + CC 927 p.u. → `tese-fortuito-interno-sumula-479`.

**II.4 Dever de seguranca / validacao da contratacao** ⭐ — **REsp 2.052.228/DF**
(Nancy Andrighi, T3, 12/09/2023): banco que viabiliza contratacao facilitada (app,
redes sociais) deve ter mecanismos que identifiquem/obstem operacoes que destoam do
perfil; ausencia = defeito. Contratacao de credito + escoamento imediato = padrao de
fraude detectavel.

**II.5 Inversao do onus da prova** ⭐ (nucleo desta acao) — **art. 6o VIII CDC**.
Nao se exige prova negativa do consumidor (provar que NAO contratou). Cabe ao
**banco comprovar a contratacao valida**: registros de autenticacao segura,
**biometria**, **geolocalizacao**, gravacao de voz, **logs de acesso**. Juntar
contrato digital ou registro unilateral **nao basta** (a jurisprudencia exige
demonstracao de efetiva confirmacao de identidade). Ausencia → inexigibilidade.
Atencao: ha julgados reconhecendo fraude **mesmo com biometria** quando ausente
prova de ciencia inequivoca, sobretudo com idoso (🟡 confirmar TJ aplicavel via
`varredura-jurisprudencial-pre-tese`).

**II.6 Hipervulneravel idoso** (se aplicavel) — Estatuto + Convencao Interamericana;
agrava o dever de validacao. → `hipervulneravel-idoso-fraude`.

**II.7 Restituicao** — valores ja descontados restituidos, corrigidos do desembolso,
juros da citacao; **em dobro** se cobranca pos 30/03/2021 (**Tema 929 + EAREsp
600.663/RS**, Corte Especial) → `devolucao-em-dobro`.

**II.8 Dano moral** — inscricao indevida em cadastro de inadimplentes (in re ipsa,
**Sum. 385 STJ** ressalvada) e/ou desvio produtivo; agravado por verba alimentar.

### III — DA TUTELA DE URGENCIA (se ha desconto/negativacao)
art. 300 CPC, inaudita altera parte: suspender exigibilidade dos contratos; abster
de descontar no beneficio/conta; abster de negativar; astreintes (537). Detalhe →
`tutela-urgencia-bancaria`.

### IV — DOS PEDIDOS
a) tutela de urgencia (suspender contratos / descontos / negativacao);
b) ao final, **declarar a inexigibilidade** de {{CONTRATOS}} e cancela-los,
afastando saldo, juros e encargos deles decorrentes;
c) **restituir** {{VALOR_DEBITO}} ja descontado (simples ou dobro conforme o gate);
d) **dano moral** (quantia certa fundamentada);
e) inversao do onus (6o VIII CDC); prioridade idoso; custas + honorarios.
**Valor da causa** = proveito economico (somatorio dos contratos cancelados) + danos.

## ⚠️ RISCO DA TESE (racha 3a x 4a Turma)
**Pro-cliente (3a Turma)**: dever de seguranca + onus do banco de provar a
contratacao valida (REsp 2.052.228). **Risco (4a Turma)**: quando a fraude
envolve entrega voluntaria de senha/token pela vitima, ha entendimento de culpa
exclusiva (materia NAO pacificada, jun/2026; 🟡 nao citar n. da 4a Turma sem
conferir). **Blindar**: nesta acao o eixo e a **inexistencia do contrato + ausencia
de prova de contratacao valida** (onus do banco). Quando NAO houve entrega de
senha/token pela vitima (contratacao "fria" por terceiro com dados vazados), o
risco da 4a Turma e menor — explorar isso. Avisar o cliente →
`monitor-temas-em-definicao` + `limites-quando-banco-ganha`.

## INTEGRACAO
ANTES: `varredura-jurisprudencial-pre-tese` + `classificador-foro-jec-comum`.
Anexa conforme o caso: `tese-fortuito-interno-sumula-479`, `rebater-culpa-exclusiva-vitima`,
`hipervulneravel-idoso-fraude`, `devolucao-em-dobro`, `tutela-urgencia-bancaria`.
Sugere `registrato-extracao-prova` (SCR = prova tecnica do emprestimo fraudulento) e
`matriz-protocolos-extrajudiciais`.
DEPOIS: `auditoria-juris-pre-envio` → `protocolo-p4-bancario`.
Cross-link soft: se houver superendividamento, expurgar este contrato ANTES de
`repactuacao-104a-104b` (sugestao, nao execucao).

---
⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
