# Available Integration Guides

This directory contains stack-specific integration guides for adding SSOJet SSO to your Laravel applications.

## 📚 Complete Guides

### Laravel Breeze

#### Laravel Breeze with Blade (Coming Soon)
- **Stack:** Laravel 11 + Breeze + Blade
- **Features:** Socialite, Session authentication, Blade templates
- **Best For:** Traditional server-rendered Laravel applications
- **Difficulty:** ⭐⭐ Intermediate

#### Laravel Breeze with Inertia + Vue (Coming Soon)
- **Stack:** Laravel 11 + Breeze + Inertia.js + Vue 3
- **Features:** Socialite, SPA-like experience, Vue components
- **Best For:** Modern Laravel with Vue frontend
- **Difficulty:** ⭐⭐ Intermediate

#### Laravel Breeze with Inertia + React (Coming Soon)
- **Stack:** Laravel 11 + Breeze + Inertia.js + React
- **Features:** Socialite, SPA-like experience, React components
- **Best For:** Modern Laravel with React frontend
- **Difficulty:** ⭐⭐ Intermediate

### Laravel Jetstream

#### Laravel Jetstream with Livewire (Coming Soon)
- **Stack:** Laravel 11 + Jetstream + Livewire
- **Features:** Socialite, Team management, Livewire components
- **Best For:** Full-featured applications with teams
- **Difficulty:** ⭐⭐⭐ Advanced

#### Laravel Jetstream with Inertia + Vue (Coming Soon)
- **Stack:** Laravel 11 + Jetstream + Inertia.js + Vue 3
- **Features:** Socialite, Team management, Vue components
- **Best For:** Enterprise applications with SPA experience
- **Difficulty:** ⭐⭐⭐ Advanced

### Laravel API

#### Laravel Sanctum API (Coming Soon)
- **Stack:** Laravel 11 + Sanctum
- **Features:** Token-based API authentication, SPA support
- **Best For:** RESTful APIs, mobile backends, SPAs
- **Difficulty:** ⭐⭐ Intermediate

#### Laravel Passport API (Coming Soon)
- **Stack:** Laravel 11 + Passport
- **Features:** Full OAuth2 server, personal access tokens
- **Best For:** OAuth2 provider, complex API authentication
- **Difficulty:** ⭐⭐⭐ Advanced

## 🎯 Choosing the Right Guide

### Use Laravel Breeze with Blade if:
- ✅ Building traditional server-rendered applications
- ✅ Need simple, lightweight authentication
- ✅ Prefer Blade templating
- ✅ Want quick setup for standard web apps

### Use Laravel Breeze with Inertia if:
- ✅ Want SPA-like experience with Laravel routing
- ✅ Prefer Vue or React for frontend
- ✅ Need modern UI without API complexity
- ✅ Building single-page applications

### Use Laravel Jetstream with Livewire if:
- ✅ Building feature-rich applications
- ✅ Need team management capabilities
- ✅ Prefer server-side rendering with reactivity
- ✅ Want full-stack Laravel development

### Use Laravel Jetstream with Inertia if:
- ✅ Need enterprise-level features
- ✅ Want team management with SPA experience
- ✅ Prefer Vue for complex UI
- ✅ Building scalable applications

### Use Laravel Sanctum API if:
- ✅ Building RESTful APIs for SPAs or mobile
- ✅ Need simple token authentication
- ✅ Want SPA authentication with cookies
- ✅ Prefer lightweight API security

### Use Laravel Passport API if:
- ✅ Need full OAuth2 server capabilities
- ✅ Building API for third-party integrations
- ✅ Want personal access tokens
- ✅ Require complex authentication flows

## 🔧 Quick Comparison

| Stack | Frontend | Auth Package | Features | Difficulty | Setup Time |
|-------|----------|--------------|----------|------------|------------|
| **Breeze + Blade** | Blade | Socialite | Simple | ⭐ | ~20 min |
| **Breeze + Inertia** | Vue/React | Socialite | SPA-like | ⭐⭐ | ~30 min |
| **Jetstream + Livewire** | Livewire | Socialite | Teams, 2FA | ⭐⭐⭐ | ~40 min |
| **Jetstream + Inertia** | Vue | Socialite | Teams, SPA | ⭐⭐⭐ | ~40 min |
| **Sanctum API** | API | Sanctum | Token auth | ⭐⭐ | ~30 min |
| **Passport API** | API | Passport | OAuth2 | ⭐⭐⭐ | ~45 min |

## 🚀 Getting Started

1. **Choose your stack** from the guides above
2. **Open the guide directory** (e.g., `breeze-blade/` or `sanctum-api/`)
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
4. See [CONTRIBUTING.md](../../CONTRIBUTING.md) for guidelines

## 📅 Upcoming Guides

We're working on guides for:
- [ ] Laravel Fortify with custom authentication
- [ ] Laravel with Filament admin panel
- [ ] Laravel Octane with OIDC
- [ ] Laravel + Nuxt.js (separate frontend/backend)
- [ ] Lumen API with JWT
- [ ] Laravel with multi-tenancy

Want to see a specific stack or configuration? [Request it here](https://github.com/ssojet/ssojet-llm-guide/issues/new)

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
