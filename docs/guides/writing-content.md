---
title: "Writing Content"
description: "Guide to writing effective documentation content"
weight: 21
date: 2025-11-14
tags: ["writing", "content", "markdown"]
---

# Writing Content

Learn how to write effective documentation using markdown.

## Basic Markdown Syntax

### Headers

```markdown
# H1 Header
## H2 Header
### H3 Header
#### H4 Header
```

### Text Formatting

**Bold text** using `**bold**` or `__bold__`

*Italic text* using `*italic*` or `_italic_`

~~Strikethrough~~ using `~~strikethrough~~`

### Lists

Unordered list:
- Item 1
- Item 2
  - Nested item 2.1
  - Nested item 2.2
- Item 3

Ordered list:
1. First item
2. Second item
3. Third item

### Links and Images

[Link text](https://example.com)

![Alt text](https://example.com/image.png)

### Blockquotes

> This is a blockquote.
> It can span multiple lines.

## Advanced Formatting

### Code Blocks

Inline code: `const x = 10;`

Fenced code blocks with syntax highlighting:

```python
def calculate_fibonacci(n):
    if n <= 1:
        return n
    return calculate_fibonacci(n-1) + calculate_fibonacci(n-2)

print(calculate_fibonacci(10))
```

### Tables

| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Data 1   | Data 2   | Data 3   |
| Data 4   | Data 5   | Data 6   |

Aligned tables:

| Left | Center | Right |
|:-----|:------:|------:|
| L1   | C1     | R1    |
| L2   | C2     | R2    |

## Best Practices

{{< tip >}}
Keep paragraphs short and focused. Aim for 2-4 sentences per paragraph.
{{< /tip >}}

### Writing Tips

1. **Be Clear and Concise**: Use simple language and avoid jargon
2. **Use Active Voice**: "Click the button" instead of "The button should be clicked"
3. **Add Examples**: Show practical examples for complex concepts
4. **Structure Content**: Use headers to organize information hierarchically

{{< note type="warning" >}}
Always proofread your content before publishing. Check for spelling, grammar, and formatting errors.
{{< /note >}}

### Content Organization

- Start with an overview
- Break content into logical sections
- Use meaningful headers
- Include code examples where relevant
- Add visual aids when helpful

## Using Frontmatter

Every page should have frontmatter:

```yaml
---
title: "Page Title"
description: "Brief description of the page"
weight: 10
date: 2025-11-14
tags: ["tag1", "tag2"]
categories: ["category1"]
---
```

### Frontmatter Fields

| Field | Description | Required |
|-------|-------------|----------|
| `title` | Page title | Yes |
| `description` | SEO description | Recommended |
| `weight` | Sort order | Optional |
| `date` | Publication date | Optional |
| `tags` | Content tags | Optional |
| `categories` | Categories | Optional |

## Next Steps

- Learn about [Using Shortcodes](/guides/shortcodes/)
- Explore [Page Organization](/guides/page-organization/)
