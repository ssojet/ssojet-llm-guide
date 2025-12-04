# AI Prompt Templates

This directory contains AI prompt templates for generating customized SSOJet integration guides for Android applications.

## 🎯 Overview

The AI prompt system allows you to generate tailored, step-by-step integration guides by providing context about your Android application and requirements. Instead of following generic documentation, you get a guide specifically designed for your Android version, architecture, and authentication needs.

## 📚 Available Templates

### Main Template
- **[ai-prompt-template.md](./ai-prompt-template.md)** - The primary prompt template for generating integration guides

## 🚀 How to Use

### Step 1: Choose Your LLM

You can use any of these LLMs:
- ChatGPT (GPT-4 or GPT-4 Turbo recommended)
- Claude (Claude 3 Opus or Sonnet recommended)
- Gemini Pro
- Any other capable LLM with good instruction-following abilities

### Step 2: Prepare Your Context

Gather information about your application:
- Android SDK version (API 21+, 24+, 26+, 30+, 34+)
- Programming language (Kotlin, Java, or both)
- Architecture pattern (MVVM, MVI, MVP, Clean Architecture)
- UI framework (Jetpack Compose, XML Views, or hybrid)
- Current authentication setup (custom, Firebase Auth, existing OAuth)
- Navigation (Jetpack Navigation, custom)
- Dependency injection (Hilt, Dagger, Koin, manual)
- Preferred OIDC library (AppAuth-Android, oauth2-oidc-sdk, custom)
- Special requirements or constraints

### Step 3: Use the Prompt

1. Open `ai-prompt-template.md`
2. Read through the entire prompt
3. Replace the placeholder variables:
   - `${ANDROID_SDK}` → Target Android SDK (e.g., "API 34")
   - `${LANGUAGE}` → Programming language (e.g., "Kotlin", "Java")
   - `${ARCHITECTURE}` → Architecture pattern (e.g., "MVVM", "Clean Architecture")
   - `${UI_FRAMEWORK}` → UI framework (e.g., "Jetpack Compose", "XML Views")
   - `${CLIENT_ID}` → Your SSOJet Client ID
   - `${CLIENT_SECRET}` → Your SSOJet Client Secret (or PKCE for mobile)
   - `${ISSUER_URL}` → Your SSOJet Issuer URL
4. Copy the customized prompt to your LLM
5. Review and refine the generated guide

### Step 4: Refine and Iterate

- Ask follow-up questions to clarify specific sections
- Request code examples for edge cases
- Adapt the generated guide to your specific needs

## 💡 Best Practices

### 1. Be Specific
❌ "I'm using Android"
✅ "I'm using Android SDK 34 with Kotlin, MVVM architecture, Jetpack Compose UI, Hilt DI, and Room database"

### 2. Provide Context
Include details about:
- Your current auth implementation (custom, Firebase, OAuth)
- Architecture pattern and project structure
- UI framework and navigation setup
- Data layer (Room, Retrofit, DataStore)
- Dependency injection framework

### 3. Mention Constraints
Share any limitations:
- Can't modify certain files
- Must maintain backward compatibility
- Specific security requirements
- Performance considerations

### 4. Test the Output
- Always review generated code for security issues
- Test in a development environment first
- Validate OIDC flow with SSOJet
- Check error handling and edge cases

## 🎨 Customization Examples

### Example 1: Modern Android with Jetpack Compose

```
Android SDK: API 34 (Android 14)
Language: Kotlin
Architecture: MVVM with Clean Architecture
UI Framework: Jetpack Compose
Auth Library: AppAuth-Android with PKCE
Navigation: Jetpack Navigation Compose
DI: Hilt
Data Layer: Room + Retrofit + DataStore
Requirements: Secure token storage, biometric authentication, deep linking
```

### Example 2: Android with XML Views

```
Android SDK: API 26 (Android 8.0)
Language: Kotlin
Architecture: MVVM
UI Framework: XML Views with ViewBinding
Auth Library: AppAuth-Android
Navigation: Jetpack Navigation (XML)
DI: Dagger 2
Data Layer: Room + Retrofit + SharedPreferences
Requirements: Support older Android versions, preserve existing login
```

### Example 3: Java-based Android App

```
Android SDK: API 24 (Android 7.0)
Language: Java
Architecture: MVP
UI Framework: XML Views
Auth Library: oauth2-oidc-sdk-android
Navigation: Manual fragment transactions
DI: Manual dependency injection
Data Layer: SQLite + OkHttp + SharedPreferences
Requirements: Legacy codebase support, minimal dependencies
```

### Example 4: Android with Firebase Integration

