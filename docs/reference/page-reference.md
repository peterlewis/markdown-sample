---
title: "Page Reference"
description: "Complete reference for page structure and frontmatter"
weight: 31
date: 2025-11-14
tags: ["reference", "pages", "frontmatter"]
---

# Page Reference

Complete technical reference for documentation pages.

## Page Structure

A documentation page consists of:

1. **Frontmatter** (YAML metadata)
2. **Content** (Markdown formatted)

```markdown
---
frontmatter fields here
---

# Page Title

Content here...
```

## Frontmatter Fields

### Required Fields

| Field | Type | Description |
|-------|------|-------------|
| `title` | string | Page title (appears in navigation and page header) |

### Recommended Fields

| Field | Type | Description |
|-------|------|-------------|
| `description` | string | Brief page description (used for SEO and previews) |
| `weight` | integer | Sort order (lower values appear first) |
| `date` | date | Publication date (YYYY-MM-DD format) |

### Optional Fields

| Field | Type | Description |
|-------|------|-------------|
| `tags` | array | List of tags for categorization |
| `categories` | array | List of categories |
| `draft` | boolean | If true, page is hidden in production |
| `author` | string | Author name |
| `toc` | boolean | Enable/disable table of contents |
| `math` | boolean | Enable math rendering (LaTeX) |
| `mermaid` | boolean | Enable Mermaid diagram support |
| `aliases` | array | Alternative URLs that redirect to this page |
| `slug` | string | Custom URL slug |
| `updated` | date | Last updated date |

## Frontmatter Examples

### Minimal Page

```yaml
---
title: "Getting Started"
---
```

### Standard Page

```yaml
---
title: "Installation Guide"
description: "Complete installation instructions"
weight: 10
date: 2025-11-14
---
```

### Full-Featured Page

```yaml
---
title: "Advanced Configuration"
description: "Advanced configuration options and best practices"
weight: 20
date: 2025-11-14
updated: 2025-11-14
author: "Documentation Team"
tags: ["configuration", "advanced", "setup"]
categories: ["guides"]
toc: true
draft: false
aliases:
  - /old-config-url/
  - /legacy-config/
---
```

## Content Formatting

### Headers

Use ATX-style headers (# syntax):

```markdown
# H1 - Page Title
## H2 - Main Sections
### H3 - Subsections
#### H4 - Minor Sections
##### H5 - Rare Use
###### H6 - Rarely Used
```

{{< note type="info" >}}
Only one H1 header per page (usually the page title). Start content with H2.
{{< /note >}}

### Text Emphasis

```markdown
**Bold text**
*Italic text*
***Bold and italic***
~~Strikethrough~~
`Inline code`
```

### Lists

Unordered lists:
```markdown
- Item 1
- Item 2
  - Nested item
  - Another nested item
- Item 3
```

Ordered lists:
```markdown
1. First item
2. Second item
3. Third item
```

Task lists:
```markdown
- [x] Completed task
- [ ] Incomplete task
- [ ] Another task
```

### Links

Internal links (relative):
```markdown
[Link text](/path/to/page/)
[Link with anchor](/path/to/page/#section)
```

External links:
```markdown
[External link](https://example.com)
[Link with title](https://example.com "Link title")
```

### Images

```markdown
![Alt text](/path/to/image.png)
![Alt text](/path/to/image.png "Image title")
```

### Code

Inline code:
```markdown
Use `variable_name` in your code.
```

Code blocks:
````markdown
```language
code here
```
````

With syntax highlighting:
````markdown
```python
def hello():
    print("Hello, World!")
```
````

### Tables

Basic table:
```markdown
| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Cell 1   | Cell 2   | Cell 3   |
| Cell 4   | Cell 5   | Cell 6   |
```

Aligned table:
```markdown
| Left | Center | Right |
|:-----|:------:|------:|
| L    | C      | R     |
```

### Blockquotes

```markdown
> This is a blockquote.
> It can span multiple lines.
>
> And multiple paragraphs.
```

Nested blockquotes:
```markdown
> Level 1
>> Level 2
>>> Level 3
```

### Horizontal Rules

```markdown
---
***
___
```

## Special Features

### Footnotes

```markdown
Here's a sentence with a footnote[^1].

[^1]: This is the footnote content.
```

### Definition Lists

```markdown
Term 1
: Definition 1

Term 2
: Definition 2a
: Definition 2b
```

### Abbreviations

```markdown
*[HTML]: Hyper Text Markup Language
*[W3C]: World Wide Web Consortium

The HTML specification is maintained by the W3C.
```

## Page Types

### Index Pages

Section index pages use `_index.md`:

```yaml
---
title: "Section Name"
description: "Section overview"
weight: 10
---

# Section Name

Overview of this section...

## Subsections
- [Page 1](/section/page1/)
- [Page 2](/section/page2/)
```

### Regular Content Pages

Standard content pages:

```yaml
---
title: "Page Title"
description: "Page description"
weight: 11
---

# Page Title

Content here...
```

### Landing Pages

Top-level landing page:

```yaml
---
title: "Home"
description: "Documentation home"
weight: 1
---

# Welcome

Welcome to the documentation...
```

## URL Structure

Pages generate URLs based on their location:

```
docs/getting-started/installation.md
→ /getting-started/installation/

docs/guides/_index.md
→ /guides/

docs/_index.md
→ /
```

### Custom URLs

Override with `slug`:

```yaml
---
title: "Page Title"
slug: "custom-url"
---
```

Result: `/section/custom-url/`

### URL Aliases

Redirect old URLs:

```yaml
---
title: "Page Title"
aliases:
  - /old-path/
  - /another-old-path/
---
```

## Best Practices

{{< grid columns="2" >}}

### Do
- Use descriptive titles
- Write clear descriptions
- Set appropriate weights
- Include publication dates
- Use tags consistently

### Don't
- Leave title empty
- Skip descriptions
- Duplicate weights
- Use future dates
- Overuse tags

{{< /grid >}}

## Validation

### Required Elements

Every page must have:
- ✅ Frontmatter delimiters (`---`)
- ✅ `title` field
- ✅ At least one content section

### Recommended Elements

Pages should have:
- 📝 `description` field
- 📝 `weight` for ordering
- 📝 `date` for tracking
- 📝 Proper header hierarchy
- 📝 Internal navigation links

## Common Issues

{{< accordion >}}
{{< accordion-item "Frontmatter not parsing" >}}
Ensure frontmatter:
- Starts on the first line
- Uses three dashes (`---`) not equals (`===`)
- Has proper YAML syntax
- Contains valid field names
{{< /accordion-item >}}

{{< accordion-item "Page not appearing" >}}
Check:
- File is saved as `.md`
- Frontmatter is valid
- `draft: false` (or field not present)
- File is in correct directory
{{< /accordion-item >}}

{{< accordion-item "Wrong page order" >}}
- Verify `weight` values
- Lower weights appear first
- Use consistent increments (10, 20, 30)
{{< /accordion-item >}}
{{< /accordion >}}

## Next Steps

- Review [Shortcode Reference](/reference/shortcode-reference/)
- Check [Configuration Reference](/reference/configuration/)
