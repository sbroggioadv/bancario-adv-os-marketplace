---
name: matriz-protocolos-extrajudiciais
description: >
  MATRIZ-PROTOCOLOS-EXTRAJUDICIAIS — Skill-guarda do cluster
  administrativo. Dado o tipo de caso bancario do CLIENTE, lista
  os protocolos/orgaos recomendados (MED, Registrato, Reclamacao
  BC, consumidor.gov.br, PROCON, ANPD, BO, notificacao
  extrajudicial), o que cada um junta nos autos e o peso
  probatorio. Reforca: a camada administrativa FORTALECE a prova,
  NAO trava o acesso ao Judiciario. Use quando o advogado disser:
  "o que protocolar", "antes de processar", "qual orgao
  acionar", "BACEN", "PROCON", "consumidor.gov", "Registrato",
  "MED", "reclamar no banco central", "fortalecer a prova",
  "tentativa extrajudicial", "notificacao antes da acao",
  "ANPD vazamento", "matriz de protocolos".
---

# MATRIZ-PROTOCOLOS-EXTRAJUDICIAIS — Skill-guarda do cluster administrativo

## ⚠️ AVISO LOAD-BEARING (ler sempre, repetir ao cliente)

A camada administrativa **NAO e condicao de procedencia** nem requisito de
admissibilidade da acao judicial (**CF art. 5º, XXXV** — livre acesso ao
Judiciario). O valor e de **FORTALECIMENTO PROBATORIO**: documenta a boa-fe da
vitima, a tentativa previa de solucao, a omissao/recusa do banco, e produz prova
tecnica. O cliente pode ir direto a Justica.
**Unica excecao:** a **representacao no crime de estelionato** (CP art. 171 §5º)
e condicao da **acao penal**, nao da acao civel.

---

## 1. COMO USAR

1. Identifique o tipo de caso (vem da `triagem-caso-bancario` ou pergunte).
2. Localize a linha na matriz abaixo.
3. Liste ao advogado a sequencia recomendada, o que cada protocolo gera nos
   autos e o peso. Sinalize sempre que e fortalecimento, nao trava.
4. Para o passo-a-passo de cada canal, remeta as skills especificas:
   `med-pix-acionamento`, `registrato-extracao-prova`,
   `orientacao-preventiva-falso-advogado`.

---

## 2. MATRIZ TIPO-DE-CASO → PROTOCOLOS

| Tipo de caso | Sequencia recomendada | Orgao(s) | O que junta nos autos | Peso |
|---|---|---|---|---|
| **Golpe PIX / falsa central / falso gerente** | MED → BO → Reclamacao BC + consumidor.gov.br → notificacao extrajudicial | Banco (app) · Policia · BCB · Senacon · Cartorio | Registro MED + resposta/recusa do banco; BO; protocolo BC; resposta consumidor.gov | Alto |
| **Emprestimo/financiamento fraudulento (nao reconhece)** | Registrato (SCR + CCS) → BO → Reclamacao BC + consumidor.gov.br → PROCON | BCB (Registrato) · Policia · BCB · Senacon · PROCON | Relatorio SCR/CCS (prova do contrato que desconhece); BO; respostas | **Altissimo** (SCR e a joia probatoria) |
| **Conta aberta indevidamente em seu nome** | Registrato (CCS) → BO | BCB (Registrato) · Policia | Relatorio CCS (todas as contas no CPF); BO | **Altissimo** (CCS) |
| **Vazamento de dados pessoais** | Requerimento ao banco (LGPD) → peticao a ANPD → BO | Banco · ANPD · Policia | Requerimento LGPD + resposta; protocolo ANPD; BO | Medio (reforca falha de seguranca; ANPD nao indeniza) |
| **Cobranca / tarifa indevida** | consumidor.gov.br → PROCON | Senacon · PROCON | Reclamacao + resposta/silencio do banco | Alto (silencio/recusa = prova) |
| **Superendividamento** | PROCON (nucleo de superendividamento) | PROCON / SNDC | Requerimento de repactuacao; ata de audiencia conciliatoria | Alto (104-C: via administrativa concorrente e facultativa) |
| **Negativacao indevida (SERASA/SPC)** | consumidor.gov.br + Reclamacao BC → notificacao extrajudicial | Senacon · BCB · Cartorio | Reclamacoes + resposta; print da negativacao; notificacao | Medio-alto |

> Em casos de fraude com idoso/hipervulneravel, registre tambem no BO essa
> condicao e mencione nas reclamacoes — agrava o dever do banco.

---

## 3. FICHA RAPIDA DOS CANAIS

- **MED (PIX):** app do banco, **≤ 80 dias** da fraude; bloqueio cautelar 72h.
  MED 2.0 obrigatorio desde **02/02/2026**. Detalhe → `med-pix-acionamento`.
  A omissao do banco no MED e **falha autonoma** que reforca a acao.
- **Registrato (BCB):** acesso via **gov.br prata/ouro**. SCR = emprestimos/
  financiamentos; CCS = contas e relacionamentos. **Prova tecnica** de credito/
  conta fraudulenta. Detalhe → `registrato-extracao-prova`.
- **Reclamacao BC / RDR (bcb.gov.br/meubc):** resposta obrigatoria do banco em
  **10 dias uteis** + entra no Ranking de Reclamacoes. **O BC NAO resolve o caso
  individual** — serve como prova de provocacao e da conduta do banco.
- **consumidor.gov.br (gov.br):** banco responde em 10 dias, consumidor avalia em
  20. **Silencio ou recusa = prova robusta** de descaso.
- **PROCON / CIP:** estadual; o CIP notifica o banco. 🟡 regras variam por estado
  (confirmar antes de citar prazo local).
- **ANPD / LGPD:** primeiro **requerimento ao banco** (controlador), depois
  peticao do titular no Sistema de Requerimentos (gov.br). Analise agregada — nao
  indeniza, mas documenta a falha de seguranca.
- **BO / Delegacia eletronica:** 🟡 URL varia por estado. Estelionato CP art. 171
  (acao penal **condicionada a representacao**); fraude eletronica art. 171 §2º-A
  (Lei 14.155/2021). Para o falso-advogado, ver `orientacao-preventiva-falso-advogado`.
- **Notificacao extrajudicial:** por AR ou Cartorio de Titulos e Documentos.
  Constitui o banco em **mora** (CC art. 397) e fixa marco temporal.

---

## 4. COMO O EXTRAJUDICIAL VIRA PROVA NA INICIAL

1. **Boa-fe da vitima:** mostra que tentou resolver antes de litigar.
2. **Omissao do banco:** resposta evasiva, silencio ou recusa = prova de descaso
   e da falha do servico (CDC art. 14).
3. **Tentativa previa:** afasta eventual alegacao de litigancia precipitada.
4. **Prova tecnica:** SCR/CCS (Registrato) e registro do MED sao documentos
   tecnicos oficiais — peso muito superior a mera narrativa.
5. **Marco temporal:** datas dos protocolos ancoram juros, mora e tutela.

Anexar a inicial: print/PDF de cada protocolo + resposta do banco (ou prova do
silencio) + relatorios Registrato + registro do MED + BO.

---

## 5. INTEGRACAO

**Upstream:** `triagem-caso-bancario` · `bancario-master`
**Downstream (detalhe por canal):** `med-pix-acionamento` ·
`registrato-extracao-prova` · `orientacao-preventiva-falso-advogado`
**Alimenta as iniciais:** `fraude-pix-golpe-terceiro` ·
`financiamento-emprestimo-fraudulento` · `tutela-urgencia-bancaria`

---

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
