---
name: registrato-extracao-prova
description: >
  REGISTRATO-EXTRACAO-PROVA — Orienta o CLIENTE a emitir os
  relatorios do Registrato (Banco Central) como PROVA TECNICA em
  acoes contra o banco. SCR (emprestimos/financiamentos) prova o
  contrato fraudulento que a vitima desconhece; CCS (contas e
  relacionamentos) prova conta aberta indevidamente no seu nome;
  Chaves Pix. Acesso via gov.br nivel prata ou ouro. URL oficial
  bcb.gov.br/cidadaniafinanceira/registrato. E a "joia
  probatoria" das fraudes de credito e conta. Use quando o
  advogado disser: "Registrato", "SCR", "CCS", "extrato do banco
  central", "relatorio de emprestimos", "ver contas no meu CPF",
  "emprestimo que nao fiz", "conta aberta no meu nome", "prova do
  contrato fraudulento", "consulta sistema de cadastro", "chaves
  pix no meu CPF".
---

# REGISTRATO-EXTRACAO-PROVA — Relatorios do BCB como prova tecnica

## ⚠️ AVISO LOAD-BEARING

Emitir os relatorios do Registrato **NAO e condicao de procedencia** nem
requisito de admissibilidade da acao (**CF art. 5º, XXXV** — livre acesso). E
**FORTALECIMENTO PROBATORIO**: os relatorios sao **documentos tecnicos oficiais
do Banco Central** que provam, em nome do proprio cliente, a existencia do
contrato/conta que ele desconhece — peso muito superior a mera narrativa.

---

## 1. O QUE E E ONDE ACESSAR

- **Registrato** = Registro de Informacoes do BCB, gratuito, no nome do titular.
- **URL oficial:** **bcb.gov.br/cidadaniafinanceira/registrato**
- **Acesso:** login **gov.br nivel prata ou ouro** (o cliente faz com o proprio
  CPF; o advogado orienta, nao acessa pelo cliente sem procuracao especifica).

---

## 2. OS TRES RELATORIOS-CHAVE

| Relatorio | O que mostra | Prova de... | Peso |
|---|---|---|---|
| **SCR** (Sistema de Informacoes de Creditos) | Todos os emprestimos, financiamentos e operacoes de credito no CPF, por instituicao | **Emprestimo/financiamento fraudulento** que a vitima desconhece | **Altissimo** |
| **CCS** (Cadastro de Clientes do Sistema Financeiro) | Todas as contas e relacionamentos (bancos, corretoras) vinculados ao CPF | **Conta aberta indevidamente** em seu nome | **Altissimo** |
| **Chaves Pix** | Chaves PIX registradas no CPF e a instituicao de cada uma | Chave criada por terceiro / conta-laranja vinculada | Alto |

> Em fraude de credito/conta, **o SCR e o CCS sao a joia probatoria** do caso:
> documentam objetivamente a operacao que sustenta a declaratoria de
> inexigibilidade.

---

## 3. PASSO-A-PASSO PARA O CLIENTE

1. Acessar **bcb.gov.br/cidadaniafinanceira/registrato** e logar com **gov.br
   prata/ouro** (se for nivel bronze, elevar o nivel — orientar como).
2. Emitir o **SCR** (relatorio detalhado por instituicao e modalidade).
3. Emitir o **CCS** (lista de relacionamentos/contas).
4. Emitir **Chaves Pix**, se o caso envolver PIX.
5. **Salvar os PDFs** gerados pelo proprio sistema do BCB (preservam a marca de
   autenticidade e a data de emissao).
6. Guardar a **data de emissao** — ela ancora o marco temporal da fraude.

---

## 4. COMO USAR NA PETICAO

- **Inicial declaratoria de inexigibilidade:** o SCR demonstra a operacao de
  credito nao reconhecida → instrui o pedido de declaracao de inexigibilidade +
  restituicao (ver `financiamento-emprestimo-fraudulento`).
- **Conta-fantasma:** o CCS demonstra o relacionamento nao contratado → instrui o
  pedido de encerramento e indenizacao.
- **Inversao do onus** (CDC art. 6º, VIII): a vitima ja traz a prova objetiva da
  existencia; cabe ao banco provar a regularidade da contratacao.
- **Tutela de urgencia:** os relatorios robustecem o fumus para suspender
  descontos/negativacao (ver `tutela-urgencia-bancaria`).
- **Banco recebedor:** o CCS pode revelar a instituicao da conta-laranja →
  pedido de exibicao dos docs de abertura/KYC (ver
  `responsabilidade-banco-recebedor`).

Anexar a inicial: PDF do SCR + PDF do CCS (+ Chaves Pix) emitidos pelo BCB, com a
data de emissao visivel.

---

## 5. CUIDADOS

- O relatorio e do **proprio titular** — orientar o cliente a emitir; o advogado
  so o faz com procuracao/poderes especificos.
- Dados financeiros sensiveis: tratar com sigilo (LGPD); nao colar em pasta
  sincronizada/compartilhada.
- Nao "lembrar" ou inventar valores — os numeros vem do PDF oficial emitido.

---

## 6. INTEGRACAO

**Upstream:** `matriz-protocolos-extrajudiciais` · `triagem-caso-bancario`
**Downstream:** `financiamento-emprestimo-fraudulento` ·
`responsabilidade-banco-recebedor` · `tutela-urgencia-bancaria`

---

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
