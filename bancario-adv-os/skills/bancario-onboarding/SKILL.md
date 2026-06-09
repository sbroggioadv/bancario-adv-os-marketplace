---
name: bancario-onboarding
description: >
  BANCARIO-ONBOARDING — Comando `/start-bancario`. Configura a persona
  do advogado operador: nome, OAB e UF (texto livre), comarca/TJ que
  atua (texto livre), tom de voz (BOTOES) e POSTURA das teses de fraude
  (BOTOES: "Honesta — avisa risco" [padrao] / "Enxuta"). Persiste em
  `<cwd>/bancario/persona.md`, fora de qualquer sync de nuvem (LGPD).
  Use SEMPRE na primeira sessao do plugin OU quando o usuario disser
  "configurar", "primeira vez", "trocar tom de voz", "mudar postura das
  teses", "adicionar comarca", "atualizar OAB", "/start-bancario".
---

> **🖱️ Escolhas = botoes:** em campos de **lista fechada** (tom de
> voz, postura das teses, atualizar/recriar, sim/nao) use a ferramenta
> **AskUserQuestion** para mostrar **botoes clicaveis** (max. 4 por
> pergunta; se houver mais, divida em 2). **Texto livre** (nome, OAB,
> UF, comarca/TJ, escritorio) segue como pergunta digitada normal.

# BANCARIO-ONBOARDING — Configuracao da Persona

## 1. ESCOPO

Cria/atualiza `<cwd>/bancario/persona.md` com a identidade do advogado
operador. Toda skill Tier 2 consulta esse arquivo via tokens runtime
`{{ADVOGADO_NOME}}`, `{{ADVOGADO_OAB}}`, `{{COMARCA}}`, `{{TJ}}`, etc.

**Pre-requisito das skills que redigem peca.** Sem persona, o
orquestrador roda esta skill primeiro.

## 2. QUANDO RODAR

- Primeira sessao (persona.md nao existe)
- Comando explicito `/start-bancario`
- Usuario disse "configurar plugin", "trocar OAB", "adicionar comarca",
  "mudar tom", "mudar postura das teses"

## 3. FLUXO DE ONBOARDING

### Passo 1 — Aviso LGPD (CRITICO)

```
⚠️ ANTES DE COMECAR: AVISO DE PRIVACIDADE (LGPD)

A pasta `bancario/` guardara sua configuracao + possivelmente notas de
casos reais. NAO crie esta pasta dentro de:
- iCloud Drive (~/Library/Mobile Documents/...)
- Google Drive / Dropbox / OneDrive
- Pastas pessoais do sistema (Documents, Desktop, Downloads)

Recomendado: pasta local fora de sync. Ex: ~/Workspace/ .
Sua sessao esta em: <cwd atual>
```

Se o cwd contem `iCloud`, `Google Drive`, `Dropbox`, `OneDrive`,
`Mobile Documents`, `CloudDocs` → **PARAR** e pedir mudanca de cwd.

### Passo 2 — Coletar dados (UMA pergunta por vez)

**TEXTO LIVRE (perguntar digitado):**
1. Nome completo profissional (como aparece nas pecas)?
   Ex: "Dra. Maria Silva" / "Joao Santos"
