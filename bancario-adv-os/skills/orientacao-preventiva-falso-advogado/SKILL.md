---
name: orientacao-preventiva-falso-advogado
description: >
  ORIENTACAO-PREVENTIVA-FALSO-ADVOGADO — Dupla face do golpe do
  falso advogado. (a) CLIENTE: como nao cair — confirmar
  identidade pelo contrato/contatos conhecidos, usar o ConfirmADV
  da OAB (confirma advogado por OAB+UF+e-mail), NUNCA pagar por
  mensagem/PIX urgente, guardar prints, ir a delegacia. (b)
  ADVOGADO usurpado: boa pratica de resposta (BO + comunicacao a
  seccional da OAB + aviso em massa aos clientes + preservacao de
  prova). Use quando o advogado disser: "falso advogado", "alguem
  se passou por mim", "golpe do advogado", "ganhei a acao taxa pra
  liberar", "intimacao falsa", "ConfirmADV", "confirmar
  advogado", "cliente caiu em golpe usando meu nome", "usurpacao
  de identidade profissional", "pix urgente para advogado".
---

# ORIENTACAO-PREVENTIVA-FALSO-ADVOGADO — Prevencao e resposta (dupla face)

## ⚠️ AVISO LOAD-BEARING

Acionar canais administrativos/preventivos (BO, OAB, ConfirmADV) **NAO e
condicao de procedencia** nem requisito de admissibilidade de eventual acao civel
(**CF art. 5º, XXXV** — livre acesso). E **FORTALECIMENTO PROBATORIO** (documenta
boa-fe, tentativa previa e a fraude). **Excecao:** a **representacao no estelionato**
(CP art. 171 §5º) e condicao da **acao penal**, nao da civel.

---

## FACE A — CLIENTE: COMO NAO CAIR NO GOLPE

### Sinais de alerta
- Mensagem dizendo que o cliente "ganhou a acao" e que ha **taxa/PIX urgente** pra
  liberar o valor.
- Contato por **numero/canal novo** alegando ser o advogado ou o cartorio.
- Pressao por **urgencia** e pedido de pagamento imediato.
- Intimacao/documento falso anexado.

### Regras de ouro (orientar o cliente)
1. **Confirmar pelo contrato e contatos conhecidos** — ligar para o numero antigo
   ja registrado do advogado/escritorio, nunca responder no canal novo.
2. **Usar o ConfirmADV da OAB** — campanha nacional (lancada 29/04/2025) em que o
   cidadao confirma a identidade do advogado por **OAB + UF + e-mail**.
3. **NUNCA pagar por mensagem/PIX urgente** — advogado nao cobra "taxa pra liberar
   valor de processo" por PIX urgente.
4. **Guardar todos os prints** — conversas, numeros, comprovantes, documentos
   recebidos.
5. **Ir a delegacia** (BO; delegacia eletronica 🟡 URL varia por estado) — se houve
   pagamento, ha estelionato (CP art. 171; fraude eletronica §2º-A, Lei 14.155/2021).
6. Se houve pagamento via PIX, acionar tambem o **MED** (ver `med-pix-acionamento`).

> Apoio documental: cartilhas OAB-SP/PR/GO/RJ/BA e alertas de STF/TRF3/TJDFT (2025)
> 🟡 confirmar a versao vigente antes de citar.

---

## FACE B — ADVOGADO USURPADO: BOA PRATICA DE RESPOSTA

> 🟡 O **dever normativo** de o advogado usurpado comunicar a OAB **nao foi
> confirmado** textualmente no corpus → tratar como **boa pratica**, nao como
> obrigacao legal. Nao afirmar como imposicao.

Checklist de resposta (boa pratica):
1. **Boletim de Ocorrencia** — registrar a usurpacao de identidade/estelionato em
   nome de terceiros, com todos os prints.
2. **Comunicar a seccional da OAB** — informar a fraude (uso indevido do nome/
   inscricao) para alerta e providencias.
3. **Aviso em massa aos clientes** — comunicado pelos canais oficiais do escritorio
   esclarecendo o golpe e reforcando que nao se cobra taxa por PIX urgente.
4. **Preservar a prova** — salvar perfis falsos, numeros, conversas, documentos
   forjados (uteis em representacao criminal e eventual acao civel).
5. Se a fraude usou **dados de processo publico** (PJe/SAJ), avaliar frente
   adicional: vazamento/seguranca de dados (LGPD/ANPD) — reforca, nao substitui.

---

## CONTEXTO (CNJ — vazamento de dados de processos)

Noticia CNJ (18/03/2026): organizacoes exploram **dados de processos publicos**
(PJe/SAJ) para o golpe; **70,5%** das denuncias vieram de advogados. Resposta
institucional: MFA nos sistemas + PL 4.709/2025 + articulacao com a ANPD. Para o
cliente vitima, o vazamento **nao transfere culpa a ele** — reforca a
previsibilidade da fraude.

---

## INTEGRACAO

**Upstream:** `matriz-protocolos-extrajudiciais` · `triagem-caso-bancario`
**Downstream:** `golpe-falso-advogado` (inicial completa) · `med-pix-acionamento`
(se houve PIX) · `responsabilidade-banco-recebedor` (conta-laranja)

---

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
