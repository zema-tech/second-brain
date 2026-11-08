---
name: Hermes Memory Setup
aliases: [mnemosyne install, setup mnemosyne]
---

# Installazione e configurazione Mnemosyne

> Package ufficiale: `mnemosyne-memory` (PyPI)  
> Docs: https://docs.mnemosyne.site/  
> Repo: https://github.com/mnemosyne-oss/mnemosyne

Mnemosyne = **Livello 2** (provider di memoria locale, SQLite, BEAM).  
Questo vault = **Livello 3** (Knowledge Layer).

---

## A) Uso standalone (Python / qualsiasi agente)

```bash
# Consigliato: venv dedicato
python3 -m venv ~/.mnemosyne-env
source ~/.mnemosyne-env/bin/activate   # Windows: .\\Scripts\\activate

pip install "mnemosyne-memory[all]"    # vector + MCP + extra
# oppure leggero:
# pip install mnemosyne-memory
```

Test rapido:

```bash
mnemosyne version
mnemosyne store "Zema preferisce tooling browser-based e free/self-host" conversation 0.9
mnemosyne recall "preferenze tooling"
mnemosyne stats
```

API Python:

```python
from mnemosyne import remember, recall
remember("Focus attuale: OMNICORE multi-agent", importance=0.9, scope="global")
print(recall("OMNICORE"))
```

DB di default: `~/.hermes/mnemosyne/data/mnemosyne.db`  
(backup: `mnemosyne backup`)

---

## B) MCP server (Cursor, Claude Code, Codex, Windsurf, Grok tools…)

```bash
# Dopo install
mnemosyne mcp --transport stdio
```

Esempio config MCP (Cursor / Claude Code / simili):

```json
{
  "mcpServers": {
    "mnemosyne": {
      "command": "mnemosyne",
      "args": ["mcp"]
    }
  }
}
```

Se usi un path assoluto al venv:

```json
{
  "mcpServers": {
    "mnemosyne": {
      "command": "/home/TUO_USER/.mnemosyne-env/bin/mnemosyne",
      "args": ["mcp"]
    }
  }
}
```

---

## C) Hermes Agent (path ufficiale)

### Opzione 1 — Plugin nativo

```bash
# Nella stessa Python di Hermes (o venv accessibile da Hermes)
pip install mnemosyne-hermes
# oppure
pip install "mnemosyne-memory[all]"

mnemosyne-hermes install          # symlink plugin (se disponibile)
# oppure configura a mano:

hermes config set memory.provider mnemosyne
# oppure edita ~/.hermes/config.yaml:
```

```yaml
memory:
  memory_enabled: true
  user_profile_enabled: true
  provider: mnemosyne
  mnemosyne:
    profile_isolation: false
    auto_sleep: true
```

Poi:

```bash
hermes memory setup          # se il comando esiste nella tua versione
hermes doctor | grep -i memory
hermes tools list | grep -i mnemosyne
```

Test tool:

```bash
hermes --tool mnemosyne_remember content="Test memoria setup" veracity="stated"
hermes --tool mnemosyne_recall query="Test memoria"
```

### Opzione 2 — Solo MCP dentro Hermes

In `~/.hermes/config.yaml`:

```yaml
mcp:
  servers:
    mnemosyne:
      command: mnemosyne
      args: ["mcp"]
```

---

## Nota importante (dal video / docs)

- **Non** installare solo dentro il venv gestito da Hermes se Hermes lo ricostruisce a ogni update → usa `pipx` oppure un venv separato (`~/.mnemosyne-env`) e collega il path.
- Match della versione Python con Hermes se usi il plugin (stesso major.minor).
- Su Debian/Ubuntu (PEP 668): usa venv, non `pip install` di sistema.

---

## Collegare questo Second Brain (Livello 3)

1. Gli agenti leggono `agents/USER.md`, `agents/SOUL.md`, `agents/MEMORY.md` (Livello 1 leggero).
2. Mnemosyne gestisce working/episodic (Livello 2) con `remember` / `recall` / `sleep`.
3. Per conoscenza stabile (progetti, aree, decisioni) → note in questo vault (`areas/`, `projects/`, `topics/`).

Workflow consigliato:
- Fatti operativi / preferenze → `mnemosyne store ...`
- Decisioni di progetto / architettura → nota Markdown nel vault + eventuale `remember` di un riassunto corto

---

## Comandi utili

| Comando | Cosa fa |
|---------|--------|
| `mnemosyne stats` | Conteggio working / episodic |
| `mnemosyne sleep` | Consolidamento working → episodic |
| `mnemosyne export file.json` | Backup portable |
| `mnemosyne import file.json` | Restore |
| `mnemosyne doctor` | Diagnostica |
| `mnemosyne backup` | Backup DB |
| `mnemosyne mcp` | Avvia server MCP |

---

## Seed iniziale (opzionale)

Dopo install, puoi caricare i focus dal vault:

```bash
mnemosyne store "Utente: Alessio Zemignani (Zema). GitHub org zema-tech. Lavora da tablet Android. Preferisce free/self-host e browser-based." conversation 0.95
mnemosyne store "Focus: OMNICORE multi-agent (J.A.R.V.I.S. + specialist), M.I.N.E. Control Center, Agente IA personale standalone, Second Brain vault." conversation 0.9
mnemosyne store "Workflow: Grok genera/fixa codice → Claude verifica su GitHub/Vercel. Non usare Lovable." conversation 0.85
mnemosyne store "Community: Drew's Empire (Mr_Drew0), nebbo zone (nebbo_riccio). Discord ID Zema: 1463921144838094861." conversation 0.8
mnemosyne stats
mnemosyne recall "focus progetti"
```
