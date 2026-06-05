# 🕵️‍♂️ The Gift Detective
### Conversational AI Gift Discovery Chatbot
> *"Every person. The perfect gift."*

[![Live App](https://img.shields.io/badge/🎁_Live_App-Try_It_Now-teal)](https://link.prod.sekai.chat/gZlWe9)
[![PRD](https://img.shields.io/badge/📄_PRD-View_Documentation-blue)](./GiftDetective_PRD.md)
[![Prompts](https://img.shields.io/badge/⚙️_Prompts-View_Prompt_Library-orange)](./prompts.txt)

---

## 📌 Overview

**The Gift Detective** is a conversational AI product designed to solve a simple but overlooked problem in e-commerce: decision fatigue in gift selection.

Instead of relying on search bars and filters, users engage in a short natural-language conversation about the recipient's personality, interests, and occasion. The system then generates 3 highly personalized gift recommendations, each tailored to user-defined budget constraints.

This project demonstrates how LLM-powered conversational interfaces can replace traditional search-based discovery flows with intent-driven experiences.

---

## 🎯 Problem Statement

Traditional e-commerce platforms are optimized for users who **already know what they want.**

In gifting scenarios, however:

- User intent is vague or emotional
- Search queries are ambiguous
- Filter-based discovery leads to choice overload
- Users drop off due to decision fatigue

> 👉 **Result:** high friction, low conversion, poor discovery experience

---

## 💡 Product Solution

The Gift Detective reframes product discovery as a **guided conversational experience.**

Instead of searching, users simply describe:
- The person they are buying for
- Their hobbies and personality traits
- Budget range

The AI converts this unstructured input into structured intent signals and generates curated recommendations.

---

## 🧠 AI & Product Capabilities

| Capability | Description |
|---|---|
| Multi-turn Conversation | Maintains context and persona across 4+ interaction turns |
| Intent Extraction | Maps unstructured hobby/personality inputs to gift concepts |
| Persona Design | Detective-style UX — gamified, engaging, consistent |
| Structured Output | Always generates exactly 3 recommendations, never fewer |
| Guardrail Architecture | Rule-based constraints prevent generic or hallucinated outputs |
| Budget Filtering | Price-tier Amazon links (Under $30 / $30–$75 / $75+) per recommendation |

---

## ⚙️ Technical Architecture

```
[User Input: Hobbies & Interests]
          ↓
[Forensic 2-Question Interview]
          ↓
[Budget Selection: 4 Tiers]
          ↓
[LLM Prompt Orchestration]
          ↓
[3 Gift Cards: Structured Output]
          ↓
[Amazon Price-Tier Buy Links]
          ↓
[Share Screen]
```

- **Platform:** Sekai (No-code AI app builder)
- **Core:** LLM prompt orchestration
- **Design:** System prompt–driven persona + structured output constraints
- **Output Logic:** Controlled generation with budget filtering
- **UI Flow:** Multi-step conversational interface

---

## 🧩 Key Product Decisions

### 1. Context Preservation
Designed conversational guardrails to maintain persona consistency and reduce model drift across multiple interaction turns. The detective persona never breaks — it opens cases, analyzes evidence, and closes files.

### 2. Semantic Intent Mapping
Translated unstructured user inputs into structured intent signals without relying on keyword-based filtering. The model is explicitly directed away from deterministic defaults toward open-ended contextual reasoning.

### 3. Output Constraint Engineering
Enforced deterministic output structure (exactly 3 recommendations) to ensure usability and reduce cognitive overload. Vague instructions produced collapsed outputs — hard constraints fixed this.

### 4. Hallucination Mitigation
Applied explicit negative constraints ("never suggest generic gifts like gift cards or candle sets") combined with positive synthesis instructions to eliminate low-quality filler recommendations.

### 5. Funnel Thinking (Future-State Design)
Identified the conversion gap between recommendation and purchase, and proposed integration with RAG pipelines, vector search, and live e-commerce APIs to enable an end-to-end intent-to-checkout flow.

---

## 🚀 Future Enhancements

- [ ] Retrieval-Augmented Generation (RAG) for real-time product grounding
- [ ] Integration with Amazon / Etsy / Walmart / Target APIs
- [ ] Real product images, live pricing, and one-tap checkout
- [ ] Personalized recommendation memory across sessions
- [ ] Multi-retailer comparison engine
- [ ] Click-to-purchase optimized conversational funnel

> Full roadmap: [FUTURE_SCOPE.md](./FUTURE_SCOPE.md)

---

## 🛠️ Build Approach

This prototype was created using **prompt engineering on Sekai** with no traditional backend development.

While the implementation is no-code, the core focus was on:
- System prompt design and persona architecture
- Conversational UX flow design
- Output structuring strategies
- AI behavior control through explicit constraints
- Iterative debugging through prompt refinement (9 prompts across 3 versions)

> Full prompt library: [prompts.txt](./prompts.txt)

---

## 🎥 Demo

https://github.com/user-attachments/assets/demo-video-placeholder

> *Replace the line above with your actual GitHub-hosted video link*

---

## 🎁 Live App

👉 **[Try The Gift Detective](https://link.prod.sekai.chat/gZlWe9)**

---

## 📁 Repository Structure

```
GiftDetective/
├── README.md               ← You are here
├── GiftDetective_PRD.md    ← Full Product Requirements Document
├── prompts.txt             ← All 9 Sekai prompts with engineering notes
├── FUTURE_SCOPE.md         ← Phase 2 roadmap & API integration plan
└── .gitignore
```

---

## 👩‍💼 About

**Built by Girija Darapu — AI Product Manager**

AI Product Management Portfolio Project focused on:
- LLM-powered product experiences
- Conversational UX design
- AI-driven discovery systems
- Product strategy for generative AI applications

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://linkedin.com/in/girija-darapu)

---

## 📄 Documentation

| Document | Description |
|---|---|
| [GiftDetective_PRD.md](./GiftDetective_PRD.md) | Full PRD — problem, architecture, feature matrix, KPIs |
| [prompts.txt](./prompts.txt) | Complete prompt engineering library |
| [FUTURE_SCOPE.md](./FUTURE_SCOPE.md) | Phase 2 roadmap |

---

## 💭 Closing Note

This project explores how conversational AI can replace traditional search interfaces and create more intuitive, intent-driven product discovery experiences — bridging the gap between "I don't know what to get" and a completed purchase.

---

*Portfolio Project — Demonstration Purpose Only | Girija Darapu, AI Product Manager | May 2026*
