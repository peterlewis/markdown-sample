---
title: "Quick Start"
description: "Quick start guide to get up and running"
weight: 12
date: 2025-11-14
tags: ["quickstart", "tutorial"]
---

# Quick Start

Get up and running in 5 minutes!

## Your First Page

Create a new markdown file with frontmatter:

{{< code-block language="markdown" >}}
---
title: "My First Page"
description: "This is my first documentation page"
weight: 1
---

# My First Page

This is the content of my first page.
{{< /code-block >}}

## Using Shortcodes

Shortcodes enhance your documentation with special features:

### Alert Boxes

{{< note type="info" >}}
This is an informational note.
{{< /note >}}

{{< note type="warning" >}}
This is a warning message.
{{< /note >}}

{{< note type="danger" >}}
This is a danger alert.
{{< /note >}}

### Code Highlighting

```python
def hello_world():
    print("Hello, World!")
    
hello_world()
```

```javascript
function helloWorld() {
    console.log("Hello, World!");
}

helloWorld();
```

### Tables

| Feature | Description | Status |
|---------|-------------|--------|
| Pages | Markdown pages with frontmatter | ✅ |
| Shortcodes | Reusable content components | ✅ |
| Navigation | Hierarchical menu structure | ✅ |

## Interactive Elements

{{< button href="/guides/" >}}
Explore Guides
{{< /button >}}

{{< video src="https://example.com/demo.mp4" >}}

## What's Next?

{{< cards >}}
{{< card title="Guides" icon="book" link="/guides/" >}}
Learn how to create different types of content
{{< /card >}}

{{< card title="Reference" icon="code" link="/reference/" >}}
Explore the technical reference documentation
{{< /card >}}

{{< card title="Examples" icon="lightbulb" link="/examples/" >}}
See real-world examples
{{< /card >}}
{{< /cards >}}
