---
name: defesa-busca-apreensao
description: >
  DEFESA-BUSCA-APREENSAO — Defesa do cliente-devedor na acao de busca e apreensao
  de bem em alienacao fiduciaria (DL 911/1969). Teses: comprovacao da mora
  imprescindivel (Sum. 72 STJ); purgacao da mora = pagamento INTEGRAL (parcelas
  vencidas + vincendas) em 5 dias (Tema 722 STJ) — avisar o cliente que NAO basta
  pagar as atrasadas; revisao incidental de encargos abusivos; Sum. 286
  (renegociacao nao impede revisao). Orienta quando cabe contestacao x quando cabe
  defesa por revisional/embargos. Use quando o advogado disser: "busca e
  apreensao", "tomaram meu carro", "defesa em busca e apreensao", "purgar a mora",
  "alienacao fiduciaria", "DL 911", "reintegracao do veiculo", "como defender
  busca e apreensao", "5 dias para pagar".
---

# DEFESA-BUSCA-APREENSAO — Cliente-devedor (DL 911/1969)

> Defesa na busca e apreensao de bem alienado fiduciariamente. O eixo e: mora
> (Sum. 72), purgacao integral (Tema 722) e revisao incidental de encargos.

## 1. AVISO CRITICO AO CLIENTE (load-bearing)

⚠️ **Purgar a mora = pagar o TOTAL (parcelas vencidas + vincendas) em 5 dias**
apos executada a liminar — **NAO basta pagar as atrasadas** (Tema 722 STJ, sob a
redacao da Lei 10.931/2004 ao DL 911/1969). Esse e o erro mais comum do cliente.
Comunicar isso ANTES de qualquer estrategia.

## 2. INPUT NECESSARIO

- Contrato de alienacao fiduciaria + situacao da mora (quantas parcelas, valores).
- Foi executada a liminar? Quando? (conta o prazo de 5 dias).
- Houve **notificacao previa** valida constituindo em mora? (Sum. 72).
- Ha indicios de encargos abusivos? (porta da revisao incidental).
- Capacidade financeira para purgacao integral?

## 3. TESES DE DEFESA (corpus validado)

### a) Mora nao comprovada (Sum. 72 STJ) — preliminar forte
- **Sum. 72:** a comprovacao da **mora** e **imprescindivel** a busca e apreensao.
- Atacar: notificacao extrajudicial ausente, enviada a endereco errado, sem AR,
  ou protesto invalido. Mora nao comprovada → **indeferimento/improcedencia**.

### b) Purgacao integral da mora (Tema 722)
- Se o cliente tem como pagar: requerer purgacao **integral** (vencidas +
  vincendas) em 5 dias → restituicao do bem e continuidade do contrato.
- Deixar claro o valor exato e o prazo. Pedir certidao/intimacao do quantum.

### c) Revisao incidental de encargos abusivos
- **Sum. 286:** renegociacao/confissao **nao impede** revisao de ilegalidades
  anteriores. Discutir capitalizacao (Sum. 539/541), comissao de permanencia
  (Sum. 472), TAC/TEC (Sum. 565), servicos de 3os (Tema 958), multa > 2% (CDC 52).
- Efeito: se o **valor da mora cai** apos expurgo, a purgacao fica menor e pode
  descaracterizar a propria mora. Puxar de `detector-encargos-abusivos`.
- Sum. 297 (CDC aplicavel); Tema 27 para juros (so com abusividade demonstrada).

### d) Tutela / continuidade
- Pedir manutencao na posse ate decisao sobre a purgacao; CPC 300 quando houver
  fumus (mora nao comprovada / encargos abusivos) + periculum (perda do bem de
  trabalho/locomocao).

## 4. CONTESTACAO x EMBARGOS x REVISIONAL (roteamento)

| Via | Quando |
|---|---|
| **Contestacao** (no DL 911) | resposta dentro da propria busca e apreensao: mora, purgacao, revisao incidental |
| **Acao revisional autonoma** | quando a discussao de encargos exige pericia e amplitude → ver `peticao-revisional-bancaria` (Justica Comum) |
| **Embargos** | NAO e a via da busca e apreensao; e da execucao de CCB → ver `embargos-execucao-ccb` |

⚠️ Busca e apreensao se defende por **contestacao** (DL 911), nao por embargos.
Embargos sao para execucao de titulo (CCB).

## 5. ESTRUTURA DA CONTESTACAO

1. Enderecamento ao juizo da busca e apreensao.
2. Preliminar — **mora nao comprovada** (Sum. 72).
3. Merito — revisao incidental de encargos (Sum. 286 + detector).
4. **Da purgacao integral** (Tema 722) — se aplicavel, requerer o quantum e o
   prazo de 5 dias; deposito.
5. Pedidos — improcedencia / restituicao do bem; subsidiariamente, purgacao.
6. Provas, gratuidade, prioridade idoso (CPC 1.048) se cabe.

## 6. PROIBICOES

1. NUNCA dizer ao cliente que basta pagar as **atrasadas** (e integral — Tema 722).
2. NUNCA tratar a defesa como "embargos" (busca e apreensao = contestacao).
3. NUNCA afirmar abusividade de juros como certa sem demonstrar (Tema 27).
4. NUNCA hardcodar taxa media BACEN no recalculo da mora.
5. NUNCA citar Sum. 479 do STF (e do STJ).

## 7. INTEGRACAO

- **Upstream:** `triagem-caso-bancario`, `detector-encargos-abusivos`.
- **Downstream:** `peticao-revisional-bancaria` (revisional autonoma),
  `recursos-civeis-router`, `protocolo-p4-bancario`.

## 💡 Proximos passos opcionais

| Proximo passo | Comando | Plugin necessario |
|---|---|---|
| Recalcular a mora apos expurgo | `/calculos calculo-revisao-bancaria` | `calculosjudiciais-adv-os` |
| Buscar julgado do TJ sobre purgacao | `/juris buscar` | `juris-adv-os` |

> Se plugin nao instalado, usar a estrutura acima manualmente.

> ⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
