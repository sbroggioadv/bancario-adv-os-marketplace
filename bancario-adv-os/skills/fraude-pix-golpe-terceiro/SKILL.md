---
name: fraude-pix-golpe-terceiro
description: >
  FRAUDE-PIX-GOLPE-TERCEIRO — Monta a inicial de indenizacao (danos
  materiais + morais) do CLIENTE-vitima contra o banco por golpe PIX,
  falso funcionario, falsa central ou "atualizacao de seguranca".
  Estrutura completa: relacao de consumo (Sum. 297, art. 2o/3o CDC),
  legitimidade passiva, responsabilidade objetiva por fortuito interno
  (Sum. 479 STJ + Tema 466 + art. 14 CDC + CC 927), dever de detectar
  transacao atipica (REsp 2.052.228 + 2.222.059, fintechs incluidas),
  inversao do onus (6o VIII), dano moral in re ipsa + desvio produtivo,
  pedidos e valor da causa. Inclui secao de RISCO DA TESE (3a x 4a Turma).
  Use quando o advogado disser: "golpe pix", "falso funcionario",
  "falsa central", "falso gerente", "atualizacao de seguranca", "estorno",
  "transferencia que nao reconheco", "acao contra banco por fraude".
---

# FRAUDE-PIX-GOLPE-TERCEIRO — Inicial de indenizacao

> Perspectiva: SEMPRE o cliente-vitima (autor) contra o banco (reu).
> Placeholders: {{CLIENTE_NOME}}, {{BANCO_REU}}, {{VALOR_MATERIAL}}, {{COMARCA}}.
> ⚠️ Anti-halucinacao: nenhuma citacao entra na peca sem passar por
> `auditoria-juris-pre-envio` (WebFetch real). Este corpus e o piso.

## 0. ARMADILHAS (gravar antes de redigir)

- 🔴 **Sumula 479 e do STJ, NUNCA do STF** (a 479/STF e margem de rios).
- 🟡 Acordaos de TJ: confirmar n. CNJ + data no inteiro teor antes de citar.
- Gate de foro: PIX + dano moral documental → JEC (opcao do autor).
  Se exigir pericia → Justica Comum (ver `classificador-foro-jec-comum`).
- ANTES de redigir: rodar `varredura-jurisprudencial-pre-tese` (gate ⭐).

## 1. INPUT NECESSARIO

1. Modalidade: golpe PIX / falso funcionario / falsa central / atualizacao de seguranca
2. Dados da conta (numero, agencia) — sem expor no doc final alem do necessario
3. Cronologia: data/hora do contato, o que o golpista sabia (dados confidenciais)
4. Transacoes nao reconhecidas: tipo (PIX/TED/transf. interna), valor, favorecido
5. Houve contato previo ao banco? Resposta do banco (recusa de estorno)?
6. Cliente e idoso/hipervulneravel? (→ `hipervulneravel-idoso-fraude`)
7. Negativacao/saldo negativo? (→ `tutela-urgencia-bancaria`)

## 2. ESTRUTURA DA PETICAO (molde dos seeds PJ/idosa)

### Enderecamento + qualificacao
`EXMO. SR. DR. JUIZ DE DIREITO DE UMA DAS VARAS CIVEIS DA COMARCA DE {{COMARCA}}`
{{CLIENTE_NOME}}, qualificacao completa, por seu advogado → ajuiza
**ACAO DE INDENIZACAO POR DANOS MATERIAIS E MORAIS** em face de {{BANCO_REU}}.

### I — DOS FATOS
Narrar em 1a pessoa do cliente, cronologico:
- Cliente e titular da conta no {{BANCO_REU}}.
- Recebeu contato de pessoa que se passou por funcionario/central do banco,
  **possuindo dados confidenciais** (numero da conta, agencia, CPF, nome do gerente).
- Golpista alegou fraude/PIX suspeito e ofereceu "atualizacao de seguranca"/estorno.
- Cliente, induzido a erro, seguiu o passo a passo. Ponto-chave: o numero/dados
  que **so o banco detinha** → indicio de vazamento interno (fortuito interno).
- Resultado: N transacoes atipicas, em sequencia, valores altos, fora do perfil.
- Cliente comunicou o banco em curto lapso; banco recusou estorno.
> Frase-ancora: "Nao seria possivel a obtencao desses dados senao por falha da Re,
> responsavel pela seguranca das informacoes a que o terceiro teve acesso."

### II — DO DIREITO

**II.1 Relacao de consumo** — art. 2o e 3o §2o CDC (servico bancario incluso)
+ **Sumula 297 STJ** (CDC aplicavel a instituicoes financeiras). PJ tambem e
consumidora por vulnerabilidade tecnica (conceito finalista mitigado, STJ).

**II.2 Legitimidade passiva** — banco e fornecedor; o golpista detinha dados
confidenciais sob guarda do banco → falha no dever de seguranca e de informacao.