2. Numero de inscricao OAB (formato UF Numero, ex: SP 123.456)?
3. UF de inscricao principal? (Ex: SP, RJ, MG, RS, BA)
4. Comarca-base e Tribunal em que mais atua? (Ex: "Sao Paulo/SP —
   TJSP"; pode listar mais de um separado por virgula)
5. Nome do escritorio (opcional)?

**BOTOES (AskUserQuestion):**
6. **Tom de voz** dos outputs (escolha 1):
   - "tecnico-direto" — sem floreio, vai ao ponto (default)
   - "didatico" — explica conceitos, util pra cliente/estagiario
   - "formal" — linguagem juridica tradicional, vocativo "Excelencia"
   - "consultivo" — conversacional, util pra parecer
7. **Postura das teses de fraude** (escolha 1):
   - "Honesta — avisa risco" (DEFAULT) — monta a tese pro-cliente
     (3a Turma STJ) E sinaliza o risco da 4a Turma (entrega de senha/
     token = culpa exclusiva) + como blindar a peca. Secao fixa
     "⚠️ Risco da tese".
   - "Enxuta" — monta so a tese pro-cliente, sem o bloco de risco
     (advogado assume o controle do alerta).

### Passo 3 — Confirmacao

```
## Resumo da configuracao
| Campo | Valor |
|---|---|
| Nome | {{ADVOGADO_NOME}} |
| OAB | {{ADVOGADO_OAB}} |
| UF | {{ADVOGADO_UF}} |
| Comarca / TJ | {{COMARCA}} / {{TJ}} |
| Escritorio | {{FIRM_NAME}} |
| Tom de voz | {{TOM_VOZ_PERFIL}} |
| Postura das teses | {{POSTURA_TESES}} |

Posso salvar em `<cwd>/bancario/persona.md`? (s/n — botoes)
```

### Passo 4 — Persistir

Criar `<cwd>/bancario/persona.md`:

```markdown
# Persona — bancario-adv-os

> Configuracao do operador. NAO commitar em repo publico. NAO incluir
> dados de processo de cliente aqui.

## Identidade
- **Nome:** [nome]
- **OAB:** [UF + numero]
- **UF de inscricao:** [UF]
- **Escritorio:** [nome ou "advocacia individual"]

## Atuacao
- **Comarca-base:** [comarca]
- **Tribunal(is):** [TJSP / TJRJ / ...]

## Preferencias
- **Tom de voz:** [tecnico-direto | didatico | formal | consultivo]
- **Postura das teses de fraude:** [honesta | enxuta]

## Auditoria interna
- **Data de configuracao:** [YYYY-MM-DD]
- **Ultima atualizacao:** [YYYY-MM-DD]
- **Versao plugin:** v0.1.0

## Notas
[espaco livre — ex: "foco em revisional veiculo", "atua em JEC e
Justica Comum capital", etc.]
```

### Passo 5 — Confirmacao final

```
✅ Persona configurada em `<cwd>/bancario/persona.md`

Proximos passos sugeridos:
- Use `/bancario` para o orquestrador rotear seu caso
- Diga o que aconteceu ("fui vitima de golpe pix", "quero revisar meu
  financiamento", "estou superendividado") e eu monto a estrategia.

Lembrete: adicione `bancario/` ao `.gitignore` do seu projeto.
```

## 4. ATUALIZACAO DE PERSONA EXISTENTE

Se `<cwd>/bancario/persona.md` ja existe, perguntar via **botoes**
(AskUserQuestion) o que atualizar:
1. Comarca / Tribunal
2. Tom de voz
3. Postura das teses de fraude
4. OAB / nome / escritorio
5. Resetar tudo (re-onboarding)
6. Cancelar

Aplicar mudanca pontual e atualizar `Ultima atualizacao:`.

## 5. OUTPUT (resumo final)

```yaml
persona:
  configurada: true
  arquivo: "<cwd>/bancario/persona.md"
  nome: "<nome>"
  oab: "<UF Numero>"
  comarca: "<comarca>"
  tj: "<tribunal>"
  tom_voz: "<perfil>"
  postura_teses: "<honesta|enxuta>"
  status: pronto_para_uso
```

## 6. AVISOS OBRIGATORIOS

- **LGPD por design:** alerta de pasta sync no Passo 1 e bloqueador.
- **Persona.md NAO vai pra repo publico** — lembrete de `.gitignore`.
- **Nenhum dado coletado sai do disco local** — sem telemetria.
- **Postura "honesta" e o default** — protege o advogado contra tese
  apresentada como pacificada quando nao e.

## 7. PROIBICOES

1. Nao salvar persona em pasta sync (iCloud/GDrive/Dropbox/OneDrive).
2. Nao coletar dados de cliente (CPF, processo, endereco) — persona e
   da OPERACAO do advogado, nao do caso.
3. Nao enviar dados para API externa — tudo em disco local.
4. Nao perguntar tudo de uma vez — UMA pergunta por vez (UX).
5. Nao usar texto livre onde a escolha e fechada — usar BOTOES.

## 💡 Proximos passos opcionais

| Proximo passo | Comando | Plugin necessario |
|---|---|---|
| Configurar persona de calculo judicial | `/start-calculos` | calculosjudiciais-adv-os |
| Configurar persona de execucao | `/start-execucao` | execucao-adv-os |
| Configurar persona do plugin-mae | `/start` | ia-combativa-adv-os |

> Cada plugin Adv-OS tem onboarding proprio — mesmo padrao de aviso
> LGPD + persona local em `<cwd>/<plugin>/`.
