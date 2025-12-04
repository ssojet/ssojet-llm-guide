# Available Integration Guides

This directory contains integration guides for adding SSOJet SSO to your Express.js (Node.js) applications.

## 📚 Complete Guides

### Express with Server-Side Rendering

#### Express with EJS Templates (Coming Soon)
- **Framework:** Express 4.x + EJS
- **Features:** Passport.js, express-session, Redis sessions
- **Best For:** Traditional server-rendered web applications
- **Difficulty:** ⭐⭐ Intermediate

#### Express with Pug Templates (Coming Soon)
- **Framework:** Express 4.x + Pug
- **Features:** Passport.js, express-session, cookie-based auth
- **Best For:** Server-side MVC applications
- **Difficulty:** ⭐⭐ Intermediate

### Express REST API

#### Express API with JWT (Coming Soon)
- **Framework:** Express 4.x + JWT
- **Features:** openid-client, JWT validation, stateless authentication
- **Best For:** RESTful APIs, SPA backends, microservices
- **Difficulty:** ⭐⭐ Intermediate

#### Express API with Sessions (Coming Soon)
- **Framework:** Express 4.x
- **Features:** Passport.js, express-session, Redis/MongoDB sessions
- **Best For:** APIs with session-based authentication
- **Difficulty:** ⭐⭐ Intermediate

### Express with Frontend Frameworks

#### Express + React SPA (Coming Soon)
- **Framework:** Express backend + React frontend
- **Features:** CORS, Passport.js, separate deployment
- **Best For:** Decoupled architecture, separate teams
- **Difficulty:** ⭐⭐⭐ Advanced

#### Express + Vue SPA (Coming Soon)
- **Framework:** Express backend + Vue.js frontend
- **Features:** CORS, JWT authentication, API-first design
- **Best For:** Modern SPA with Node.js backend
- **Difficulty:** ⭐⭐⭐ Advanced

## 🎯 Choosing the Right Guide

### Use Express with EJS/Pug if:
- ✅ Building traditional server-rendered applications
- ✅ Need SEO-friendly content
- ✅ Prefer server-side session management
- ✅ Want simple template-based rendering

### Use Express API with JWT if:
- ✅ Building stateless RESTful APIs
- ✅ Need token-based authentication
- ✅ Want scalable microservices architecture
- ✅ Prefer decoupled frontend/backend

### Use Express API with Sessions if:
- ✅ Building session-based APIs
- ✅ Need server-side state management
- ✅ Prefer traditional cookie-based authentication
- ✅ Want centralized session storage (Redis/MongoDB)

### Use Express + React/Vue SPA if:
- ✅ Building modern single-page applications
- ✅ Need separate frontend/backend deployment
- ✅ Want independent team workflows
- ✅ Prefer API-first design

## 🔧 Quick Comparison

| Framework | Rendering | Auth Type | Session Storage | Difficulty | Setup Time |
|-----------|-----------|-----------|-----------------|------------|------------|
| **Express + EJS** | Server | Session | Redis/Memory | ⭐⭐ | ~30 min |
| **Express + Pug** | Server | Session | Redis/Memory | ⭐⭐ | ~30 min |
| **Express API (JWT)** | None | JWT | Stateless | ⭐⭐ | ~25 min |
| **Express API (Session)** | None | Session | Redis/MongoDB | ⭐⭐ | ~30 min |
| **Express + React** | Client | JWT | Client | ⭐⭐⭐ | ~45 min |
| **Express + Vue** | Client | JWT | Client | ⭐⭐⭐ | ~45 min |

## 🚀 Getting Started

1. **Choose your setup** from the guides above
2. **Open the guide directory** (e.g., `express-jwt-api/` or `express-ejs/`)
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

## 🤝 Contributing

Want to add a guide for another framework?

1. Use the AI prompt template to generate the guide
2. Test the integration thoroughly
3. Submit a pull request
4. See [CONTRIBUTING.md](../CONTRIBUTING.md) for guidelines

## 📅 Upcoming Guides

We're working on guides for:
- [ ] Express with Handlebars
- [ ] Express GraphQL API with JWT
- [ ] Express with TypeScript
- [ ] Express microservices architecture
- [ ] Express with Passport Local + OIDC
- [ ] Express with Socket.io authentication

Want to see a specific setup or pattern? [Request it here](https://github.com/ssojet/ssojet-llm-guide/issues/new)

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
