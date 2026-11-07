---
name: security-and-learnings
description: Security audit findings and architectural principles for OMNICORE
sources: [backfill]
aliases: []
---
- [stated] Multi-password auth system (bcrypt hashing, rate limiting, role-based permissions) audited and confirmed secure
- [stated] Known gaps: API keys stored unencrypted in localStorage, fragile verifyPassword pattern, CSP weakened by unsafe-inline/unsafe-eval, client-side-only approval for write/critical actions
- [stated] Human-approval model for AI actions (risk levels: read / write / critical) is a strong architectural decision worth preserving
