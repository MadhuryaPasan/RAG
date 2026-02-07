# RAG System version 0.1 

A fully containerized RAG application built with a **Python backend** and a **Next.js frontend** using the AI SDK. This system is designed specifically to analyze **PDF documents**.

* Backend: Python, Fastapi, Langchain
* Frontend: NextJs, Vercel AI SDK 6

## Getting Started

### 1. Close Host Ollama

Ensure any Ollama server running on your host machine is shut down to prevent port conflicts.

### 2. Start the Containers

Run the following command to start the services:

```bash
docker compose up -d

```

### 3. Track Model Progress

Models may take time to download. To check the progress:

* Open **Docker Desktop**.
* Click on the `init-ollama` container.
* Check the **Logs** for the download status.

> **Note:** If performance is slow, consider using the [`using-host-device-ollama-server`](https://github.com/MadhuryaPasan/RAG/tree/using-host-device-ollama-server) repository instead.

---

## Development and Storage

### Dev Containers (Recommended)

To work within the environment:

1. Press `Ctrl+Shift+P`.
2. Select `Dev Containers: Reopen in Container`.
3. Choose either the **backend** or **frontend** container.

### PDF Management

The system only supports PDF analysis. All uploaded files are stored in a Docker volume named `rag_backend_uploads`.
