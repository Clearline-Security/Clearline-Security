# SCOPE Tooling Guide

## Recommended Tool Stack by Adversary Tier

**Developed by Clearline Security**

---

## Overview

This guide provides recommended tooling for each adversary tier defined in the SCOPE Framework. It should be read alongside the framework itself — tools are a supporting layer, not a substitute for operational discipline.

The central principle of this guide:

> **Tools reduce risk. Architecture prevents catastrophe.**

No single application provides safety in isolation. Protection emerges when sources, communications, devices, and identities are structurally separated so that compromise cannot propagate.

---

## The Tier Progression

The shift across tiers is not simply "more tools." It is a shift in philosophy:

| Tier | Security Model |
|------|---------------|
| A1–A2 | Account security |
| A3 | Device + identity separation |
| A4 | Compartmentalized computing |
| A5 | Compartmentalized operations |
| A6 | Assumed compromise + blast-radius containment |

---

## Tier A1 — Opportunistic Attacker

**Capability: Low**

### Threat Profile
- Credential reuse attacks
- Basic phishing
- Malware from untrusted downloads
- Opportunistic device theft

### Recommended Stack

**Identity & Access**
- Password manager: Bitwarden (free) or 1Password
- Multi-factor authentication: authenticator app (Aegis on Android, Raivo on iOS) or hardware key (YubiKey)

**Devices**
- Modern OS with automatic updates enabled
- Full-disk encryption enabled (on by default on iOS, macOS, modern Android; enable manually on Windows via BitLocker)

**Communications**
- Signal for all sensitive messaging — baseline standard at every tier

**Email**
- Any major provider with MFA enabled
- Proton Mail recommended for sensitive correspondence

**Backup**
- Encrypted automatic backups (Proton Drive, or local encrypted drive)

---

## Tier A2 — Targeted Harassment / Medium Threat Actors

**Capability: Moderate**

### Threat Profile
- Phishing targeting individuals by name
- Social engineering attempts
- Account takeover attempts
- OSINT-based profiling and doxxing

### Recommended Stack (additions to A1)

**Communications Hardening**
- Signal with verified safety numbers — contact verification is mandatory
- Disable SMS fallback authentication on all accounts

**Identity Separation**
- Separate email addresses for: public identity, sensitive communications
- No cross-linking between identities

**Device Security**
- Strong screen lock; disable biometrics in high-risk contexts (border crossings, protests, arrests)
- Auto-lock set to 1–2 minutes maximum

**Browser Hygiene**
- Firefox (with uBlock Origin) or Brave
- Minimal browser extension footprint — each extension is an attack surface

**Account Protection**
- Hardware security keys (YubiKey or equivalent) for email and social accounts
- Remove phone number as account recovery option where possible

---

## Tier A3 — Organized Crime / High Capability Actors

**Capability: High**

### Threat Profile
- Persistent, targeted phishing campaigns
- Device theft with forensic intent
- Paid insiders or compromised contacts
- Surveillance of communications metadata

### Recommended Stack (additions to A2)

**Secure Communications**
- Signal (primary) with strict contact verification
- Briar for high-risk local communication (peer-to-peer, no central server)
- Channel separation: different tools for different operational contexts

**Anonymity Layer**
- Tor Browser for sensitive research and browsing
- Do not mix Tor sessions with identified accounts

**Operating System**
- GrapheneOS on Pixel devices — strongly recommended for mobile in this tier
- Hardened desktop OS with minimal installed software

**Document Protection**
- VeraCrypt for encrypted containers of sensitive materials
- Proton Drive for encrypted cloud storage

**Device Separation**
- Maintain at least two devices: daily device and sensitive work device
- Never cross-contaminate accounts, contacts, or sessions between them

---

## Tier A4 — Private Intelligence Firms / Advanced Persistent Actors

**Capability: High — Sophisticated**

### Threat Profile
- Sophisticated phishing combined with zero-day exploitation
- Cross-platform surveillance and correlation
- Metadata analysis across multiple services
- Targeted malware delivery via trusted channels

### Recommended Stack (additions to A3)

