---
name: Architecture
aliases: [memory stack, 3 livelli, agent memory]
---

# Architettura Memoria Agenti — Second Brain

> Ispirato al tutorial di Callum (Waterlitz) sulla memoria per agenti AI.
> Questo vault è il **Livello 3: Knowledge Layer**.

## I 3 livelli

### Livello 1 — Memoria Integrata (Built-in)
File leggeri iniettati ad ogni sessione:
- `agents/USER.md` → chi sei
- `agents/SOUL.md` → principi, preferenze, modo di lavorare
- `agents/MEMORY.md` → snapshot corrente (top of mind)

**Uso:** chat semplici, contesto minimo obbligatorio.
**Limite:** non scala; consuma token se diventa grosso.

### Livello 2 — Provider di Memoria Esterni
Sistemi esterni che l'agente **interroga** invece di ricevere tutto nel prompt:
- **Mnemosyne** → locale, SQLite, leggero, <100ms, privacy totale (anche Raspberry Pi)
- **Hindsight** → server, knowledge graph, `hindsight_reflect`, più potente

Configurazione tipica (Hermes): `hermes memory setup`
Principio: universale → funziona con qualsiasi agente (Claude, Grok, Cursor, Codex…).

### Livello 3 — Knowledge Layer (questo vault)
Conoscenza stabile e duratura, indipendente dalla singola sessione/agente.
Obsidian-style: note linkate, MOC, progetti, aree, persone, topic.

**Questo repo = Livello 3.**
Gli agenti leggono da qui. I provider di Livello 2 possono indicizzarlo.

## Come usarlo con un agente

1. **Sessione leggera** → inietta solo `agents/USER.md` + `agents/SOUL.md` + `agents/MEMORY.md`
2. **Progetto complesso** → collega un provider (Mnemosyne/Hindsight) + punta a questa cartella come knowledge base
3. **Recall** → l'agente cerca nelle note invece di ricevere tutto il contesto

## Cartelle chiave

| Cartella | Ruolo |
|----------|--------|
| `agents/` | Contesto built-in per qualsiasi agente |
| `memory/working/` | Focus attuale / top of mind |
| `memory/episodic/` | Storia di sessioni e decisioni |
| `memory/semantic/` | Conoscenza distillata |
| `memory/scratchpad/` | Appunti temporanei |
| `areas/` | Responsabilità continuative |
| `projects/` | Lavori con obiettivo |
| `people/` | Persone |
| `topics/` | Argomenti trasversali |
| `prompts/` | Prompt e istruzioni per agenti |

## Principio guida

> Un agente **stateful** non risponde solo al messaggio corrente:
> porta avanti la relazione e il lavoro, ricordando preferenze, progetti e decisioni.
