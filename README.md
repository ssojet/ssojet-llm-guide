# SSOJet Frontend Integration Guides - AI-Powered

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![SSOJet](https://img.shields.io/badge/Powered%20by-SSOJet-blue)](https://ssojet.com)

> **AI-Powered Integration Guide**: Let our LLM AI prompts guide you in creating a secure and seamless SSO integration, tailored specifically to your frontend application's needs.

## 🚀 Overview

This repository provides AI-powered integration guides for implementing **"Sign in with SSO"** functionality in modern frontend applications using [SSOJet](https://ssojet.com) as an OIDC identity provider. Our LLM-powered approach generates customized, step-by-step instructions tailored to your specific frontend framework and application structure.

### What Makes This Different?

Instead of static documentation, we use AI prompts to generate **contextual, framework-specific integration guides** that adapt to:
- Your frontend framework (React, Vue, Angular, Next.js, JavaScript)
- Your existing authentication setup
- Your application architecture
- Your specific requirements

## 📚 Features

- ✅ **AI-Generated Integration Guides** - Customized for your frontend stack
- ✅ **OIDC Standard Compliance** - Following OpenID Connect best practices
- ✅ **Non-Disruptive Integration** - Preserves existing authentication flows
- ✅ **Multiple Frameworks** - Support for React, Vue, Angular, Next.js, and JavaScript
- ✅ **Production-Ready Examples** - Complete with error handling and security considerations
- ✅ **Step-by-Step Instructions** - From setup to deployment

## 🎯 Quick Start

### Using the AI Prompt Generator

1. **Clone this repository:**
   ```bash
   git clone https://github.com/ssojet/ssojet-frontend-integration-guides.git
   cd ssojet-frontend-integration-guides
   ```

2. **Choose your framework:**
   - Navigate to the framework directory (`react/`, `vue/`, `angular/`, `nextjs/`, `javascript/`)
   - Each directory contains guides, prompts, and examples

3. **Generate your custom guide:**
   - Use the `ai-prompt-template.md` from your chosen framework
   - Specify your framework version and requirements
   - Get a tailored integration guide instantly

### Prerequisites

Before starting, ensure you have:
- An active [SSOJet account](https://portal.ssojet.com/)

## 📖 Available Technologies & Frameworks

### 🎨 Frontend Technologies

| Technology | Description | Guides | Examples | Prompts |
|------------|-------------|--------|----------|---------|
| 🔷 **[React](./frontend/react/)** | Modern UI library by Facebook | [View Guides](./frontend/react/guides/) | [View Examples](./frontend/react/examples/) | [View Prompts](./frontend/react/prompts/) |
| 💚 **[Vue.js](./frontend/vue/)** | Progressive JavaScript framework | [View Guides](./frontend/vue/guides/) | [View Examples](./frontend/vue/examples/) | [View Prompts](./frontend/vue/prompts/) |
| 🔴 **[Angular](./frontend/angular/)** | Platform for building web applications | [View Guides](./frontend/angular/guides/) | [View Examples](./frontend/angular/examples/) | [View Prompts](./frontend/angular/prompts/) |
| ⚡ **[Next.js](./frontend/nextjs/)** | React framework with SSR and SSG | [View Guides](./frontend/nextjs/guides/) | [View Examples](./frontend/nextjs/examples/) | [View Prompts](./frontend/nextjs/prompts/) |
| 🟡 **[JavaScript](./frontend/javascript/)** | Vanilla JavaScript implementations | [View Guides](./frontend/javascript/guides/) | [View Examples](./frontend/javascript/examples/) | [View Prompts](./frontend/javascript/prompts/) |

### 🖥️ Backend Technologies

| Technology | Description | Guides | Examples | Prompts |
|------------|-------------|--------|----------|---------|
| 🟢 **[Express.js](./backend/express/)** | Fast, minimalist Node.js framework | [View Guides](./backend/express/guides/) | [View Examples](./backend/express/examples/) | [View Prompts](./backend/express/prompts/) |
| 🐍 **[Python](./backend/python/)** | Django, Flask, FastAPI integrations | [View Guides](./backend/python/guides/) | [View Examples](./backend/python/examples/) | [View Prompts](./backend/python/prompts/) |
| 🔵 **[Go (Golang)](./backend/golang/)** | Efficient and scalable backend | [View Guides](./backend/golang/guides/) | [View Examples](./backend/golang/examples/) | [View Prompts](./backend/golang/prompts/) |
| 🟣 **[.NET Core](./backend/dotnet/)** | Cross-platform .NET framework | [View Guides](./backend/dotnet/guides/) | [View Examples](./backend/dotnet/examples/) | [View Prompts](./backend/dotnet/prompts/) |
| ☕ **[Java EE](./backend/java-ee/)** | Enterprise Java applications | [View Guides](./backend/java-ee/guides/) | [View Examples](./backend/java-ee/examples/) | [View Prompts](./backend/java-ee/prompts/) |
| 🍃 **[Spring Boot](./backend/spring-boot/)** | Java Spring framework | [View Guides](./backend/spring-boot/guides/) | [View Examples](./backend/spring-boot/examples/) | [View Prompts](./backend/spring-boot/prompts/) |
| 🎨 **[Laravel](./backend/laravel/)** | PHP framework for web artisans | [View Guides](./backend/laravel/guides/) | [View Examples](./backend/laravel/examples/) | [View Prompts](./backend/laravel/prompts/) |
| 🐘 **[PHP](./backend/php/)** | Symfony, Slim, CodeIgniter, native PHP | [View Guides](./backend/php/guides/) | [View Examples](./backend/php/examples/) | [View Prompts](./backend/php/prompts/) |

### 📱 Native Mobile Platforms

| Platform | Description | Guides | Examples | Prompts |
|----------|-------------|--------|----------|---------|
| 🤖 **[Android](./native/android/)** | Native Android, Kotlin, Java, Compose | [View Guides](./native/android/guides/) | [View Examples](./native/android/examples/) | [View Prompts](./native/android/prompts/) |
| 🍎 **[iOS](./native/ios/)** | Native iOS, Swift, SwiftUI, Objective-C | [View Guides](./native/ios/guides/) | [View Examples](./native/ios/examples/) | [View Prompts](./native/ios/prompts/) |

### 🔧 Other Technologies

| Technology | Description | Guides | Examples | Prompts |
|------------|-------------|--------|----------|---------|
| 🤝 **[M2M (Machine-to-Machine)](./other/m2m/)** | Service-to-service authentication | [View Guides](./other/m2m/guides/) | [View Examples](./other/m2m/examples/) | [View Prompts](./other/m2m/prompts/) |

---

### Custom Guide Generation

Use our AI prompt templates to generate guides for:
- Custom frontend/backend setups
- Specific authentication libraries
- Unique application architectures
- Hybrid authentication scenarios

Navigate to the technology-specific directory and check the `/prompts/` folder for AI templates.

##  How It Works

### The AI Integration Process

1. **Provide Context**: Share details about your React application, framework, and existing authentication setup
2. **AI Analysis**: Our LLM analyzes your requirements and generates a customized guide
3. **Step-by-Step Implementation**: Follow the generated guide to modify your login page
4. **Testing & Validation**: Test both traditional and SSO login flows
5. **Production Deployment**: Deploy with confidence using best practices

## 🌟 Why SSOJet?

[SSOJet](https://ssojet.com) is a modern OIDC identity provider designed for developers:

- 🚀 **Quick Setup** - Get started in minutes
- 🔧 **Developer-Friendly** - Comprehensive APIs and SDKs
- 🔒 **Enterprise Security** - SOC 2 compliant
- 📊 **Analytics & Monitoring** - Real-time insights
- 💬 **Great Support** - Expert assistance when you need it

**[Start Free →](https://portal.ssojet.com/)**

## 📝 Contributing

We welcome contributions! Whether it's:
- New framework guides
- Improved AI prompts
- Bug fixes
- Documentation improvements
- Example applications

See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

## 🔗 Resources

### SSOJet Resources
- **[SSOJet Website](https://ssojet.com)** - Official website
- **[SSOJet Documentation](https://docs.ssojet.com)** - Complete documentation
- **[SSOJet Dashboard](https://portal.ssojet.com)** - Application management
- **[SSO Connection Setup Guide](https://docs.ssojet.com/how-to-guides/sso/integrations/)** - Configure SSO connections

### OIDC & OAuth Resources
- [OpenID Connect Specification](https://openid.net/connect/)
- [OAuth 2.0 RFC](https://tools.ietf.org/html/rfc6749)
- [OIDC Playground](https://openidconnect.net/)

## 💬 Support

Need help? We're here for you:

- **📧 Email**: [support@ssojet.com](mailto:support@ssojet.com)
- ** Issues**: [GitHub Issues](https://github.com/ssojet/ssojet-llm-guide/issues)
- **📚 Docs**: [SSOJet Documentation](https://docs.ssojet.com)

## ⭐ Star Us!

If this project helps you, please consider giving it a star! It helps others discover this resource.

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>

<p align="center">
  <a href="https://ssojet.com">Website</a> •
  <a href="https://docs.ssojet.com">Documentation</a> •
  <a href="https://twitter.com/sso_jet">Twitter</a> •
  <a href="https://github.com/ssojet">GitHub</a>
</p>
