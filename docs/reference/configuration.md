---
title: "Configuration"
description: "Configuration reference for documentation system"
weight: 33
date: 2025-11-14
tags: ["reference", "configuration"]
---

# Configuration Reference

Configuration options for your documentation system.

## Configuration File

Most documentation systems use a configuration file (e.g., `config.yaml`, `config.toml`, or `docusaurus.config.js`).

### YAML Configuration Example

```yaml
# Site Configuration
title: "Documentation Title"
baseURL: "https://docs.example.com"
languageCode: "en-us"
defaultContentLanguage: "en"

# Theme Configuration
theme: "docs-theme"
themeConfig:
  logo: "/images/logo.png"
  favicon: "/images/favicon.ico"
  
# Navigation
menu:
  main:
    - name: "Getting Started"
      url: "/getting-started/"
      weight: 10
    - name: "Guides"
      url: "/guides/"
      weight: 20
    - name: "Reference"
      url: "/reference/"
      weight: 30

# Features
params:
  # Search
  search:
    enabled: true
    provider: "algolia"
    
  # Table of Contents
  toc:
    enabled: true
    minHeadings: 2
    maxHeadings: 4
    
  # Syntax Highlighting
  highlight:
    enabled: true
    style: "monokai"
    lineNumbers: true
    
  # Analytics
  analytics:
    google: "UA-XXXXXXXXX-X"
    
  # Social
  social:
    github: "https://github.com/username/repo"
    twitter: "https://twitter.com/username"
```

## Site Settings

### Basic Settings

| Setting | Type | Description |
|---------|------|-------------|
| `title` | string | Site title |
| `baseURL` | string | Base URL for the site |
| `languageCode` | string | Primary language code |
| `defaultContentLanguage` | string | Default content language |

### Theme Settings

| Setting | Type | Description |
|---------|------|-------------|
| `theme` | string | Theme name |
| `logo` | string | Path to logo image |
| `favicon` | string | Path to favicon |
| `colorScheme` | string | Color scheme (light/dark/auto) |

## Navigation Configuration

### Main Menu

```yaml
menu:
  main:
    - name: "Home"
      url: "/"
      weight: 1
    - name: "Documentation"
      url: "/docs/"
      weight: 10
    - name: "API"
      url: "/api/"
      weight: 20
```

### Sidebar

```yaml
sidebar:
  - section: "Getting Started"
    items:
      - name: "Installation"
        url: "/getting-started/installation/"
      - name: "Quick Start"
        url: "/getting-started/quick-start/"
  - section: "Guides"
    items:
      - name: "Writing Content"
        url: "/guides/writing-content/"
```

## Feature Configuration

### Search

```yaml
search:
  enabled: true
  provider: "algolia"  # algolia, lunr, or custom
  algolia:
    appId: "YOUR_APP_ID"
    apiKey: "YOUR_API_KEY"
    indexName: "docs"
```

### Table of Contents

```yaml
toc:
  enabled: true
  minHeadings: 2      # Minimum heading level (H2)
  maxHeadings: 4      # Maximum heading level (H4)
  sticky: true        # Sticky TOC on scroll
  position: "right"   # left or right
```

### Syntax Highlighting

```yaml
highlight:
  enabled: true
  style: "monokai"           # Theme name
  lineNumbers: true          # Show line numbers
  lineNumbersInTable: false  # Line numbers in table
  tabWidth: 2                # Tab width
  languages:                 # Additional languages
    - yaml
    - toml
```

### Code Copy Button

```yaml
codeBlock:
  copyButton: true
  maxLines: 50      # Collapse blocks larger than this
  expandText: "Show more"
  collapseText: "Show less"
```

## Content Settings

### Markdown

```yaml
markdown:
  gfm: true                  # GitHub Flavored Markdown
  footnotes: true            # Enable footnotes
  smartypants: true          # Smart quotes
  taskLists: true            # Task list support
  tables: true               # Table support
  strikethrough: true        # Strikethrough support
  linkify: true              # Auto-link URLs
  typographer: true          # Typographic replacements
```

### Frontmatter

```yaml
frontmatter:
  date: ["date", "publishDate", "lastmod"]
  expiryDate: ["expiryDate"]
  lastmod: ["lastmod", ":git", "date"]
  publishDate: ["publishDate", "date"]
```

## Build Settings

### Output

```yaml
output:
  home: ["HTML", "RSS", "JSON"]
  page: ["HTML"]
  section: ["HTML", "RSS"]
```

### Permalinks

```yaml
permalinks:
  posts: "/:year/:month/:slug/"
  pages: "/:slug/"
```

### Paths

```yaml
paths:
  content: "content"
  static: "static"
  layouts: "layouts"
  data: "data"
  archetypes: "archetypes"
  assetDir: "assets"
  publishDir: "public"
```

## SEO & Meta

### Site Meta

