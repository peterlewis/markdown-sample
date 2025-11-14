---
title: "Advanced Shortcode Examples"
description: "Examples of advanced shortcode usage and combinations"
weight: 42
date: 2025-11-14
tags: ["examples", "shortcodes", "advanced"]
---

# Advanced Shortcode Examples

Complex shortcode combinations and real-world usage patterns.

## Nested Shortcodes

### Tabs with Code Blocks

Combine tabs with syntax-highlighted code:

````markdown
{{< tabs >}}
{{< tab "JavaScript" >}}
```javascript
function greet(name) {
    console.log(`Hello, ${name}!`);
}

greet("World");
```
{{< /tab >}}

{{< tab "Python" >}}
```python
def greet(name):
    print(f"Hello, {name}!")

greet("World")
```
{{< /tab >}}

{{< tab "Go" >}}
```go
package main

import "fmt"

func greet(name string) {
    fmt.Printf("Hello, %s!\n", name)
}

func main() {
    greet("World")
}
```
{{< /tab >}}
{{< /tabs >}}
````

### Accordion with Notes

Combine accordion with alert boxes:

```markdown
{{< accordion >}}
{{< accordion-item "Important Security Notice" >}}
{{< note type="warning" >}}
**Warning:** Always use HTTPS in production environments.
{{< /note >}}

Additional security considerations:
- Enable two-factor authentication
- Use strong passwords
- Regularly update dependencies
{{< /accordion-item >}}

{{< accordion-item "Performance Tips" >}}
{{< tip >}}
Cache frequently accessed data to improve performance.
{{< /tip >}}

Other optimization strategies:
- Minimize HTTP requests
- Compress assets
- Use a CDN
{{< /accordion-item >}}
{{< /accordion >}}
```

### Cards with Multiple Elements

Create rich cards with various content:

```markdown
{{< cards >}}
{{< card title="Getting Started" icon="rocket" link="/getting-started/" >}}

{{< note type="info" >}}
New to the platform? Start here!
{{< /note >}}

**What you'll learn:**
- Basic setup
- Core concepts
- Your first project

{{< button href="/getting-started/installation/" >}}
Install Now
{{< /button >}}
{{< /card >}}

{{< card title="Advanced Guides" icon="book" link="/guides/" >}}

Master advanced features and best practices.

**Topics covered:**
- Performance optimization
- Security hardening
- Scaling strategies

{{< button href="/guides/" type="primary" >}}
Explore Guides
{{< /button >}}
{{< /card >}}
{{< /cards >}}
```

## Real-World Examples

### API Endpoint Documentation

Document API endpoints with all details:

```markdown
## POST /api/users

Create a new user account.

{{< note type="info" >}}
**Authentication Required:** This endpoint requires a valid API key.
{{< /note >}}

### Request

{{< tabs >}}
{{< tab "cURL" >}}
```bash
curl -X POST https://api.example.com/users \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "John Doe",
    "email": "john@example.com"
  }'
```
{{< /tab >}}

{{< tab "JavaScript" >}}
```javascript
const response = await fetch('https://api.example.com/users', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    name: 'John Doe',
    email: 'john@example.com'
  })
});

const data = await response.json();
```
{{< /tab >}}

{{< tab "Python" >}}
```python
import requests

response = requests.post(
    'https://api.example.com/users',
    headers={
        'Authorization': 'Bearer YOUR_API_KEY',
        'Content-Type': 'application/json'
    },
    json={
        'name': 'John Doe',
        'email': 'john@example.com'
    }
)

data = response.json()
```
{{< /tab >}}
{{< /tabs >}}

### Response

```json
{
  "id": "user_123456",
  "name": "John Doe",
  "email": "john@example.com",
  "created_at": "2025-11-14T10:30:00Z"
}
```

{{< success >}}
User created successfully! The API returns a 201 status code.
{{< /success >}}
```

### Installation Guide with Platform-Specific Instructions

