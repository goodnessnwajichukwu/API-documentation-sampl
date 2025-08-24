# 🦙 Meta Llama API Documentation

Welcome to the **Meta Llama API**.  
The Llama API allows developers to integrate Meta’s state-of-the-art large language models (LLMs) into their applications with just a few lines of code.  

This documentation provides all the details you need to get started, authenticate, and make requests.

---

## 📖 Table of Contents
1. [Introduction](#introduction)
2. [Base URL](#base-url)
3. [Authentication](#authentication)
4. [Quick Start](#quick-start)
5. [Endpoints](#endpoints)
   - [Generate Text](#generate-text)
   - [Chat Completion](#chat-completion)
   - [Embeddings](#embeddings)
6. [Error Handling](#error-handling)
7. [Rate Limits](#rate-limits)
8. [Examples](#examples)
9. [Support](#support)

---

## 🔹 Introduction

The Llama API gives developers access to the **Llama 3 models** for:
- Natural language understanding
- Content generation
- Conversational AI
- Text embeddings

It is designed for simplicity:
- **RESTful JSON API**
- Authentication via **Bearer token**
- SDKs for Python, Node.js, and Java coming soon

---

## 🌐 Base URL

All API requests are made to:

https://api.meta.ai/llama/v1/

---

## 🔑 Authentication

Requests require an API key.  
You can obtain your key from the **Meta Developer Dashboard**.

Include it in the `Authorization` header:

Authorization: Bearer YOUR_API_KEY

---

## ⚡ Quick Start

Example request using `curl`:

```bash
curl -X POST "https://api.meta.ai/llama/v1/generate" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
        "model": "llama-3-70b",
        "prompt": "Explain technical writing in one sentence.",
        "max_tokens": 50
      }'


---

📌 Endpoints

1. Generate Text

POST /generate

Generate text from a given prompt.

Request Body

Field	Type	Required	Description

model	string	✅	Model name (e.g., llama-3-70b)
prompt	string	✅	Input text prompt
max_tokens	integer	❌	Maximum tokens in response
temperature	float	❌	Controls randomness (0.0 – 1.0)


Response Example

{
  "id": "gen-12345",
  "object": "text_completion",
  "model": "llama-3-70b",
  "created": 1713897600,
  "choices": [
    {
      "text": "Technical writing is the practice of explaining complex ideas clearly and concisely."
    }
  ]
}


---

2. Chat Completion

POST /chat/completions

Engage in multi-turn conversations with the Llama model.

Request Body

{
  "model": "llama-3-70b-chat",
  "messages": [
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user", "content": "What is API documentation?"}
  ]
}

Response Example

{
  "id": "chat-67890",
  "object": "chat.completion",
  "choices": [
    {
      "message": {
        "role": "assistant",
        "content": "API documentation is a guide that explains how to use an API, including endpoints, parameters, and examples."
      }
    }
  ]
}


---

3. Embeddings

POST /embeddings

Generate vector embeddings for semantic search or clustering.

Request Body

{
  "model": "llama-3-embed",
  "input": "Technical writing improves developer experience."
}

Response Example

{
  "data": [
    {
      "embedding": [0.0123, -0.9876, 0.4567, ...]
    }
  ]
}


---

❗ Error Handling

The API uses standard HTTP response codes:

Code	Meaning

200	Success
400	Bad Request (check parameters)
401	Unauthorized (invalid or missing API key)
429	Too Many Requests (rate limit exceeded)
500	Server Error



---

📊 Rate Limits

Free tier: 60 requests per minute

Pro tier: 600 requests per minute

Enterprise: Custom limits available



---

🧪 Examples

Python Example

import requests

url = "https://api.meta.ai/llama/v1/generate"
headers = {"Authorization": "Bearer YOUR_API_KEY"}
data = {
    "model": "llama-3-70b",
    "prompt": "Write a haiku about APIs.",
    "max_tokens": 30
}

response = requests.post(url, headers=headers, json=data)
print(response.json())

Node.js Example

import fetch from "node-fetch";

const response = await fetch("https://api.meta.ai/llama/v1/generate", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
    "Authorization": "Bearer YOUR_API_KEY"
  },
  body: JSON.stringify({
    model: "llama-3-70b",
    prompt: "Explain the importance of documentation.",
    max_tokens: 50
  })
});

const data = await response.json();
console.log(data);


---

📞 Support

📚 Official Docs

🐛 GitHub Issues

💬 Developer Community (coming soon)



---

Last updated: April 2025
Version: v1.0
