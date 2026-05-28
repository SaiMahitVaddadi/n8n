# Routing n8n through the local LiteLLM gateway

n8n configures LLM credentials per-node in the UI. There is no global
env var for OpenAI base URL.

1. Start n8n.
2. UI → Credentials → "Create" → **OpenAi**.
3. Fill in:
   - **API Key:** `sk-litemagic-123`
   - **Base URL:** `http://localhost:4000/v1`
4. In any workflow, use the **OpenAI** node (or the **LangChain
   OpenAI Chat Model** sub-node) and select this credential.

The same credential works for the Embeddings node. For Anthropic-style
nodes, point Base URL at `http://localhost:4000` (the gateway exposes
`/v1/messages` for Anthropic-compatible routes).