**II.3 Responsabilidade objetiva / fortuito interno** (nucleo)
- **Sumula 479 STJ**: "As instituicoes financeiras respondem objetivamente
  pelos danos gerados por fortuito interno relativo a fraudes e delitos
  praticados por terceiros no ambito de operacoes bancarias."
- **Tema 466 STJ** (repetitivo de origem da Sum. 479).
- **art. 14 CDC** (resp. objetiva por defeito do servico) + **CC art. 927 p.u.**
  (teoria do risco da atividade). Detalhamento → `tese-fortuito-interno-sumula-479`.

**II.4 Dever de detectar transacao atipica** ⭐ (diferencial 2025)
- **REsp 2.052.228/DF** (Nancy Andrighi, T3, 12/09/2023): banco deve
  identificar/obstar **movimentacao atipica** ao perfil (valor, horario, local,
  frequencia); ausencia = defeito do servico.
- **REsp 2.222.059/SP** (Villas Boas Cueva, T3, j. 07/10/2025): **instituicoes
  de pagamento/fintechs respondem como bancos** — mata a defesa "sou so IP".
  🟡 (confirmar antes de citar — julgado recente, conferir publicacao oficial).
- Argumento: as operacoes destoavam do perfil; o sistema deveria ter parado.

**II.5 Afastar culpa exclusiva da vitima** — art. 14 §3o CDC so admite
excludente se o defeito inexiste OU culpa exclusiva. A entrega de senha/token
mediante engano NAO e culpa exclusiva: a falha de seguranca do banco e concausa.
Detalhamento + risco → `rebater-culpa-exclusiva-vitima` e secao de risco abaixo.

**II.6 Inversao do onus da prova** — art. 6o VIII CDC (verossimilhanca +
hipossuficiencia tecnica). Cabe ao banco provar a regularidade/idoneidade.

**II.7 Danos materiais** — restituicao integral do valor subtraido
({{VALOR_MATERIAL}}), corrigido desde cada desembolso, juros desde o evento.

**II.8 Dano moral in re ipsa + desvio produtivo**
- Abalo presumido pela quebra de confianca + privacao de recursos.
- **Desvio produtivo do consumidor** (tempo perdido com banco/BO/diligencias).
- PJ tambem sofre dano moral por honra objetiva (**Sumula 227 STJ**).

### III — DOS PEDIDOS
a) procedencia, condenando {{BANCO_REU}} a restituir {{VALOR_MATERIAL}} (material),
corrigido desde o desembolso + juros desde o evento;
b) condenacao em dano moral (sugerir valor fundamentado, ex.: 10 SM ou quantia certa);
c) inversao do onus (6o VIII CDC);
d) (se aplicavel) tutela de urgencia → ver `tutela-urgencia-bancaria`;
e) citacao do reu; producao de todas as provas; honorarios 10-20%.
**Valor da causa** = soma material + moral. Desinteresse em audiencia (334 §5o CPC).

## ⚠️ RISCO DA TESE (racha 3a x 4a Turma)

**A tese pro-cliente** se ancora na **3a Turma STJ** (dever de seguranca /
risco da atividade — REsp 2.052.228 e 2.220.333): o foco e a **operacao atipica
que o banco deveria ter barrado**, nao "quem digitou a senha".

**O RISCO** vem da **4a Turma STJ** (dez/2025-jan/2026): entendimento de que a
**entrega voluntaria de senha + token** configura **culpa exclusiva da vitima =
fortuito externo**, afastando a responsabilidade. 🟡 Numeros divergem entre
fontes — NAO citar n. de REsp da 4a Turma sem confirmar na integra oficial.
**Materia NAO pacificada na 2a Secao** (jun/2026) → risco real por Turma.

**Como BLINDAR a peca:**
1. Nao construir a causa de pedir em "fui enganado/entreguei a senha".
   Construir em **defeito autonomo do servico**: o sistema nao barrou a
   transacao atipica (perfil, valor, frequencia, encadeamento) — REsp 2.052.228.
2. Apontar **concausa**: qualquer falha do banco (nao acionou MED, dado vazado
   internamente, conta-laranja recebedora) quebra a exclusividade da culpa.
3. Invocar **atipicidade da operacao** como o cerne (nao a vitima).
4. Se idoso/hipervulneravel → eleva o dever (Estatuto + Convencao Interamericana).
5. Avisar o cliente do cenario adverso → `monitor-temas-em-definicao` +
   `limites-quando-banco-ganha`.

## INTEGRACAO
- ANTES: `varredura-jurisprudencial-pre-tese` + `classificador-foro-jec-comum`
- Auto-anexa: `tese-fortuito-interno-sumula-479`, `rebater-culpa-exclusiva-vitima`,
  `tutela-urgencia-bancaria`, (se idoso) `hipervulneravel-idoso-fraude`
- Sugere: `matriz-protocolos-extrajudiciais` (fortalecimento probatorio: Registrato/MED)
- DEPOIS (peca final): `auditoria-juris-pre-envio` → `protocolo-p4-bancario`

---
⚠️ Validar via `auditoria-juris-pre-envio` antes de protocolar.
