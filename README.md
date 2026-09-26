# 💬 Real-Time AI Customer Support System

> A live chat support system where an AI agent instantly resolves customer queries — and smartly escalates to a human when needed.

---

## 🚀 Overview

A production-grade customer support platform that handles real-time chat between users and an AI agent. The LLM auto-resolves Tier-1 queries using a knowledge base. If the AI is not confident, it automatically escalates the chat to a human agent. Every chat event is streamed through Kafka for real-time analytics.

**Real-world use cases:**
- E-commerce support chat (Flipkart, Amazon style)
- Banking customer care
- Telecom & utility helpdesks
- Any product needing 24/7 instant support

---

## 🏗️ Architecture

```
User → Login → Start Chat (WebSocket)
                      ↓
            Spring Boot WebSocket Server
                      ↓
            LLM Agent (Groq API)
            + Knowledge Base (PostgreSQL)
                      ↓
         Confident? → Reply instantly
         Not confident? → Escalate to human agent
                      ↓
         Every message → Kafka Topic
                      ↓
         Kafka Consumer → Analytics Service
                      ↓
         Stats cached in Redis → Analytics API
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Backend | Java 17, Spring Boot 3 |
| Real-time Communication | WebSockets (STOMP) |
| AI / LLM | Groq API (LLaMA 3) |
| Message Streaming | Apache Kafka |
| Session & Cache | Redis |
| Database | PostgreSQL |
| Authentication | Spring Security + JWT |
| Containerization | Docker |
| Deployment | AWS EC2 + Docker Compose |
| CI/CD | GitHub Actions |

---

## ✨ Key Features

- 💬 Real-time bidirectional chat via WebSockets
- 🤖 LLM agent auto-resolves common queries instantly
- 🔁 Smart escalation to human agent when AI confidence is low
- 📊 Real-time analytics — ticket volume, resolution rate, response time
- ⚡ Redis-cached dashboard stats for fast reads
- 📨 Kafka-powered event streaming for every chat message
- 🔐 JWT-based authentication & session management
- 🐳 Fully containerized with Docker

---

## 📊 Analytics Dashboard (API)

| Metric | Description |
|---|---|
| Total Tickets | Total chats initiated today |
| AI Resolved | % handled by AI without human |
| Avg Response Time | Average LLM response time |
| Escalation Rate | % handed over to human agents |

---

## 📁 Project Structure

```
ai-customer-support-system/
├── src/
│   ├── main/java/com/support/
│   │   ├── controller/        # REST + WebSocket controllers
│   │   ├── service/           # Chat, AI agent, analytics logic
│   │   ├── kafka/             # Producers & Consumers
│   │   ├── ai/                # LLM integration & escalation logic
│   │   ├── repository/        # DB layer
│   │   └── config/            # WebSocket, Security, Redis config
├── docker-compose.yml
├── Dockerfile
└── README.md
```

---

## 👨‍💻 Author

**Omkar** 
