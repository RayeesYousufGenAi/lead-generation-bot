# AI Lead Generation Bot 🤖

**Capture, Qualify, and Convert Leads Automatically 24/7**

[![n8n](https://img.shields.io/badge/n8n-Workflow-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)](https://n8n.io/)
[![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)]()
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)

---

## 📋 Overview

The **AI Lead Generation Bot** is a powerful automation system designed to handle inbound leads from multiple channels (WhatsApp, Web, Email). It uses AI to engage visitors, qualify their intent, and sync valid leads to your CRM or Database.

**Dual Mode System:**
- 🟢 **Free Mode**: Uses open-source LLMs (Groq/Ollama) and Free Storage (Google Sheets)
- 🟡 **Pro Mode**: Uses GPT-4o/Claude 3.5 and Enterprise CRMs (HubSpot/Salesforce)

---

## 📊 Architecture

```mermaid
graph TD
    A[Inbound Lead] --> B{Source?}
    B -->|WhatsApp| C[WhatsApp Trigger]
    B -->|Website| D[Webhook / Form]
    
    C & D --> E[AI Agent Router]
    
    E -->|Question| F[Knowledge Base Retrieval]
    E -->|Lead| G[Lead Qualification AI]
    
    G --> H{Budget/Intent?}
    H -->|High Value| I[Notify Sales Team (Slack/Email)]
    H -->|Standard| J[Add to CRM/Sheets]
    
    I & J --> K[Generate Personalized Reply]
    K --> L[Send Response via Channel]
```

---

## ✨ Key Features

### 🎯 Intelligent Automation
- ✅ **Instant Engagement** - Responds to leads within seconds, 24/7.
- ✅ **Natural Conversation** - Uses LLMs to understand context, slang, and intent.
- ✅ **Lead Scoring** - Automatically categorizes leads (Hot, Warm, Cold).
- ✅ **Spam Filtering** - Ignores irrelevant messages or spam bots.

### 💰 Cost-Effective Options
- **100% Free Tier**: Run completely on free credits (Groq + Google Sheets).
- **Scalable Tier**: Switch to Paid APIs (OpenAI) only when you grow.

### 🛠 Integrations (Flexible)
- **Messaging**: WhatsApp Business API, Telegram, Web Chat.
- **AI Brain**: OpenAI (GPT-4), Anthropic (Claude), Groq (Llama 3 - Free).
- **Database**: Google Sheets (Free), Airtable, HubSpot, Salesforce.

---

## 🛠️ Tech Stack & Requirements

### 🟢 Free Mode (Zero Cost)
| Component | Technology | Cost |
|-----------|------------|------|
| **Core** | n8n (Self-Hosted) | Free (Open Source) |
| **AI Model** | **Groq API** (Llama 3 70B) | Free (Currently) |
| **Database** | Google Sheets | Free |
| **Messaging** | WhatsApp Cloud API | First 1K msgs/mo Free |

### 🟡 Pro Mode (Enterprise)
| Component | Technology | Cost |
|-----------|------------|------|
| **Core** | n8n Cloud | Starts @ €20/mo |
| **AI Model** | OpenAI GPT-4o | ~$5/mo (Usage based) |
| **Database** | HubSpot / Airtable | Free/Paid Tiers |
| **Messaging** | Twilio / WABA | ~$0.005/msg |

---

## 🚀 Quick Start Guide

### Option 1: Docker (Recommended)
Fastest way to get the bot running locally or on a VPS.

1. **Clone the repository**
   ```bash
   git clone https://github.com/RayeesYousufGenAi/lead-generation-bot.git
   cd lead-generation-bot
   ```

2. **Configure Environment**
   ```bash
   cp .env.example .env
   # Edit .env with your API Keys (Groq, OpenAI, Google)
   ```

3. **Run with Docker**
   ```bash
   docker-compose up -d
   ```
   Access n8n at `http://localhost:5678`

### Option 2: n8n Import
If you already have n8n running:

1. Download **`workflow.json`** from this repo.
2. Open your n8n dashboard.
3. Click **"Import from File"** (top right).
4. Select the JSON file.
5. Activate the workflow!

---

## ⚙️ Configuration

### 1. Setting up AI (Groq - Free)
1. Go to [console.groq.com](https://console.groq.com).
2. Create a free API Key.
3. In n8n, create a "Groq Cloud" credential.
4. Paste your key.

### 2. Setting up Google Sheets (Database)
1. Create a new Google Sheet with headers:
   `Date`, `Name`, `Phone`, `Email`, `Company`, `Interest`, `Status`
2. Share the sheet with your Service Account email (n8n).
3. Connect the Google Sheets node in the workflow.

---

## 📈 Dashboard Layout

The bot automatically updates a Lead Dashboard:

| Date | Lead Name | Source | Sentiment | Qualification | Revenue Potential |
|------|-----------|--------|-----------|---------------|-------------------|
| 01/02| John Doe | WhatsApp| Interested| Hot Lead 🔥 | $500 - $1k |
| 01/02| Sarah Smith| Web | Curious | Warm Lead 🌤️| Unknown |

---

## 👤 Author

**Rayees Yousuf**
- GitHub: [@RayeesYousufGenAi](https://github.com/RayeesYousufGenAi)
- Email: rayeesyousuf80@gmail.com

---

**Built with ❤️ for automation enthusiasts.**
