# Taxentia.ai – Product Requirements Document (PRD)
**Version:** 0.1  
**Status:** Active Draft  
**Last Updated:** 2025-05-15  
**Owner:** Bader Ale  

---

## 1. Executive Summary

**Taxentia.ai** is a professional-grade AI assistant for CPAs, tax attorneys, and enrolled agents. It interprets IRS tax code and related guidance (Regs, Pubs, Rulings, Court Cases) and delivers citation-backed, logic-driven answers with audit-trail precision. Unlike consumer-facing tools, Taxentia is optimized for regulatory-grade clarity, legal soundness, and professional accountability.

This document defines the core product vision, MVP scope, target users, feature set, and system architecture.

---

## 2. Goals & Success Metrics

### 2.1 Goals
- Deliver logic-aware, citation-rich answers to complex tax questions.
- Provide audit-trail-quality output, including PDF memos.
- Serve as a daily-use research tool for credentialed professionals.

### 2.2 Success Metrics
- Tier usage (Free, Pro, Firm)
- Revenue growth and new user signups
- PDF exports generated
- Churn and refund rate
- Confidence score improvements over time

---

## 3. Target Audience

- **Primary:** Certified Public Accountants (CPAs)
- **Secondary:** Tax attorneys, Enrolled Agents (EAs), firm staff
- **Future:** Bookkeepers, financial planners, tax educators

---

## 4. MVP Scope (Launch v1.0)

### Core Features
- Web-based chat UI (mobile responsive)
- Natural language query interface
- Citation-backed, logic-chain responses
- Confidence scoring (color + numeric)
- PDF memo generation (auto-generated, not manually editable)
- User login (via Supabase or Outseta)
- 3 pricing tiers with tier-based limits
- Timestamped, stored query history with citation versioning

### Supported Memo Types (Initial)
- [Pending user clarification on types] — but will include metadata:
  - Client name
  - Date printed
  - Tax year
  - IRS citations/forms used
  - Question + linked sources

---

## 5. Product Architecture (Pending Final Stack Confirmation)

| Layer        | Tool/Tech           | Purpose                                  |
|--------------|---------------------|------------------------------------------|
| LLM          | GPT-4-turbo (OpenAI)| Reasoning + structured tax output        |
| Embeddings   | `text-embedding-3-small` | IRS source chunking                   |
| Vector DB    | Pinecone            | Semantic retrieval of legal text         |
| Auth         | Supabase / Outseta  | User management                          |
| UI           | WeWeb / Retool      | Low-code interface for dashboard/chat    |
| Backend Logic| n8n                 | Query → Embed → Search → Format → Return|
| Billing      | Stripe + Outseta    | Tiered pricing logic                     |
| PDF Export   | PDFMonkey / Placid  | Memo generation                          |

---

## 6. User Roles & Plans (Preliminary)

| Tier   | Price     | Features                                                    |
|--------|-----------|-------------------------------------------------------------|
| Free   | $0        | 5 queries/day, full IRS source access, view-only citations  |
| Pro    | $59/month | Unlimited queries, export to PDF, query history             |
| Firm   | $279/month| Everything in Pro + client folders, memo generation         |

Admin roles for usage metrics and log review are under consideration.

---

## 7. Fallback Logic for Low Confidence

Taxentia will **not** fall back to “consult a CPA.”  
Instead, fallback behavior will include:
- Summary of what is known
- Confidence score highlighted in red
- Inline note: *“This answer has limited support in primary sources. Proceed with caution.”*

All answers include a logic chain, even if partial.

---

## 8. Security & Logging

- All queries and outputs will be stored (if user is authenticated).
- All citations are timestamped to enable audit trails.
- Versioning of tax sources (e.g., IRC §199A from 2023 vs 2025) is built into metadata.
- No specific compliance frameworks (e.g., SOC 2) are required at this stage.

---

## 9. Analytics

### Internal Admin Analytics
- Most queried IRC sections
- Average confidence score across users
- Query volume per user/client
- Churn rate by tier
- Export frequency

### End-User Access
- Saved memo history
- Ability to download prior exports

---

## 10. Roadmap Alignment

This PRD reflects **Phase 1 (MVP BUILD)** of the official Taxentia Roadmap:
- Vector embedding pipeline using Pinecone
- Functional chat UI with prompt/response loop
- PDF memo output logic
- Live product testing with real CPAs (planned for private beta)

---

## 11. Risks & Open Questions

| Area              | Concern / Risk                                              |
|-------------------|-------------------------------------------------------------|
| Tool Stack        | Final confirmation of WeWeb vs. Vercel + Supabase           |
| Pricing Model     | Validation of $59/$279 pricing with early adopters          |
| LLM Stability     | Hallucination risk must be mitigated via prompt logic       |
| Legal Sensitivity | Outputs may be used in IRS correspondence; audit quality is key |
| Memo Types        | Clarification needed on which memo templates are most desired|

---

## 12. Versioning

- **Current Version:** `0.1`
- This PRD is a living document and will evolve alongside product needs.
- All changes to this document will be tracked in the `taxentia-docs/PRD.md` file with GitHub commit history.

---

## 13. Appendix: Sample Prompt Structure

User Query: “Can my client deduct startup expenses in Year 1?”  
**Response Format:**   
        Summary Answer  
        Step-by-step legal logic  
        Citations with links  
        Confidence score  
        Timestamp  
