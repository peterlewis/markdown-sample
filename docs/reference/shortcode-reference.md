---
title: "Shortcode Reference"
description: "Complete reference for all available shortcodes"
weight: 32
date: 2025-11-14
tags: ["reference", "shortcodes"]
---

# Shortcode Reference

Complete technical reference for all available shortcodes.

## Shortcode Syntax

### Basic Shortcode

```
{{< shortcode_name >}}
```

### Shortcode with Parameters

```
{{< shortcode_name param1="value1" param2="value2" >}}
```

### Shortcode with Content

```
{{< shortcode_name >}}
Content goes here
{{< /shortcode_name >}}
```

## Alert & Notice Shortcodes

### note

Display informational, warning, or danger alerts.

**Parameters:**
- `type` (string): Alert type - `info`, `warning`, `danger`, `success`

**Examples:**

```
{{< note type="info" >}}
This is an informational note.
{{< /note >}}

{{< note type="warning" >}}
This is a warning.
{{< /note >}}

{{< note type="danger" >}}
This is a danger alert.
{{< /note >}}
```

**Output:**

{{< note type="info" >}}
This is an informational note.
{{< /note >}}

### tip

Display helpful tips.

**Parameters:** None

**Example:**

```
{{< tip >}}
Here's a helpful tip for your users.
{{< /tip >}}
```

**Output:**

{{< tip >}}
Here's a helpful tip for your users.
{{< /tip >}}

### success

Display success messages.

**Parameters:** None

**Example:**

```
{{< success >}}
Operation completed successfully!
{{< /success >}}
```

## Navigation Shortcodes

### button

Create clickable buttons.

**Parameters:**
- `href` (string, required): Link URL
- `type` (string): Button style - `primary`, `secondary`, `outline`
- `size` (string): Button size - `small`, `medium`, `large`

**Examples:**

```
{{< button href="/getting-started/" >}}Get Started{{< /button >}}
{{< button href="/docs/" type="primary" >}}Documentation{{< /button >}}
{{< button href="/api/" type="secondary" size="large" >}}API Reference{{< /button >}}
```

### cards

Create a grid of cards.

**Parameters:** None (uses nested `card` shortcodes)

**Example:**

```
{{< cards >}}
{{< card title="Card 1" icon="star" link="/link1/" >}}
Description of card 1
{{< /card >}}
{{< card title="Card 2" icon="heart" link="/link2/" >}}
Description of card 2
{{< /card >}}
{{< /cards >}}
```

### card

Individual card (used within `cards`).

**Parameters:**
- `title` (string, required): Card title
- `icon` (string): Icon name
- `link` (string): URL link

**Example:** See `cards` above

## Layout Shortcodes

### tabs

Create tabbed content sections.

**Parameters:** None (uses nested `tab` shortcodes)

**Example:**

```
{{< tabs >}}
{{< tab "Tab 1" >}}
Content for tab 1
{{< /tab >}}
{{< tab "Tab 2" >}}
Content for tab 2
{{< /tab >}}
{{< tab "Tab 3" >}}
Content for tab 3
{{< /tab >}}
{{< /tabs >}}
```

**Output:**

{{< tabs >}}
{{< tab "Overview" >}}
This is the overview tab content.
{{< /tab >}}
{{< tab "Details" >}}
This is the details tab content.
{{< /tab >}}
{{< /tabs >}}

### tab

Individual tab (used within `tabs`).

**Parameters:**
- First parameter (string, required): Tab label

**Example:** See `tabs` above

### accordion

Create collapsible accordion sections.

**Parameters:** None (uses nested `accordion-item` shortcodes)

**Example:**

```
{{< accordion >}}
{{< accordion-item "Section 1" >}}
Content for section 1
{{< /accordion-item >}}
{{< accordion-item "Section 2" >}}
Content for section 2
{{< /accordion-item >}}
{{< /accordion >}}
```

### accordion-item

Individual accordion item (used within `accordion`).

**Parameters:**
- First parameter (string, required): Section title

**Example:** See `accordion` above

### grid

Create responsive column layouts.

**Parameters:**
- `columns` (string): Number of columns - `1`, `2`, `3`, `4`
- `gap` (string): Gap size - `small`, `medium`, `large`

**Example:**

```
{{< grid columns="3" >}}

#### Column 1
Content for first column

#### Column 2
Content for second column

#### Column 3
Content for third column

{{< /grid >}}
```

## Content Shortcodes

### code-block

Enhanced code block with highlighting.

**Parameters:**
- `language` (string): Programming language
- `highlight` (string): Lines to highlight (e.g., "1,3-5,7")
- `lineNumbers` (boolean): Show line numbers

**Example:**

```
{{< code-block language="python" highlight="2,4" lineNumbers="true" >}}
def hello():
    print("This line is highlighted")
    x = 10
    return x  # This line is highlighted
{{< /code-block >}}
```

### image

Enhanced image display.

**Parameters:**
- `src` (string, required): Image path
- `alt` (string, required): Alt text
- `caption` (string): Image caption
- `width` (string): Image width
- `height` (string): Image height

