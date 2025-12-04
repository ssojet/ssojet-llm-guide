# Available Integration Guides

This directory contains configuration-specific integration guides for adding SSOJet SSO to your Spring Boot applications.

## 📚 Complete Guides

### Spring MVC (Traditional Web Apps)

#### Spring Boot MVC with Thymeleaf (Coming Soon)
- **Stack:** Spring Boot 3.x + Spring MVC + Thymeleaf
- **Features:** Spring Security OAuth2 Client, session management
- **Best For:** Server-side rendered web applications
- **Difficulty:** ⭐⭐ Intermediate

#### Spring Boot MVC with JSP (Coming Soon)
- **Stack:** Spring Boot 3.x + Spring MVC + JSP
- **Features:** Spring Security OAuth2 Client, traditional views
- **Best For:** Legacy Spring applications, JSP templates
- **Difficulty:** ⭐⭐ Intermediate

### Spring REST APIs

#### Spring Boot REST API with JWT (Coming Soon)
- **Stack:** Spring Boot 3.x + Spring Web
- **Features:** Spring Security OAuth2 Resource Server, JWT validation
- **Best For:** RESTful APIs, microservices, SPA backends
- **Difficulty:** ⭐⭐⭐ Advanced

#### Spring Boot REST API with OAuth2 (Coming Soon)
- **Stack:** Spring Boot 3.x + Spring Security OAuth2
- **Features:** OAuth2 Resource Server, custom authentication
- **Best For:** OAuth2-compliant APIs, complex authorization
- **Difficulty:** ⭐⭐⭐ Advanced

### Spring WebFlux (Reactive)

#### Spring WebFlux with OAuth2 (Coming Soon)
- **Stack:** Spring Boot 3.x + Spring WebFlux
- **Features:** Reactive OAuth2 Client, async/reactive programming
- **Best For:** High-throughput reactive applications
- **Difficulty:** ⭐⭐⭐⭐ Expert

### Spring with Keycloak

#### Spring Boot with Keycloak Adapter (Coming Soon)
- **Stack:** Spring Boot 3.x + Keycloak Spring Adapter
- **Features:** Keycloak integration, role-based access control
- **Best For:** Keycloak deployments, enterprise security
- **Difficulty:** ⭐⭐⭐ Advanced

## 🎯 Choosing the Right Guide

### Use Spring MVC with Thymeleaf if:
- ✅ Building server-rendered web applications
- ✅ Need modern template engine
- ✅ Prefer HTML5 templates
- ✅ Want Spring Boot best practices

### Use Spring MVC with JSP if:
- ✅ Have existing JSP applications
- ✅ Need legacy compatibility
- ✅ Prefer traditional Java web development
- ✅ Working with older Spring projects

### Use Spring REST API with JWT if:
- ✅ Building stateless RESTful APIs
- ✅ Need JWT token validation
- ✅ Want microservices architecture
- ✅ Prefer Resource Server pattern

### Use Spring REST API with OAuth2 if:
- ✅ Building OAuth2-compliant APIs
- ✅ Need complex authorization flows
- ✅ Want full OAuth2 features
- ✅ Require fine-grained access control

### Use Spring WebFlux if:
- ✅ Building reactive applications
- ✅ Need high throughput and scalability
- ✅ Want async/non-blocking I/O
- ✅ Prefer functional programming style

### Use Spring with Keycloak if:
- ✅ Using Keycloak as identity provider
- ✅ Need enterprise IAM features
- ✅ Want role-based access control
- ✅ Require seamless Keycloak integration

## 🔧 Quick Comparison

| Configuration | Type | Auth Type | Reactive | Difficulty | Setup Time |
|---------------|------|-----------|----------|------------|------------|
| **MVC + Thymeleaf** | Web | OAuth2 Client | ❌ | ⭐⭐ | ~30 min |
| **MVC + JSP** | Web | OAuth2 Client | ❌ | ⭐⭐ | ~30 min |
| **REST API JWT** | API | Resource Server | ❌ | ⭐⭐⭐ | ~35 min |
| **REST API OAuth2** | API | OAuth2 RS | ❌ | ⭐⭐⭐ | ~40 min |
| **WebFlux** | Reactive | OAuth2 Client | ✅ | ⭐⭐⭐⭐ | ~45 min |
| **Keycloak Adapter** | Web/API | Keycloak | ❌ | ⭐⭐⭐ | ~35 min |

## 🚀 Getting Started

1. **Choose your configuration** from the guides above
2. **Open the guide directory** (e.g., `mvc-thymeleaf/` or `rest-jwt/`)
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
- [ ] Spring Boot with Spring Authorization Server
- [ ] Spring Boot GraphQL with OAuth2
- [ ] Spring Cloud Gateway with OAuth2
- [ ] Spring Native (GraalVM) with OAuth2
- [ ] Spring Boot with Auth0 integration
- [ ] Spring Boot microservices with OAuth2

Want to see a specific configuration or pattern? [Request it here](https://github.com/ssojet/ssojet-llm-guide/issues/new)

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
