# Squadding Quads — Independent Ownership & ChatGPT Setup Guide

## Copy this prompt into your own ChatGPT

I own the YouTube channel https://www.youtube.com/@squaddingquads. My friend built a prototype livestream overlay project in https://github.com/alfonsogordon/squadding-quads-overlays. **I want to own and operate a fully independent copy under MY GitHub and Cloudflare accounts**, so that the system continues working if my friend stops hosting or maintaining anything.

Act as my patient, step-by-step setup assistant. Read the source repository and this guide before proposing steps. Ask me to do ONE step at a time, explain the exact UI clicks, and verify the result before moving on. Never assume a feature is live just because the demo displays simulated data.

### What I want
- Three independently resizable transparent frosted-glass OBS browser overlays: public YouTube subscriber count, live YouTube chat, and vertically scrolling Patreon + YouTube paid-member acknowledgements.
- Preserve the existing glass design, readable text shadows and transparent production background. The FPV screenshot is for preview only.
- Prefer free tiers and straightforward maintenance. No dependence on my friend's GitHub account, Cloudflare account, API keys, domains, credentials or infrastructure once migration is complete.

### Stage 1 — Take ownership of the source
1. Help me sign in to or create **my own GitHub account**.
2. Inspect the friend's repository for source files, configuration, licensing and any dependencies. Determine whether I can fork it; otherwise guide me through downloading the ZIP and creating a **new repository owned by me**. Do not assume a public repo grants a software licence; ask the original author to grant reuse/redistribution permission if necessary.
3. Verify all necessary source files are copied, including the preview and documentation. Remove demo-only data from production where appropriate. Search for any hard-coded URLs, usernames, API endpoints, tokens or references to my friend's hosting and replace them with my own settings.
4. Ensure my repository has its own main branch, README, licence/permission where appropriate, and a simple way to update the site. The original repository should be a reference only, not a runtime dependency.

### Stage 2 — My own GitHub Pages hosting
5. In MY repository, open Settings > Pages. Configure Build and deployment using the method appropriate for this repository (for a simple static site: Deploy from a branch > main > /(root) > Save).
6. Wait for the deployment and open MY actual published Pages URL. Do not invent the URL. Check preview/index and each of subscribers.html, chat.html and supporters.html (or their actual filenames).
7. Check all asset links are relative and there are no runtime requests to my friend's GitHub Pages URL.
8. Explain how I can update files myself, roll back a change, and check GitHub Pages deployment status.

### Stage 3 — My own Cloudflare account and backend
9. Help me create or sign in to **my own Cloudflare account** and select the free plan where suitable. I do not need to transfer any domain or buy one merely to use a workers.dev address.
10. Inspect the source code to determine which backend is actually implemented. If none exists, explain that clearly and help build/deploy a Cloudflare Worker in MY account. Configure a workers.dev URL and verify it responds.
11. Set up only the required storage (such as Workers KV or D1) in MY Cloudflare account, respecting current free-tier limits and quotas.
12. Configure MY Worker secrets, API keys and OAuth credentials through Cloudflare's secure secret management, **not in GitHub Pages, public code, OBS URLs, or this chat**.
13. Update MY GitHub Pages overlay configuration to point to MY Worker endpoint. Configure CORS and caching narrowly and safely; never expose private supporter records or tokens from public endpoints.
14. Confirm that the deployed system has no dependency on my friend's Cloudflare Worker, storage, scheduled jobs, or account. Give me a simple way to monitor errors and usage.

### Stage 4 — Connect my own accounts
15. YouTube subscribers: help me set up my own Google Cloud project, enable the YouTube Data API, create and restrict an API key as appropriate, and connect the public subscriber count. Explain that public counts are rounded and refresh within quota limits.
16. Live chat: connect to my active YouTube livestream using the appropriate official API and credentials, test with a real live broadcast, render messages safely, and handle offline periods and quota limits.
17. Patreon: guide me through authorizing MY Patreon creator account using a secure OAuth flow, fetching eligible active supporters, honouring public-name preferences/consent, and handling cancellations and revoked access.
18. YouTube paid members: verify whether my channel has access to the official YouTube Memberships API and what it can return. If unavailable, propose an explicitly limited consent-based or event-driven alternative; do not promise automatic full-roster synchronization without proof.
19. Never ask me to paste passwords, OAuth tokens, client secrets or private supporter lists into ChatGPT. Use the provider's official authorization and secret-management screens.

### Stage 5 — OBS and independence checks
20. In OBS, create three Browser Sources using MY published URLs. Show me how to set dimensions, crop/resize each source, and test transparent backgrounds and text readability.
21. Test live refresh, live chat, supporter scrolling, offline states, and recovery after OBS/browser restart. Clearly distinguish working live integrations from placeholders.
22. Verify independence by checking that no production asset, API request, secret, scheduler, or domain relies on my friend's accounts. Do not delete or disable his setup; just ensure mine works independently.
23. Provide a one-page owner handover with MY actual GitHub repository, Pages URLs, Cloudflare Worker URL, account ownership checklist, renewal/authorization instructions, troubleshooting, and recovery/export steps.

### Important rules
- Work one step at a time; wait for my confirmation before advancing.
- Do not claim anything has been deployed or connected until verified.
- Use official documentation and check current pricing/quotas; avoid unexpected paid subscriptions.
- Treat the original repository as a **prototype**, not proof that the API integrations are finished.
- Preserve the appearance of the overlays while making their infrastructure independent.
