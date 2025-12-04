# Available Integration Guides

This directory contains application server and technology-specific integration guides for adding SSOJet SSO to your Java EE / Jakarta EE applications.

## 📚 Complete Guides

### WildFly / JBoss

#### WildFly with Jakarta Security (Coming Soon)
- **Server:** WildFly 30+ (Jakarta EE 10)
- **Features:** Jakarta Security API, JSF, CDI, JPA
- **Best For:** Modern Jakarta EE applications, enterprise apps
- **Difficulty:** ⭐⭐ Intermediate

#### WildFly with Keycloak Adapter (Coming Soon)
- **Server:** WildFly 26+ (Jakarta EE 8)
- **Features:** Keycloak adapter, JAAS, container security
- **Best For:** Keycloak integration, existing WildFly apps
- **Difficulty:** ⭐⭐ Intermediate

### Payara Server

#### Payara with MicroProfile JWT (Coming Soon)
- **Server:** Payara 6+ (Jakarta EE 10)
- **Features:** MicroProfile JWT, JAX-RS, REST APIs
- **Best For:** Microservices, cloud-native applications
- **Difficulty:** ⭐⭐ Intermediate

#### Payara with JSF and Sessions (Coming Soon)
- **Server:** Payara 5+ (Jakarta EE 8)
- **Features:** JSF, CDI, container-managed security
- **Best For:** Traditional web applications with UI
- **Difficulty:** ⭐⭐ Intermediate

### Apache TomEE

#### TomEE with Custom OIDC (Coming Soon)
- **Server:** Apache TomEE 9+ (Jakarta EE 9)
- **Features:** JAX-RS, CDI, Apache CXF, custom auth
- **Best For:** Lightweight Java EE apps, Tomcat users
- **Difficulty:** ⭐⭐⭐ Advanced

### Open Liberty

#### Liberty with MicroProfile (Coming Soon)
- **Server:** Open Liberty 23.x (Jakarta EE 10)
- **Features:** MicroProfile JWT, Social Login, Liberty features
- **Best For:** Microservices, IBM ecosystem, cloud deployment
- **Difficulty:** ⭐⭐ Intermediate

## 🎯 Choosing the Right Guide

### Use WildFly if:
- ✅ Need full Jakarta EE 10 support with modern features
- ✅ Want robust, production-ready application server
- ✅ Building enterprise applications with JSF or REST
- ✅ Prefer open-source with strong community support

### Use Payara if:
- ✅ Need Jakarta EE with cloud-native features
- ✅ Want MicroProfile support for microservices
- ✅ Building applications for Kubernetes/Docker
- ✅ Prefer enterprise support and commercial backing

### Use Apache TomEE if:
- ✅ Have existing Tomcat applications to migrate
- ✅ Want lightweight Java EE with Apache ecosystem
- ✅ Need Apache CXF for web services
- ✅ Prefer simpler, more focused application server

### Use Open Liberty if:
- ✅ Building cloud-native microservices
- ✅ Want MicroProfile with IBM ecosystem integration
- ✅ Need flexible, modular server configuration
- ✅ Prefer lightweight, fast startup times

## 🔧 Quick Comparison

| Server | Jakarta EE | Session Support | MicroProfile | Difficulty | Setup Time |
|--------|-----------|-----------------|--------------|------------|------------|
| **WildFly** | 10 | ✅ Native | ❌ | ⭐⭐ | ~30 min |
| **Payara** | 10 | ✅ Native | ✅ Full | ⭐⭐ | ~30 min |
| **TomEE** | 9.1 | ✅ Native | ❌ | ⭐ | ~25 min |
| **Liberty** | 10 | ✅ Native | ✅ Full | ⭐⭐ | ~30 min |

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

## 🤝 Contributing

Want to add a guide for another framework?

1. Use the AI prompt template to generate the guide
2. Test the integration thoroughly
3. Submit a pull request
4. See [CONTRIBUTING.md](../../CONTRIBUTING.md) for guidelines

## 📅 Upcoming Guides

We're working on guides for:
- [ ] GlassFish with Jakarta Security
- [ ] Oracle WebLogic with OPSS
- [ ] IBM WebSphere with Liberty Profile
- [ ] Apache Tomcat with Custom OIDC
- [ ] Quarkus with OpenID Connect
- [ ] Helidon with MicroProfile JWT

Want to see a specific server or configuration? [Request it here](https://github.com/ssojet/ssojet-llm-guide/issues/new)

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
