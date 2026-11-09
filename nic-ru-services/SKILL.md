---
name: nic-ru-services
description: Navigate and operate NIC.RU (Руцентр, RU-CENTER) services for domains, DNS, corporate email, SSL, shared hosting and VPS/VDS. Use for service identification, account navigation, troubleshooting and authorized changes on NIC.RU.
---

# NIC.RU services

1. Identify the task, service type and exact target. For account work verify the active contract, domain or service ID in the current panel. For servers match the exact public IP or service ID. A catalog listing only proves a product is offered. Domain registration, authoritative DNS, web hosting and mail can belong to different providers or contracts.
2. Start with the [NIC.RU account](https://www.nic.ru/my-account) or [official help](https://www.nic.ru/help/). Prefer a verified existing browser session for interactive work. If no session works, report the specific obstacle and use public checks where relevant. Never bypass TLS warnings, CAPTCHA or account protections. Keep credentials, AuthInfo codes, keys, cookies and session URLs out of logs, shell arguments and deliverables.
3. Read the relevant reference:
   - [Account, domains and DNS](references/account-domains-dns.md) for sign-in, contract selection, delegation, records, renewal and transfers.
   - [Mail, SSL and hosting](references/mail-ssl-hosting.md) for mailbox and mail routing, certificate checks, shared hosting, VPS and SSH diagnostics.
4. For an authorized change, capture relevant current values, confirm target and scope, apply only the intended change, then read it back. Verify the external result where possible. For a DNS change, query authoritative servers. For HTTPS, check the presented chain and hostname. For SSH, distinguish TCP, protocol greeting, host identity, authentication and the logged-in user's identity.
5. Separate what you saw in the catalog, what the account shows, and what worked externally. Treat paid orders, transfer, cancellation, account recovery, DNS changes and access grants as distinct actions. Apply the user's authorization and the tool's rules at the action boundary.

Use a documented API only after verifying that the documentation covers the specific product, account type, credential scope and operation. A browser endpoint observed in the panel is insufficient evidence of a supported integration. No API client or account connection is bundled.