**Operating System Compartmentalization**
- Qubes OS — mandatory at this tier for high-assurance work environments
- Each operational context runs in a separate, isolated virtual machine

**Amnesic Environments**
- Tails OS for episodic sensitive sessions — leaves no trace on host hardware

**Communication Discipline**
- Strict identity compartmentalization: no shared recovery channels, no cross-linked accounts
- Assume all contact lists are exposed — limit who knows what

**Hardware Security**
- Hardware security keys required for all critical accounts
- Separate keys per identity domain

**Network Security**
- Tor for all sensitive browsing and research
- Avoid commercial VPNs as a substitute for Tor — they shift trust, not eliminate it

**Data Minimization**
- Aggressive reduction of stored sensitive data
- Zero retention principle: do not keep what you do not need

---

## Tier A5 — Government-Level Adversaries

**Capability: Very High**

### Threat Profile
- Legal coercion of service providers and platforms
- Advanced surveillance capabilities including IMSI catchers
- Physical device seizure and forensic analysis
- Multi-vector intelligence fusion: digital + physical + human sources

### Critical Note

At this tier, **tooling alone is insufficient**. Architecture matters more than any individual tool. The question is not "which app" but "how is the entire operational structure designed."

### Recommended Stack (additions to A4)

**Core Architecture Shift**
- Assume endpoint compromise is possible at any time
- Assume metadata exposure across all services
- Focus on compartmentalization and minimization over encryption alone

**Compartmentalization Stack**
- Qubes OS for all sensitive work domains
- Tails for episodic sensitive activity
- Separate physical devices per operational identity — not separate accounts on one device

**Encryption**
- Full-disk encryption on all devices without exception
- Hardware key management discipline — keys stored offline when not in active use

**Communication Doctrine**
- Signal only, with tightly controlled and verified contact graph
- No cloud-synced messaging history anywhere
- Assume any contact may be compromised or coerced

**Data Strategy**
- Minimal retention of source-identifying information
- Encrypted offline storage for critical materials — not cloud-connected

**Network Strategy**
- Tor as default for all sensitive browsing
- Physical network awareness: avoid predictable locations for sensitive work

---

## Tier A6 — Intelligence Services / Nation-State Level

**Capability: Exceptional**

### Threat Profile
- Multi-year targeted operations with patience and resources
- Supply chain compromise of hardware and software
- Zero-click exploitation requiring no user interaction
- Physical + digital + legal + human intelligence fusion
- Endpoint compromise treated as baseline assumption

### Critical Note

At this tier, the goal is not perfect security. Perfect security against a nation-state adversary does not exist. The goal is:

> **Reduce blast radius. Preserve source safety. Ensure compartment failure does not cascade.**

### Architectural Principles (more important than tools)

**1. Hard Compartmentalization**
Strict separation of identities, devices, communication channels, and operational contexts. A compromise in one compartment must not expose others.

**2. Minimal Digital Footprint**
Reduce stored sensitive material to the absolute minimum. Prefer ephemeral workflows. What does not exist cannot be seized or exposed.

**3. Source Protection Priority**
Sources are never directly linked to devices, accounts, or communication histories — under any circumstances.

**4. Assumed Compromise Model**
Every endpoint is potentially compromised. Security is validated through structural separation, not trust in any single tool or system.

### Tool Stack (supporting layer only)

**Operating Systems**
- Qubes OS for primary secure workstation
- Tails for all ephemeral operations

**Communications**
- Signal with strict verification and compartmented identities
- Face-to-face communication for highest-sensitivity discussions — no digital record

**Cryptography**
- Hardware security keys across all identity domains
- Strong offline encrypted storage — air-gapped where feasible

**Networking**
- Tor for all sensitive browsing and research without exception

**Data Handling**
- Encrypted, offline-first document storage
- No single centralized repository of sensitive information
- Assume any cloud service can be legally compelled

---

## Final Principle

The most important idea across all tiers:

> Tools reduce risk. Architecture prevents catastrophe.

No single application — Signal, Tor, Qubes, encryption — provides safety by itself. Real protection emerges when sources, communications, devices, and identities are structurally separated so that the failure of any one component does not compromise the whole.

---

*© Clearline Security — Released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)*
