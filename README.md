# 🎯 Lead Sniper AI: Autonomous Prospecting Engine
Lead Sniper AI is an autonomous prospecting engine designed to identify business opportunities in real time within tech communities. It uses an AI-powered semantic analysis approach to detect technical “pain points” and generate immediate value propositions.

# 🚀 Overview
Unlike traditional keyword-based scrapers, this workflow orchestrated in n8n uses large-scale language models (LLMs) to understand the intent and urgency behind each post on forums like Hacker News or Reddit.

The system monitors RSS feeds, processes the information through Groq (Llama 3) for low-latency inference, and delivers qualified leads directly to a Telegram bot with a personalized pitch ready to be sent.

# ✨ Key Features
- Multi-Channel Monitoring: Integration with RSS feeds from high-signal communities (Hacker News, Reddit, etc.).
- AI Brain (Groq + Llama 3): Deep text analysis to filter out noise and detect real needs for infrastructure, automation, or development.
- Dynamic Lead Scoring: Automatic classification by urgency level (1-10) and summary of the main issue.
- Contextual Pitch Generation: Automatic drafting of contact messages tailored to the company’s tone and style.
- Microservices Architecture: Deployed via Docker to ensure portability and scalability.

🛠️ Technical Stack
- Orchestrator: n8n.
- AI Engine: Groq API (Llama 3-70b).
- Notifications: Telegram Bot API.
- Infrastructure: Docker & Docker Compose.
- Development Hardware: Dell Latitude 7400.

📦 Installation and Deployment
- Prerequisites
- Docker and Docker Compose installed.
- Groq API Keys and Telegram Bot Token.

Execution with Docker Bash

```
  docker run -d \
  --name n8n_sniper \
  -p 5678:5678 \
  -v n8n_data:/home/node/.n8n \
  docker.n8n.io/n8nio/n8n
```

# 🧠 Workflow Logic
- Trigger: RSS node checks for new entries every 15 minutes.
- Brain: The AI node evaluates the content. If the is_lead parameter is true, the workflow continues.
- Filter: A conditional node validates the LLM's response.
- Action: Sends an enriched notification to Telegram.

--- 
Developed with a problem-solving mindset by Angel Leonardo Vera Soto.
Systems and Software Engineer
