---
title: "Page Organization"
description: "How to organize your documentation pages effectively"
weight: 23
date: 2025-11-14
tags: ["organization", "structure", "navigation"]
---

# Page Organization

Learn how to organize your documentation for optimal user experience.

## Directory Structure

A well-organized documentation follows a hierarchical structure:

```
docs/
├── _index.md                 # Home page
├── getting-started/
│   ├── _index.md            # Section index
│   ├── installation.md
│   └── quick-start.md
├── guides/
│   ├── _index.md
│   ├── writing-content.md
│   └── shortcodes.md
├── reference/
│   ├── _index.md
│   ├── api.md
│   └── configuration.md
└── examples/
    ├── _index.md
    └── use-cases.md
```

## Naming Conventions

### File Names

Use descriptive, lowercase file names with hyphens:

{{< grid columns="2" >}}

**Good:**
- `installation.md`
- `quick-start.md`
- `api-reference.md`

**Avoid:**
- `Installation.md`
- `quick_start.md`
- `APIReference.md`

{{< /grid >}}

### Section Indexes

Use `_index.md` for section landing pages:

```yaml
---
title: "Section Name"
description: "Section description"
weight: 10
---
```

## Page Weight/Order

Use the `weight` field in frontmatter to control page order:

```yaml
---
title: "First Page"
weight: 1
---
```

Lower weights appear first:
- weight: 1 (appears first)
- weight: 10 (appears second)
- weight: 20 (appears third)

{{< tip >}}
Use increments of 10 (10, 20, 30) to leave room for inserting pages later.
{{< /tip >}}

## Content Hierarchy

### Top Level Sections

Organize content into major sections:

1. **Getting Started**: Introductory content
2. **Guides**: How-to guides and tutorials
3. **Reference**: Technical documentation
4. **Examples**: Practical examples
5. **API**: API documentation (if applicable)
6. **FAQ**: Frequently asked questions

### Sub-sections

Group related content within sections:

```
guides/
├── _index.md
├── basics/
│   ├── _index.md
│   ├── markdown.md
│   └── frontmatter.md
└── advanced/
    ├── _index.md
    ├── shortcodes.md
    └── custom-layouts.md
```

## Navigation Structure

### Breadcrumbs

Pages inherit their position from the directory structure:
```
Home > Guides > Writing Content
```

### Table of Contents

Include a TOC for long pages:

```markdown
## Table of Contents
- [Section 1](#section-1)
- [Section 2](#section-2)
- [Section 3](#section-3)
```

## Cross-References

### Internal Links

Link to other pages using relative paths:

```markdown
[Installation Guide](/getting-started/installation/)
[Quick Start](/getting-started/quick-start/)
```

### Anchor Links

Link to specific sections:

```markdown
[Jump to Best Practices](#best-practices)
```

## Metadata and Frontmatter

### Essential Fields

```yaml
---
title: "Page Title"           # Required
description: "Description"    # Recommended for SEO
weight: 10                    # For ordering
date: 2025-11-14             # Publication date
---
```

### Optional Fields

```yaml
---
tags: ["tag1", "tag2"]       # Categorization
categories: ["category"]      # Grouping
draft: false                 # Visibility
author: "Author Name"        # Attribution
toc: true                    # Table of contents
---
```

## Content Types

### Landing Pages

Section index pages (`_index.md`) should:
- Provide overview of the section
- List subsections
- Include quick links
- Set the context

Example:
```markdown
---
title: "Guides"
---

# Guides

This section contains comprehensive guides.

## Available Guides
- [Writing Content](/guides/writing-content/)
- [Using Shortcodes](/guides/shortcodes/)
```

### Content Pages

Individual content pages should:
- Have clear, descriptive titles
- Start with an introduction
- Use headers for structure
- Include examples
- Link to related content

## Best Practices

{{< note type="info" >}}
**Organization Principles:**
1. Keep related content together
2. Use consistent naming
3. Maintain a logical hierarchy
4. Make navigation intuitive
{{< /note >}}

### Do's

- ✅ Use clear, descriptive names
- ✅ Group related content
- ✅ Maintain consistent structure
- ✅ Include index pages for sections
- ✅ Use frontmatter consistently

### Don'ts

- ❌ Create deeply nested hierarchies (max 3-4 levels)
- ❌ Use inconsistent naming conventions
- ❌ Skip section index pages
- ❌ Create orphaned pages
- ❌ Forget to set page weight for ordering

## Search Optimization

### Improve Discoverability

1. Use descriptive titles
2. Write clear descriptions
3. Add relevant tags
4. Include keywords naturally
5. Create comprehensive content

### Frontmatter for SEO

```yaml
---
title: "Clear, Descriptive Title with Keywords"
description: "Concise description that includes important keywords and summarizes content"
tags: ["keyword1", "keyword2", "keyword3"]
---
```

## Maintenance

### Regular Reviews

- Review structure quarterly
- Update outdated content
- Fix broken links
- Consolidate redundant pages
- Archive obsolete content

### Version Control

Track changes to documentation:
- Use meaningful commit messages
- Document major restructures
- Maintain changelog
- Tag releases

## Tools and Automation

### Link Checking

Regularly check for broken links:
```bash
# Example using a link checker
find . -name "*.md" -exec markdown-link-check {} \;
```

### Validation

Validate frontmatter and structure:
```bash
# Check for required frontmatter fields
grep -L "^title:" docs/**/*.md
```

## Next Steps

- Review [Examples](/examples/) for practical organization patterns
- Explore [Reference](/reference/) for technical details
