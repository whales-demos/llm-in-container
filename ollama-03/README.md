

```bash
# Download the model
docker compose --profile fetch up
# Build an image with the model inside
docker compose --profile build up
# Use the image
docker compose --profile server up
```


```bash
curl http://localhost:11434/v1/chat/completions \
-H "Content-Type: application/json" \
-d '{
    "model": "deepseek-coder",
    "messages": [
        {
            "role": "system",
            "content": "You are a programming assistant."
        },
        {
            "role": "user",
            "content": "write me an hello world program in GoLang"
        }
    ],
    "stream": false
}' | jq
```

