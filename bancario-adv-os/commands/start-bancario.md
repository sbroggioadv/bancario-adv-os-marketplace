---
description: Onboarding do plugin bancario-adv-os. Configura o advogado usuario (nome, OAB, comarca/TJ em que atua, tom de voz) e a postura das teses de fraude. Use na primeira vez que usar o plugin, ou quando quiser reconfigurar. Aciona a skill bancario-onboarding com botoes clicaveis (AskUserQuestion) nas escolhas de lista fechada.
---

# /start-bancario

Configuracao inicial do plugin **bancario-adv-os**.

Aciona a skill **`bancario-onboarding`**, que vai perguntar (com botoes nas escolhas fechadas):

- Nome e OAB do advogado (texto)
- Comarca / Tribunal de Justica em que atua (texto)
- Tom de voz das pecas (botoes)
- Postura nas teses de fraude diante do racha 3a x 4a Turma do STJ (botoes): honesta (avisa o risco) — padrao.

A configuracao fica salva localmente na persona do usuario (fora do plugin distribuido).
