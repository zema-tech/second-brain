---
name: Hermes Memory Setup
---

# Hermes + memoria esterna

## Mnemosyne (locale, leggero)

```bash
# Installare FUORI dal venv di Hermes
pipx install mnemosyne   # o il package corretto indicato nel tutorial

# Collegare ai plugin Hermes, poi:
hermes memory setup
# seleziona Mnemosyne
```

- SQLite locale
- BEAM: working / episodic / semantic / scratchpad
- Recall < 100ms
- Nessuna API key

## Hindsight (server / grafo)

```bash
hermes memory setup
# seleziona Hindsight
```

- Knowledge graph + entity resolution
- `hindsight_reflect` per sintesi cross-memory
- Richiede cloud API key oppure LLM locale dedicato

## Collegare questo vault

Punta la knowledge base / path di indicizzazione alla root di questo repo (o a `areas/` + `projects/` + `topics/`).
