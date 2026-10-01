# AdGuard Allow-List

This repository contains my personal **allowlist** for [AdGuard Home](https://adguard.com/en/adguard-home/overview.html).  
The goal is to keep **ad/tracker blocking strong** while ensuring essential work and productivity apps continue functioning.

---

### Contents
- [Purpose](#purpose)
- [Current Applications Covered](#current-applications-covered)
- [Repository Contents](#repository-contents)
- [How to Use](#how-to-use)
- [Notes](#notes)
- [Changelog](#changelog)

---

## Purpose
AdGuard Home is very aggressive with blocking telemetry and tracking services.  
While this is great for privacy, some SaaS apps (Slack, Teams, Salesforce, Outlook, etc.) can break if critical domains are blocked.

This repo provides a **curated list of allowed domains** so these apps work normally without compromising the ad-blocking experience.  

[Back to top](#adguard-allow-list)

---

## Current Applications Covered
- **Microsoft 365** → Teams, Outlook, OneNote, SharePoint, Authentication  
- **Salesforce** → CRM core, platform, live agent  
- **Slack** → app, APIs, CDN, messaging  
- **Google Core** → Chrome sync, authentication, APIs  
- (Optional) Zoom/Webex → commented out for now, can be enabled if needed  

[Back to top](#adguard-allow-list)

---

## Repository Contents
- `allowlist.txt` → main list of domains to be whitelisted in AdGuard  
- `blocklist.txt` → small custom blocklist (e.g. dead device clouds that devices hammer)  
- (optional) `README.md` → this documentation  
- (optional) `changelog.md` → track when/why new domains are added  

[Back to top](#adguard-allow-list)

---

## How to Use
1. Copy the **raw URL** to `allowlist.txt`.  
2. In AdGuard Home → **Filters → Allowlists** → **Add allowlist**.  
3. Enter a name (e.g., “Work Tools”) and paste the raw GitHub URL.  
4. **Save** and click **Check for updates** (or restart AdGuard Home).  
5. Add the raw URL to `blocklist.txt` under **Filters → DNS blocklists** (not Allowlists — every rule in an allowlist subscription is treated as an allow rule, including `||domain^` block rules).  

[Back to top](#adguard-allow-list)

---

## Notes
- This allowlist is intentionally minimal — only domains required for core functionality are included.  
- If an app breaks, check AdGuard’s **Query Log** → add the blocked domain → commit back to this repo.  
- **Comments go on their own line.** AdGuard only treats `!` / `#` as a comment at the start of a line; a rule with trailing text like `@@||example.com^$important ! note` is silently discarded.  
- PRs or suggestions welcome if you see improvements.  

[Back to top](#adguard-allow-list)

---

## Changelog
- **2025-10-14** → Initial commit (Microsoft 365, Salesforce, Slack, Chrome/Google core services).  
- **2026-10-01** → Moved trailing comments onto their own lines — only 38 of 338 rules were actually in effect, the rest were discarded by AdGuard. Removed duplicate rules, fixed `||.ui.com` and `||https://graph.facebook.com`, allowed `vpn.azure.com` (corp VPN), added `blocklist.txt` with the defunct Sengled cloud.  

[Back to top](#adguard-allow-list)

---

Goal: Maintain **privacy + usability** balance — keep trackers out while ensuring workflows stay smooth.  
