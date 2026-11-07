---
name: omnicore-ia
description: Repo zema-tech/Omnicore-ia- — agente IA nato dalla fusione di Hermes Agent, OpenCode e OpenClaw; obiettivo e stato del lavoro
sources: [chat]
aliases: [Omnicore-ia, Omnicore-ia-, zema-tech/Omnicore-ia-]
---

- [stated] Repo github.com/zema-tech/Omnicore-ia-: vuole che Omnicore diventi un agente IA nato dalla fusione di Hermes Agent, OpenCode e OpenClaw, che unisce il meglio dei tre e li rende più forti
- [stated] Ragionamento: fondendo i migliori agenti, il suo sarà il migliore
- [stated] OpenCode stava modificando il repo ma non ha pushato; intende dirgli di pushare verso le 15:30
- [stated] Sta facendo brainstorming sull'idea con Claude
- [stated] Primo passo: collegare a Omnicore CLM (github.com/Contrastive-LM/CLM) e Mirage (github.com/strukto-ai/mirage), dopo aver aggiunto alcune altre cose
- [stated] Idea: più versioni nello stesso repo, una light, una medium e una "alt"
- [stated] Memoria: pensa a un "cervello" tipo Obsidian
- [stated] Poi vuole collegarlo ad altre cose, tipo un browser personale dell'IA
- [stated] Decisione: consigliare le chiavi API di IA, ma offrire entrambe le soluzioni (API e LLM locale)
- [stated] Dato che CLM usa la GPU, vorrebbe creare qualcosa di simile che faccia risparmiare token all'IA e la faccia ragionare meglio
- [stated] Vuole prendere la logica di Jev (IA di TypeSafe) e di CLM e fonderle per risparmiare token e far ragionare meglio l'IA
- [stated] Tappa 0 completata da OpenCode (lavoro già su main). Approvata la decisione di OpenCode: core in TypeScript, `omnicore_py/mind/` e `omnicore_py/pipeline.py` marcati DEPRECATO, `server.py` resta come guscio HTTP che delega il turno al loop TS; via libera alla Tappa 1
- [stated] Vuole ospitare Omnicore su Hugging Face (Space Docker, porta 7860, OMNICORE_API_TOKEN e chiavi LLM come Secrets)
- [stated] Non ha il piano Pro di Hugging Face, quindi lo Space Docker non è praticabile: vuole dividere il repo in più servizi gratuiti (Render, Supabase, parte su Hugging Face Space) e ospitare un LLM su servizi free (Google Colab, Kaggle o un altro Space)
- [stated] Il token dato a Grok era di Hugging Face, non di GitHub
- [stated] Su plugged.host (egg Node.js generico, indirizzo fr1.plugged.host:30035) è riuscita a far partire Omnicore (`npm run serve` → `python3 server.py`) con un `index.js` nella radice che entra in `Omnicore-ia--main`, fa `npm install` e avvia il server; il clone Git dell'egg non funzionava, quindi ha caricato il repo come ZIP
- [stated] Vuole che OpenCode crei comandi CLI per Omnicore tipo `omnicore doctor` e `omnicore web` (come in Hermes Agent e OpenCode) e implementi altre funzioni fino a Tappa 60
