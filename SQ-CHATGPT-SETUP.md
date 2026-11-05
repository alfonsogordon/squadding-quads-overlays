# Squadding Quads — ChatGPT setup and handover guide

## Paste the following into your own ChatGPT

I am the owner/operator of the YouTube channel https://www.youtube.com/@squaddingquads. A friend has developed a three-widget livestream overlay project for me at https://github.com/alfonsogordon/squadding-quads-overlays.

Please act as my step-by-step setup assistant. Inspect the actual repository and its README first. Do not assume integrations are working just because mock overlays render. Ask me to do only one task at a time and verify each stage before moving on.

The desired widgets are:
1. Total public YouTube subscriber count, periodically refreshed (YouTube public counts may be rounded).
2. Real YouTube live chat for my currently active livestream, including usernames and messages.
3. A compact vertical-scrolling supporter credits box combining current Patreon supporters and paid YouTube channel members who have consented to public recognition.

Design: transparent, frosted-glass minimal panels, rounded edges, white text with strong shadows, individually movable/resizable OBS Browser Sources. The FPV image is only for the test preview, never for the production overlay.

Hosting goal: public static overlays on GitHub Pages, optional Cloudflare Worker/backend for authenticated API integrations. Prefer free tiers and low-maintenance setup. Keep secrets server-side; never place OAuth tokens, Patreon credentials, API secrets or private member data in GitHub Pages, public GitHub commits or OBS URLs.

Guide me through:
A. Check the GitHub Pages deployment and identify the actual published overlay URLs. If Pages is not enabled, explain how to enable Settings > Pages > Deploy from branch > main/root, or the repository's actual deployment method.
B. Test each browser source in OBS (1920x1080 canvas or appropriate source dimensions); configure each independently and verify transparency.
C. Identify the correct YouTube channel ID and implement the subscriber-count data source using the official YouTube Data API, handling public rounded counts, quotas and refresh intervals.
D. Identify the currently active YouTube live broadcast and implement live chat polling or the appropriate official API with quota-aware handling, stream-offline behaviour, and safe message rendering.
E. Help me authorize Patreon access securely to fetch active supporters and only publish names allowed for public acknowledgement. Handle revocations and membership expiry.
F. Check whether my channel qualifies for the official YouTube Memberships API. If not, clearly explain limitations and offer a consent-based/manual or supported event-driven alternative rather than pretending full membership roster sync is possible.
G. If needed, deploy a Cloudflare Worker with secrets and any storage. Confirm free-tier suitability and avoid leaking supporter private data.
H. Switch from simulated to live data, test while streaming, and produce a final one-page OBS setup and troubleshooting checklist.

Do not ask me to paste credentials or tokens into ChatGPT. Prefer OAuth flows and service dashboards. Do not claim a step is complete until it is verified. Explain anything I must do in the YouTube, Patreon, GitHub, Cloudflare or OBS UI with precise clicks. Keep it concise and do one step at a time.
