# 🕵️‍♂️ The Gift Detective
### Conversational AI Gift Curation Chatbot — Built on Sekai

> *"Every person. The perfect gift."*

---

## 📌 Overview

**The Gift Detective** is a no-code AI-powered chatbot built on the [Sekai](https://sekai.ai) platform. It solves a real consumer problem: the paralysis of not knowing what to gift someone.

Instead of typing keywords into Amazon and getting overwhelmed, users answer 2 natural-language questions about the recipient. The chatbot — persona-locked as a witty forensic detective — analyzes the responses and outputs 3 hyper-personalized gift recommendations, each with direct Amazon shopping links filtered by price range.

**Built by:** Girija Darapu — AI Product Manager  
**Platform:** Sekai (no-code mobile AI app builder)  
**Status:** Portfolio Project — Demonstration Purpose Only

---

## 🧠 The Problem

| Traditional E-Commerce | The Gift Detective |
|------------------------|-------------------|
| Requires you to know what to search | Works from personality & hobbies |
| Returns hundreds of irrelevant results | Returns exactly 3 curated picks |
| No personalization | Tailored to the specific recipient |
| Generic keyword search | Conversational discovery layer |

> **Amazon solves "I know what I want."  
> The Gift Detective solves "I have no idea what to get."**

---

## ✨ Features

- 🎭 **Detective Persona** — Consistent gamified forensic theme across all conversation turns
- 🗣️ **2-Question Forensic Interview** — Extracts hobbies, personality, and lifestyle signals
- 💰 **Budget Filter** — User selects Under $25 / $25–$50 / $50–$100 / $100+
- 🎁 **3 Gift Cards** — Hyper-personalized, emoji-themed, with unique descriptions
- 🛒 **Amazon Price-Tier Links** — 3 buttons per card (Under $30 / $30–$75 / $75+) linking directly to filtered Amazon search
- 📤 **Share Screen** — "Share Evidence" CTA to share results with friends

---

## 🏗️ How It Was Built

This app was built entirely using **prompt engineering** on Sekai — no code written. Each screen and feature was defined through structured natural-language prompts fed to Sekai's AI builder.

**Prompt engineering decisions made:**
- Persona guardrails to prevent model drift across turns
- Structured output constraints to always return exactly 3 gift cards
- Dynamic URL generation to convert gift names into Amazon search parameters
- Price filter encoding using Amazon's native `p_36` URL parameter

See [`prompts.txt`](./prompts.txt) for the full prompt sequence used to build this app.

---

## 📁 Repository Structure

```
GiftDetective/
├── README.md                     # This file
├── prompts.txt                   # All Sekai prompts used to build the app
├── GiftDetective_PRD_v1.2.docx  # Full Product Requirements Document
└── FUTURE_SCOPE.md               # Phase 2 roadmap — multi-retailer API integration
```

---

## 🚀 Future Scope

The MVP uses Amazon search links. The next phase bridges conversational discovery directly into live e-commerce:

- **Amazon Product Advertising API** — real product images, live pricing, direct purchase links
- **Walmart & Target Affiliate APIs** — localized retail options
- **Etsy Open API** — artisanal and niche alternatives
- **RAG Pipeline** — convert LLM text output into product embeddings matched against live inventory

Goal: Zero ideas → executed checkout in under 2 minutes.

---

## 📄 PRD

Full Product Requirements Document available in [`GiftDetective_PRD_v1.2.docx`](./GiftDetective_PRD_v1.2.docx)

Covers: Executive Summary, User Stories, System Architecture, Feature Matrix, Success KPIs, and Version Control Log.

---

## 👩‍💼 About

Built as part of an AI Product Manager portfolio to demonstrate:
- Prompt engineering for consumer product outcomes
- Conversational UX design
- LLM persona design & guardrail architecture
- No-code AI app prototyping
- E-commerce funnel thinking

**LinkedIn:** [Connect with Girija Darapu](https://linkedin.com/in/girija-darapu)

---

*Portfolio Project — Demonstration Purpose Only*
