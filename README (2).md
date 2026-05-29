# BIT Updates — BITS AI Agent System
## Google Cloud Rapid Agent Hackathon · MongoDB MCP Track

> An agentic AI ticket management system for BIT Wardha campus.  
> Powered by **Gemini 2.0 Flash** + **MongoDB Atlas Data API** + **Firebase RTDB**

---

## 🚀 One-Tap Deploy (Netlify or Vercel)

### Netlify
1. Drag-and-drop this entire folder to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Done ✅

### Vercel
1. `npx vercel --prod` in this folder
2. Done ✅

---

## 🔑 API Keys Setup (edit `index.html` lines ~4100)

Find the `BITS_CONFIG` object and fill in:

```js
const BITS_CONFIG = {
  // 1. Gemini — https://aistudio.google.com/app/apikey
  GEMINI_API_KEY: 'YOUR_GEMINI_KEY',

  // 2. MongoDB Atlas Data API (HTTP REST — no driver needed)
  //    Atlas → Project → App Services → Data API → Enable
  //    Copy the App URL and create an API Key
  MONGODB_DATA_API_URL: 'https://data.mongodb-api.com/app/YOUR_APP_ID/endpoint/data/v1',
  MONGODB_API_KEY: 'YOUR_ATLAS_DATA_API_KEY',
  MONGODB_DB: 'bitupdates',
  MONGODB_CLUSTER: 'Cluster0',  // your cluster name
};
```

The Firebase config is already pre-configured for BIT Wardha.

---

## 🤖 AI Agent Pipeline

```
User Input
    │
    ▼
🧠 Orchestrator (Gemini 2.0 Flash)
    │  Intent: new_complaint / chat / analytics / status
    │
    ├──────────────────────────────────────┐
    ▼                                      ▼
🔍 Triage Agent              💬 Sentiment Agent
  (category, escalation,       (urgency score,
   resolution ETA, tags)        priority P1-P4)
    │                                      │
    └──────────────┬───────────────────────┘
                   ▼
              🗺️ Routing Agent
              (department assignment,
               SLA hours, HOD escalation)
                   │
                   ▼
              🍃 MongoDB Agent
              (HTTP Data API — stores
               AI enrichments serverlessly)
                   │
                   ▼
              🤖 Chatbot Agent (RAG)
              (Gemini + MongoDB context
               + Campus FAQ)
```

---

## 🏆 Hackathon Criteria Met

| Criterion | How |
|---|---|
| **Move Beyond Chat** | Full pipeline: classify → triage → sentiment → route → store → notify |
| **Multi-Step Mission** | 5-agent pipeline runs automatically on ticket submit |
| **Partner Power (MongoDB)** | Atlas Data API (HTTP MCP) stores every AI enrichment in real-time |
| **Gemini Brain** | All agents use `gemini-2.0-flash` for classification, analysis, RAG |
| **One-Tap Deploy** | Pure HTML/CSS/JS — drag to Netlify or `vercel --prod` |

---

## 📁 Files

```
index.html      ← The entire app (Firebase RTDB + BITS AI agents)
vercel.json     ← Vercel deploy config
netlify.toml    ← Netlify deploy config  
README.md       ← This file
```

---

MIT License · Built for Google Cloud Rapid Agent Hackathon · MongoDB Track
