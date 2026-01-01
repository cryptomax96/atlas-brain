# 🤖 AI/ML Knowledge Domain

<div align="center">

![AI/ML](https://img.shields.io/badge/AI%2FML-Engineering-4ECDC4?style=for-the-badge)
![RAG](https://img.shields.io/badge/RAG-Systems-blue?style=for-the-badge)
![Vector](https://img.shields.io/badge/Vector-Databases-green?style=for-the-badge)

**Advanced AI/ML engineering techniques for production systems**

</div>

---

## 📖 Overview

This domain contains cutting-edge knowledge for building production-grade AI/ML systems, with a focus on **RAG**, **vector databases**, **embeddings**, and **agent frameworks**.

### What You'll Learn

- **RAG Systems** - Architecture, chunking strategies, retrieval optimization
- **Vector Databases** - ChromaDB, Pinecone, Qdrant, Weaviate
- **Embeddings** - OpenAI, Voyage, Cohere, custom models
- **Agent Frameworks** - LangChain, CrewAI, AutoGen
- **LLM Optimization** - Fine-tuning, prompt caching, context management

---

## 📁 Structure

```
ai-ml/
├── docs/
│   ├── rag-systems.md
│   ├── vector-databases.md
│   └── embeddings.md
├── examples/
│   ├── basic-rag/
│   └── chromadb-rag/
└── templates/
    └── rag-pipeline/
```

---

## 💻 Quick Example

### Basic RAG with ChromaDB

```python
import chromadb

client = chromadb.PersistentClient(path="./chroma_db")
collection = client.get_or_create_collection("knowledge_base")

# Add documents
collection.add(
    documents=["RAG systems combine retrieval with generation."],
    ids=["doc_1"]
)

# Query
results = collection.query(
    query_texts=["What are RAG systems?"],
    n_results=3
)
```

---

## 🎯 Best Practices

✅ **Do:**
- Chunk documents based on semantic boundaries
- Use hybrid search (vector + keyword)
- Implement reranking for better accuracy
- Cache embeddings to reduce costs

❌ **Don't:**
- Use fixed-size chunks without overlap
- Rely solely on vector similarity
- Skip evaluation and testing

---

## 🚀 Quick Links

- [← Back to Atlas Brain](../)
- [ChromaDB Docs](https://docs.trychroma.com)
- [LangChain Docs](https://python.langchain.com)

---

<div align="center">

**Build intelligent systems!** 🤖

*Last updated: 2025-01-01*

</div>