```markdown
## Installation

{{< tabs >}}
{{< tab "Linux" >}}

### Ubuntu/Debian

```bash
sudo apt update
sudo apt install -y software-name
```

{{< note type="info" >}}
For Ubuntu 20.04 or later
{{< /note >}}

### Fedora/RHEL

```bash
sudo dnf install software-name
```

### Arch Linux

```bash
sudo pacman -S software-name
```

{{< /tab >}}

{{< tab "macOS" >}}

### Using Homebrew

```bash
brew install software-name
```

{{< tip >}}
Don't have Homebrew? Install it from [brew.sh](https://brew.sh)
{{< /tip >}}

### Using MacPorts

```bash
sudo port install software-name
```

{{< /tab >}}

{{< tab "Windows" >}}

### Using Chocolatey

```powershell
choco install software-name
```

### Using Scoop

```powershell
scoop install software-name
```

### Manual Installation

1. Download the installer from [website.com](https://website.com)
2. Run the installer
3. Follow the installation wizard

{{< note type="warning" >}}
Requires Administrator privileges
{{< /note >}}

{{< /tab >}}
{{< /tabs >}}

### Verify Installation

```bash
software-name --version
```

{{< success >}}
If you see the version number, installation was successful!
{{< /success >}}
```

### Troubleshooting Section

Comprehensive troubleshooting with collapsible sections:

```markdown
## Troubleshooting

{{< accordion >}}
{{< accordion-item "Installation fails with permission errors" >}}

{{< note type="warning" >}}
This usually indicates insufficient permissions.
{{< /note >}}

**Solution:**

{{< tabs >}}
{{< tab "Linux/macOS" >}}
Run the command with `sudo`:
```bash
sudo npm install -g package-name
```
{{< /tab >}}

{{< tab "Windows" >}}
Run Command Prompt or PowerShell as Administrator.
{{< /tab >}}
{{< /tabs >}}

{{< /accordion-item >}}

{{< accordion-item "Module not found error" >}}

{{< note type="info" >}}
This occurs when dependencies are not properly installed.
{{< /note >}}

**Solution:**

1. Clear the cache:
   ```bash
   npm cache clean --force
   ```

2. Remove node_modules:
   ```bash
   rm -rf node_modules package-lock.json
   ```

3. Reinstall dependencies:
   ```bash
   npm install
   ```

{{< tip >}}
Try using `npm ci` instead of `npm install` for more reliable installs.
{{< /tip >}}

{{< /accordion-item >}}

{{< accordion-item "Build fails in production" >}}

Common causes and solutions:

{{< grid columns="2" >}}

**Environment Variables**
- Ensure all required env vars are set
- Check `.env.production` file
- Verify environment in hosting platform

**Dependencies**
- Check for missing dependencies
- Verify versions match
- Review build logs

{{< /grid >}}

{{< note type="danger" >}}
Never commit sensitive credentials to version control!
{{< /note >}}

{{< /accordion-item >}}
{{< /accordion >}}
```

### Feature Comparison Table with Details

```markdown
## Plan Comparison

| Feature | Starter | Professional | Enterprise |
|---------|---------|--------------|------------|
| **Users** | Up to 5 | Up to 50 | Unlimited |
| **Storage** | 10 GB | 100 GB | Custom |
| **API Calls** | 1,000/mo | 10,000/mo | Unlimited |
| **Support** | Community | Email | 24/7 Phone |
| **SLA** | - | 99.9% | 99.99% |
| **Price** | Free | $49/mo | Custom |

{{< accordion >}}
{{< accordion-item "What's included in Starter?" >}}

The Starter plan includes:
- Core features
- Community support
- Basic analytics
- Email notifications

{{< tip >}}
Perfect for individuals and small projects!
{{< /tip >}}

{{< button href="/signup?plan=starter" >}}
Start Free
{{< /button >}}

{{< /accordion-item >}}

{{< accordion-item "What's included in Professional?" >}}

Everything in Starter, plus:
- Advanced analytics
- Priority email support
- Custom integrations
- Advanced security features

{{< note type="info" >}}
Most popular for growing teams!
{{< /note >}}

{{< button href="/signup?plan=pro" type="primary" >}}
Start Trial
{{< /button >}}

{{< /accordion-item >}}

{{< accordion-item "What's included in Enterprise?" >}}

Everything in Professional, plus:
- Unlimited everything
- 24/7 phone support
- Dedicated account manager
- Custom SLA
- On-premise deployment option

{{< button href="/contact-sales" >}}
Contact Sales
{{< /button >}}

{{< /accordion-item >}}
{{< /accordion >}}
```

