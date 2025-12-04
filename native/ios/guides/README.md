# Available Integration Guides

This directory contains integration guides for adding SSOJet SSO to your iOS applications.

## 📚 Complete Guides

### Native iOS (Swift)

#### iOS Swift with AppAuth (Coming Soon)
- **Stack:** iOS SDK + Swift + AppAuth-iOS
- **Features:** PKCE flow, ASWebAuthenticationSession, secure keychain storage
- **Best For:** Modern iOS apps, recommended by Apple
- **Difficulty:** ⭐⭐ Intermediate

#### iOS Swift with Manual OIDC (Coming Soon)
- **Stack:** iOS SDK + Swift + URLSession
- **Features:** Custom OIDC implementation, full control
- **Best For:** Custom authentication flows, learning OIDC
- **Difficulty:** ⭐⭐⭐ Advanced

### Native iOS (Objective-C)

#### iOS Objective-C with AppAuth (Coming Soon)
- **Stack:** iOS SDK + Objective-C + AppAuth-iOS
- **Features:** PKCE flow, secure authentication, token management
- **Best For:** Legacy Objective-C iOS apps
- **Difficulty:** ⭐⭐ Intermediate

### SwiftUI

#### SwiftUI with AppAuth (Coming Soon)
- **Stack:** iOS SDK + SwiftUI + AppAuth
- **Features:** Declarative UI, modern iOS, PKCE
- **Best For:** New iOS apps with SwiftUI
- **Difficulty:** ⭐⭐ Intermediate

### React Native

#### React Native with react-native-app-auth (Coming Soon)
- **Stack:** React Native + react-native-app-auth
- **Features:** Cross-platform, AppAuth wrapper, PKCE
- **Best For:** Cross-platform mobile apps
- **Difficulty:** ⭐⭐ Intermediate

### Flutter

#### Flutter with flutter_appauth (Coming Soon)
- **Stack:** Flutter + flutter_appauth
- **Features:** Cross-platform, Dart, PKCE flow
- **Best For:** Flutter mobile applications
- **Difficulty:** ⭐⭐ Intermediate

## 🎯 Choosing the Right Guide

### Use iOS Swift with AppAuth if:
- ✅ Building modern native iOS apps
- ✅ Want Apple-recommended OIDC library
- ✅ Need secure, standards-compliant authentication
- ✅ Prefer Swift for iOS development

### Use iOS with Manual OIDC if:
- ✅ Need full control over authentication flow
- ✅ Have custom OIDC requirements
- ✅ Want to learn OIDC internals
- ✅ Building highly customized authentication

### Use iOS Objective-C with AppAuth if:
- ✅ Maintaining existing Objective-C iOS apps
- ✅ Team prefers Objective-C over Swift
- ✅ Need backward compatibility
- ✅ Want proven, stable libraries

### Use SwiftUI with AppAuth if:
- ✅ Building new iOS apps with modern UI
- ✅ Want declarative UI framework
- ✅ Prefer SwiftUI over UIKit
- ✅ Need modern iOS development patterns

### Use React Native if:
- ✅ Building cross-platform mobile apps (iOS + Android)
- ✅ Team has React/JavaScript expertise
- ✅ Want code sharing between platforms
- ✅ Need faster development cycles

### Use Flutter if:
- ✅ Building cross-platform with Dart
- ✅ Want high-performance native UI
- ✅ Need beautiful, customizable widgets
- ✅ Prefer Flutter ecosystem

## 🔧 Quick Comparison

| Stack | Language | Library | Cross-Platform | Difficulty | Setup Time |
|-------|----------|---------|----------------|------------|------------|
| **iOS Swift + AppAuth** | Swift | AppAuth | ❌ | ⭐⭐ | ~30 min |
| **iOS + Manual OIDC** | Swift | URLSession | ❌ | ⭐⭐⭐ | ~45 min |
| **iOS Objective-C + AppAuth** | Objective-C | AppAuth | ❌ | ⭐⭐ | ~30 min |
| **SwiftUI + AppAuth** | Swift | AppAuth | ❌ | ⭐⭐ | ~35 min |
| **React Native** | JavaScript | app-auth | ✅ | ⭐⭐ | ~35 min |
| **Flutter** | Dart | flutter_appauth | ✅ | ⭐⭐ | ~35 min |

## 🚀 Getting Started

1. **Choose your stack** from the guides above
2. **Open the guide directory** (e.g., `swift-appauth/` or `swiftui/`)
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
- [ ] iOS with Sign in with Apple + OIDC
- [ ] iOS with Firebase Authentication + OIDC
- [ ] Xamarin.iOS with OIDC
- [ ] Kotlin Multiplatform Mobile (KMM)
- [ ] iOS with Face ID/Touch ID integration
- [ ] iOS Safari Extension with OIDC

Want to see a specific stack or pattern? [Request it here](https://github.com/ssojet/ssojet-llm-guide/issues/new)

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
