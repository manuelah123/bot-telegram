# 📰 Intelligent News Search and Automatic Summarization System using n8n and AI

[🇪🇸 Español](README.md)

## Description

This project implements a chatbot built with **n8n** that searches for recent news through **Telegram**.

Users send a topic (Artificial Intelligence, Technology, Sports, etc.). The workflow retrieves news from **GNews**, summarizes it using **Groq (compound-mini)** and sends the results back through Telegram.

## Architecture

```text
User
 │
Telegram
 │
Telegram Trigger
 │
Edit Fields
 │
HTTP Request (GNews API)
 │
Basic LLM Chain (Groq)
 │
Send Telegram Message
 │
User
```

## Workflow

Add your screenshot to:

```text
docs/flujo-n8n.png
```

## Technologies

- n8n
- Telegram Bot API
- GNews API
- Groq
- ngrok
- JSON

## Requirements

- n8n
- Node.js
- Telegram account
- Telegram Bot (BotFather)
- GNews API Key
- Groq API Key
- ngrok

## Setup

### Run n8n

```bash
n8n
```

Default URL:

```text
http://localhost:5678
```

### Configure ngrok

```bash
ngrok http 5678
```

You'll receive a public URL:

```text
https://xxxx.ngrok-free.app
```

Run n8n with:

**CMD**

```cmd
set WEBHOOK_URL=https://xxxx.ngrok-free.app
n8n
```

**PowerShell**

```powershell
$env:WEBHOOK_URL="https://xxxx.ngrok-free.app"
n8n
```

### Credentials

#### Telegram

Create a **Telegram API** credential using your BotFather Bot Token.

#### GNews

Replace:

```text
YOUR_GNEWS_API_KEY
```

with your API key.

#### Groq

Create a **Groq API** credential and paste your API key.

## Import Workflow

Import:

```text
workflow/telegram-news-bot-workflow.json
```

Assign Telegram and Groq credentials and configure the GNews API key.

## Example

User:

```text
Artificial Intelligence
```

Bot:

```text
📰 OpenAI releases a new AI model

Summary:
...

🔗 https://...
```

## Status

Academic/portfolio project. Credentials must be configured before execution.

## License

MIT
