# Available Integration Guides

This directory contains framework-specific integration guides for adding SSOJet SSO to your Python applications.

## 📚 Complete Guides

### Django

#### Django with django-allauth (Coming Soon)
- **Framework:** Django 5.x
- **Features:** django-allauth, social authentication, session management
- **Best For:** Full-featured web applications, admin panels
- **Difficulty:** ⭐⭐ Intermediate

#### Django with Social Auth (Coming Soon)
- **Framework:** Django 5.x
- **Features:** social-auth-app-django, OAuth2, customizable
- **Best For:** Custom authentication flows
- **Difficulty:** ⭐⭐ Intermediate

### Django REST Framework

#### Django REST with JWT (Coming Soon)
- **Framework:** Django REST Framework 3.x
- **Features:** djangorestframework-simplejwt, token authentication
- **Best For:** RESTful APIs, SPA backends, mobile apps
- **Difficulty:** ⭐⭐⭐ Advanced

#### Django REST with OAuth2 Toolkit (Coming Soon)
- **Framework:** Django REST Framework 3.x
- **Features:** django-oauth-toolkit, OAuth2 provider
- **Best For:** OAuth2 provider, third-party integrations
- **Difficulty:** ⭐⭐⭐ Advanced

### Flask

#### Flask with Flask-Login (Coming Soon)
- **Framework:** Flask 3.x
- **Features:** Flask-Login, Authlib, session management
- **Best For:** Lightweight web applications, microservices
- **Difficulty:** ⭐⭐ Intermediate

#### Flask API with JWT (Coming Soon)
- **Framework:** Flask 3.x
- **Features:** Flask-JWT-Extended, stateless authentication
- **Best For:** RESTful APIs, minimal setup
- **Difficulty:** ⭐⭐ Intermediate

### FastAPI

#### FastAPI with OAuth2 (Coming Soon)
- **Framework:** FastAPI 0.1x
- **Features:** OAuth2PasswordBearer, async support, Pydantic
- **Best For:** Modern async APIs, high performance
- **Difficulty:** ⭐⭐ Intermediate

#### FastAPI with Authlib (Coming Soon)
- **Framework:** FastAPI 0.1x
- **Features:** Authlib, OIDC integration, async
- **Best For:** OIDC-compliant APIs, async workflows
- **Difficulty:** ⭐⭐⭐ Advanced

## 🎯 Choosing the Right Guide

### Use Django with django-allauth if:
- ✅ Building full-featured web applications
- ✅ Need admin panel and ORM
- ✅ Want batteries-included framework
- ✅ Prefer comprehensive authentication solution

### Use Django with Social Auth if:
- ✅ Need custom authentication flows
- ✅ Want more control over OAuth2
- ✅ Building complex authentication logic
- ✅ Require multiple social providers

### Use Django REST with JWT if:
- ✅ Building stateless RESTful APIs
- ✅ Need token-based authentication
- ✅ Want DRF integration
- ✅ Prefer JWT tokens

### Use Django REST with OAuth2 Toolkit if:
- ✅ Building OAuth2 provider
- ✅ Need authorization server
- ✅ Want third-party integrations
- ✅ Require OAuth2 compliance

### Use Flask with Flask-Login if:
- ✅ Building lightweight web applications
- ✅ Need simple session management
- ✅ Prefer minimal framework
- ✅ Want flexibility and control

### Use Flask API with JWT if:
- ✅ Building minimal RESTful APIs
- ✅ Need stateless authentication
- ✅ Want fast development
- ✅ Prefer lightweight solution

### Use FastAPI with OAuth2 if:
- ✅ Building modern async APIs
- ✅ Need high performance
- ✅ Want automatic documentation
- ✅ Prefer type hints and Pydantic

### Use FastAPI with Authlib if:
- ✅ Need full OIDC compliance
- ✅ Building async workflows
- ✅ Want advanced OAuth2 features
- ✅ Require professional-grade security

## 🔧 Quick Comparison

| Framework | Type | Auth Library | Async | Difficulty | Setup Time |
|-----------|------|--------------|-------|------------|------------|
| **Django + allauth** | Full-stack | django-allauth | ❌ | ⭐⭐ | ~30 min |
| **Django + Social** | Full-stack | social-auth | ❌ | ⭐⭐ | ~30 min |
| **Django REST JWT** | API | simplejwt | ❌ | ⭐⭐⭐ | ~35 min |
| **Django REST OAuth2** | API | oauth-toolkit | ❌ | ⭐⭐⭐ | ~40 min |
| **Flask + Login** | Web | Flask-Login | ❌ | ⭐⭐ | ~25 min |
| **Flask API JWT** | API | JWT-Extended | ❌ | ⭐⭐ | ~25 min |
| **FastAPI OAuth2** | API | OAuth2Bearer | ✅ | ⭐⭐ | ~30 min |
| **FastAPI Authlib** | API | Authlib | ✅ | ⭐⭐⭐ | ~35 min |

## 🚀 Getting Started

1. **Choose your framework** from the guides above
2. **Open the guide directory** (e.g., `django-allauth/` or `fastapi-oauth2/`)
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
- [ ] Tornado with OAuth2
- [ ] Starlette with OIDC
- [ ] Bottle Framework
- [ ] Pyramid with OAuth2
- [ ] Sanic with JWT
- [ ] Quart (async Flask)

Want to see a specific framework or setup? [Request it here](https://github.com/ssojet/ssojet-llm-guide/issues/new)

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
