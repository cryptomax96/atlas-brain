# 📋 Documentation Templates

Comprehensive templates for contributing knowledge to Atlas Brain.

---

## Knowledge Entry Template

Use this template for all documentation entries in the `docs/` folders.

```markdown
---
title: "Your Document Title"
domain: claude-code | ai-ml | architecture | journalism | product
tags: [tag1, tag2, tag3]
difficulty: beginner | intermediate | advanced
last_updated: YYYY-MM-DD
contributors: [github_username]
version: X.Y.Z
sources:
  - name: "Source Name"
    url: "https://..."
    accessed: YYYY-MM-DD
---

# Your Document Title

## Overview

Brief introduction (2-3 sentences).

**Key Takeaways:**
- Main point 1
- Main point 2
- Main point 3

---

## Prerequisites

- Prerequisite 1
- Prerequisite 2

---

## Core Concepts

### Concept 1

Explanation with code examples.

---

## Best Practices

### ✅ Do
- Best practice 1

### ❌ Don't
- Anti-pattern 1

---

## Common Pitfalls

### Pitfall 1

**Problem:** What goes wrong
**Solution:** How to fix it

---

## Further Reading

- [Resource 1](url)

---

**Tags:** #tag1 #tag2
**Last Updated:** YYYY-MM-DD
```

---

## Metadata Standards

### Required Frontmatter

```yaml
---
title: "Exact Title of Document"
domain: "claude-code"  # Required
tags: [tag1, tag2, tag3]  # 3-7 tags
difficulty: beginner  # beginner|intermediate|advanced
last_updated: 2025-01-01
contributors: [username]
version: 1.0.0
---
```

### Difficulty Levels

**Beginner (⭐)** - No prerequisites, fundamental concepts
**Intermediate (⭐⭐)** - Basic domain knowledge required
**Advanced (⭐⭐⭐)** - Significant expertise required

---

## Code Example Template

```
example-name/
├── README.md
├── requirements.txt
├── .env.example
├── src/
│   └── main.py
└── tests/
    └── test_main.py
```

---

**Last Updated:** 2025-01-01
