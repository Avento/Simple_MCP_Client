# MCP 简单聊天机器人

一个使用模型上下文协议 (MCP) 与各种工具和LLM提供商交互的简单聊天机器人实现。

## 功能

- 连接MCP服务器并列出可用工具
- 使用重试机制执行MCP工具
- 通过OpenAI兼容API与LLM提供商交互
- 管理服务器连接和资源
- 处理用户输入和LLM响应

## 要求

- Python 3.10+
- uv
- MCP服务器配置

## 安装

1. 克隆仓库：
```bash
git clone https://github.com/your-repo/mcp-simple-chatbot.git
cd mcp-simple-chatbot
```

2. 使用uv创建并激活虚拟环境：
```bash
uv venv .venv
# Windows系统：
.\.venv\Scripts\activate
# macOS/Linux系统：
source .venv/bin/activate
```

3. 安装依赖：
```bash
uv pip install -r requirements.txt
```

4. 复制示例配置文件：
```bash
cp .env.example .env
cp servers_config.json.example servers_config.json
```

## 配置

1. 编辑`.env`文件，填写LLM提供商凭证：

对于OpenAI：
```
LLM_API_KEY=your-openai-api-key
LLM_BASE_URL=https://api.openai.com/v1
LLM_MODEL_ID=gpt-4
```

对于Deepseek：
```
LLM_API_KEY=your-deepseek-api-key
LLM_BASE_URL=https://api.deepseek.com/v1
LLM_MODEL_ID=deepseek-chat
```

2. 在`servers_config.json`中配置MCP服务器：
```json
{
  "mcpServers": {
    "server-name": {
      "command": "npx",
      "args": ""
    }
  }
}
```

## 使用

1. 激活虚拟环境：
```bash
# Windows系统：
.\.venv\Scripts\activate
# macOS/Linux系统：
source .venv/bin/activate
```

2. 运行聊天机器人：
```bash
python main.py
```

可用命令：
- 输入消息进行聊天
- 输入'quit'或'exit'结束会话

## 贡献

1. Fork本仓库
2. 创建你的功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交你的更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送分支 (`git push origin feature/AmazingFeature`)
5. 提交Pull Request

## 许可证

基于MIT许可证分发。详见`LICENSE`文件。
