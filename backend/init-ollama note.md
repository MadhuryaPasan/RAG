when the docker container created it need some time to download the ollama model.

so use this to see the progress in the host computer

```bash
docker compose logs init-ollama
```

or check the container directly with docker desktop