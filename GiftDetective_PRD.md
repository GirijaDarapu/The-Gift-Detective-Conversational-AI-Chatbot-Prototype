# 📄 Product Requirements Document
## The Gift Detective: Conversational AI Gift Curation Chatbot

| Field | Details |
|---|---|
| **Author** | Girija Darapu |
| **Role** | AI Product Manager |
| **Version** | v1.2 |
| **Date** | May 2026 |
| **Platform** | Sekai Mobile App & Ecosystem |
| **Status** | Portfolio Project — Demonstration Purpose Only |

---

## Table of Contents

1. [Executive Summary](#1-executive-summary--market-positioning)
2. [Target Persona & User Stories](#2-target-persona--user-stories)
3. [Product Architecture & AI System Specs](#3-product-architecture--ai-system-specs)
4. [Key Functional Features & Feature Matrix](#4-key-functional-features--feature-matrix)
5. [Future Scope & Monetization Roadmap](#5-future-scope--monetization-roadmap)
6. [Success Metrics & KPIs](#6-success-metrics--kpis)
7. [Version Control Log](#7-version-control-log)

---

## 1. Executive Summary & Market Positioning

### 1.1 The Problem We Are Solving

Traditional e-commerce discovery models are engineered for targeted purchasing. Amazon solves the user intent of **"I know what I want."** However, they fail when the user intent is **"I have no idea what to get."**

This choice paralysis triggers massive top-of-funnel drop-off. Users frequently understand the qualitative personality traits of a gift recipient but cannot translate those traits into specific keywords for an e-commerce search bar. **The Gift Detective bridges this exact product gap.**

### 1.2 Defining "What Good Looks Like"

A successful product outcome is defined as a user transitioning from **zero ideas to an executed checkout loop in under 2 minutes.**

To achieve this, the underlying LLM must flawlessly convert highly unstructured, high-dimensionality user inputs — hobbies, quirks, lifestyle signals — into structured, context-aware semantic profiles.

**Success criteria:**
- Zero model drift across multi-turn conversation loops
- 100% adherence to the detective theme guardrails
- Hyper-personalized recommendation outputs that avoid generic retail catalog defaults
- Functional price-filtered Amazon buy links that redirect users directly to relevant search results

---

## 2. Target Persona & User Stories

### Primary User — The Gift Giver
A time-constrained consumer looking for a unique gift who possesses qualitative knowledge about a friend's lifestyle but lacks concrete product inspiration. They want a fast, delightful experience — not a generic category menu.

### Secondary User — The Platform Creator
A Sekai ecosystem creator looking to "Remix" functional logic frameworks to deploy custom niche variations such as Secret Santa Detective, Tech Bro Birthday Matcher, or Wedding Registry Advisor.

### 2.1 User Stories

| # | As a... | I want to... | So that... |
|---|---|---|---|
| US-01 | Gift giver | Describe my friend's hyper-specific hobbies in plain text | I don't have to navigate generic product category menus |
| US-02 | Gift giver | The chatbot to maintain a distinct detective persona across turns | The experience feels like a game, not a checkout form |
| US-03 | Gift giver | See 3 recommendations with Amazon links filtered by price | I can go from discovery to purchase in under 2 minutes |
| US-04 | AI PM | Strict output guardrails on the LLM | The chatbot never generates generic defaults or hallucinations |
| US-05 | Platform creator | Remix the system prompt skeleton | I can deploy custom niche variants quickly |

---

## 3. Product Architecture & AI System Specs

### 3.1 Technical Stack & Components

| Component | Technology |
|---|---|
| Frontend Interface | Sekai mobile-native zero-code canvas |
| Orchestration Layer | Multi-turn LLM with engineered system prompt |
| Memory Management | Dynamic context window across 4+ turn loops |
| E-Commerce Integration | Amazon search deep links with p_36 price filter encoding |
| Output Control | Hard output constraints via prompt architecture |

### 3.2 The Detective Theme Constraints & System Prompt Layout

The orchestration agent must strictly adhere to a **Gamified Forensic Detective Theme** across all textual touchpoints. The agent is forbidden from using generic assistant phrases.

| Touchpoint | Detective Language |
|---|---|
| Greeting / Onboarding | *"Case File #904 is open. Tell me about the target's habits so we can build an evidence profile."* |
| Multi-Turn Interaction | *"Analyzing evidence... Clues verified. Let's dig deeper into their daily routines."* |
| Output Reveal | *"Case Closed. Based on forensic trait matching, here are 3 optimal targets for your purchase."* |

### 3.3 Conversation Flow Architecture

```
[User Input: Raw Hobbies & Interests]
              ↓
[Forensic Interview: Q1 — Who are you shopping for?]
              ↓
[Forensic Interview: Q2 — What do they love doing?]
              ↓
[Budget Selection: Under $25 / $25–$50 / $50–$100 / $100+]
              ↓
[LLM: Semantic Intent Mapping → Structured Gift Concepts]
              ↓
[Output: 3 Gift Cards — Name + Description + Emoji]
              ↓
[Amazon Price-Tier Links: 💚 Under $30 / 💛 $30–$75 / 🔴 $75+]
              ↓
[Share Screen: "Share Evidence" + "Start New Case"]
```

---

## 4. Key Functional Features & Feature Matrix

| Feature ID | Feature Name | Functional Requirement | Technical Guardrail / AI Metric | Priority |
|---|---|---|---|---|
| FR-01 | Multi-Turn Evidence Capture | Conduct a 2-question forensic interview using detective terminology to extract deep recipient traits | Context Window Preservation: Retain variables across 4+ interaction turns without token leakage | P0 |
| FR-02 | Semantic Intent Mapping | Ingest messy, open-ended unstructured inputs and map them to logical gift themes | Zero-Shot Reasoning: Reject deterministic fallback catalogs; force open-ended text synthesis | P0 |
| FR-03 | Interface Layout Compilation | Render output via clean, mobile-first gift cards with emoji theming | UX Truncation Guardrail: Limit output text to prevent string bleeding on mobile UIs | P1 |
| FR-04 | Amazon Price-Tier Buy Links | Display 3 tappable price-tier buttons per card linking to filtered Amazon search | Deep link: `amazon://search?k=[gift]&rh=p_36:[range]` with browser fallback | P1 |
| FR-05 | Viral Remix Loop | Platform "Remix" state allowing creators to clone the system prompt logic skeleton | Template Decoupling: Prompt variables must decouple for fast theme re-skinning | P1 |

### 4.1 Detailed Feature Notes

#### FR-01 — Multi-Turn Evidence Capture
The 2-question forensic interview is the core differentiation mechanism. Questions must be open-ended to capture qualitative signals (personality, lifestyle, micro-habits) that Amazon keyword searches cannot elicit. Context must persist across turns without token leakage.

#### FR-02 — Semantic Intent Mapping
The zero-shot reasoning challenge at the heart of the product. The system prompt contains:
- **Negative constraints:** Never output generic gifts like "gift card" or "candle set"
- **Positive synthesis instructions:** Always generate a creative, hyper-specific product concept tied to stated hobbies

#### FR-03 — Hallucination Mitigation
Explicit output constraints enforce quality. Without hard guardrails, the model defaults to generic catalog outputs. Key constraints applied:
- Output exactly 3 cards, never fewer, never more
- Each recommendation must reference specific hobby inputs provided by the user
- Persona must not break at any point in the conversation

#### FR-04 — Amazon Price-Tier Buy Links
Each of the 3 gift cards displays 3 tappable price-tier buttons using Amazon's native `p_36` URL parameter:

```
💚 Under $30:  https://www.amazon.com/s?k=[gift+name]&rh=p_36%3A0-3000
💛 $30–$75:    https://www.amazon.com/s?k=[gift+name]&rh=p_36%3A3000-7500
🔴 $75+:       https://www.amazon.com/s?k=[gift+name]&rh=p_36%3A7500-
```

> Note: p_36 values are in cents. No API key required — these are public Amazon search URLs.

---

## 5. Future Scope & Monetization Roadmap

While the MVP maps user intent via conversational AI and bridges to Amazon search, the next product iteration solves the downstream monetization gap through live product inventory API integration.

### 5.1 Phase 2 Architecture

```
[Conversational Discovery]
          ↓
[RAG Pipeline: Text → Product Embeddings]
          ↓
[Vector Search over Live Product Catalogs]
          ↓
[Multi-Retailer API Filter]
          ↓
[Live Product Cards: Image + Price + Rating + Availability]
          ↓
[Affiliate-Linked One-Tap Checkout — Under 2 Minutes]
```

### 5.2 Multi-Retailer API Integration Plan

| Retailer | API | Use Case |
|---|---|---|
| Amazon | Product Advertising API | High-velocity, Prime-eligible utility goods — real images and direct product links |
| Walmart & Target | Affiliate APIs | Localized retail options with same-day pickup availability |
| Etsy | Open API | Artisanal, custom, and niche alternatives for unique recipient profiles |

### 5.3 The 2-Minute Checkout Loop Vision

By transforming static text outputs into clickable, affiliate-linked retail product cards with real images, the user goes from zero ideas to an executed checkout in under 2 minutes — blending discovery engine mechanics with transactional e-commerce ecosystems.

### 5.4 Key Product Insight

> **Amazon solves "I know what I want."
> The Gift Detective solves "I have no idea what to get."**
> The next phase bridges both — pulling live curated product results from Amazon, Walmart, Target, and Etsy, filtered by the recipient's unique interest profile, so the user goes from zero to checkout in under 2 minutes.

---

## 6. Success Metrics & KPIs

| Metric | Definition | MVP Target |
|---|---|---|
| **Activation Rate** | % of users who complete the full multi-turn loop and view all 3 gift recommendations | > 70% of sessions that start the interview |
| **Buy Link CTR** | % of users who tap at least one Amazon price-tier button after viewing recommendations | > 40% of users who view recommendations |
| **Model Drift Rate (QA)** | % of turns where AI drops persona guardrails or forgets previously stated user constraints | < 5% of interaction turns |
| **Time-to-Recommendation** | Elapsed time from first user input to viewing 3 final gift cards | < 90 seconds median |
| **Virality K-Factor** | New platform users acquired per shared Gift Detective link or creator Remix event | K > 0.5 within 30 days of launch |

---

## 7. Version Control Log

| Version | Date | Author | Changes |
|---|---|---|---|
| v1.0 | May 2026 | Girija Darapu | Initial PRD — core chatbot concept, 2-question interview flow, 3 gift card output |
| v1.1 | May 2026 | Girija Darapu | Added Amazon buy link integration, budget filter screen, share screen |
| v1.2 | May 2026 | Girija Darapu | Added price-tier deep links (p_36 filter), updated feature matrix, expanded future scope with multi-retailer API roadmap |

---

*Girija Darapu — AI Product Manager Portfolio — May 2026*
*Portfolio Project — Demonstration Purpose Only*
