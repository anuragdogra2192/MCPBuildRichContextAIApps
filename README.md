# Building Rich Context AI Apps with Model Context Protocol (MCP)

A comprehensive educational course teaching how to build AI applications using the Model Context Protocol to connect Claude with external tools, resources, and data sources.

## Overview

This repository contains hands-on code examples for each lesson in the MCP course, demonstrating progressive concepts from basic chatbots to production-ready remote servers. The course teaches how to:

- Build MCP servers that expose tools, resources, and prompts
- Create MCP clients that connect to multiple servers
- Integrate Claude API for intelligent tool use
- Deploy MCP servers to production environments

## Course Outline & Lessons

### Foundational Concepts (Video Only)
- **Lesson 1: Why MCP?** - Understanding the value of Model Context Protocol
- **Lesson 2: MCP Architecture** - Core concepts and design patterns

### Hands-On Implementation
- **[ChatbotExample](./ChatbotExample)** - Build a basic MCP chatbot with Claude integration
- **[CreatingAnMCPServer](./CreatingAnMCPServer)** - Create your first MCP server with tools
- **[CreatingAnMCPClient](./CreatingAnMCPClient)** - Build an MCP client connecting to servers
- **[ConnectingTheMCPChatbotToReferenceServers](./ConnectingTheMCPChatbotToReferenceServers)** - Add resources and context to servers
- **[AddingPromptAndResourceFeatures](./AddingPromptAndResourceFeatures)** - Implement prompts and advanced features
- **[CreatingAndDeployingRemoteServers](./CreatingAndDeployingRemoteServers)** - Deploy MCP servers with SSE transport

### Advanced Topics (Video Only)
- **Lesson 8: Configuring Servers for Claude Desktop** - Desktop app integration
- **Lesson 10: MCP Roadmap & Conclusion** - Future directions and best practices

## Quick Start

### Prerequisites
- Python 3.10+
- [uv](https://github.com/astral-sh/uv) - Fast Python package manager
- Anthropic API key (set as `ANTHROPIC_API_KEY` environment variable)

### Installation

```bash
# Install dependencies
pip install -r requirements.txt

# Or using uv
uv pip install -r requirements.txt
```

### Running a Lesson

Each lesson directory contains an `mcp_project` folder with runnable code:

```bash
cd ChatbotExample/mcp_project
uv run mcp_chatbot.py
```

## Project Structure

```
MCPBuildRichContextAIApps/
├── ChatbotExample/                          # Lesson 3: Basic chatbot example
│   ├── chatbot_example.ipynb               # Jupyter notebook with explanations
│   └── mcp_project/                        # Runnable Python code
│       ├── mcp_chatbot.py                  # MCP client implementation
│       ├── server_config.json              # Server configuration
│       └── pyproject.toml                  # Project dependencies
│
├── CreatingAnMCPServer/                    # Lesson 4: Building MCP servers
│   ├── creating_an_mcp_server.ipynb
│   └── mcp_project/
│       ├── research_server.py              # FastMCP server with tools
│       └── ...
│
├── CreatingAnMCPClient/                    # Lesson 5: Building MCP clients
│   ├── creating_an_mcp_client.ipynb
│   └── mcp_project/
│       ├── mcp_chatbot.py                  # Client with tool use loop
│       └── ...
│
├── ConnectingTheMCPChatbotToReferenceServers/  # Lesson 6: Adding resources
├── AddingPromptAndResourceFeatures/            # Lesson 7: Prompts & features
├── CreatingAndDeployingRemoteServers/          # Lesson 9: Remote deployment
│
├── CLAUDE.md                                # Development guide for Claude Code
├── requirements.txt                         # Root-level dependencies
└── readme.md                                # This file
```

## Key Technologies

- **MCP (Model Context Protocol)**: Standardized protocol for AI-tool integration
- **FastMCP**: High-level Python library for building MCP servers
- **Anthropic SDK**: Claude API integration
- **asyncio**: Async/await patterns for concurrent operations
- **arXiv API**: Research paper search (used in examples)
- **Docker**: Containerization for deployment

## Core Concepts

### MCP Servers
Expose capabilities through:
- **Tools** (`@mcp.tool()`): Functions Claude can call
- **Resources** (`@mcp.resource()`): Data/context Claude can read
- **Prompts** (`@mcp.prompt()`): Templates Claude can use

### MCP Clients
- Connect to servers via stdio, SSE, or streamable-http transports
- Discover available tools and resources
- Implement tool use loop with Claude API

### Tool Use Loop
1. Send query to Claude with available tools
2. Claude returns tool_use content block
3. Call tool via MCP client
4. Send result back to Claude
5. Repeat until Claude returns only text

## Dependencies

```
anthropic>=0.51.0        # Claude API
mcp>=1.7.1              # Model Context Protocol
arxiv>=2.2.0            # Research paper search
pypdf2>=3.0.1           # PDF parsing
python-dotenv>=1.1.0    # Environment variables
uv                      # Package manager
```

## Environment Setup

Create a `.env` file in any lesson's `mcp_project` directory:

```bash
ANTHROPIC_API_KEY=your_key_here
```

## Testing & Debugging

### Using MCP Inspector
Test servers interactively:
```bash
npx @modelcontextprotocol/inspector
```

### Running Individual Lessons
Each lesson can be run independently. Start with `ChatbotExample` to understand the fundamentals.

## Learning Path

1. **Start with ChatbotExample** - Understand chatbot basics and MCP concepts
2. **Progress through CreatingAnMCPServer** - Learn to build servers
3. **Implement CreatingAnMCPClient** - Understand client connection patterns
4. **Add ConnectingTheMCPChatbotToReferenceServers** - Work with resources
5. **Enhance with AddingPromptAndResourceFeatures** - Advanced features
6. **Deploy CreatingAndDeployingRemoteServers** - Production readiness

## Resources & References

- [Model Context Protocol Documentation](https://modelcontextprotocol.io/)
- [Anthropic API Documentation](https://docs.anthropic.com/)
- [FastMCP GitHub Repository](https://github.com/modelcontextprotocol/python-sdk)
- [MCP Inspector Tool](https://modelcontextprotocol.io/docs/tools/inspector)

## Notes

- Each lesson builds on concepts from previous lessons
- Code examples demonstrate progressive complexity
- Notebooks provide detailed explanations alongside code
- Jupyter notebooks can be run interactively for learning

## Contact 
**Anurag Dogra**

[My accomplishment Link](https://www.deeplearning.ai/accomplishments/6b1f5369-932a-447a-a5f8-44b3480823bd?_gl=1*13ajx92*_gcl_au*NzY0NzQ5MTQ4LjE3ODMwMDcyNjk.*_ga*MjAwMTA1MjU3Ny4xNzgzMDA3MjY5*_ga_FR2MZ1VLMS*czE3ODc2MTYzMDUkbzEyMSRnMSR0MTc4NzYyNDI5NiRqNDckbDAkaDA.&usp=sharing)

anuragdogra2192@gmail.com
