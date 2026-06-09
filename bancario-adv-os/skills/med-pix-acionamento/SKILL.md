---
name: med-pix-acionamento
description: >
  MED-PIX-ACIONAMENTO — Guia do Mecanismo Especial de Devolucao
  (MED) do PIX para o CLIENTE vitima de golpe. Aplica gate de
  data: fraude antes de 02/02/2026 segue Res. BCB 103/2021;
  fraude a partir de 02/02/2026 segue o MED 2.0 (Res. BCB
  493/2025 — rastreio ate 5 camadas, monitoramento 90 dias, 100%
  digital). Orienta acionamento pelo app (prazo ate 80 dias),
  bloqueio cautelar de 72h, e como usar o registro/recusa do
  banco como prova de (in)diligencia. Tese: omissao no MED =
  falha autonoma do banco. Use quando o advogado disser: "MED",
  "devolver o pix", "estorno do golpe", "mecanismo de devolucao",
  "bloqueio cautelar pix", "acionar o banco do golpe",
  "MED 2.0", "resolucao 493", "rastreio do pix".
---

# MED-PIX-ACIONAMENTO — Acionar o Mecanismo Especial de Devolucao

## ⚠️ AVISO LOAD-BEARING

Acionar o MED **NAO e condicao de procedencia** nem requisito de admissibilidade
da acao civel (**CF art. 5º, XXXV** — livre acesso). E **FORTALECIMENTO
PROBATORIO**: o registro do MED e a resposta (ou silencio/recusa) do banco
documentam a tentativa previa, a boa-fe da vitima e a (in)diligencia da
instituicao. A vitima pode litigar mesmo sem ter acionado o MED, ou apos a recusa.

---

## 1. GATE DE DATA (decidir SEMPRE primeiro)

Pergunte a **data da fraude** e aplique:

| Data da fraude | Regime aplicavel | Citacao |
|---|---|---|
| **Antes de 02/02/2026** | MED original — **Res. BCB 103/2021** (instituiu o MED; em operacao desde 16/11/2021) | Res. BCB 103/2021 + Res. BCB 1/2020, art. 39-B |
| **A partir de 02/02/2026** | **MED 2.0** — **Res. BCB 493/2025** (facultativo desde 23/11/2025, **obrigatorio desde 02/02/2026**) | Res. BCB 1/2020, art. 39-B, com redacao da Res. BCB 493/2025 |

Forma canonica de citar (mantem o marco): *"Res. BCB 1/2020, art. 39-B, c/
redacao da Res. BCB 493/2025"*, indicando a Res. 103/2021 como norma instituidora.

🟡 A **redacao literal dos artigos** da Res. BCB 493/2025 deve ser **confirmada
antes de transcrever em peca** (corpus marca ✅ existencia/datas, 🟡 texto literal).

---

## 2. O QUE MUDA NO MED 2.0 (a partir de 02/02/2026)

- **Rastreio em ate 5 camadas** da movimentacao fraudulenta (segue o dinheiro
  alem da primeira conta-laranja).
- **Bloqueio coordenado** entre as instituicoes da cadeia.
- **Monitoramento de 90 dias** pelo PSP recebedor.
- **Bloqueio cautelar de 72h** sob fundada suspeita (art. 39-B).
- **Processo 100% digital.**

Esses deveres reforcados sustentam a tese de que, na fraude pos-02/02/2026, a
inercia do banco e ainda mais grave (havia obrigacao regulamentar de rastrear).

---

## 3. PASSO-A-PASSO DO ACIONAMENTO

1. **Onde:** app/canais do **banco pagador** (de onde saiu o PIX). O proprio
   sistema encaminha ao PSP recebedor.
2. **Prazo:** registrar o MED em **ate 80 dias** da transacao fraudulenta. Quanto
   mais cedo, maior a chance de bloqueio do saldo.
3. **Bloqueio cautelar:** o PSP recebedor pode bloquear o valor por **72h** sob
   fundada suspeita (art. 39-B) enquanto analisa.
4. **Acompanhar e registrar tudo:** numero de protocolo, prints de cada etapa,
   data/hora e a resposta final (devolucao total/parcial ou recusa).
5. **Se recusa ou silencio:** preservar a resposta — vira prova da falha (vai a
   inicial e a `tutela-urgencia-bancaria`).

---

## 4. TESE — OMISSAO NO MED = FALHA AUTONOMA

A nao adocao tempestiva/diligente do MED pelo banco e um **defeito autonomo do
servico** (CDC art. 14), independente da discussao sobre quem digitou a senha.
Ancoras (sempre via `auditoria-juris-pre-envio`):

- **Sumula 479 STJ** — responsabilidade objetiva por fortuito interno em fraudes
  de terceiros nas operacoes bancarias.
- **Dever de seguranca** (corpus §1): o banco deve identificar/obstar
  movimentacao atipica; falhar no MED reforca esse descumprimento.
- A **concausa** (banco nao acionou/atrasou o MED) **quebra a exclusividade** de
  eventual culpa atribuida a vitima → ver `rebater-culpa-exclusiva-vitima`.

> 🟡 **Risco da tese:** a 4ª Turma do STJ tem precedentes (entrega voluntaria de
> senha/token = culpa exclusiva) — ver `monitor-temas-em-definicao` e
> `limites-quando-banco-ganha`. A omissao no MED ajuda a blindar a peca, mas nao
> e blindagem absoluta.

---

## 5. COMO USAR COMO PROVA

| Resultado do MED | Como usar nos autos |
|---|---|
| Devolucao total | Encerra o dano patrimonial; restam danos morais/consequenciais |
| Devolucao parcial | Documenta o saldo nao recuperado + a falha de rastreio |
| Recusa | Prova de descaso e da falha do servico → sustenta tutela e merito |
| Silencio/sem resposta | Prova de inercia → inversao do onus (CDC art. 6º, VIII) |

Sempre anexar: comprovante de registro do MED + protocolo + resposta do banco
(ou prova do silencio) + extrato da transacao.

---

## 6. INTEGRACAO

**Upstream:** `matriz-protocolos-extrajudiciais` · `triagem-caso-bancario`
**Downstream:** `fraude-pix-golpe-terceiro` · `tutela-urgencia-bancaria` ·
`responsabilidade-banco-recebedor` · `rebater-culpa-exclusiva-vitima`

---

⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
