# 🚀 Quick Start Guide

Get up and running with Atlas Brain in 5 minutes!

---

## Step 1: Clone the Repository

```bash
git clone https://github.com/cryptomax96/atlas-brain.git
cd atlas-brain
```

---

## Step 2: Explore Knowledge Domains

```bash
# Browse by domain
ls claude-code/docs/
ls ai-ml/docs/
ls architecture/docs/
ls journalism/docs/
ls product/docs/

# Search for topics
grep -r "RAG" ai-ml/
grep -r "MCP" claude-code/
```

---

## Step 3: Use with AI Tools

### Reference in Claude Code

```
I'm building an MCP server. Please reference the Atlas Brain knowledge
at /path/to/atlas-brain/claude-code/docs/mcp-servers.md for best practices.
```

### Index in Vector Database

```python
import chromadb
from pathlib import Path

client = chromadb.PersistentClient(path="./atlas_vectors")
collection = client.get_or_create_collection("atlas_brain")

atlas_path = Path("/path/to/atlas-brain")
for md_file in atlas_path.rglob("*.md"):
    if md_file.parent.name == "docs":
        content = md_file.read_text()
        collection.add(
            documents=[content],
            metadatas=[{"domain": md_file.parts[-3]}],
            ids=[str(md_file)]
        )
```

---

## Common Use Cases

### For Developers
- **MCP Servers:** [claude-code/docs/mcp-servers.md](./claude-code/docs/mcp-servers.md)
- **RAG Systems:** [ai-ml/docs/rag-systems.md](./ai-ml/docs/rag-systems.md)

### For Product Managers
- **PRD Template:** [product/templates/prd-template/](./product/templates/prd-template/)

### For Journalists
- **Style Guide:** [journalism/docs/style-guide.md](./journalism/docs/style-guide.md)

---

## Next Steps

1. ✅ Clone the repository
2. ✅ Explore a knowledge domain
3. 🎯 Make your first contribution
4. 🌟 Star the repository

---

<div align="center">

**Welcome to Atlas Brain!** 🧠

</div>
