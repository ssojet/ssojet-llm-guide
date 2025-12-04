# Available Integration Guides

This directory contains framework-specific integration guides for adding SSOJet SSO to your PHP applications.

## 📚 Complete Guides

### Symfony

#### Symfony with Guard/Security Component (Coming Soon)
- **Framework:** Symfony 6.x/7.x
- **Features:** Security Component, OAuth2 Bundle, Twig templates
- **Best For:** Enterprise PHP applications, robust security
- **Difficulty:** ⭐⭐⭐ Advanced

#### Symfony API with JWT (Coming Soon)
- **Framework:** Symfony 6.x/7.x + API Platform
- **Features:** LexikJWTAuthenticationBundle, API Platform
- **Best For:** RESTful APIs, headless backends
- **Difficulty:** ⭐⭐⭐ Advanced

### Slim Framework

#### Slim Framework 4 (Coming Soon)
- **Framework:** Slim 4
- **Features:** PSR-7, league/oauth2-client, PHP-DI
- **Best For:** Lightweight APIs, microservices
- **Difficulty:** ⭐⭐ Intermediate

### CodeIgniter

#### CodeIgniter 4 (Coming Soon)
- **Framework:** CodeIgniter 4
- **Features:** CodeIgniter OAuth2, Session library
- **Best For:** Rapid development, traditional MVC
- **Difficulty:** ⭐⭐ Intermediate

### Vanilla PHP

#### Native PHP with Sessions (Coming Soon)
- **Framework:** Native PHP 8.x
- **Features:** league/oauth2-client, native sessions
- **Best For:** Custom applications, learning OIDC
- **Difficulty:** ⭐⭐⭐ Advanced

#### Native PHP with Composer (Coming Soon)
- **Framework:** Native PHP 8.x + Composer
- **Features:** jumbojett/openid-connect-php, modern PHP
- **Best For:** Custom projects, maximum control
- **Difficulty:** ⭐⭐ Intermediate

## 🎯 Choosing the Right Guide

### Use Symfony if:
- ✅ Building enterprise-grade applications
- ✅ Need robust security and architecture
- ✅ Prefer full-featured framework
- ✅ Want mature ecosystem and bundles

### Use Symfony API if:
- ✅ Building RESTful or GraphQL APIs
- ✅ Need API Platform features
- ✅ Want automatic documentation
- ✅ Prefer modern API development

### Use Slim Framework if:
- ✅ Building lightweight APIs or microservices
- ✅ Need minimal overhead
- ✅ Want PSR-7 compliance
- ✅ Prefer micro-framework approach

### Use CodeIgniter if:
- ✅ Need rapid application development
- ✅ Prefer traditional MVC pattern
- ✅ Want simple, straightforward framework
- ✅ Building medium-sized applications

### Use Native PHP with Sessions if:
- ✅ Learning OIDC from scratch
- ✅ Need maximum control
- ✅ Have custom requirements
- ✅ Building simple applications

### Use Native PHP with Composer if:
- ✅ Want modern PHP practices
- ✅ Need lightweight solution with packages
- ✅ Prefer dependency management
- ✅ Building custom projects

## 🔧 Quick Comparison

| Framework | Type | OAuth2 Library | Templating | Difficulty | Setup Time |
|-----------|------|----------------|------------|------------|------------|
| **Symfony** | Full-stack | KnpU OAuth2 | Twig | ⭐⭐⭐ | ~40 min |
| **Symfony API** | API | JWT Bundle | None | ⭐⭐⭐ | ~45 min |
| **Slim** | Micro | league/oauth2 | Custom | ⭐⭐ | ~30 min |
| **CodeIgniter** | MVC | Custom | CI Views | ⭐⭐ | ~30 min |
| **Native PHP** | Custom | league/oauth2 | Native | ⭐⭐⭐ | ~35 min |
| **PHP + Composer** | Custom | openid-connect | Custom | ⭐⭐ | ~25 min |

## 🚀 Getting Started

1. **Choose your framework** from the guides above
2. **Open the guide directory** (e.g., `symfony/` or `slim/`)
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
- [ ] CakePHP with OAuth2
- [ ] Yii2 Framework
- [ ] Phalcon with OIDC
- [ ] WordPress with OpenID Connect
- [ ] Drupal with OAuth2
- [ ] Laminas (Zend Framework)

Want to see a specific framework or setup? [Request it here](https://github.com/ssojet/ssojet-llm-guide/issues/new)

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