```
Android SDK: API 30 (Android 11)
Language: Kotlin
Architecture: MVVM
UI Framework: Jetpack Compose
Auth Library: AppAuth-Android + Firebase Auth
Navigation: Jetpack Navigation Compose
DI: Koin
Data Layer: Firestore + Firebase Storage
Requirements: Integrate SSO with existing Firebase Auth, maintain Cloud Firestore
```

## 📖 Prompt Template Structure

The main prompt template follows this structure:

1. **Task Requirements** - Defines the objective and scope
2. **Target Audience** - Specifies who the guide is for
3. **Step-by-Step Instructions** - Detailed generation steps:
   - Context setting
   - Prerequisites
   - SSOJet setup
   - Project modification
   - Testing procedures
4. **Additional Considerations** - Security, error handling, etc.
5. **Customization Instructions** - How to adapt for different frameworks

## 🔧 Advanced Usage

### Combining with Examples

For better results, provide working code samples:

```
"Here's my current login component:
[paste your code]

Please generate a guide showing exactly how to modify this."
```

### Multi-Step Refinement

1. Generate initial guide
2. Ask for specific section improvements
3. Request additional examples
4. Clarify unclear steps

### Framework-Specific Requests

Add Android-specific requirements:

```
"For Android:
- Use PKCE for secure mobile authentication
- Implement secure token storage with EncryptedSharedPreferences
- Show proper deep linking configuration with AndroidManifest
- Include biometric authentication (fingerprint/face)
- Add proper lifecycle handling for auth state
- Show ProGuard/R8 rules for production builds"
```

## 🛠️ Troubleshooting

### Issue: Generated guide is too generic
**Solution**: Provide more specific details about your setup and requirements

### Issue: Code examples don't match my structure
**Solution**: Share your actual code structure and ask for adaptation

### Issue: Missing error handling
**Solution**: Explicitly request error handling examples in the prompt

### Issue: Security concerns
**Solution**: Ask the LLM to explain security considerations and best practices

## 📚 Additional Resources

### SSOJet Resources
- [SSOJet Documentation](https://docs.ssojet.com)
- [SSO Connection Setup](https://docs.ssojet.com/how-to-guides/sso/integrations/)
- [API Endpoints](https://docs.ssojet.com/api-reference/)

### OIDC Libraries for Android
- **AppAuth-Android** - Official OpenID Connect client (recommended)
- **oauth2-oidc-sdk-android** - OAuth 2.0 and OIDC SDK
- **ScribeJava** - OAuth library for Java/Android
- **Nimbus OAuth 2.0 SDK** - Comprehensive OAuth/OIDC implementation

### Android Architecture Components
- **Jetpack Compose** - Modern declarative UI toolkit
- **ViewModel** - Lifecycle-aware data holder
- **LiveData / StateFlow** - Observable data holder
- **Room** - SQLite database abstraction
- **Navigation** - Fragment/Composable navigation
- **DataStore** - Modern data storage (replaces SharedPreferences)
- **WorkManager** - Background task scheduling

### Dependency Injection
- **Hilt** - Android-specific DI built on Dagger
- **Dagger 2** - Compile-time dependency injection
- **Koin** - Lightweight Kotlin DI framework
- **Manual DI** - Constructor injection pattern

### Security & Storage
- **EncryptedSharedPreferences** - Encrypted key-value storage
- **Keystore** - Hardware-backed key storage
- **BiometricPrompt** - Fingerprint/face authentication
- **SafetyNet** - Device integrity verification

### Networking & Data
- **Retrofit** - Type-safe HTTP client
- **OkHttp** - HTTP client and interceptor
- **Gson / Moshi / Kotlinx.serialization** - JSON parsing
- **Coil / Glide** - Image loading

### Learning Resources
- [OpenID Connect Explained](https://openid.net/connect/)
- [OAuth 2.0 RFC](https://tools.ietf.org/html/rfc6749)
- [Android Developers - Authentication](https://developer.android.com/training/id-auth)
- [AppAuth-Android Guide](https://github.com/openid/AppAuth-Android)

## 🤝 Contributing

Have ideas for improving the prompt templates? See [CONTRIBUTING.md](../CONTRIBUTING.md) for guidelines.

### Ways to Contribute:
- Improve prompt clarity
- Add framework-specific examples
- Share successful customizations
- Report issues with generated guides

## 💬 Support

Need help using the prompts?
- 📧 Email: [support@ssojet.com](mailto:support@ssojet.com)
- 🐛 Issues: [GitHub Issues](https://github.com/ssojet/ssojet-llm-guide/issues)

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
