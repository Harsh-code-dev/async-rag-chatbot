# AI Knowledge Assistant (Asynchronous RAG System)

## Overview

An AI-powered Retrieval-Augmented Generation (RAG) application that answers questions from PDF documents using semantic search and Large Language Models.

The project uses FastAPI for serving APIs, Qdrant as the vector database, Redis Queue (RQ) for background task execution, Docker for containerization, and OpenAI embeddings for semantic retrieval.

---

## Features

* PDF-based question answering
* Semantic search using vector embeddings
* FastAPI REST APIs
* Background task processing using Redis Queue (RQ)
* Qdrant vector database
* Dockerized services
* OpenAI embeddings and LLM integration

---

## Tech Stack

* Python
* FastAPI
* LangChain
* OpenAI API
* Qdrant
* Redis
* RQ (Redis Queue)
* Docker

---

## Project Structure

```
rag_queue/
│── client/
│── queues/
│── main.py
│── server.py
│── docker-compose.yml
│── requirements.txt
│── .env.example
```

---

## Installation

Clone the repository

```bash
git clone <repository-url>
cd rag_queue
```

Create a virtual environment

```bash
python -m venv venv
```

Activate it

Windows

```bash
venv\Scripts\activate
```

Install dependencies

```bash
pip install -r requirements.txt
```

Create a `.env` file

```
OPENAI_API_KEY=your_api_key
```

Start Docker

```bash
docker compose up -d
```

Run the FastAPI server

```bash
python -m rag_queue.main
```

Run the worker

```bash
rq worker --worker-class rq.worker.SimpleWorker
```

---

## API Documentation

After starting the server, visit

```
http://localhost:8000/docs
```

to access the Swagger UI.
