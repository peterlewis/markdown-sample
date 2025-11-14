# Markdown Sample Documentation

A comprehensive sample markdown documentation repository demonstrating pages and shortcodes structure for documentation systems.

## Overview

This repository contains sample markdown documentation that follows best practices for modern documentation systems. It includes examples of:

- **Pages with Frontmatter**: Properly structured markdown files with YAML metadata
- **Shortcodes**: Reusable content components for enhanced documentation
- **Hierarchical Organization**: Logical directory structure for easy navigation
- **Real-World Examples**: Practical examples for different documentation types

## Directory Structure

```
docs/
├── _index.md                           # Home page
├── getting-started/                    # Getting started section
│   ├── _index.md                       # Section overview
│   ├── installation.md                 # Installation guide
│   └── quick-start.md                  # Quick start tutorial
├── guides/                             # Comprehensive guides
│   ├── _index.md                       # Guides overview
│   ├── writing-content.md              # Content writing guide
│   ├── shortcodes.md                   # Shortcode usage guide
│   └── page-organization.md            # Organization best practices
├── reference/                          # Technical reference
│   ├── _index.md                       # Reference overview
│   ├── page-reference.md               # Page structure reference
│   ├── shortcode-reference.md          # Shortcode reference
│   └── configuration.md                # Configuration reference
└── examples/                           # Real-world examples
    ├── _index.md                       # Examples overview
    ├── basic-pages.md                  # Basic page examples
    ├── advanced-shortcodes.md          # Advanced shortcode usage
    └── complete-documentation.md       # Complete documentation examples
```

## Features

### Pages

All pages include:
- **Frontmatter**: YAML metadata with title, description, weight, date, and tags
- **Proper Structure**: Clear hierarchy with headers and sections
- **Cross-References**: Links to related content
- **Examples**: Practical code examples and use cases

### Shortcodes

Examples of common shortcodes:
- `note`: Info, warning, danger, and success alerts
- `tip`: Helpful tips and suggestions
- `tabs`: Tabbed content sections
- `accordion`: Collapsible content
- `cards`: Card layouts
- `button`: Clickable buttons
- `code-block`: Enhanced code blocks
- `grid`: Responsive grid layouts
- `timeline`: Chronological events
- `mermaid`: Diagrams and flowcharts

## Documentation Sections

### Getting Started
Learn the basics of markdown documentation, including installation and quick start guides.

### Guides
Comprehensive guides covering:
- Writing effective content
- Using shortcodes
- Organizing pages

### Reference
Technical reference documentation:
- Page structure and frontmatter fields
- Complete shortcode reference
- Configuration options

### Examples
Real-world examples for:
- Basic pages (tutorials, FAQs, changelogs)
- Advanced shortcode usage
- Complete documentation structures (CLI, API, Library, Product)

## Usage

This repository serves as a reference and template for creating documentation. You can:

1. **Browse**: Explore the structure and examples
2. **Copy**: Use pages as templates for your own documentation
3. **Adapt**: Modify the structure to fit your project's needs
4. **Learn**: Study best practices for documentation writing

## Page Frontmatter

Each page includes frontmatter with metadata:

```yaml
---
title: "Page Title"              # Required: Page title
description: "Page description"  # Recommended: SEO description
weight: 10                       # Optional: Sort order (lower first)
date: 2025-11-14                # Optional: Publication date
tags: ["tag1", "tag2"]          # Optional: Tags for categorization
---
```

## Shortcode Examples

### Note/Alert Box

```markdown
{{< note type="info" >}}
This is an informational note.
{{< /note >}}
```

### Tabbed Content

```markdown
{{< tabs >}}
{{< tab "Tab 1" >}}
Content for tab 1
{{< /tab >}}
{{< tab "Tab 2" >}}
Content for tab 2
{{< /tab >}}
{{< /tabs >}}
```

### Cards

```markdown
{{< cards >}}
{{< card title="Card Title" icon="star" link="/link/" >}}
Card content
{{< /card >}}
{{< /cards >}}
```

## Best Practices

This documentation demonstrates:

- ✅ Clear, hierarchical structure
- ✅ Consistent frontmatter usage
- ✅ Proper use of headers (H1 for title, H2+ for sections)
- ✅ Cross-referencing between pages
- ✅ Code examples with syntax highlighting
- ✅ Shortcodes for enhanced content
- ✅ Responsive and accessible design patterns

## Contributing

Feel free to use this as a template for your own documentation projects. The structure is designed to be flexible and adaptable to different types of documentation needs.

## License

This is a sample documentation repository for reference purposes.