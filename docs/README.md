# Taxentia.ai – Smarter Tax Intelligence for Professionals

**Taxentia** is a logic-first, citation-powered AI copilot for CPAs, tax attorneys, and enrolled agents. Built on LLMs, Pinecone, and n8n, it delivers audit-ready responses backed by IRS citations and step-by-step logic chains.

---

## 🔍 What It Does

- Interprets IRS code, Treasury Regs, Pubs, and Court Rulings
- Returns structured answers with citations, confidence scores, and exportable memos
- Helps tax professionals answer questions faster, with legal clarity and audit-trail quality

---

## 💻 Tech Stack

| Layer         | Tool/Platform         |
|---------------|------------------------|
| LLM           | OpenAI GPT-4-turbo     |
| Embeddings    | OpenAI `text-embedding-3-small` |
| Vector DB     | Pinecone               |
| Backend       | n8n                    |
| UI            | WeWeb or Retool        |
| Auth/DB       | Supabase or Outseta    |
| Billing       | Stripe + Outseta       |
| Export        | PDFMonkey or Placid    |

---

## 🚀 Getting Started (MVP)

1. Clone this repo
2. Navigate to `taxentia-core/` and configure API keys
3. Run `n8n` with backend logic
4. Navigate to `taxentia-ui/` to launch frontend (WeWeb/Retool project)
5. Use `taxentia-embeddings/` to run ingestion scripts
6. All product documentation is in `taxentia-docs/`

---

## 📁 Repository Structure

taxentia/  
├── taxentia-core/ # n8n workflows, OpenAI API logic  
├── taxentia-ui/ # Retool/WeWeb UI build  
├── taxentia-embeddings/ # Data preprocessing & embeddings  
├── taxentia-prompts/ # Logic chain prompt templates  
├── taxentia-docs/ # PRD, roadmap, onboarding docs  


---

## 👥 Maintainers

- Bader Ale (Founder)
- Contributors welcome — submit a PR or open an issue
