# RAG
Python Backend. Next js + AI SDK Frontnd

01. Download the ollama server 
02. Then pull this models by running this in CLI
```bash
ollama pull MadhuryaPasan/qwen3-no-thinking:1.7b-q8_0
ollama pull qwen3-embedding:0.6b

```
03. Then start the docker container
```Bash
docker compose up
```
04. If you want to start the project in a dev container
- ctrl+shift+p
- search: >Dev Containers: Reopen in Container
- hit enter and chose the dev container backend or frontend

> All the pdf will be saved on a docker volume named `rag_backend_uploads`. Manage the file using this.