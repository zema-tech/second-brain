# Second Brain — Guida operativa per le IA

> Questo file è la porta d'ingresso per qualsiasi IA che legge o aggiorna questo vault. Non è la memoria in sé: è una mappa per trovare, interpretare e mantenere correttamente i file originali.
>
> **Regola fondamentale:** prima consulta i documenti pertinenti; non dedurre dettagli dal solo nome di un file e non inventare informazioni mancanti.

## 1. Che cos'è questo repository

Questo repository è il Second Brain personale di Zema, organizzato come vault Markdown compatibile con Obsidian. Contiene contesto personale, progetti, persone, argomenti trasversali e snapshot di memoria importati da conversazioni precedenti.

- Repository: [zema-tech/second-brain](https://github.com/zema-tech/second-brain)
- Branch principale: `main`
- Indice Obsidian: [[Home]]
- Profilo: [[profile]]
- Snapshot storico/importato: [[00 - Claude Memory Snapshot]]

Il vault è una memoria condivisa consultabile da IA diverse. Ogni IA deve leggere i file dal repository e non presumere di possedere già tutto il contesto.

## 2. Ordine di lettura consigliato

Per iniziare una nuova sessione:

1. Leggi questo `README.md`: contiene le regole operative e la mappa.
2. Leggi [[Home]] per vedere l'indice Obsidian e i collegamenti principali.
3. Leggi [[profile]] per il contesto generale della persona e le preferenze operative.
4. Leggi [[00 - Claude Memory Snapshot]] solo come panoramica storica/importata, non come unica fonte di verità.
5. Cerca in `areas/`, `projects/`, `people/` e `topics/` i documenti pertinenti alla richiesta.
6. Prima di agire su un progetto, verifica lo stato reale nel repository, nel servizio o nell'app coinvolta quando gli strumenti lo consentono. Una nota di memoria non prova che un deploy, una modifica o un'integrazione siano ancora attivi.

Non è necessario leggere tutto il vault a ogni turno: consulta solo i documenti rilevanti, seguendo i collegamenti.

## 3. Mappa delle cartelle e dei file

### Radice

| Percorso | Ruolo |
|---|---|
| `README.md` | Questa guida per le IA: orientamento, priorità delle fonti e regole di manutenzione |
| [[Home]] | Mappa dei contenuti (MOC) e indice navigabile del vault |
| [[profile]] | Profilo generale, contesto e preferenze note |
| [[00 - Claude Memory Snapshot]] | Snapshot esteso importato da Claude; utile per recuperare contesto, ma potenzialmente datato |

### `areas/` — Aree e progetti continuativi

Ogni file rappresenta un'area/progetto. Apri il file specifico prima di rispondere o modificare qualcosa che lo riguarda.

- `agente-ia-personale-perchance.md` — agente IA personale e migrazione da Perchance
- `alleanza-scarletmc.md` — alleanza e community legata a ScarletMC
- `arsenale.md` — mod Minecraft Arsenale
- `claude-desktop-deb.md` — Claude Desktop su Debian
- `costituzione-pdf.md` — progetto relativo alla Costituzione PDF
- `discord-multi-server-bot.md` — bot Discord multi-server
- `dominio-game.md` — gioco/progetto Dominio
- `drews-empire-sanctum.md` — server/community Drew's Empire Sanctum
- `drews-empire.md` — ecosistema Drew's Empire
- `governo-mondiale.md` — progetto Governo mondiale
- `hermes-agent.md` — Hermes Agent
- `mine-control-center.md` — M.I.N.E. Control Center
- `minicpm-chat-space.md` — MiniCPM Chat Space
- `n8n-render.md` — n8n ospitato su Render
- `nebbo-zone.md` — community nebbo zone
- `new-horizons.md` — progetto New Horizons
- `omnicore-hub.md` — hub OMNICORE
- `omnicore-ia.md` — agente/progetto OMNICORE IA
- `pelican-mcp.md` — Pelican MCP
- `presentazione-overtourism.md` — presentazione sull'overtourism
- `red-bot.md` — RED Bot
- `redtie.md` — R.E.D.T.I.E.
- `website-mode-server.md` — Website Mode Server
- `zemabot.md` — ZemaBot

### `projects/` — Memoria approfondita di un progetto

Il vault contiene attualmente il progetto `projects/019f9ece-b7c9-702f-87b2-12b1af127c11/`:

- `index.md` — pagina indice/identità del progetto
- `overview.md` — architettura, stack, stato e obiettivi
- `project-memory.md` — memoria e contesto esteso del progetto
- `security-and-learnings.md` — sicurezza, rischi e lezioni apprese
- `ways-of-working.md` — modalità di collaborazione e workflow

**Nota di coerenza:** il nome/descrizione dell'indice contiene il riferimento "mine platform", mentre overview e memoria descrivono OMNICORE e i suoi agenti. Non appiattire questa differenza con supposizioni: confronta i file e chiedi conferma a Zema prima di rinominare o unificare concetti.

### `people/` — Persone

- `mr-drew0.md`
- `nebbo-riccio.md`

Usa questi file per il contesto relativo alle persone. Non trasferire dettagli da una persona all'altra e non dedurre relazioni non esplicitate.

### `topics/` — Conoscenze trasversali

- `gaming.md` — contesto gaming
- `recent-work.md` — attività e priorità recenti registrate
- `tooling.md` — strumenti, hosting e workflow

### `.obsidian/` — Configurazione di Obsidian

Contiene impostazioni dell'app e dei plugin/core features (`app.json`, `appearance.json`, `core-plugins.json`). Non modificarle durante una normale manutenzione della memoria; intervieni solo se la richiesta riguarda esplicitamente la configurazione Obsidian.

## 4. Come interpretare le informazioni

- I collegamenti Obsidian `[[nome-file]]` e `[[percorso/nome-file|etichetta]]` sono collegamenti interni: seguili quando servono.
- I frontmatter YAML (per esempio `name`, `description`, `aliases`, `sources`) sono metadati. Mantienili validi e coerenti quando modifichi un documento.
- Marcatori come `[stated]` indicano che un'informazione è stata riportata come dichiarazione. Non trasformarla in una verifica indipendente.
- `sources: [chat]` o `sources: [backfill]` indicano provenienza/contesto di raccolta, non necessariamente attualità.
- Distingui sempre: **fatto dichiarato**, **decisione**, **ipotesi**, **obiettivo**, **attività completata** e **stato verificato**.
- Le date e gli stati possono diventare obsoleti. Se manca una data, non inventarla.
- In caso di conflitto tra file, non scegliere arbitrariamente: segnala il conflitto, considera la data e la specificità delle fonti e chiedi conferma se la decisione cambia il significato.

## 5. Regole per aggiornare il Second Brain

Quando Zema comunica una nuova informazione o chiede di aggiornare la memoria:

1. Individua il file più specifico già esistente e leggilo per intero prima di modificarlo.
2. Aggiorna il documento esistente invece di creare duplicati o nuove pagine quasi identiche.
3. Crea un nuovo file solo se il concetto è davvero distinto e ha una collocazione chiara.
4. Mantieni stile, lingua, frontmatter, alias e collegamenti già usati nel documento.
5. Conserva le informazioni storiche utili: correggi o marca ciò che è superato, senza cancellare decisioni e lezioni importanti.
6. Se una nota è un obiettivo, non descriverlo come completato. Se è un piano, non descriverlo come stato attuale.
7. Aggiungi o aggiorna i collegamenti in [[Home]] quando nasce una nuova pagina di primo livello o un nuovo progetto importante.
8. Non riscrivere lo snapshot completo per una piccola modifica locale. Aggiornalo solo quando la richiesta riguarda esplicitamente la memoria riepilogativa.
9. Non salvare password, token, chiavi API, cookie, credenziali o altri segreti. Registra al massimo il nome di una variabile/secret e dove viene gestita, mai il suo valore.
10. Dopo una modifica, rileggi il file e verifica collegamenti, sintassi e coerenza.

## 6. Regole di comportamento per le IA

- **Leggi prima di rispondere:** cerca nel vault le informazioni pertinenti, senza chiedere a Zema di ripetere ciò che è già documentato.
- **Non fingere verifiche:** una nota dice cosa era stato riferito; solo una verifica aggiornata dimostra lo stato attuale.
- **Non inventare:** se un file manca, un collegamento è rotto o il dato è ambiguo, dichiaralo.
- **Preserva la voce e le decisioni di Zema:** non trasformare preferenze o decisioni esplicite senza autorizzazione.
- **Minimizza le modifiche:** cambia solo i file necessari alla richiesta.
- **Rendi tracciabile il lavoro:** quando modifichi il repository, riporta file toccati, motivo e commit/link.
- **Rispetta i permessi:** usa l'account GitHub con autorizzazione di scrittura; un account con sola lettura può verificare ma non deve essere usato per tentare scritture.
- **Non assumere che tutte le IA condividano la stessa memoria interna:** il repository è il riferimento condiviso, quindi rileggi i documenti necessari a ogni sessione.

## 7. Procedura rapida per una richiesta su un progetto

1. Cerca il nome del progetto in [[Home]] e in `areas/`.
2. Leggi la relativa nota e segui eventuali link verso `projects/`.
3. Controlla [[topics/recent-work]] e [[topics/tooling]] se la richiesta riguarda priorità o strumenti.
4. Se ci sono decisioni tecniche o rischi, consulta `security-and-learnings.md` e `ways-of-working.md` del progetto, quando presenti.
5. Verifica lo stato corrente con gli strumenti autorizzati.
6. Esegui solo l'azione richiesta e aggiorna la memoria solo se emerge un'informazione durevole o Zema lo chiede.
7. Nel resoconto finale separa ciò che hai letto, ciò che hai verificato e ciò che hai modificato.

---

**Principio guida:** questo README orienta le IA; i file collegati contengono la memoria. In caso di dubbio, torna alla fonte originale e chiedi a Zema invece di colmare i vuoti con supposizioni.
