# SSOJet Android Integration Guide

This guide helps you integrate **SSOJet** (OIDC authentication) into your **Android** applications using industry-standard libraries.

## 📋 Prerequisites

- Android Studio installed
- An SSOJet account with an OIDC application configured
- Client ID, Client Secret, and Redirect URI from your SSOJet dashboard
- Basic knowledge of Android development (Kotlin/Java)

## 🔧 Recommended Libraries

### AppAuth-Android (Recommended)
The official Android OIDC client library maintained by OpenID Foundation.

**Why AppAuth?**
- ✅ Full OIDC compliance
- ✅ Built-in PKCE support
- ✅ Secure token storage
- ✅ Chrome Custom Tabs integration
- ✅ Actively maintained

**Installation:**
```gradle
dependencies {
    implementation 'net.openid:appauth:0.11.1'
}
```

**Documentation:** [AppAuth-Android GitHub](https://github.com/openid/AppAuth-Android)

## 📂 Directory Structure

```
android/
├── README.md                    # This file
├── examples/                    # Example Android projects
│   └── README.md
├── guides/                      # Step-by-step integration guides
│   └── README.md
└── prompts/                     # AI prompt templates for code generation
    ├── README.md
    └── ai-prompt-template.md
```

## 🚀 Getting Started

1. **Explore Examples**: Check the `examples/` folder for working Android projects
2. **Read Integration Guides**: Follow the `guides/` for detailed setup instructions
3. **Use AI Prompts**: Leverage `prompts/` to generate custom integration code with LLMs

## 🔗 Useful Links

- [SSOJet Dashboard](https://portal.ssojet.com/)
- [SSOJet OIDC Documentation](https://docs.ssojet.com)
- [AppAuth-Android](https://github.com/openid/AppAuth-Android)
- [OIDC Concepts](../../oidc-concepts.md)

## 📝 Common Use Cases

- Mobile app authentication with SSOJet
- Social login integration (Google, Facebook, etc.)
- Single Sign-On (SSO) for enterprise apps
- Secure API access with access tokens
- Biometric authentication flow

## 🆘 Need Help?

- Review the [OIDC Concepts](../../oidc-concepts.md) for authentication fundamentals
- Use the AI prompt templates to generate working code
