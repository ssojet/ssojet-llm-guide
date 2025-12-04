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
- An active [SSOJet account](https://ssojet.com/signup)
- A frontend application with an existing login page
- Basic knowledge of your framework and OIDC concepts
- Node.js 18+ installed (for most frameworks)

## 📖 Available Frameworks

### 🎨 Frontend Technologies

#### 🔷 **[React](./react/README.md)** | 💚 **[Vue.js](./vue/README.md)** | 🔴 **[Angular](./angular/README.md)** | ⚡ **[Next.js](./nextjs/README.md)** | 🟡 **[JavaScript](./javascript/README.md)**

### 🖥️ Backend Technologies

#### 🟢 **[Express](./backend/express/README.md)** | 🐍 **[Python](./backend/python/README.md)** | 🔵 **[Go](./backend/golang/README.md)** | 🟣 **[.NET Core](./backend/dotnet/README.md)**

#### ☕ **[Java EE](./backend/java-ee/README.md)** | 🍃 **[Spring Boot](./backend/spring-boot/README.md)** | 🎨 **[Laravel](./backend/laravel/README.md)** | 🐘 **[PHP](./backend/php/README.md)**

### 📱 Native Mobile

#### 🤖 **[Android](./native/android/README.md)** | 🍎 **[iOS](./native/ios/README.md)**

### 🔧 Other Technologies

#### 🤝 **[M2M (Machine-to-Machine)](./other/m2m/README.md)**

---

### Custom Guide Generation

Use our AI prompt templates to generate guides for:
- Custom frontend/backend setups
- Specific authentication libraries
- Unique application architectures
- Hybrid authentication scenarios

Navigate to the technology-specific directory and check the `/prompts/` folder for AI templates.

## 🛠️ Repository Structure

```
ssojet-react-llm-guide/
├── README.md                          # This file
├── LICENSE                            # MIT License
├── CONTRIBUTING.md                    # Contribution guidelines
├── .gitignore                         # Git ignore rules
│
├── prompts/                           # AI prompt templates
│   ├── README.md                      # Prompt usage guide
│   ├── ai-prompt-template.md         # Main AI prompt template
│   └── customization-examples.md     # Example customizations
│
├── guides/                            # Pre-generated integration guides
│   ├── react-cra/                    # Create React App guide
│   │   ├── README.md
│   │   └── examples/
│   ├── nextjs-app-router/            # Next.js App Router guide
│   │   ├── README.md
│   │   └── examples/
│   ├── nextjs-pages-router/          # Next.js Pages Router guide
│   │   ├── README.md
│   │   └── examples/
│   ├── remix/                        # Remix framework guide
│   │   ├── README.md
│   │   └── examples/
│   └── vite-react/                   # Vite + React guide
│       ├── README.md
│       └── examples/
│
├── examples/                          # Complete working examples
│   ├── react-cra-example/
│   ├── nextjs-example/
│   └── remix-example/
│
├── assets/                            # Shared assets
│   ├── images/                       # Screenshots and diagrams
│   └── logos/                        # SSOJet branding
│
└── docs/                             # Additional documentation
    ├── ssojet-setup.md               # SSOJet configuration guide
    ├── oidc-concepts.md              # OIDC fundamentals
    └── troubleshooting.md            # Common issues and solutions
```

## 🔧 How It Works

### The AI Integration Process

1. **Provide Context**: Share details about your React application, framework, and existing authentication setup
2. **AI Analysis**: Our LLM analyzes your requirements and generates a customized guide
3. **Step-by-Step Implementation**: Follow the generated guide to modify your login page
4. **Testing & Validation**: Test both traditional and SSO login flows
5. **Production Deployment**: Deploy with confidence using best practices

### Integration Flow

```
┌─────────────────────┐
│  Existing Login     │
│  Page (Email/Pass)  │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ Add "Sign in with   │
│      SSO" Link      │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  User Clicks SSO    │
│  (Toggle UI)        │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  OIDC Request with  │
│   login_hint Email  │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  SSOJet Auth Flow   │
│   (OIDC Provider)   │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Handle Callback    │
│  (Authorization     │
│   Code Exchange)    │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Redirect to        │
│  Dashboard/App      │
└─────────────────────┘
```

## 🔐 Security Considerations

All generated guides include:
- **Secure token handling** - Following OAuth 2.0 best practices
- **PKCE support** - For public clients (SPAs)
- **CSRF protection** - State parameter validation
- **Session management** - Secure session handling
- **Error handling** - Graceful error responses
- **Production readiness** - Environment-specific configurations

## 🌟 Why SSOJet?

[SSOJet](https://ssojet.com) is a modern OIDC identity provider designed for developers:

- 🚀 **Quick Setup** - Get started in minutes
- 🔧 **Developer-Friendly** - Comprehensive APIs and SDKs
- 🔒 **Enterprise Security** - SOC 2 compliant
- 📊 **Analytics & Monitoring** - Real-time insights
- 💬 **Great Support** - Expert assistance when you need it

**[Start Free Trial →](https://ssojet.com/signup)**

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

### React & Framework Resources
- [React Documentation](https://react.dev)
- [Next.js Documentation](https://nextjs.org/docs)
- [Remix Documentation](https://remix.run/docs)

## 💬 Support

Need help? We're here for you:

- **📧 Email**: [support@ssojet.com](mailto:support@ssojet.com)
- ** Issues**: [GitHub Issues](https://github.com/ssojet/ssojet-react-llm-guide/issues)
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
  <a href="https://twitter.com/ssojet">Twitter</a> •
  <a href="https://github.com/ssojet">GitHub</a>
</p>
