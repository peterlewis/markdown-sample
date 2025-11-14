---
title: "Using Shortcodes"
description: "Comprehensive guide to using shortcodes in your documentation"
weight: 22
date: 2025-11-14
tags: ["shortcodes", "components"]
---

# Using Shortcodes

Shortcodes are reusable components that add enhanced functionality to your markdown documentation.

## What are Shortcodes?

Shortcodes are special snippets that allow you to embed complex HTML or interactive elements without writing raw HTML.

### Basic Syntax

```
{{< shortcode_name >}}
```

With parameters:
```
{{< shortcode_name param1="value1" param2="value2" >}}
```

With content:
```
{{< shortcode_name >}}
Content goes here
{{< /shortcode_name >}}
```

## Common Shortcodes

### Note/Alert Boxes

Display important information with styled alert boxes:

{{< note type="info" >}}
**Info:** This is an informational message.
{{< /note >}}

```
{{< note type="info" >}}
Your informational message here
{{< /note >}}
```

{{< note type="warning" >}}
**Warning:** This is a warning message.
{{< /note >}}

```
{{< note type="warning" >}}
Your warning message here
{{< /note >}}
```

{{< note type="danger" >}}
**Danger:** This is a danger alert.
{{< /note >}}

```
{{< note type="danger" >}}
Your danger message here
{{< /note >}}
```

{{< tip >}}
**Tip:** Use tips to provide helpful suggestions.
{{< /tip >}}

```
{{< tip >}}
Your helpful tip here
{{< /tip >}}
```

### Buttons

Create clickable buttons with custom text and links:

{{< button href="/getting-started/" >}}Get Started{{< /button >}}
{{< button href="/guides/" type="primary" >}}Primary Button{{< /button >}}
{{< button href="/reference/" type="secondary" >}}Secondary Button{{< /button >}}

```
{{< button href="/getting-started/" >}}Get Started{{< /button >}}
{{< button href="/guides/" type="primary" >}}Primary Button{{< /button >}}
```

### Tabs

Organize content in tabbed interfaces:

{{< tabs >}}
{{< tab "JavaScript" >}}
```javascript
console.log("Hello from JavaScript!");
```
{{< /tab >}}
{{< tab "Python" >}}
```python
print("Hello from Python!")
```
{{< /tab >}}
{{< tab "Ruby" >}}
```ruby
puts "Hello from Ruby!"
```
{{< /tab >}}
{{< /tabs >}}

```
{{< tabs >}}
{{< tab "JavaScript" >}}
Your JavaScript content
{{< /tab >}}
{{< tab "Python" >}}
Your Python content
{{< /tab >}}
{{< /tabs >}}
```

### Accordions

Create collapsible content sections:

{{< accordion >}}
{{< accordion-item "What is an accordion?" >}}
An accordion is a collapsible content section that expands when clicked.
{{< /accordion-item >}}

{{< accordion-item "When should I use accordions?" >}}
Use accordions for:
- FAQ sections
- Optional/advanced information
- Long lists of items
- Content that users may want to skip
{{< /accordion-item >}}
{{< /accordion >}}

```
{{< accordion >}}
{{< accordion-item "Question 1" >}}
Answer to question 1
{{< /accordion-item >}}
{{< accordion-item "Question 2" >}}
Answer to question 2
{{< /accordion-item >}}
{{< /accordion >}}
```

### Code Blocks

Enhanced code blocks with features:

{{< code-block language="python" highlight="2,4" >}}
def example():
    # This line is highlighted
    x = 10
    # This line is also highlighted
    return x * 2
{{< /code-block >}}

```
{{< code-block language="python" highlight="2,4" >}}
Your code here
{{< /code-block >}}
```

### Cards

Display content in card layouts:

{{< cards >}}
{{< card title="Feature 1" icon="star" >}}
Description of feature 1
{{< /card >}}

{{< card title="Feature 2" icon="heart" >}}
Description of feature 2
{{< /card >}}

{{< card title="Feature 3" icon="check" >}}
Description of feature 3
{{< /card >}}
{{< /cards >}}

```
{{< cards >}}
{{< card title="Title" icon="icon-name" >}}
Card content
{{< /card >}}
{{< /cards >}}
```

### Grid Layout

Create responsive grid layouts:

{{< grid columns="3" >}}

#### Column 1
Content for first column

#### Column 2
Content for second column

#### Column 3
Content for third column

{{< /grid >}}

```
{{< grid columns="3" >}}
Content divided into 3 columns
{{< /grid >}}
```

### Images

Enhanced image handling:

{{< image src="/images/example.png" alt="Example image" caption="This is a caption" >}}

```
{{< image src="/path/to/image.png" alt="Description" caption="Optional caption" >}}
```

### Videos

Embed videos:

{{< video src="https://example.com/video.mp4" poster="/images/poster.jpg" >}}

```
{{< video src="video-url" poster="poster-image-url" >}}
```

### Timeline

Display chronological information:

{{< timeline >}}
- **2025-11-14**: Initial release
- **2025-11-13**: Beta testing begins
- **2025-11-12**: Development starts
{{< /timeline >}}

```
{{< timeline >}}
- **Date**: Event description
- **Date**: Event description
{{< /timeline >}}
```

### Mermaid Diagrams

Create diagrams using Mermaid:

{{< mermaid >}}
graph TD
    A[Start] --> B{Decision}
    B -->|Yes| C[Action 1]
    B -->|No| D[Action 2]
    C --> E[End]
    D --> E
{{< /mermaid >}}

```
{{< mermaid >}}
graph TD
    A[Start] --> B[End]
{{< /mermaid >}}
```

## Advanced Usage

### Nested Shortcodes

You can nest shortcodes within each other:

```
{{< tabs >}}
{{< tab "Overview" >}}
{{< note type="info" >}}
This is a note inside a tab
{{< /note >}}
{{< /tab >}}
{{< /tabs >}}
```

### Shortcode Parameters

Many shortcodes accept parameters:

```
{{< button href="/link/" type="primary" size="large" >}}
Button Text
{{< /button >}}
```

Common parameter types:
- `href`: URL links
- `type`: Style variants (primary, secondary, etc.)
- `size`: Size options (small, medium, large)
- `icon`: Icon names
- `class`: Custom CSS classes

## Best Practices

{{< tip >}}
Use shortcodes consistently throughout your documentation to maintain a uniform look and feel.
{{< /tip >}}

1. **Choose the Right Shortcode**: Use the appropriate shortcode for your content type
2. **Don't Overuse**: Too many shortcodes can make content hard to maintain
3. **Test Rendering**: Always preview how shortcodes render in your system
4. **Document Custom Shortcodes**: If you create custom shortcodes, document their usage

## Next Steps

- Explore [Page Organization](/guides/page-organization/)
- See [Examples](/examples/) for real-world usage
