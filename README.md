# MCP Web-Scraped Documentation Server

A fast MCP (Model Context Protocol) server for searching and retrieving documentation from LangChain, LlamaIndex, and OpenAI official sources via a unified API.

## Features
- Unified API for documentation search
- Supports LangChain, LlamaIndex, and OpenAI
- Returns up-to-date documentation snippets
- Asynchronous and efficient

## Supported Libraries
- LangChain: [python.langchain.com/docs](https://python.langchain.com/docs)
- LlamaIndex: [docs.llamaindex.ai/en/stable](https://docs.llamaindex.ai/en/stable)
- OpenAI: [platform.openai.com/docs](https://platform.openai.com/docs)

## Usage
1. Start the server:
   ```bash
   python main.py
   ```
2. Use the `get_docs` tool to query documentation:
   - `query`: Search term (e.g., "Chroma DB")
   - `library`: One of `langchain`, `llama-index`, or `openai`

## Example
```python
result = await get_docs("memory", "langchain")
```

## Environment Variables
- `SERPER_API_KEY`: API key for Google Serper search

## Installation
1. Create a uv virtual environment:
   ```bash
   uv venv .venv
   ```
2. Activate the virtual environment:
   - On Windows:
     ```powershell
     .venv\Scripts\activate
     ```
   - On macOS/Linux:
     ```bash
     source .venv/bin/activate
     ```
3. Install dependencies:
   ```bash
   uv sync
   ```
4. Set up `.env` file with your Serper API key.

## MCP Server Configuration Example

Add the following to your MCP configuration (e.g., mcp.json):

```jsonc
{
   "servers": {
      "documentation": {
         "command": "uv",
         "args": [
            "--directory",
            "D:/projects/mcp/documentation",
            "run",
            "main.py"
         ]
      }
   }
}
```

## License
MIT