### Architecture Diagram with Description

```markdown
## System Architecture

{{< mermaid >}}
graph TB
    Client[Client Application]
    LB[Load Balancer]
    API1[API Server 1]
    API2[API Server 2]
    Cache[(Redis Cache)]
    DB[(PostgreSQL)]
    Queue[Message Queue]
    Worker[Background Worker]
    
    Client --> LB
    LB --> API1
    LB --> API2
    API1 --> Cache
    API2 --> Cache
    API1 --> DB
    API2 --> DB
    API1 --> Queue
    API2 --> Queue
    Queue --> Worker
    Worker --> DB
{{< /mermaid >}}

{{< grid columns="2" >}}

### Components

**Load Balancer**
- Distributes traffic
- Health checks
- SSL termination

**API Servers**
- Handle requests
- Stateless design
- Horizontal scaling

**Cache Layer**
- Redis for caching
- Session storage
- Rate limiting

**Database**
- PostgreSQL primary
- Read replicas
- Automated backups

{{< /grid >}}

{{< tip >}}
This architecture supports high availability and horizontal scaling.
{{< /tip >}}
```

### Migration Guide

```markdown
## Migrating from v1 to v2

{{< note type="warning" >}}
**Breaking Changes:** Version 2 includes breaking changes. Review this guide carefully.
{{< /note >}}

### Migration Steps

{{< timeline >}}
- **Step 1**: Backup your data
- **Step 2**: Update dependencies
- **Step 3**: Update configuration
- **Step 4**: Run migration scripts
- **Step 5**: Test thoroughly
- **Step 6**: Deploy to production
{{< /timeline >}}

### Detailed Instructions

{{< tabs >}}
{{< tab "1. Backup" >}}

Create a complete backup:

```bash
# Backup database
pg_dump dbname > backup.sql

# Backup files
tar -czf files-backup.tar.gz /path/to/files
```

{{< success >}}
Store backups in a safe location before proceeding!
{{< /success >}}

{{< /tab >}}

{{< tab "2. Update Dependencies" >}}

Update your package.json:

```json
{
  "dependencies": {
    "package-name": "^2.0.0"
  }
}
```

Then run:
```bash
npm install
```

{{< note type="info" >}}
Check for peer dependency warnings
{{< /note >}}

{{< /tab >}}

{{< tab "3. Configuration" >}}

Update your configuration file:

```yaml
# Old (v1)
api_version: "v1"
legacy_mode: true

# New (v2)
api_version: "v2"
features:
  new_feature: true
```

{{< /tab >}}
{{< /tabs >}}
```

## Advanced Grid Layouts

```markdown
{{< grid columns="3" gap="large" >}}

### Quick Start
{{< note type="info" >}}
Get started in minutes
{{< /note >}}
- Step 1
- Step 2
- Step 3

### In-Depth Guide
{{< note type="info" >}}
Comprehensive tutorial
{{< /note >}}
- Deep dive
- Best practices
- Advanced topics

### Video Tutorial
{{< video src="/videos/tutorial.mp4" >}}

{{< button href="/tutorials/" >}}
Watch Now
{{< /button >}}

{{< /grid >}}
```

## Best Practices

{{< tip >}}
**Shortcode Combination Tips:**
1. Keep nesting shallow (max 2-3 levels)
2. Test rendering in your system
3. Ensure accessibility
4. Consider mobile users
5. Don't overuse - maintain readability
{{< /tip >}}

## Next Steps

- See [Complete Documentation Examples](/examples/complete-documentation/)
- Review [Shortcode Reference](/reference/shortcode-reference/)
