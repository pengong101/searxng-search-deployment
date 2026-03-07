# OpenClaw SearXNG Search

**Privacy-focused meta-search engine for OpenClaw AI Assistant**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Stars](https://img.shields.io/github/stars/pengong101/openclaw-searxng-search)](https://github.com/pengong101/openclaw-searxng-search)
[![Issues](https://img.shields.io/github/issues/pengong101/openclaw-searxng-search)](https://github.com/pengong101/openclaw-searxng-search/issues)
[![Forks](https://img.shields.io/github/forks/pengong101/openclaw-searxng-search)](https://github.com/pengong101/openclaw-searxng-search/network/members)
[![Release](https://img.shields.io/github/v/release/pengong101/openclaw-searxng-search)](https://github.com/pengong101/openclaw-searxng-search/releases)

[![AI Agent](https://img.shields.io/badge/AI-Agent-blue)](https://github.com/topics/ai-agent)
[![Self-hosted](https://img.shields.io/badge/Self--hosted-Search-green)](https://github.com/topics/self-hosted)
[![Privacy](https://img.shields.io/badge/Privacy-First-red)](https://github.com/topics/privacy)
[![Docker](https://img.shields.io/badge/Docker-Ready-blue)](https://www.docker.com/)

---

## 🎯 Overview

Complete SearXNG deployment solution for OpenClaw AI Assistant. Build your **privacy-focused AI search engine** in 5 minutes!

### ✨ Key Features

- 🔒 **Privacy-First** - Self-hosted, no data tracking
- 🤖 **AI-Powered** - Seamless OpenClaw integration
- 🇨🇳 **China-Ready** - Baidu/Bing Chinese search support
- ⚡ **Zero-Cost** - No paid API required
- 🚀 **5-Min Deploy** - One-click Docker deployment
- 📊 **Auto-Ops** - DevOpsBot monitoring & auto-recovery
- ✅ **Tested & Verified** - Search functionality verified

---

## 🏗️ Architecture

```
┌─────────────┐     ┌──────────────────┐     ┌─────────────┐
│  OpenClaw   │────▶│ OpenSERP Adapter │────▶│  SearXNG    │
│ AI Assistant│     │  (Port 8765)     │     │ (Port 8083) │
└─────────────┘     └──────────────────┘     └──────┬──────┘
                                                    │
                     ┌──────────────────────────────┼──────────────────────────────┐
                     │                              │                              │
              ┌──────▼──────┐              ┌───────▼───────┐             ┌────────▼────────┐
              │   Baidu     │              │   Bing CN     │             │    Wikipedia    │
              │  (baidu)    │              │  (cn.bing)    │             │   (zh.wikipedia)│
              └─────────────┘              └───────────────┘             └─────────────────┘
```

---

## 🚀 Quick Start

### 1. Deploy SearXNG (2 minutes)

```bash
cd searxng-deployment
docker-compose up -d
```

### 2. Test Search (30 seconds)

```bash
# Health check
curl http://localhost:8083/health

# Test search
curl "http://localhost:8083/search?q=test&format=json"
```

### 3. Configure OpenSERP Adapter (1 minute)

```bash
cd ../openserp-brave-adapter
export OPENSERP_BASE_URL=http://localhost:8083
node index-searxng.js
```

### 4. Configure OpenClaw (1 minute)

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

### 5. Test in OpenClaw (30 seconds)

Send message: `"Search for mmWave radar 2026"`

**Total Time: < 5 minutes!** ⚡

---

## 📚 Documentation

| Document | Description |
|----------|-------------|
| [Deployment Guide](docs/DEPLOYMENT-GUIDE.md) | Step-by-step deployment |
| [Integration Guide](docs/INTEGRATION-GUIDE.md) | How to integrate with OpenClaw |
| [API Reference](docs/API-REFERENCE.md) | API documentation |
| [Test Report](docs/TEST-REPORT.md) | Functionality test results |
| [Use Cases](docs/USE-CASES.md) | 8 real-world use cases |

---

## 📝 Technical Blog

| # | Title | Description |
|---|-------|-------------|
| 001 | OpenClaw + SearXNG: Privacy-First AI Search | Complete introduction to the project |
| 002 | 5-Minute Deploy Your Privacy Search Engine | Quick deployment tutorial |
| 003 | AI Intelligence Officer: 30-Second Report Generation | Real-world use case demo |
| 004 | SearXNG China Optimization Guide | Baidu/Bing CN configuration |

**Coming soon on:** Zhihu, Juejin, WeChat Official Account

---

## 🧪 Testing

### Search Results

| Query | Results | Status |
|-------|---------|--------|
| test | 19 | ✅ |
| 毫米波雷达 | 18 | ✅ |
| 核聚变 | 10 | ✅ |
| 恒生科技走势 | 10 | ✅ |

**All tests passed!** Search functionality is working correctly.

---

## 🎯 OpenClaw Integration

This project is part of the OpenClaw ecosystem.

**OpenClaw Main Repo:** https://github.com/openclaw/openclaw  
**OpenClaw Status:** Most starred project on GitHub (200k+ stars)

**Our Role:**
- Privacy-focused search capability
- China-optimized (Baidu/Bing CN)
- Self-hosted deployment
- Complete documentation

---

## 🤝 Contributing

We welcome contributions!

1. **Fork** the repository
2. Create feature branch
3. Commit changes
4. Push to branch
5. Open a **Pull Request**

---

## 📄 License

MIT License - see [LICENSE](LICENSE) file.

---

<div align="center">

**⭐ If you like this project, please give it a star!**

**Built with ❤️ by Agent Team @ OpenClaw**

</div>
