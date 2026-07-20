# AI Minute 🚀

An AI-powered content automation system that discovers trending AI topics, generates educational Instagram carousel posts, creates branded designs, and publishes approved content automatically using **n8n** and **LLMs**.

---

## 📌 Overview

AI Minute automates the end-to-end workflow of creating educational AI content for Instagram. Instead of manually researching topics, writing posts, designing carousels, and scheduling publications, the system uses AI agents and workflow automation to streamline the entire process while keeping a human approval step before publishing.

---

## 🎯 Problem

Creating high-quality educational content requires continuous research, writing, designing, and publishing. This process is time-consuming, repetitive, and difficult to scale.

---

## 💡 Solution

The system automates the complete content creation pipeline by:

- Discovering trending AI topics
- Selecting educational and relevant content
- Avoiding duplicate topics
- Generating Instagram carousel content
- Writing engaging captions
- Creating branded carousel designs using Canva
- Requesting human approval via Telegram
- Publishing approved posts automatically to Instagram

---

## ⚙️ High-Level Workflow

```text
Daily Trigger
      │
      ▼
AI Research
      │
      ▼
Topic Selection
      │
      ▼
Content Generation
      │
      ▼
Caption Generation
      │
      ▼
Telegram Approval
      │
      ▼
Canva Automation
      │
      ▼
Design Approval
      │
      ▼
Publishing Queue
      │
      ▼
Instagram Publishing
```

---

## 🧩 System Components

| Component | Responsibility |
|----------|----------------|
| AI Research Agent | Discover trending AI topics from trusted sources |
| Topic Selection Agent | Select valuable educational topics and prevent duplicates |
| Content Memory | Store published topics in Airtable |
| Content Generation Agent | Generate a 5-slide Instagram carousel |
| Caption Generation Agent | Generate engaging captions with CTA |
| Telegram Approval | Human review before publishing |
| Canva Automation | Generate branded carousel designs |
| Publishing Queue | Schedule and publish approved content |

---

## 🛠️ Tech Stack

| Layer | Technology |
|--------|------------|
| Workflow Automation | n8n |
| AI Models | GPT / Gemini |
| Research | Web Search APIs + RSS |
| Database | Airtable |
| Communication | Telegram Bot API |
| Design | Canva API |
| Publishing | Instagram Graph API |

---

## ✅ MVP Features

- AI topic discovery
- Trend analysis
- Duplicate topic detection
- Educational carousel generation
- Caption generation
- Telegram approval workflow
- Canva design automation
- Instagram scheduling and publishing

---

## 🚀 Future Improvements

- Multi-platform publishing
- AI-generated videos
- Analytics dashboard
- Performance feedback loop
- Personalized content strategy
- Vector database for semantic memory

---

## 📊 Success Metrics

- Reduced manual content creation time
- High approval rate
- Reliable publishing workflow
- Consistent educational content quality
- Diverse and non-duplicated AI topics

---

## 📁 Project Structure

```
AI-Minute/
│
├── workflows/
│   └── n8n workflow
│
├── docs/
│   ├── Design_Document.md
│   └── Tech_Spec.md
│
├── assets/
│
└── README.md
```

---

## 👤 Author

**Tasnim Alshair**

AI Automation Engineer | AI & No-Code Automation Enthusiast

---

## 📄 License

This project is intended for educational and portfolio purposes.