```yaml
params:
  description: "Site description for SEO"
  keywords: ["keyword1", "keyword2", "keyword3"]
  author: "Author Name"
  images: ["/images/og-image.png"]
  
  # Open Graph
  og:
    siteName: "Site Name"
    type: "website"
    locale: "en_US"
  
  # Twitter Card
  twitter:
    card: "summary_large_image"
    site: "@username"
    creator: "@username"
```

### Robots

```yaml
enableRobotsTXT: true
robotsContent: |
  User-agent: *
  Allow: /
  Sitemap: https://example.com/sitemap.xml
```

### Sitemap

```yaml
sitemap:
  changefreq: "weekly"
  priority: 0.5
  filename: "sitemap.xml"
```

## Analytics & Tracking

### Google Analytics

```yaml
googleAnalytics: "UA-XXXXXXXXX-X"
# or for GA4
params:
  analytics:
    google:
      measurementId: "G-XXXXXXXXXX"
```

### Custom Analytics

```yaml
params:
  analytics:
    plausible:
      domain: "docs.example.com"
    fathom:
      siteId: "ABCDEFG"
```

## Social & External

### Social Links

```yaml
params:
  social:
    github: "https://github.com/username"
    twitter: "https://twitter.com/username"
    linkedin: "https://linkedin.com/in/username"
    email: "contact@example.com"
```

### Edit Links

```yaml
params:
  editURL: "https://github.com/user/repo/edit/main/docs"
  editText: "Edit this page"
```

## Advanced Settings

### Security

```yaml
security:
  exec:
    allow: ["^dart-sass-embedded$", "^go$", "^npx$"]
  funcs:
    getenv: ["^HUGO_"]
  http:
    methods: ["GET"]
    urls: [".*"]
```

### Caching

```yaml
caches:
  assets:
    dir: ":resourceDir/_gen"
    maxAge: "24h"
  getjson:
    dir: ":cacheDir/:project"
    maxAge: "1h"
  getcsv:
    dir: ":cacheDir/:project"
    maxAge: "1h"
```

### Minification

```yaml
minify:
  minifyOutput: true
  tdewolff:
    html:
      keepWhitespace: false
    css:
      precision: 2
    js:
      precision: 2
```

## Environment-Specific

### Development

```yaml
# config.development.yaml
baseURL: "http://localhost:1313"
buildDrafts: true
buildFuture: true
enableRobotsTXT: false
```

### Production

```yaml
# config.production.yaml
baseURL: "https://docs.example.com"
buildDrafts: false
buildFuture: false
enableRobotsTXT: true
minify:
  minifyOutput: true
```

## Shortcode Configuration

### Global Shortcode Settings

```yaml
params:
  shortcodes:
    # Note shortcode defaults
    note:
      defaultType: "info"
      icons: true
    
    # Code block defaults
    codeBlock:
      copyButton: true
      lineNumbers: false
    
    # Tab defaults
    tabs:
      defaultTab: 0
      persist: true
    
    # Image defaults
    image:
      loading: "lazy"
      quality: 85
```

## Internationalization

### Languages

```yaml
languages:
  en:
    languageName: "English"
    weight: 1
    params:
      description: "English documentation"
  es:
    languageName: "Español"
    weight: 2
    params:
      description: "Documentación en español"
  fr:
    languageName: "Français"
    weight: 3
    params:
      description: "Documentation en français"
```

### Translation

```yaml
defaultContentLanguageInSubdir: true
disableLanguages: ["de", "it"]
```

## Custom Parameters

Add custom parameters for your theme:

```yaml
params:
  # Custom theme params
  customCSS: ["/css/custom.css"]
  customJS: ["/js/custom.js"]
  
  # Feature flags
  features:
    darkMode: true
    search: true
    comments: true
    
  # Custom sections
  footer:
    logo: "/images/footer-logo.png"
    copyright: "© 2025 Company Name"
    links:
      - name: "Privacy"
        url: "/privacy/"
      - name: "Terms"
        url: "/terms/"
```

## Example Complete Configuration

```yaml
title: "Sample Documentation"
baseURL: "https://docs.example.com"
languageCode: "en-us"
theme: "docs-theme"

params:
  description: "Comprehensive documentation site"
  author: "Documentation Team"
  
  logo: "/images/logo.png"
  favicon: "/images/favicon.ico"
  
  search:
    enabled: true
  
  toc:
    enabled: true
    minHeadings: 2
    maxHeadings: 4
  
  social:
    github: "https://github.com/username/repo"
    twitter: "https://twitter.com/username"
  
  editURL: "https://github.com/user/repo/edit/main/docs"

menu:
  main:
    - name: "Getting Started"
      url: "/getting-started/"
      weight: 10
    - name: "Guides"
      url: "/guides/"
      weight: 20
    - name: "Reference"
      url: "/reference/"
      weight: 30

markup:
  highlight:
    style: "monokai"
    lineNumbers: true
  goldmark:
    renderer:
      unsafe: true
```

## Next Steps

- Review [Page Reference](/reference/page-reference/) for page configuration
- See [Examples](/examples/) for configuration examples
