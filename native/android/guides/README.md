# Available Integration Guides

This directory contains integration guides for adding SSOJet SSO to your Android applications.

## 📚 Complete Guides

### Native Android (Kotlin)

#### Android with AppAuth (Coming Soon)
- **Stack:** Android SDK + Kotlin + AppAuth-Android
- **Features:** PKCE flow, Chrome Custom Tabs, secure token storage
- **Best For:** Modern Android apps, recommended by Google
- **Difficulty:** ⭐⭐ Intermediate

#### Android with OkHttp + Manual OIDC (Coming Soon)
- **Stack:** Android SDK + Kotlin + OkHttp
- **Features:** Custom OIDC implementation, full control
- **Best For:** Custom authentication flows, learning OIDC
- **Difficulty:** ⭐⭐⭐ Advanced

### Native Android (Java)

#### Android Java with AppAuth (Coming Soon)
- **Stack:** Android SDK + Java + AppAuth-Android
- **Features:** PKCE flow, Chrome Custom Tabs, token management
- **Best For:** Legacy Java Android apps
- **Difficulty:** ⭐⭐ Intermediate

### Jetpack Compose

#### Jetpack Compose with AppAuth (Coming Soon)
- **Stack:** Android SDK + Jetpack Compose + AppAuth
- **Features:** Declarative UI, modern Android, PKCE
- **Best For:** New Android apps with Compose UI
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

### Use Android Kotlin with AppAuth if:
- ✅ Building modern native Android apps
- ✅ Want Google-recommended OIDC library
- ✅ Need secure, standards-compliant authentication
- ✅ Prefer Kotlin for Android development

### Use Android with Manual OIDC if:
- ✅ Need full control over authentication flow
- ✅ Have custom OIDC requirements
- ✅ Want to learn OIDC internals
- ✅ Building highly customized authentication

### Use Android Java with AppAuth if:
- ✅ Maintaining existing Java Android apps
- ✅ Team prefers Java over Kotlin
- ✅ Need backward compatibility
- ✅ Want proven, stable libraries

### Use Jetpack Compose with AppAuth if:
- ✅ Building new Android apps with modern UI
- ✅ Want declarative UI framework
- ✅ Prefer Jetpack Compose over XML layouts
- ✅ Need modern Android development patterns

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
| **Android Kotlin + AppAuth** | Kotlin | AppAuth | ❌ | ⭐⭐ | ~30 min |
| **Android + Manual OIDC** | Kotlin | OkHttp | ❌ | ⭐⭐⭐ | ~45 min |
| **Android Java + AppAuth** | Java | AppAuth | ❌ | ⭐⭐ | ~30 min |
| **Compose + AppAuth** | Kotlin | AppAuth | ❌ | ⭐⭐ | ~35 min |
| **React Native** | JavaScript | app-auth | ✅ | ⭐⭐ | ~35 min |
| **Flutter** | Dart | flutter_appauth | ✅ | ⭐⭐ | ~35 min |

## 🚀 Getting Started

1. **Choose your stack** from the guides above
2. **Open the guide directory** (e.g., `kotlin-appauth/` or `react-native/`)
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
- [ ] Android with Jetpack Security for encrypted storage
- [ ] Android with Firebase Authentication + OIDC
- [ ] Xamarin.Android with OIDC
- [ ] Kotlin Multiplatform Mobile (KMM)
- [ ] Android WebView with OIDC
- [ ] Android with biometric authentication

Want to see a specific stack or pattern? [Request it here](https://github.com/ssojet/ssojet-llm-guide/issues/new)

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
