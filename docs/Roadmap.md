# Taxentia.ai – Roadmap

**Version:** 0.1  
**Status:** Active Development  
**Time Horizon:** 0–16 weeks post-initiation

---

## 🚦 Phase 0: Foundation

**Timeline:** Week 0–1  
**Goals:**
- Lock brand, domain, stack
- Set up GitHub and project board
- Finalize product vision and architecture

**Deliverables:**
- taxentia.ai domain, email setup
- GitHub repo structure
- Initial PRD (this doc)
- Onboarding doc for devs

---

## 🛠️ Phase 1: MVP Build

**Timeline:** Weeks 1–4  
**Goals:**
- Build working prototype with full logic pipeline

### Milestone 1.1: IRS Data Ingestion
- Chunk Title 26, IRS Pubs, Rev. Rulings
- Embed via OpenAI
- Store with metadata in Pinecone

### Milestone 1.2: Query → Response Chain
- Build n8n flow:
  User query → embed → Pinecone search → GPT → structured output

### Milestone 1.3: MVP UI
- Build WeWeb/Retool frontend
- Add login, query history, expandable citations
- PDF export integration

---

## 🔍 Phase 2: Test & Validate

**Timeline:** Weeks 5–6  
**Goals:** Private beta with 5–10 CPAs

**Deliverables:**
- Structured feedback form
- Track usage patterns, trust in logic, citation depth

---

## 🌐 Phase 3: Public Launch

**Timeline:** Weeks 7–10  
**Goals:**
- Launch on Product Hunt, Reddit, CPA forums
- Begin onboarding for Pro & Firm tiers

---

## 📈 Phase 4: Scale & Expand

**Timeline:** Weeks 10–16+

**Goals:**
- Add AI Memo Generator
- Client folders
- IRS update alerts
- Early enterprise analytics

---

## 🚧 Known Constraints

- Stack finalization pending
- Pricing validation pending
- Memo types for PDF export to be confirmed
