# SearXNG Deployment Guide

## Prerequisites

- Docker 19.03+
- Docker Compose 1.27+

## Quick Deployment

### 1. Create Directory

```bash
mkdir -p /data/Docker/searxng
cd /data/Docker/searxng
```

### 2. Create docker-compose.yml

```yaml
version: '3.8'
services:
  searxng:
    image: searxng/searxng:latest
    container_name: searxng
    ports:
      - "8083:8080"
    environment:
      - SEARXNG_BASE_URL=http://localhost:8083
      - SEARXNG_SECRET_KEY=your-secret-key
    volumes:
      - ./settings.yml:/etc/searxng/settings.yml:rw
    restart: unless-stopped
```

### 3. Create settings.yml

```yaml
use_default_settings: true
search:
  formats: [html, json]
engines:
  - name: 百度
    engine: baidu
    disabled: false
  - name: bing
    engine: bing
    disabled: false
```

### 4. Start

```bash
docker-compose up -d
```

### 5. Verify

```bash
curl http://localhost:8083/health
curl "http://localhost:8083/search?q=test&format=json"
```

---

**Last Updated:** 2026-03-06
