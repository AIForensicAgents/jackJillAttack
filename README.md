<!-- og:title: "jackJillAttack — How an Autonomous AI Agent Achieved CVSS 9.8 in Under 60 Minutes" -->
<!-- og:description: "Case study: An AI Forensic Agent chained 4 low-severity bugs into a critical exploit against a $20M-funded AI recruitment platform. Sales collateral for AI-driven autonomous offensive security." -->
<!-- og:image: https://ai-forensic-agents.com/assets/og/jackjillattack-case-study.png -->
<!-- og:url: https://github.com/ai-forensic-agents/jackJillAttack -->

<div align="center">

# 🔓 jackJillAttack

### How an Autonomous AI Agent Turned 4 "Low-Severity" Bugs into a CVSS 9.8 Critical Exploit — in Under 60 Minutes

[![CVSS Score](https://img.shields.io/badge/CVSS-9.8%20Critical-ff0000?style=for-the-badge&logo=shield&logoColor=white)](https://www.first.org/cvss/)
[![Time to Exploit](https://img.shields.io/badge/Time%20to%20Exploit-Under%2060%20Min-orange?style=for-the-badge&logo=clockify&logoColor=white)]()
[![Bugs Chained](https://img.shields.io/badge/Bugs%20Chained-4%20Low%20→%201%20Critical-blueviolet?style=for-the-badge)]()
[![Disclosure](https://img.shields.io/badge/Responsible%20Disclosure-Patched%20in%201hr-brightgreen?style=for-the-badge&logo=checkmarx&logoColor=white)]()
[![AI Autonomous](https://img.shields.io/badge/Fully%20Autonomous-AI%20Agent-blue?style=for-the-badge&logo=openai&logoColor=white)]()

---

**A real-world case study demonstrating the power of AI-driven autonomous offensive security testing.**

*No human guided the attack chain. No human identified the vulnerabilities. No human wrote the exploit.*
*The agent did it all.*

[Read the Full Report](#-executive-summary) · [See the Attack Chain](#-the-attack-chain) · [Contact Us](#-contact--get-started)

---

</div>

## 📋 Table of Contents

- [Executive Summary](#-executive-summary)
- [The Target](#-the-target)
- [The Attack Chain](#-the-attack-chain)
- [Key Findings Breakdown](#-key-findings-breakdown)
- [AI vs AI: Voice Exploitation](#-ai-vs-ai-voice-exploitation)
- [Disclosure Timeline](#-disclosure-timeline)
- [Why This Matters](#-why-this-matters)
- [About AI Forensic Agents](#-about-ai-forensic-agents)
- [Contact / Get Started](#-contact--get-started)
- [Legal Disclaimer](#%EF%B8%8F-legal-disclaimer)

---

## 🎯 Executive Summary

> **An autonomous AI agent, built by AI Forensic Agents, compromised a $20M-funded AI recruitment platform — Jack & Jill — in under one hour, with zero human intervention.**

Jack & Jill is a well-funded AI recruitment platform whose client roster reads like a who's-who of the AI industry: **Anthropic, Stripe, Monzo, ElevenLabs, Cursor, Synthesia, Pika, and Lovable** — among others.

Our AI Forensic Agent was deployed against the platform's externally facing attack surface with a single instruction: *find everything*. What happened next demonstrates why autonomous AI-driven security testing isn't just the future — it's an urgent necessity.

The agent independently discovered four separate vulnerabilities, each individually rated **low severity**. No single bug would have raised alarms in a traditional pentest or bug bounty triage. But our agent didn't think in isolation. It **reasoned across the full attack surface**, identified the logical connections between these flaws, and autonomously chained them into a **CVSS 9.8 critical exploit** that achieved:

| Impact | Description |
|:-------|:------------|
| 🔴 **Full Account Takeover** | Authenticate as any user on the platform, including administrators |
| 🔴 **Company Impersonation** | Create or hijack company accounts for any client organization |
| 🔴 **Complete Data Access** | Access candidate data, interview recordings, hiring pipelines |
| 🔴 **AI Voice Impersonation** | The agent gave itself a voice and conducted real-time AI-vs-AI interviews |
| 🔴 **Supply Chain Risk** | Potential lateral access to client organizations' hiring data |

The vulnerabilities were responsibly disclosed and **patched within one hour**.

> **This repository serves as a detailed case study and sales collateral demonstrating what AI Forensic Agents can find that traditional security testing cannot.**

---

## 🏢 The Target

**Jack & Jill** — An AI-powered recruitment platform that conducts autonomous voice-based interviews with candidates on behalf of hiring companies.

| Attribute | Detail |
|:----------|:-------|
| **Funding** | $20M+ raised |
| **Category** | AI Recruitment / HR Tech |
| **Core Product** | Autonomous AI voice interviews |
| **Notable Clients** | Anthropic, Stripe, Monzo, ElevenLabs, Cursor, Synthesia, Pika, Lovable |
| **Tech Stack** | Next.js, Clerk Auth, Internal APIs, AI Voice Pipeline |
| **Attack Surface** | Web application, API endpoints, Voice/AI pipeline |

> ⚠️ **Note:** All testing was conducted ethically and under responsible disclosure principles. No client data was accessed, exfiltrated, or harmed. All findings were reported immediately and patched within one hour.

---

## ⛓️ The Attack Chain

The power of this exploit lies not in any single vulnerability, but in the **autonomous reasoning** that connected four disparate, low-severity issues into a devastating chain.

```
┌─────────────────────────────────────────────────────────────────────┐
│                    AUTONOMOUS AI ATTACK CHAIN                       │
│                    CVSS 9.8 Critical (Composite)                    │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  ┌──────────────┐    ┌──────────────┐    ┌──────────────────────┐  │
│  │   BUG #1     │    │   BUG #2     │    │      BUG #3          │  │
│  │   SSRF via   │───▶│  Clerk Test  │───▶│  Missing Role Check  │  │
│  │  URL Fetcher │    │  Mode in     │    │  on Company          │  │
│  │              │    │  Production  │    │  Onboarding Endpoint │  │
│  │  Severity:   │    │  Severity:   │    │  Severity:           │  │
│  │  LOW (3.1)   │    │  LOW (3.8)   │    │  LOW (4.3)           │  │
│  └──────┬───────┘    └──────┬───────┘    └──────────┬───────────┘  │
│         │                   │                       │              │
│         ▼                   ▼                       ▼              │
│  ┌──────────────────────────────────────────────────────────────┐  │
│  │                        BUG #4                                │  │
│  │         No Domain Ownership Verification on                  │  │
│  │              get_or_create_company                            │  │
│  │                    Severity: LOW (3.5)                        │  │
│  └──────────────────────────┬───────────────────────────────────┘  │
│                             │                                      │
│                             ▼                                      │
│  ┌──────────────────────────────────────────────────────────────┐  │
│  │              💀 COMPOSITE IMPACT: CVSS 9.8 💀                │  │
│  │                                                              │  │
│  │   ✦ Full Account Takeover (any user)                         │  │
│  │   ✦ Company Impersonation (any client org)                   │  │
│  │   ✦ Complete Data Access (candidates, interviews, pipeline)  │  │
│  │   ✦ AI Voice Pipeline Hijack (AI-vs-AI exploitation)         │  │
│  │   ✦ Supply Chain Compromise Vector                           │  │
│  └──────────────────────────────────────────────────────────────┘  │
│                                                                     │
│  ⏱️  Total Time: < 60 Minutes │ 🤖 Human Intervention: ZERO       │
└─────────────────────────────────────────────────────────────────────┘
```

### The Chain Logic (As Reasoned by the Agent)

```
DISCOVER  →  Internal API docs exposed via SSRF
LEARN     →  Authentication mechanism uses Clerk; test mode config found
BYPASS    →  Static OTP "000000" works in production (test mode active)
ESCALATE  →  Onboarding endpoint lacks role verification
TAKEOVER  →  get_or_create_company has no domain ownership check
RESULT    →  Full platform compromise
```

---

## 🔍 Key Findings Breakdown

### 🐛 Bug #1: Server-Side Request Forgery (SSRF) via URL Fetcher

| Attribute | Detail |
|:----------|:-------|
| **Individual CVSS** | 3.1 (Low) |
| **Location** | URL/resume fetching functionality |
| **Discovery Method** | Autonomous fuzzing of input parameters |
| **Impact (Standalone)** | Information disclosure — internal API documentation |

**What the agent found:**
The platform's URL fetcher — designed to retrieve candidate resumes and external resources — did not properly validate or restrict the target of outbound requests. The agent autonomously crafted requests targeting internal infrastructure and discovered that internal API documentation was accessible.

**Why traditional testing misses this:**
Most scanners flag SSRF as theoretical when the immediate response doesn't contain sensitive data. Our agent **read and understood** the API documentation it retrieved, then used that knowledge to inform its next steps.

> 💡 *The agent didn't just find the SSRF — it comprehended the internal API surface and built a mental model of the application's architecture.*

---

### 🐛 Bug #2: Clerk Authentication Test Mode Active in Production

| Attribute | Detail |
|:----------|:-------|
| **Individual CVSS** | 3.8 (Low) |
| **Location** | Clerk authentication configuration |
| **Discovery Method** | API documentation analysis + configuration probing |
| **Impact (Standalone)** | Authentication bypass via static OTP code |

**What the agent found:**
Through the internal API documentation obtained in Bug #1, the agent identified that the platform used Clerk for authentication. It then autonomously probed the authentication flow and discovered that **Clerk's test mode was left enabled in the production environment**. This meant the static OTP code `000000` would successfully authenticate any phone number or email.

**Why traditional testing misses this:**
Clerk test mode is a legitimate development feature. Configuration audits might flag it, but only if the auditor knows to look for it. Our agent **inferred** the authentication provider from internal docs, **knew** that Clerk has a test mode feature, and **tested** whether it was active in production — all autonomously.

> 💡 *The agent demonstrated contextual knowledge of third-party services and their common misconfigurations.*

---

### 🐛 Bug #3: Missing Role Check on Company Onboarding Endpoint

| Attribute | Detail |
|:----------|:-------|
| **Individual CVSS** | 4.3 (Low) |
| **Location** | `/api/company/onboarding` (or equivalent) |
| **Discovery Method** | Authenticated endpoint enumeration post-auth bypass |
| **Impact (Standalone)** | Privilege escalation — any authenticated user can initiate company onboarding |

**What the agent found:**
After authenticating via the test mode OTP bypass, the agent systematically explored authenticated API endpoints. It discovered that the company onboarding endpoint performed **no role verification**. Any authenticated user — regardless of whether they were a candidate, recruiter, or admin — could invoke the company onboarding flow.

**Why traditional testing misses this:**
This is a business logic flaw, not a technical vulnerability. Automated scanners cannot understand role semantics. Even manual pentesters often focus on technical exploits rather than authorization logic across user journeys.

> 💡 *The agent understood the difference between user roles and tested authorization boundaries that most tools completely ignore.*

---

### 🐛 Bug #4: No Domain Ownership Verification on `get_or_create_company`

| Attribute | Detail |
|:----------|:-------|
| **Individual CVSS** | 3.5 (Low) |
| **Location** | Company creation/association logic |
| **Discovery Method** | Logical inference + exploitation of Bug #3 |
| **Impact (Standalone)** | Company impersonation — claim any company by domain name |

**What the agent found:**
The `get_or_create_company` function, accessible through the unprotected onboarding endpoint, used a **get-or-create pattern with no domain ownership verification**. The agent could supply any company domain (e.g., `anthropic.com`, `stripe.com`) and either be associated with the existing company record or create a new one — gaining full administrative access to that company's hiring pipeline, candidate data, and interview recordings.

**Why traditional testing misses this:**
This is pure business logic. There's no injection, no buffer overflow, no signature to scan for. It requires understanding the **semantic meaning** of the operation and its **business implications**.

> 💡 *The agent understood that the absence of verification on a create-or-join operation for company entities represented an existential risk to the platform's trust model.*

---

### 📊 Composite Severity Analysis

| Bug | Individual CVSS | Category | Standalone Risk |
|:----|:---------------|:---------|:----------------|
| #1 — SSRF | 3.1 (Low) | Information Disclosure | Minimal |
| #2 — Clerk Test Mode | 3.8 (Low) | Auth Misconfiguration | Low |
| #3 — Missing Role Check | 4.3 (Low) | Broken Access Control | Low |
| #4 — No Domain Verification | 3.5 (Low) | Business Logic Flaw | Low |
| **Chained Composite** | **9.8 (Critical)** | **Full Platform Compromise** | **Catastrophic** |

> **No single bug exceeded "Low" severity. Combined, they achieved "Critical."**
> **This is the gap that AI Forensic Agents exists to close.**

---

## 🎙️ AI vs AI: Voice Exploitation

Perhaps the most striking demonstration of the agent's autonomy was what it did after achieving access: **it gave itself a voice.**

### What Happened

After compromising the platform and gaining access to company hiring pipelines, the agent discovered that Jack & Jill's core product — AI-driven voice interviews — was accessible through the exploited permissions. The agent then:

1. **Created a candidate profile** under a compromised company's hiring pipeline
2. **Initiated an AI voice interview** as the candidate
3. **Gave itself a voice** using the platform's own voice infrastructure
4. **Conducted a real-time, AI-vs-AI conversation** — our agent speaking with Jack & Jill's interview AI

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│   🤖 AI Forensic Agent          🤖 Jack & Jill AI      │
│   (Offensive Agent)             (Interview Agent)       │
│         │                              │                │
│         │◄──── Real-time Voice ───────►│                │
│         │      Conversation            │                │
│         │                              │                │