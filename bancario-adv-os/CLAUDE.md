# CLAUDE.md — plugin-bancario (interno do source)

> Regras internas do source `plugin-bancario/`. Plugin alvo: `bancario-adv-os`. Familia Adv-OS.
> Spec e corpus jurídico vivem em `.planning/` (dev-only, fora do marketplace).

## Identidade
- **Slug:** `bancario-adv-os` · **Orquestrador:** `bancario-master` · **Onboarding:** `/start-bancario`
- **Source privado:** este diretorio → repo privado do organizador
- **Marketplace publico:** repo `bancario-adv-os-marketplace` (org do organizador)
- **Posicionamento:** plugin-mae premium. Preco sugerido R$ 298–398 (definir FASE 6).
- **Perspectiva:** sempre o CLIENTE do banco (autor/vitima/devedor), nunca o banco.

## Filosofia (3 pilares + 1 gate)
1. **Standalone-first** — zero dependencia de runtime; cross-link = sugestao de comando (texto), nunca import/execucao.
2. **Anti-halucinacao por design** — toda citacao passa por `auditoria-juris-pre-envio` (WebFetch real). Corpus marca ✅/🟡/🔴. Tese em disputa NUNCA e afirmada como pacificada.
3. **Auditoria, nao so geracao** — `protocolo-p4-bancario` + `limites-quando-banco-ganha` (postura honesta).
4. **Gate exclusivo:** `varredura-jurisprudencial-pre-tese` ⭐ — varredura do entendimento atual ANTES de redigir (bloqueante para pecas).

## Postura das teses de fraude (decisao do operador, 2026-06-09): HONESTA
Skills de fraude montam a tese pro-cliente (3a Turma STJ) MAS sinalizam o risco da 4a Turma (entrega de senha/token = culpa exclusiva) e como blindar a peca. Secao fixa "⚠️ Risco da tese" + skill `monitor-temas-em-definicao` (com `limites-quando-banco-ganha` embutido).

## Skill map (35 + orquestrador) — ver .planning/2026-06-09-design-spec.md §3
Tier 0: bancario-master, bancario-onboarding
Tier 1: triagem-caso-bancario, varredura-jurisprudencial-pre-tese, classificador-foro-jec-comum
Tier 2 fraudes: fraude-pix-golpe-terceiro, golpe-falso-advogado, financiamento-emprestimo-fraudulento, tese-fortuito-interno-sumula-479, rebater-culpa-exclusiva-vitima, responsabilidade-banco-recebedor, hipervulneravel-idoso-fraude, tutela-urgencia-bancaria
Tier 2 revisional: previa-abusividade-revisional, detector-encargos-abusivos, peticao-revisional-bancaria, defesa-busca-apreensao, embargos-execucao-ccb
Tier 2 superendiv.: triagem-superendividamento, repactuacao-104a-104b, minimo-existencial-e-sancoes
Tier 3 pericia: gerador-quesitos-pericia-contabil, recomendador-perito-contabil
Tier 3 extrajudicial: matriz-protocolos-extrajudiciais, med-pix-acionamento, registrato-extracao-prova, orientacao-preventiva-falso-advogado
Tier 4 processual: replica-contestacao, recursos-civeis-router, devolucao-em-dobro, prescricao-bancaria, gratuidade-e-prioridade
Tier 5 meta: auditoria-juris-pre-envio, protocolo-p4-bancario, monitor-temas-em-definicao

## Auto-chains (bloqueantes)
- Toda peticao → ANTES: varredura-jurisprudencial-pre-tese + classificador-foro-jec-comum.
- Toda peca final → auditoria-juris-pre-envio → protocolo-p4-bancario.
- triagem-superendividamento → expurga fraude (financiamento-emprestimo-fraudulento) ANTES de repactuacao-104a-104b.
- fraude → auto-anexa fortuito-interno + rebater-culpa + tutela + (idoso) hipervulneravel + sugere matriz-protocolos.
- peticao-revisional → auto-anexa gerador-quesitos + recomendador-perito.

## Regras duras da familia
1. Skill folder = SO SKILL.md (≤ 11.000 bytes). Dados → scripts/data/.
2. plugin.json minimal (4 campos).
3. description + when_to_use ≤ 1024 chars.
4. Onboarding usa AskUserQuestion (botoes) nas escolhas fechadas.
5. hooks.json = SessionStart com echo, ZERO python (GATE DE HOOKS).
6. `python3 audit/audit.py` LIMPO + `python3 scripts/check-skill-descriptions.py` APROVADO antes de todo push.
7. `claude plugin validate` PASS antes do push do marketplace.
8. Toda skill que cita jurisprudencia: bloco de aviso anti-halucinacao + remete a auditoria-juris-pre-envio.
9. Bloco fixo de cross-link soft no fim do output do orquestrador (sugestao, nao execucao).

## Cross-link soft (NAO importar/executar)
calculosjudiciais-adv-os (calculo/auditoria de laudo) · juris-adv-os (jurisprudencia) · execucao-adv-os (execucao/monitoria) · ia-combativa-adv-os (Suprema Corte ampliada).

## Anti-despersonalizacao
`audit/forbidden-terms.json` bloqueia nome civil/OAB/email/escritorio + nomes reais de partes/advogadas das peticoes-modelo (seed dev-only). Skills usam placeholders genericos (autor, cliente, banco reu).

## Comunicacao
Idioma PT-BR. Docs internos tecnicos sem mencoes pessoais. Skills/comandos acolhedores e tecnicos, respeitando tom_voz configurado em runtime.

---
**Ultima atualizacao:** 2026-06-09 — scaffold + spec (FASE 1 do PLAYBOOK).
