# SSOJet iOS Integration Guide

This guide helps you integrate **SSOJet** (OIDC authentication) into your **iOS** applications using industry-standard libraries.

## 📋 Prerequisites

- Xcode installed
- An SSOJet account with an OIDC application configured
- Client ID, Client Secret, and Redirect URI from your SSOJet dashboard
- Basic knowledge of iOS development (Swift/Objective-C)

## 🔧 Recommended Libraries

### AppAuth-iOS (Recommended)
The official iOS OIDC client library maintained by OpenID Foundation.

**Why AppAuth?**
- ✅ Full OIDC compliance
- ✅ Built-in PKCE support
- ✅ Secure token storage with Keychain
- ✅ SFSafariViewController integration
- ✅ Actively maintained

**Installation (CocoaPods):**
```ruby
pod 'AppAuth'
```

**Installation (Swift Package Manager):**
```swift
dependencies: [
    .package(url: "https://github.com/openid/AppAuth-iOS.git", from: "1.6.0")
]
```

**Documentation:** [AppAuth-iOS GitHub](https://github.com/openid/AppAuth-iOS)

## 📂 Directory Structure

```
ios/
├── README.md                    # This file
├── examples/                    # Example iOS projects
│   └── README.md
├── guides/                      # Step-by-step integration guides
│   └── README.md
└── prompts/                     # AI prompt templates for code generation
    ├── README.md
    └── ai-prompt-template.md
```

## 🚀 Getting Started

1. **Explore Examples**: Check the `examples/` folder for working iOS projects
2. **Read Integration Guides**: Follow the `guides/` for detailed setup instructions
3. **Use AI Prompts**: Leverage `prompts/` to generate custom integration code with LLMs

## 🔗 Useful Links

- [SSOJet Dashboard](https://portal.ssojet.com)
- [SSOJet OIDC Documentation](https://docs.ssojet.com)
- [AppAuth-iOS](https://github.com/openid/AppAuth-iOS)
- [OIDC Concepts](../../oidc-concepts.md)

## 📝 Common Use Cases

- Mobile app authentication with SSOJet
- Social login integration (Apple, Google, etc.)
- Single Sign-On (SSO) for enterprise apps
- Secure API access with access tokens
- Face ID / Touch ID authentication flow

## 🆘 Need Help?

- Review the [OIDC Concepts](../../oidc-concepts.md) for authentication fundamentals
- Use the AI prompt templates to generate working code
