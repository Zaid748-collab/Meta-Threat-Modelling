### Kill Chain Attack Description: Instagram Login & API Access

Note: Once you’ve read this, see Scenario 1 for HLDs, MITRE ATT&CK mappings, controls, and mitigations tailored to this Instagram API model.

## Introduction

This threat model shows how an attacker could move from initial motivation to accessing Instagram accounts and API data. It’s designed to be clear for developers and security reviewers: short stages, simple actions, and straightforward objectives.

## Stages of the Attack
# Origins

A motivated adversary (e.g., cybercriminals, fraudsters, or a targeted stalker) wants access to Instagram accounts or API data for fraud, data theft, impersonation, or mass scraping.

# Reconnaissance

The attacker gathers info: public-facing API endpoints, application OAuth flows, developer keys, employee emails, and third‑party integrations.

# Weaponization

Create phishing pages, malicious mobile apps, or scripts to automate credential stuffing and token replay. Prepare tools to harvest tokens (e.g., via XSS or malicious browser extensions).

# Delivery

Send phishing emails, SMS, or social messages; publish malicious apps; push poisoned links in comments or DMs; exploit exposed API endpoints or misconfigured OAuth redirect URIs.

# Exploitation

Use stolen credentials (credential stuffing / valid logins), exploit OAuth misconfigurations, run XSS to steal tokens, or abuse insecure token storage to gain access tokens or refresh tokens.

# Installation / Persistence

Register malicious OAuth apps, mint long‑lived refresh tokens, install backdoors in compromised developer accounts, or push malicious extensions to retain access.

# Command & Control

Attacker uses valid tokens or compromised API keys to make API calls, pivot to other accounts, coordinate exfiltration, or control compromised apps.

# Actions on Objectives

Account takeover: Post, DM, or change account settings.

Data exfiltration: Pull private messages, follower lists, photos, contacts.

Impersonation / Fraud: Send phishing DMs from compromised accounts.

Mass scraping / abuse: Use API access to collect user data at scale.

Disruption: Revoke tokens, delete content, or lock owners out.

```mermaid

flowchart TD
  A[Attacker Origins
   - Cybercriminals
  - Fraudsters
  - Targeted stalkers] --> B[Reconnaissance
  - Enumerate APIs & OAuth
  - Harvest emails & dev info]

  B --> C[Weaponization
  - Build phishing pages
  - Create malicious apps
  - Prepare credential stuffing tools]

  C --> D[Delivery
  - Send phishing links or SMS
  - Publish malicious app
  - Exploit misconfigured OAuth]

  D --> E[Exploitation
  - Credential stuffing or valid logins
  - XSS or token theft
  - Abuse insecure token storage]

  E --> F[Persistence / Installation
  - Register malicious OAuth app
  - Obtain refresh tokens
  - Create hidden dev accounts]

  F --> G[Command & Control
  - Use access tokens to call APIs
  - Maintain covert API sessions]

  G --> H[Actions on Objectives
  - Account takeover
  - Data exfiltration
