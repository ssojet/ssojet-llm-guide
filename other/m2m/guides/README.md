# Available Integration Guides

This directory contains integration guides for Machine-to-Machine (M2M) authentication using SSOJet with OAuth2 Client Credentials flow.

## 📚 Complete Guides

### Node.js / JavaScript

#### Node.js with axios (Coming Soon)
- **Stack:** Node.js + axios
- **Features:** Client Credentials flow, token caching, automatic refresh
- **Best For:** Node.js services, microservices, backend automation
- **Difficulty:** ⭐⭐ Intermediate

#### Node.js with node-fetch (Coming Soon)
- **Stack:** Node.js + node-fetch
- **Features:** Native fetch API, minimal dependencies
- **Best For:** Modern Node.js (18+), lightweight services
- **Difficulty:** ⭐ Beginner

### Python

#### Python with requests (Coming Soon)
- **Stack:** Python 3.x + requests
- **Features:** Simple HTTP client, token management
- **Best For:** Python scripts, data pipelines, automation
- **Difficulty:** ⭐ Beginner

#### Python with authlib (Coming Soon)
- **Stack:** Python 3.x + authlib
- **Features:** Full OAuth2 client, advanced features
- **Best For:** Complex OAuth2 flows, enterprise Python apps
- **Difficulty:** ⭐⭐ Intermediate

### Java

#### Java with OkHttp (Coming Soon)
- **Stack:** Java 11+ + OkHttp
- **Features:** Robust HTTP client, connection pooling
- **Best For:** Java microservices, Spring-less services
- **Difficulty:** ⭐⭐ Intermediate

#### Spring Boot WebClient (Coming Soon)
- **Stack:** Spring Boot 3.x + WebClient
- **Features:** Reactive HTTP client, OAuth2 support
- **Best For:** Spring Boot microservices, reactive apps
- **Difficulty:** ⭐⭐ Intermediate

### Go

#### Go with standard http client (Coming Soon)
- **Stack:** Go 1.21+ + net/http
- **Features:** Native HTTP client, no dependencies
- **Best For:** Go microservices, CLI tools
- **Difficulty:** ⭐⭐ Intermediate

### Other Languages

#### .NET with HttpClient (Coming Soon)
- **Stack:** .NET 8+ + HttpClient
- **Features:** Async/await, dependency injection
- **Best For:** .NET microservices, Azure functions
- **Difficulty:** ⭐⭐ Intermediate

#### PHP with Guzzle (Coming Soon)
- **Stack:** PHP 8.x + Guzzle
- **Features:** PSR-7 compliant, middleware support
- **Best For:** PHP background jobs, API integrations
- **Difficulty:** ⭐⭐ Intermediate

#### Ruby with HTTParty (Coming Soon)
- **Stack:** Ruby 3.x + HTTParty
- **Features:** Simple DSL, automatic parsing
- **Best For:** Ruby scripts, background workers
- **Difficulty:** ⭐ Beginner

## 🎯 Choosing the Right Guide

### Use Node.js with axios if:
- ✅ Building Node.js microservices or backend services
- ✅ Need robust HTTP client with interceptors
- ✅ Want built-in token caching and refresh
- ✅ Prefer popular, well-maintained libraries

### Use Node.js with node-fetch if:
- ✅ Using modern Node.js (18+) with native fetch
- ✅ Want minimal dependencies
- ✅ Prefer standard Web APIs
- ✅ Building lightweight services

### Use Python with requests if:
- ✅ Building Python automation scripts
- ✅ Need simple, straightforward HTTP client
- ✅ Want beginner-friendly library
- ✅ Building data pipelines or cron jobs

### Use Python with authlib if:
- ✅ Need full-featured OAuth2 client
- ✅ Building complex authentication flows
- ✅ Want industry-standard implementation
- ✅ Require advanced OAuth2 features

### Use Java with OkHttp if:
- ✅ Building Java microservices without Spring
- ✅ Need connection pooling and retries
- ✅ Want efficient HTTP client
- ✅ Prefer standalone Java applications

### Use Spring Boot WebClient if:
- ✅ Building Spring Boot microservices
- ✅ Want reactive, non-blocking HTTP client
- ✅ Need Spring ecosystem integration
- ✅ Prefer dependency injection

### Use Go with net/http if:
- ✅ Building Go microservices or CLI tools
- ✅ Want zero external dependencies
- ✅ Need high performance and low overhead
- ✅ Prefer Go standard library

### Use .NET HttpClient if:
- ✅ Building .NET microservices or Azure Functions
- ✅ Want async/await patterns
- ✅ Need dependency injection support
- ✅ Prefer .NET ecosystem

### Use PHP with Guzzle if:
- ✅ Building PHP background jobs or workers
- ✅ Need PSR-7 compliant HTTP client
- ✅ Want middleware and plugin support
- ✅ Building API integrations

### Use Ruby with HTTParty if:
- ✅ Building Ruby scripts or Sidekiq workers
- ✅ Want simple, elegant syntax
- ✅ Need automatic JSON parsing
- ✅ Prefer Ruby ecosystem

## 🔧 Quick Comparison

| Language/Stack | HTTP Library | Token Caching | Async | Difficulty | Setup Time |
|----------------|--------------|---------------|-------|------------|------------|
| **Node.js + axios** | axios | ✅ | ✅ | ⭐⭐ | ~20 min |
| **Node.js + fetch** | native | Manual | ✅ | ⭐ | ~15 min |
| **Python + requests** | requests | Manual | ❌ | ⭐ | ~15 min |
| **Python + authlib** | authlib | ✅ | ❌ | ⭐⭐ | ~20 min |
| **Java + OkHttp** | OkHttp | Manual | ✅ | ⭐⭐ | ~25 min |
| **Spring WebClient** | WebClient | ✅ | ✅ | ⭐⭐ | ~25 min |
| **Go + net/http** | net/http | Manual | ✅ | ⭐⭐ | ~20 min |
| **.NET HttpClient** | HttpClient | Manual | ✅ | ⭐⭐ | ~20 min |
| **PHP + Guzzle** | Guzzle | Manual | ✅ | ⭐⭐ | ~20 min |
| **Ruby + HTTParty** | HTTParty | Manual | ❌ | ⭐ | ~15 min |

## 🚀 Getting Started

1. **Choose your language/stack** from the guides above
2. **Open the guide directory** (e.g., `nodejs-axios/` or `python-requests/`)
3. **Follow the README** step-by-step
4. **Test the M2M authentication** with your SSOJet Client Credentials

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
- **M2M Authentication:** See [OAuth2 Client Credentials Flow](https://oauth.net/2/grant-types/client-credentials/)

## 🤝 Contributing

Want to add a guide for another framework?

1. Use the AI prompt template to generate the guide
2. Test the integration thoroughly
3. Submit a pull request
4. See [CONTRIBUTING.md](../../CONTRIBUTING.md) for guidelines

## 📅 Upcoming Guides

We're working on guides for:
- [ ] Rust with reqwest
- [ ] Elixir with HTTPoison
- [ ] Scala with http4s
- [ ] Kotlin with Ktor Client
- [ ] Swift for server-side (Vapor)
- [ ] Deno with native fetch

Want to see a specific language or use case? [Request it here](https://github.com/ssojet/ssojet-llm-guide/issues/new)

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
