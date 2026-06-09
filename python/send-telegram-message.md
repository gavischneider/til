# Send a Telegram Message in Pure Python

**Credentials** — Two env vars are required:

- `TELEGRAM_BOT_TOKEN` — your bot's API token (from @BotFather)
- `TELEGRAM_CHAT_ID` — the ID of the chat/group/channel to post to

In your Terminal app, run:

```bash
export TELEGRAM_BOT_TOKEN=“<your_bot_token>“
export TELEGRAM_CHAT_ID=“<your_chat_id>”
```

**API Endpoint** — Telegram's Bot API uses the following URL: `https://api.telegram.org/bot<TOKEN>/sendMessage`. The token is embedded directly in the path (not a header).

```python
import requests

token = os.environ.get("TELEGRAM_BOT_TOKEN")
chat_id = os.environ.get("TELEGRAM_CHAT_ID")
message = "Hello from Python!"

# Construct the API URL
url = f"https://api.telegram.org/bot<token>/sendMessage"

# Define the payload
payload = {
    "chat_id": chat_id,
    "text": message,
    "parse_mode": "Markdown"  # Optional, allows Markdown formatting
}

# Send the HTTP POST request
response = requests.post(url, json=payload)

# Check if the message was sent successfully
if response.status_code == 200:
    print("Message sent successfully!")
else:
    print(f"Failed to send message. Error: {response.text}")
```

[Telegram Bot API](https://core.telegram.org/bots/api)
