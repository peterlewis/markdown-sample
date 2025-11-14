---
title: "Complete Documentation Examples"
description: "Full documentation structure examples for different project types"
weight: 43
date: 2025-11-14
tags: ["examples", "complete", "templates"]
---

# Complete Documentation Examples

Complete documentation structures for different types of projects.

## Example 1: CLI Tool Documentation

Structure for command-line tool documentation:

```
docs/
├── _index.md               # Welcome & overview
├── installation/
│   ├── _index.md          # Installation overview
│   ├── linux.md           # Linux installation
│   ├── macos.md           # macOS installation
│   └── windows.md         # Windows installation
├── getting-started/
│   ├── _index.md          # Getting started overview
│   ├── first-command.md   # Your first command
│   └── configuration.md   # Basic configuration
├── commands/
│   ├── _index.md          # Command reference overview
│   ├── init.md            # init command
│   ├── build.md           # build command
│   ├── deploy.md          # deploy command
│   └── config.md          # config command
├── guides/
│   ├── _index.md          # Guides overview
│   ├── workflows.md       # Common workflows
│   ├── plugins.md         # Working with plugins
│   └── ci-cd.md           # CI/CD integration
└── troubleshooting/
    ├── _index.md          # Troubleshooting overview
    ├── common-errors.md   # Common errors
    └── debugging.md       # Debugging guide
```

### Sample CLI Tool Index Page

```markdown
---
title: "ToolName Documentation"
description: "Complete guide to using ToolName"
weight: 1
---

# ToolName

**ToolName** is a powerful CLI tool for managing your projects.

## Quick Start

{{< code-block language="bash" >}}
# Install
npm install -g toolname

# Initialize a project
toolname init my-project

# Build
toolname build
{{< /code-block >}}

{{< cards >}}
{{< card title="Installation" icon="download" link="/installation/" >}}
Install on your platform
{{< /card >}}

{{< card title="Getting Started" icon="rocket" link="/getting-started/" >}}
Your first steps
{{< /card >}}

{{< card title="Commands" icon="terminal" link="/commands/" >}}
Command reference
{{< /card >}}
{{< /cards >}}

## Features

- ⚡ Fast and efficient
- 🔧 Highly configurable
- 🎨 Beautiful output
- 🔌 Plugin system
```

## Example 2: REST API Documentation

Structure for REST API documentation:

```
docs/
├── _index.md              # API overview
├── authentication/
│   ├── _index.md         # Auth overview
│   ├── api-keys.md       # API key auth
│   ├── oauth.md          # OAuth 2.0
│   └── jwt.md            # JWT tokens
├── endpoints/
│   ├── _index.md         # Endpoints overview
│   ├── users.md          # User endpoints
│   ├── posts.md          # Post endpoints
│   ├── comments.md       # Comment endpoints
│   └── media.md          # Media endpoints
├── guides/
│   ├── _index.md         # Guides overview
│   ├── rate-limiting.md  # Rate limiting
│   ├── pagination.md     # Pagination
│   ├── filtering.md      # Filtering & sorting
│   └── webhooks.md       # Webhooks
├── errors/
│   ├── _index.md         # Error handling
│   └── codes.md          # Error codes
└── changelog/
    └── _index.md         # API changelog
```

### Sample API Endpoint Page

```markdown
---
title: "Users API"
description: "User management endpoints"
weight: 10
---

# Users API

Manage user accounts and profiles.

## List Users

`GET /api/v1/users`

Retrieve a paginated list of users.

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `page` | integer | No | Page number (default: 1) |
| `limit` | integer | No | Items per page (default: 20, max: 100) |
| `sort` | string | No | Sort field (e.g., `created_at`, `-name`) |

### Example Request

{{< tabs >}}
{{< tab "cURL" >}}
```bash
curl -X GET "https://api.example.com/v1/users?page=1&limit=20" \
  -H "Authorization: Bearer YOUR_API_KEY"
```
{{< /tab >}}

{{< tab "JavaScript" >}}
```javascript
const response = await fetch('https://api.example.com/v1/users?page=1&limit=20', {
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY'
  }
});
const users = await response.json();
```
{{< /tab >}}

{{< tab "Python" >}}
```python
import requests

response = requests.get(
    'https://api.example.com/v1/users',
    params={'page': 1, 'limit': 20},
    headers={'Authorization': 'Bearer YOUR_API_KEY'}
)
users = response.json()
```
{{< /tab >}}
{{< /tabs >}}

### Example Response

```json
{
  "data": [
    {
      "id": "user_123",
      "name": "John Doe",
      "email": "john@example.com",
      "created_at": "2025-11-14T10:30:00Z"
    }
  ],
  "pagination": {
    "page": 1,
    "limit": 20,
    "total": 100,
    "pages": 5
  }
}
```

{{< note type="info" >}}
**Rate Limit:** 100 requests per minute
{{< /note >}}

## Create User

`POST /api/v1/users`

Create a new user account.

### Request Body

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `name` | string | Yes | User's full name |
| `email` | string | Yes | User's email address |
| `password` | string | Yes | Password (min 8 characters) |

### Example Request

```bash
curl -X POST "https://api.example.com/v1/users" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Jane Doe",
    "email": "jane@example.com",
    "password": "secure_password"
  }'