**Example:**

```
{{< image src="/images/screenshot.png" alt="Screenshot" caption="Application screenshot" width="600" >}}
```

### video

Embed videos.

**Parameters:**
- `src` (string, required): Video URL
- `poster` (string): Poster image URL
- `autoplay` (boolean): Auto-play video
- `loop` (boolean): Loop video

**Example:**

```
{{< video src="/videos/demo.mp4" poster="/images/poster.jpg" >}}
```

### youtube

Embed YouTube videos.

**Parameters:**
- `id` (string, required): YouTube video ID

**Example:**

```
{{< youtube id="dQw4w9WgXcQ" >}}
```

### vimeo

Embed Vimeo videos.

**Parameters:**
- `id` (string, required): Vimeo video ID

**Example:**

```
{{< vimeo id="123456789" >}}
```

## Diagram Shortcodes

### mermaid

Create diagrams using Mermaid syntax.

**Parameters:** None

**Example:**

```
{{< mermaid >}}
graph TD
    A[Start] --> B{Decision}
    B -->|Yes| C[Action 1]
    B -->|No| D[Action 2]
    C --> E[End]
    D --> E
{{< /mermaid >}}
```

## Data Shortcodes

### timeline

Display chronological events.

**Parameters:** None

**Example:**

```
{{< timeline >}}
- **2025-11-14**: Event 1 description
- **2025-11-13**: Event 2 description
- **2025-11-12**: Event 3 description
{{< /timeline >}}
```

**Output:**

{{< timeline >}}
- **2025-11-14**: Documentation created
- **2025-11-13**: Project initialized
{{< /timeline >}}

## Utility Shortcodes

### expand

Create expandable content section.

**Parameters:**
- First parameter (string): Button text (default: "Show more")

**Example:**

```
{{< expand "Click to see more" >}}
This content is hidden by default and expands when clicked.
{{< /expand >}}
```

### details

HTML details/summary element.

**Parameters:**
- `summary` (string, required): Summary text
- `open` (boolean): Initially open

**Example:**

```
{{< details summary="Click to expand" >}}
Hidden content here.
{{< /details >}}
```

### columns

Create side-by-side columns.

**Parameters:**
- `count` (string): Number of columns

**Example:**

```
{{< columns count="2" >}}

Left column content

---

Right column content

{{< /columns >}}
```

## Reference Tables

### Parameter Types

| Type | Description | Example |
|------|-------------|---------|
| string | Text value | `"hello"` |
| boolean | True/false | `true`, `false` |
| integer | Number | `10`, `100` |
| array | List of values | `["a", "b", "c"]` |

### Common Icons

Available icon names:
- `star`, `heart`, `check`, `cross`
- `info`, `warning`, `danger`, `success`
- `file`, `folder`, `code`, `book`
- `home`, `settings`, `user`, `search`

### Color Schemes

Available color types:
- `primary`: Primary brand color
- `secondary`: Secondary color
- `info`: Informational blue
- `success`: Success green
- `warning`: Warning yellow/orange
- `danger`: Danger red

## Nesting Shortcodes

You can nest compatible shortcodes:

```
{{< tabs >}}
{{< tab "Code Examples" >}}
{{< code-block language="python" >}}
print("Hello")
{{< /code-block >}}
{{< /tab >}}
{{< tab "Notes" >}}
{{< note type="info" >}}
Important information
{{< /note >}}
{{< /tab >}}
{{< /tabs >}}
```

## Best Practices

{{< tip >}}
**Shortcode Guidelines:**
1. Use the simplest shortcode that meets your needs
2. Always close paired shortcodes
3. Validate shortcode syntax
4. Test rendering in your documentation system
5. Document custom shortcodes
{{< /tip >}}

### Do's
- ✅ Use semantic shortcode names
- ✅ Provide required parameters
- ✅ Close paired shortcodes
- ✅ Test in preview before publishing

### Don'ts
- ❌ Overuse shortcodes (keep content readable)
- ❌ Nest incompatible shortcodes
- ❌ Use deprecated shortcodes
- ❌ Forget closing tags

## Troubleshooting

{{< accordion >}}
{{< accordion-item "Shortcode not rendering" >}}
Check:
- Correct syntax: `{{<` not `{<`
- Shortcode name spelling
- Required parameters provided
- Closing tag for paired shortcodes
{{< /accordion-item >}}

{{< accordion-item "Content appearing as text" >}}
Ensure:
- Content is between opening and closing tags
- Using correct delimiter: `{{<` for shortcodes
- Shortcode supports content
{{< /accordion-item >}}

{{< accordion-item "Nested shortcodes failing" >}}
Verify:
- Shortcodes are compatible for nesting
- Proper nesting order
- All tags are properly closed
{{< /accordion-item >}}
{{< /accordion >}}

## Next Steps

- See [Examples](/examples/) for real-world shortcode usage
- Review [Configuration](/reference/configuration/) for shortcode settings
