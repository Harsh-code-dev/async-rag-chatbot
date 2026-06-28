# 🚀 AI Knowledge Assistant (Asynchronous RAG System)

## 📖 Overview

AI Knowledge Assistant is a Retrieval-Augmented Generation (RAG) application that enables users to ask questions about PDF documents using natural language.

The application converts PDF content into vector embeddings, stores them in **Qdrant**, retrieves the most relevant document chunks based on semantic similarity, and generates context-aware answers using the **OpenAI API**.

To improve scalability, query processing is handled asynchronously using **Redis Queue (RQ)** while **FastAPI** exposes REST APIs.

---

## ✨ Features

* 📄 PDF document ingestion
* 🔍 Semantic search using vector embeddings
* 🤖 AI-powered question answering
* ⚡ Asynchronous background processing with Redis Queue (RQ)
* 🌐 FastAPI REST API
* 🐳 Dockerized Qdrant Vector Database
* 📚 Automatic API documentation with Swagger UI

---

## 🛠 Tech Stack

| Category         | Technologies                  |
| ---------------- | ----------------------------- |
| Backend          | Python, FastAPI               |
| AI Framework     | LangChain                     |
| LLM              | OpenAI GPT                    |
| Embeddings       | OpenAI text-embedding-3-large |
| Vector Database  | Qdrant                        |
| Queue System     | Redis Queue (RQ)              |
| Containerization | Docker                        |
| Environment      | Python Virtual Environment    |

---

## 🏗 Architecture

```text
User
   │
   ▼
FastAPI Server
   │
   ▼
Redis Queue (RQ)
   │
   ▼
Background Worker
   │
   ├── Qdrant Vector Database
   └── OpenAI API
```

---

## 📂 Project Structure

```text
rag_queue/
│── client/
│── queues/
│── main.py
│── server.py
│── docker-compose.yml
│── requirements.txt
│── .env.example
│── README.md
```

---

## ⚙️ Installation

### Clone the repository

```bash
git clone https://github.com/Harsh-code-dev/async-rag-chatbot.git
cd async-rag-chatbot
```

### Create a virtual environment

```bash
python -m venv venv
```

### Activate it

Windows

```bash
venv\Scripts\activate
```

### Install dependencies

```bash
pip install -r requirements.txt
```

### Configure environment variables

Create a `.env` file.

```env
OPENAI_API_KEY=your_openai_api_key
```

---

## ▶️ Running the Project

### Start Qdrant

```bash
docker compose up -d
```

### Start the FastAPI server

```bash
python -m rag_queue.main
```

### Start the Redis Queue Worker (Windows)

```bash
rq worker --worker-class rq.worker.SimpleWorker
```

---

## 📚 API Documentation

Once the server is running, open:

```text
http://localhost:8000/docs
```

Swagger UI provides interactive documentation for all available endpoints.

---

## 🔮 Future Improvements

* Multi-document support
* Chat history
* Streaming responses
* User authentication
* Conversation memory
* Cloud deployment

---

## 👨‍💻 Author

**Harsh Kumar**

GitHub: https://github.com/Harsh-code-dev
