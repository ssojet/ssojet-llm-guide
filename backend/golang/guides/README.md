# Available Integration Guides

This directory contains framework-specific integration guides for adding SSOJet SSO to your Go (Golang) applications.

## 📚 Complete Guides

### Gin Framework

#### Gin with Session Authentication (Coming Soon)
- **Framework:** Gin
- **Features:** Middleware, Sessions, coreos/go-oidc, Redis
- **Best For:** RESTful APIs, web applications with sessions
- **Difficulty:** ⭐⭐ Intermediate

#### Gin with JWT Authentication (Coming Soon)
- **Framework:** Gin
- **Features:** JWT middleware, stateless auth, token validation
- **Best For:** Microservices, API-only applications
- **Difficulty:** ⭐⭐ Intermediate

### Echo Framework

#### Echo with OIDC (Coming Soon)
- **Framework:** Echo
- **Features:** Middleware, JWT, OAuth2, coreos/go-oidc
- **Best For:** High-performance APIs, microservices
- **Difficulty:** ⭐⭐ Intermediate

### Fiber Framework

#### Fiber with Session Auth (Coming Soon)
- **Framework:** Fiber
- **Features:** Fast HTTP, sessions, middleware, OIDC
- **Best For:** High-performance web apps, Express-like API
- **Difficulty:** ⭐⭐ Intermediate

### Standard Library

#### net/http with Chi Router (Coming Soon)
- **Framework:** Chi router + net/http
- **Features:** Minimal dependencies, middleware, OIDC
- **Best For:** Lightweight services, standard library preference
- **Difficulty:** ⭐⭐⭐ Advanced

## 🎯 Choosing the Right Guide

### Use Gin if:
- ✅ Want a fast, popular web framework with excellent documentation
- ✅ Need middleware support and routing flexibility
- ✅ Building RESTful APIs or web applications
- ✅ Prefer Express.js-like API design

### Use Echo if:
- ✅ Need high-performance HTTP server
- ✅ Want minimalist, optimized framework
- ✅ Building microservices or APIs
- ✅ Prefer clean, simple architecture

### Use Fiber if:
- ✅ Need the fastest Go web framework
- ✅ Want Express.js-inspired API in Go
- ✅ Building high-throughput applications
- ✅ Prefer modern, developer-friendly syntax

### Use net/http with Chi if:
- ✅ Want minimal dependencies and standard library approach
- ✅ Need complete control over HTTP handling
- ✅ Building lightweight services
- ✅ Prefer idiomatic Go patterns

## 🔧 Quick Comparison

| Framework | Performance | Middleware | Session Support | Difficulty | Setup Time |
|-----------|-------------|------------|-----------------|------------|------------|
| **Gin** | ⚡⚡⚡ Fast | ✅ Excellent | ✅ Built-in | ⭐⭐ | ~30 min |
| **Echo** | ⚡⚡⚡⚡ Very Fast | ✅ Excellent | ✅ Built-in | ⭐⭐ | ~30 min |
| **Fiber** | ⚡⚡⚡⚡⚡ Fastest | ✅ Excellent | ✅ Built-in | ⭐⭐ | ~30 min |
| **Chi + net/http** | ⚡⚡⚡ Fast | ✅ Good | ⚙️ Manual | ⭐⭐⭐ | ~40 min |

## 🚀 Getting Started

1. **Choose your framework** from the guides above
2. **Open the guide directory** (e.g., `nextjs-app-router/`)
3. **Follow the README** step-by-step
4. **Test the integration** with your SSOJet account

## 📝 Custom Guide Generation

Don't see your framework or setup? Use our **AI prompt template** to generate a custom guide:

1. Navigate to `/prompts/`
2. Open `ai-prompt-template.md`
3. Customize for your framework
4. Use with your preferred LLM (ChatGPT, Claude, etc.)
5. Get a tailored integration guide!

## 🆘 Need Help?

- **General Questions:** See [main README](../../README.md)
- **Setup Issues:** Check [SSOJet Setup Guide](../../ssojet-setup.md)
- **OIDC Concepts:** Read [OIDC Concepts](../../oidc-concepts.md)
- **Go OIDC Libraries:** Check [coreos/go-oidc](https://github.com/coreos/go-oidc)

## 🤝 Contributing

Want to add a guide for another framework?

1. Use the AI prompt template to generate the guide
2. Test the integration thoroughly
3. Submit a pull request
4. See [CONTRIBUTING.md](../../CONTRIBUTING.md) for guidelines

## 📅 Upcoming Guides

We're working on guides for:
- [ ] Gin with Session Authentication
- [ ] Gin with JWT Authentication
- [ ] Echo with OIDC
- [ ] Fiber with Session Auth
- [ ] Chi Router with net/http
- [ ] Gorilla Mux
- [ ] Beego Framework
- [ ] Buffalo Framework

Want to see a specific framework? [Request it here](https://github.com/ssojet/ssojet-llm-guide/issues/new)

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
