# RAG System version 0.1 (Local Ollama Version)

A RAG application for **PDF analysis** using a **Python backend** and a **Next.js + AI SDK frontend**. This version connects to an Ollama server running directly on your host machine for better performance.

## Installation and Setup

### 1. Install Ollama

Download and install the Ollama server on your host machine from the official website.

### 2. Pull Required Models

Run the following commands in your terminal to download the necessary LLM and embedding models:

```bash
ollama pull MadhuryaPasan/qwen3-no-thinking:1.7b-q8_0
ollama pull qwen3-embedding:0.6b

```

### 3. Launch the Application

Start the frontend and backend services using Docker:

```bash
docker compose up -d

```

---

## Development Environment

### Dev Containers (Recommended)

To develop within the environment:

1. Press `Ctrl+Shift+P` in VS Code.
2. Search for `Dev Containers: Reopen in Container`.
3. Select either the **backend** or **frontend** container.

### Storage

* This project currently supports **PDF analysis only**.
* Uploaded PDFs are stored in the Docker volume: `rag_backend_uploads`.