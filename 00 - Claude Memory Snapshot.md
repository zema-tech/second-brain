---
name: Claude Memory Snapshot
aliases: [claude memory, full memory]
---

**Work context**

Zema is a developer, administrator, and community manager working across multiple Discord and Minecraft projects under the `zema-tech` GitHub organization. He works primarily from an Android tablet (Samsung Galaxy S10 FE), which shapes all tooling and hosting decisions toward browser-based, cloud-native solutions. His core workflow involves using Claude to architect and prompt, then delegating code generation to tools like Grok, Lovable, bolt.new, and Emergent, with Claude reviewing commits for accuracy.

**Personal context**

Zema is an Italian speaker associated with the community of Italian Minecraft content creator Mr_Drew0, whose brand is Drew's Empire (fans called Drewers). He has a strong interest in Minecraft gameplay and server culture, including active play on Italian servers like ScarletMC, and enjoys worldbuilding, lore creation, and community governance design.

**Top of mind**

Zema recently connected a Withone MCP integration and successfully tested sending Discord messages through it, with the `zema-tech` GitHub org as relevant context for future integrations. He is actively rebuilding a Perchance-based AI character chat project as a standalone agentic app outside Perchance, with provider flexibility (Claude/OpenAI switching) and real tool-calling support — the previous `Synapse-Omega.js` component is being eliminated entirely. He is also configuring and expanding the M.I.N.E. control panel (repo: `zema-tech/m.i.n.e.-control-center`) on Lovable with Falix API integration, a Matrix-style UI, and ambitions to expand it into a universal multi-host management panel with a multi-agent AI system. A Minecraft server called Drews_Empire_Sanctum (`aurelion.falixsrv.me:26470`) is running on Falix with crossplay via Geyser/Floodgate for a small community of Drew's Empire staff and subscribers.

**Brief history**

*Recent months*

Zema has been heavily focused on the **nebbo zone** Discord server (for Italian YouTuber nebbo_riccio), configuring a full bot stack (Discohook/Discohook Utils, Sapphire, Dyno, SafeNET, AuthGG, Xenon) and producing extensive content including welcome messages, rule embeds styled as "I 10 Comandamenti," staff hierarchy with a red/white color gradient using Mathematical Bold Unicode, notification role buttons, and Dyno forms. A key lesson: Discohook components must be added via Discohook Utils after sending — including them in the raw JSON editor causes an "Excessive key components" error.

**ZemaBot** (multi-server Discord bot, repo under `zema-tech`) has been designed with Supabase storage, Groq-powered AI features (Architetto IA, chat assistant, automod, ticket triage), and a modular cog architecture. Hosting settled on **Bot-Hosting.net** (one free bot, no card) and **Wispbyte** for stable 24/7 Python hosting. R.E.D.T.I.E. (the primary Drew's Empire bot) is the more production-grade bot with confirmed-working cogs: `ticket_creation`, `ai_triage`, and others.

(See full original memory in source export for complete detail on OMNICORE, Hermes, multi-agent architecture, security learnings, and current priorities.)
