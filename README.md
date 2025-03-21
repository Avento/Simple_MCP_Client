# MCP Simple Chatbot

A simple chatbot implementation using the Model Context Protocol (MCP) to interact with various tools and LLM providers.

## Features

- Connect to MCP servers and list available tools
- Execute MCP tools with retry mechanism
- Interact with LLM providers through OpenAI-compatible API
- Manage server connections and resources
- Process user input and LLM responses

## Requirements

- Python 3.10+
- [Poetry](https://python-poetry.org/) (recommended)
- MCP server configuration

## Installation

1. Clone the repository:
```bash
git clone https://github.com/your-repo/mcp-simple-chatbot.git
cd mcp-simple-chatbot
```

2. Create and activate virtual environment using uv:
```bash
uv venv .venv
# On Windows:
.\.venv\Scripts\activate
# On macOS/Linux:
source .venv/bin/activate
```

3. Install dependencies:
```bash
uv pip install -r requirements.txt
```

4. Copy example configuration files:
```bash
cp .env.example .env
cp servers_config.json.example servers_config.json
```

## Configuration

1. Edit `.env` file with your LLM provider credentials:

For OpenAI:
```
LLM_API_KEY=your-openai-api-key
LLM_BASE_URL=https://api.openai.com/v1
LLM_MODEL_ID=gpt-4
```

For Deepseek:
```
LLM_API_KEY=your-deepseek-api-key
LLM_BASE_URL=https://api.deepseek.com/v1
LLM_MODEL_ID=deepseek-chat
```

2. Configure MCP servers in `servers_config.json`:
```json
{
  "mcpServers": {
    "server-name": {
      "command": "npx",
      "args": ["@modelcontextprotocol/server-name"],
      "env": {
        "API_KEY": "your-server-api-key"
      }
    }
  }
}
```

## Usage

1. Activate virtual environment:
```bash
# On Windows:
.\.venv\Scripts\activate
# On macOS/Linux:
source .venv/bin/activate
```

2. Run the chatbot:
```bash
python main.py
```

Available commands:
- Type your message to chat
- Type 'quit' or 'exit' to end the session

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

Distributed under the MIT License. See `LICENSE` for more information.
