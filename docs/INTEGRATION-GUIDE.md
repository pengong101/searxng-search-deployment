# SearXNG + OpenClaw Integration Guide

## Overview

Integrate SearXNG meta-search engine with OpenClaw AI Assistant.

## Architecture

```
OpenClaw → OpenSERP Adapter (8765) → SearXNG (8083) → Search Engines
```

## Quick Integration

### 1. Deploy SearXNG

See [DEPLOYMENT-GUIDE.md](DEPLOYMENT-GUIDE.md)

### 2. Deploy Adapter

```bash
cd openserp-brave-adapter
export OPENSERP_BASE_URL=http://localhost:8083
node index-searxng.js
```

### 3. Configure OpenClaw

Edit `~/.openclaw/openclaw.json`:

```json
{
  "tools": {
    "web": {
      "search": {
        "provider": "brave",
        "baseUrl": "http://localhost:8765"
      }
    }
  }
}
```

### 4. Test

```bash
curl "http://localhost:8765/search?q=test&count=5"
```

## API Reference

### Search Endpoint

```
GET /search?q=query&count=10
```

**Response:**

```json
{
  "web": {
    "results": [
      {
        "title": "Page Title",
        "url": "https://example.com",
        "description": "Search snippet..."
      }
    ]
  }
}
```

---

**Last Updated:** 2026-03-06
