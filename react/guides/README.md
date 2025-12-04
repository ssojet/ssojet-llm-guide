# Available Integration Guides

This directory contains framework-specific integration guides for adding SSOJet SSO to your React applications.

## 📚 Complete Guides

### Next.js

#### [Next.js with App Router](./nextjs-app-router/)
- **Framework:** Next.js 14+
- **Features:** App Router, Server Components, NextAuth v5
- **Best For:** New Next.js projects, modern React patterns
- **Difficulty:** ⭐⭐ Intermediate

#### Next.js with Pages Router (Coming Soon)
- **Framework:** Next.js 13
- **Features:** Pages Router, API Routes, NextAuth v4
- **Best For:** Existing Next.js projects, traditional SSR
- **Difficulty:** ⭐⭐ Intermediate

### React SPA

#### Create React App (Coming Soon)
- **Framework:** Create React App
- **Features:** React Router, oidc-client-ts, PKCE
- **Best For:** Traditional React SPAs, client-side authentication
- **Difficulty:** ⭐⭐⭐ Advanced (requires understanding of PKCE)

#### Vite + React (Coming Soon)
- **Framework:** Vite + React 18
- **Features:** Fast HMR, React Router, oidc-client-ts
- **Best For:** Modern React development, performance-focused apps
- **Difficulty:** ⭐⭐⭐ Advanced

### Remix

#### Remix (Coming Soon)
- **Framework:** Remix v2
- **Features:** Loaders, Actions, remix-auth, Server-side sessions
- **Best For:** Full-stack React apps, progressive enhancement
- **Difficulty:** ⭐⭐ Intermediate

## 🎯 Choosing the Right Guide

### Use Next.js (App Router) if:
- ✅ Building a new project with Next.js 14+
- ✅ Want to use latest React features (Server Components)
- ✅ Need SEO and SSR
- ✅ Prefer server-side session management

### Use Next.js (Pages Router) if:
- ✅ Have an existing Next.js project with Pages Router
- ✅ Familiar with traditional Next.js patterns
- ✅ Need backward compatibility
- ✅ Want stable, well-documented APIs

### Use Create React App if:
- ✅ Building a pure client-side application
- ✅ Have an existing CRA project
- ✅ Don't need server-side rendering
- ✅ Want simple deployment (static hosting)

### Use Vite + React if:
- ✅ Want fastest development experience
- ✅ Building a modern SPA
- ✅ Need optimal build performance
- ✅ Prefer modern tooling

### Use Remix if:
- ✅ Want full-stack React capabilities
- ✅ Need progressive enhancement
- ✅ Prefer form-based workflows
- ✅ Want server-side by default

## 🔧 Quick Comparison

| Framework | SSR | Client-Side | Session Storage | Difficulty | Setup Time |
|-----------|-----|-------------|-----------------|------------|------------|
| **Next.js (App)** | ✅ | ✅ | Server | ⭐⭐ | ~30 min |
| **Next.js (Pages)** | ✅ | ✅ | Server | ⭐⭐ | ~30 min |
| **CRA** | ❌ | ✅ | Client | ⭐⭐⭐ | ~45 min |
| **Vite** | ❌ | ✅ | Client | ⭐⭐⭐ | ~45 min |
| **Remix** | ✅ | ✅ | Server | ⭐⭐ | ~40 min |

## 🚀 Getting Started

1. **Choose your framework** from the guides above
2. **Open the guide directory** (e.g., `nextjs-app-router/`)
3. **Follow the README** step-by-step
4. **Test the integration** with your SSOJet account

## 📝 Custom Guide Generation

Don't see your framework or setup? Use our **AI prompt template** to generate a custom guide:

1. Navigate to [`/prompts/`](/prompts/)
2. Open `ai-prompt-template.md`
3. Customize for your framework
4. Use with your preferred LLM (ChatGPT, Claude, etc.)
5. Get a tailored integration guide!

## 🆘 Need Help?

- **General Questions:** See [main README](../README.md)
- **Setup Issues:** Check [SSOJet Setup Guide](../docs/ssojet-setup.md)
- **Troubleshooting:** See [Troubleshooting Guide](../docs/troubleshooting.md)
- **OIDC Concepts:** Read [OIDC Concepts](../docs/oidc-concepts.md)

## 🤝 Contributing

Want to add a guide for another framework?

1. Use the AI prompt template to generate the guide
2. Test the integration thoroughly
3. Submit a pull request
4. See [CONTRIBUTING.md](../CONTRIBUTING.md) for guidelines

## 📅 Upcoming Guides

We're working on guides for:
- [ ] React Native (Expo)
- [ ] Gatsby
- [ ] Astro with React
- [ ] Electron with React
- [ ] React + Express (separate frontend/backend)
- [ ] React + NestJS

Want to see a specific framework? [Request it here](https://github.com/ssojet/ssojet-react-llm-guide/issues/new)

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