```

### Response Codes

| Code | Description |
|------|-------------|
| `201` | User created successfully |
| `400` | Invalid request data |
| `409` | Email already exists |
| `429` | Rate limit exceeded |
```

## Example 3: Library/SDK Documentation

Structure for library documentation:

```
docs/
├── _index.md              # Library overview
├── installation/
│   ├── _index.md         # Installation guide
│   ├── npm.md            # npm installation
│   ├── yarn.md           # yarn installation
│   └── cdn.md            # CDN usage
├── quickstart/
│   └── _index.md         # Quick start guide
├── core-concepts/
│   ├── _index.md         # Concepts overview
│   ├── initialization.md # Initialization
│   ├── configuration.md  # Configuration
│   └── methods.md        # Core methods
├── api/
│   ├── _index.md         # API reference
│   ├── classes/          # Class documentation
│   ├── methods/          # Method documentation
│   └── types.md          # Type definitions
├── guides/
│   ├── _index.md         # Guides overview
│   ├── authentication.md # Authentication
│   ├── error-handling.md # Error handling
│   └── best-practices.md # Best practices
└── examples/
    ├── _index.md         # Examples overview
    ├── basic.md          # Basic examples
    └── advanced.md       # Advanced examples
```

### Sample Library Quick Start

```markdown
---
title: "Quick Start"
description: "Get started with LibraryName in 5 minutes"
weight: 2
---

# Quick Start

Get up and running with LibraryName in just a few minutes.

## Installation

{{< tabs >}}
{{< tab "npm" >}}
```bash
npm install library-name
```
{{< /tab >}}

{{< tab "yarn" >}}
```bash
yarn add library-name
```
{{< /tab >}}

{{< tab "CDN" >}}
```html
<script src="https://cdn.example.com/library-name@latest/dist/library.min.js"></script>
```
{{< /tab >}}
{{< /tabs >}}

## Basic Usage

### 1. Import the Library

```javascript
import LibraryName from 'library-name';
```

### 2. Initialize

```javascript
const lib = new LibraryName({
  apiKey: 'your-api-key',
  region: 'us-east-1'
});
```

### 3. Use Core Features

```javascript
// Example operation
const result = await lib.doSomething({
  param1: 'value1',
  param2: 'value2'
});

console.log(result);
```

## Complete Example

{{< code-block language="javascript" highlight="4,8" >}}
import LibraryName from 'library-name';

// Initialize
const lib = new LibraryName({
  apiKey: process.env.API_KEY
});

// Perform operation
async function example() {
  try {
    const result = await lib.doSomething({
      param: 'value'
    });
    console.log('Success:', result);
  } catch (error) {
    console.error('Error:', error);
  }
}

example();
{{< /code-block >}}

{{< success >}}
You're all set! Check out the [Guides](/guides/) for more advanced usage.
{{< /success >}}

## Next Steps

{{< cards >}}
{{< card title="Core Concepts" link="/core-concepts/" >}}
Understanding the fundamentals
{{< /card >}}

{{< card title="API Reference" link="/api/" >}}
Complete API documentation
{{< /card >}}

{{< card title="Examples" link="/examples/" >}}
Real-world code examples
{{< /card >}}
{{< /cards >}}
```

## Example 4: Product Documentation

Structure for product/SaaS documentation:

```
docs/
├── _index.md                    # Product overview
├── getting-started/
│   ├── _index.md               # Getting started
│   ├── sign-up.md              # Account creation
│   ├── onboarding.md           # Onboarding tutorial
│   └── first-project.md        # First project
├── features/
│   ├── _index.md               # Features overview
│   ├── dashboard.md            # Dashboard
│   ├── projects.md             # Projects
│   ├── collaboration.md        # Collaboration
│   └── integrations.md         # Integrations
├── how-to/
│   ├── _index.md               # How-to guides
│   ├── invite-users.md         # Inviting users
│   ├── manage-billing.md       # Managing billing
│   └── export-data.md          # Exporting data
├── integrations/
│   ├── _index.md               # Integrations overview
│   ├── slack.md                # Slack integration
│   ├── github.md               # GitHub integration
│   └── zapier.md               # Zapier integration
├── account/
│   ├── _index.md               # Account management
│   ├── profile.md              # Profile settings
│   ├── security.md             # Security settings
│   └── billing.md              # Billing & plans
└── faq/
    └── _index.md               # Frequently asked questions
```

## Documentation Best Practices

{{< grid columns="2" >}}

### Structure
- Organize by user journey
- Group related topics
- Use clear hierarchy
- Include navigation aids

### Content
- Start with quick start
- Include examples
- Use visuals
- Keep it updated

### Writing
- Write for your audience
- Be concise and clear
- Use active voice
- Provide context

### Maintenance
- Regular updates
- Version control
- Track changes
- Gather feedback

{{< /grid >}}

## Templates

Use these structures as templates for your own documentation:

{{< note type="tip" >}}
**Pro Tip:** Start with one of these examples and customize it for your specific needs.
{{< /note >}}

### Choosing the Right Structure

| Project Type | Recommended Structure |
|--------------|----------------------|
| CLI Tool | Example 1 |
| REST API | Example 2 |
| Library/SDK | Example 3 |
| SaaS Product | Example 4 |

## Next Steps

- Review [Page Organization Guide](/guides/page-organization/)
- Explore [Writing Content](/guides/writing-content/)
- Check [Reference Documentation](/reference/)
