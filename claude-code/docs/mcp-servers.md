---
title: "Building MCP Servers: Complete Guide"
domain: claude-code
tags: [mcp, server, fastmcp, python, tools, resources]
difficulty: intermediate
last_updated: 2025-01-01
contributors: [qawasmi]
version: 1.0.0
sources:
  - name: "Model Context Protocol Specification"
    url: "https://modelcontextprotocol.io"
    type: documentation
    accessed: 2025-01-01
  - name: "FastMCP GitHub Repository"
    url: "https://github.com/jlowin/fastmcp"
    type: documentation
    accessed: 2025-01-01
---

# Building MCP Servers: Complete Guide

## Overview

The **Model Context Protocol (MCP)** enables seamless communication between AI applications (like Claude Code) and external tools, data sources, and services. This guide covers everything you need to build production-ready MCP servers using **FastMCP**.

**Key Takeaways:**
- MCP servers expose tools, resources, and prompts to AI applications
- FastMCP 0.4+ provides a clean, decorator-based API
- Production servers require proper error handling, logging, and monitoring
- Type safety with Pydantic ensures robust tool interfaces

---

## Prerequisites

- Python 3.11+ basics
- Async/await patterns in Python
- Basic understanding of APIs and JSON

---

## Core Concepts

### What is an MCP Server?

An MCP server is a service that exposes capabilities to AI applications:

1. **Tools**: Functions the AI can call to perform actions
2. **Resources**: Data sources the AI can read from
3. **Prompts**: Pre-defined prompt templates

### Tools vs Resources

| Aspect | Tools | Resources |
|--------|-------|----------|
| **Purpose** | Perform actions | Provide data |
| **Direction** | AI calls server | AI reads from server |
| **Examples** | Create file, send email | Read docs, query DB |
| **State Change** | May modify state | Read-only |

---

## Implementation

### Step 1: Install FastMCP

```bash
uv pip install "fastmcp>=0.4.0"
```

### Step 2: Create Basic Server

```python
from fastmcp import FastMCP

mcp = FastMCP("My First MCP Server")

@mcp.tool()
async def greet(name: str) -> str:
    """Greet someone by name"""
    return f"Hello, {name}!"

if __name__ == "__main__":
    mcp.run()
```

### Step 3: Add Resources

```python
@mcp.resource("docs://{topic}")
async def get_documentation(topic: str) -> str:
    """Get documentation for a specific topic"""
    docs = {
        "python": "Python is a high-level programming language...",
        "mcp": "Model Context Protocol enables...",
    }
    return docs.get(topic, "Documentation not found")
```

---

## Best Practices

### ✅ Do

- **Use type hints**: Enable better tooling and validation
- **Write descriptive docstrings**: AI uses these to understand tools
- **Handle errors gracefully**: Return user-friendly error messages
- **Validate inputs**: Use Pydantic models for complex inputs

### ❌ Don't

- **Block the event loop**: Use async for I/O operations
- **Expose secrets**: Never return credentials or API keys
- **Skip validation**: Always validate user inputs

---

## Common Pitfalls

### Pitfall 1: Blocking the Event Loop

**Problem:** Using synchronous I/O in async functions

```python
# ❌ Wrong
@mcp.tool()
async def fetch_data(url: str) -> str:
    import requests
    response = requests.get(url)  # Synchronous!
    return response.text
```

**Solution:** Use async HTTP clients

```python
# ✅ Correct
import httpx

@mcp.tool()
async def fetch_data(url: str) -> str:
    async with httpx.AsyncClient() as client:
        response = await client.get(url)
        return response.text
```

---

## Further Reading

- [FastMCP Documentation](https://github.com/jlowin/fastmcp)
- [MCP Specification](https://modelcontextprotocol.io)

---

**Tags:** #mcp #server #fastmcp #python

**Last Updated:** 2025-01-01
