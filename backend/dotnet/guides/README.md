# Available Integration Guides

This directory contains framework-specific integration guides for adding SSOJet SSO to your ASP.NET Core applications.

## 📚 Complete Guides

### ASP.NET Core MVC

#### ASP.NET Core MVC (Coming Soon)
- **Framework:** ASP.NET Core 8.0 MVC
- **Features:** Razor Views, Microsoft.Identity.Web, Cookie Authentication
- **Best For:** Traditional web applications with server-side rendering
- **Difficulty:** ⭐⭐ Intermediate

#### ASP.NET Core Razor Pages (Coming Soon)
- **Framework:** ASP.NET Core 8.0 Razor Pages
- **Features:** Page-based routing, Microsoft.Identity.Web
- **Best For:** Simpler page-focused applications
- **Difficulty:** ⭐ Beginner

### ASP.NET Core Web API

#### ASP.NET Core Web API with JWT (Coming Soon)
- **Framework:** ASP.NET Core 8.0 Web API
- **Features:** JWT Bearer authentication, OAuth2 Resource Server
- **Best For:** RESTful APIs, SPA backends, microservices
- **Difficulty:** ⭐⭐ Intermediate

#### ASP.NET Core Web API with Cookies (Coming Soon)
- **Framework:** ASP.NET Core 8.0 Web API
- **Features:** Cookie authentication, CORS configuration
- **Best For:** APIs consumed by same-origin clients
- **Difficulty:** ⭐⭐ Intermediate

### Blazor

#### Blazor Server (Coming Soon)
- **Framework:** Blazor Server (.NET 8)
- **Features:** Server-side rendering, SignalR, OAuth2 integration
- **Best For:** Rich interactive web apps, real-time applications
- **Difficulty:** ⭐⭐ Intermediate

#### Blazor WebAssembly (Coming Soon)
- **Framework:** Blazor WASM (.NET 8)
- **Features:** Client-side SPA, OIDC with PKCE
- **Best For:** Progressive web apps, offline-capable applications
- **Difficulty:** ⭐⭐⭐ Advanced

## 🎯 Choosing the Right Guide

### Use ASP.NET Core MVC if:
- ✅ Building traditional web applications with server-side rendering
- ✅ Need MVC pattern separation (Model-View-Controller)
- ✅ Prefer Razor views with C# code
- ✅ Require complex routing and filters

### Use ASP.NET Core Razor Pages if:
- ✅ Building simpler page-focused applications
- ✅ Want cleaner organization for CRUD operations
- ✅ Prefer convention over configuration
- ✅ Need quick development for form-based apps

### Use ASP.NET Core Web API (JWT) if:
- ✅ Building RESTful APIs for SPAs or mobile apps
- ✅ Need stateless authentication
- ✅ Want microservices architecture
- ✅ Require scalable, distributed systems

### Use ASP.NET Core Web API (Cookies) if:
- ✅ Building APIs for same-origin clients
- ✅ Prefer server-side session management
- ✅ Need traditional cookie-based authentication
- ✅ Don't need distributed token validation

### Use Blazor Server if:
- ✅ Want rich interactive UI without JavaScript
- ✅ Need real-time updates with SignalR
- ✅ Prefer server-side execution
- ✅ Building line-of-business applications

### Use Blazor WebAssembly if:
- ✅ Want client-side SPA with C#
- ✅ Need offline capabilities
- ✅ Building progressive web apps
- ✅ Prefer client-side execution

## 🔧 Quick Comparison

| Framework | UI Rendering | Auth Type | Session Storage | Difficulty | Setup Time |
|-----------|--------------|-----------|-----------------|------------|------------|
| **MVC** | Server | Cookie | Server | ⭐⭐ | ~30 min |
| **Razor Pages** | Server | Cookie | Server | ⭐ | ~25 min |
| **Web API (JWT)** | None | JWT | Stateless | ⭐⭐ | ~35 min |
| **Web API (Cookie)** | None | Cookie | Server | ⭐⭐ | ~30 min |
| **Blazor Server** | Server | Cookie | Server | ⭐⭐ | ~40 min |
| **Blazor WASM** | Client | JWT | Client | ⭐⭐⭐ | ~45 min |

## 🚀 Getting Started

1. **Choose your framework** from the guides above
2. **Open the guide directory** (e.g., `mvc/` or `web-api-jwt/`)
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
- **OIDC Concepts:** Read [OIDC Concepts](../docs/oidc-concepts.md)

## 🤝 Contributing

Want to add a guide for another framework?

1. Use the AI prompt template to generate the guide
2. Test the integration thoroughly
3. Submit a pull request
4. See [CONTRIBUTING.md](../CONTRIBUTING.md) for guidelines

## 📅 Upcoming Guides

We're working on guides for:
- [ ] ASP.NET Core MVC with Identity
- [ ] ASP.NET Core with IdentityServer integration
- [ ] ASP.NET Core Minimal APIs with JWT
- [ ] ASP.NET Core gRPC with Authentication
- [ ] Blazor Hybrid (MAUI)
- [ ] ASP.NET Core with Duende IdentityServer

Want to see a specific framework or configuration? [Request it here](https://github.com/ssojet/ssojet-llm-guide/issues/new)
- [ ] Minimal APIs with JWT
- [ ] gRPC services with OAuth2
- [ ] Azure AD B2C integration
- [ ] Multi-tenant ASP.NET Core applications

Want to see a specific scenario? [Request it here](https://github.com/ssojet/ssojet-llm-guide/issues/new)

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
