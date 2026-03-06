# SearXNG Search Deployment

**Privacy-focused meta-search engine for OpenClaw AI Assistant**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## Overview

Complete SearXNG deployment for OpenClaw AI Assistant with:
- Self-hosted search API
- Baidu/Bing Chinese search support
- Automated DevOps monitoring
- 7x24 availability

---

## Quick Start

```bash
# Deploy SearXNG
cd searxng-deployment && docker-compose up -d

# Test
curl http://localhost:8083/search?q=test\&format=json

# Configure OpenClaw
# Edit ~/.openclaw/openclaw.json with baseUrl: http://localhost:8765
```

---

## Documentation

- [Integration Guide](docs/INTEGRATION-GUIDE.md)
- [Deployment Guide](docs/DEPLOYMENT-GUIDE.md)

---

## License

MIT License
