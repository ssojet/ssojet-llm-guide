# AI Prompt Templates

This directory contains AI prompt templates for generating customized SSOJet integration guides for iOS applications.

## 🎯 Overview

The AI prompt system allows you to generate tailored, step-by-step integration guides by providing context about your iOS application and requirements. Instead of following generic documentation, you get a guide specifically designed for your iOS version, architecture, and authentication needs.

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
- iOS deployment target (iOS 13+, 14+, 15+, 16+, 17+, 18+)
- Programming language (Swift, Objective-C, or both)
- Architecture pattern (MVVM, MVI, VIPER, Clean Architecture)
- UI framework (SwiftUI, UIKit, or hybrid)
- Current authentication setup (custom, Firebase Auth, existing OAuth)
- Navigation (NavigationStack, UINavigationController, Coordinator pattern)
- Dependency management (SPM, CocoaPods, Carthage, manual)
- Preferred OIDC library (AppAuth-iOS, OAuthSwift, custom)
- Special requirements or constraints

### Step 3: Use the Prompt

1. Open `ai-prompt-template.md`
2. Read through the entire prompt
3. Replace the placeholder variables:
   - `${IOS_VERSION}` → iOS deployment target (e.g., "iOS 16")
   - `${LANGUAGE}` → Programming language (e.g., "Swift", "Objective-C")
   - `${ARCHITECTURE}` → Architecture pattern (e.g., "MVVM", "VIPER")
   - `${UI_FRAMEWORK}` → UI framework (e.g., "SwiftUI", "UIKit")
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
❌ "I'm using iOS"
✅ "I'm using iOS 17 with Swift, MVVM architecture, SwiftUI, Combine for reactive programming, and CoreData for persistence"

### 2. Provide Context
Include details about:
- Your current auth implementation (custom, Firebase, OAuth)
- Architecture pattern and project structure
- UI framework and navigation setup
- Data layer (CoreData, Realm, UserDefaults, Keychain)
- Dependency management and third-party libraries

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

### Example 1: Modern iOS with SwiftUI

```
iOS Version: iOS 17
Language: Swift 5.9
Architecture: MVVM with Combine
UI Framework: SwiftUI
Auth Library: AppAuth-iOS with PKCE
Navigation: NavigationStack
Dependency Management: Swift Package Manager
Data Layer: SwiftData + Keychain
Requirements: Secure token storage, biometric authentication, deep linking
```

### Example 2: iOS with UIKit

```
iOS Version: iOS 14
Language: Swift 5.7
Architecture: MVVM
UI Framework: UIKit with Storyboards
Auth Library: AppAuth-iOS
Navigation: UINavigationController
Dependency Management: CocoaPods
Data Layer: CoreData + Keychain
Requirements: Support older iOS versions, preserve existing login
```

### Example 3: Objective-C Legacy App

```
iOS Version: iOS 13
Language: Objective-C
Architecture: MVC
UI Framework: UIKit (XIBs)
Auth Library: AppAuth-iOS
Navigation: UINavigationController
Dependency Management: CocoaPods
Data Layer: NSUserDefaults + Keychain Services
Requirements: Legacy codebase support, minimal Swift code
```

### Example 4: iOS with Firebase Integration

```
iOS Version: iOS 16
Language: Swift 5.8
Architecture: MVVM
UI Framework: SwiftUI
Auth Library: AppAuth-iOS + Firebase Auth
Navigation: NavigationStack
Dependency Management: Swift Package Manager
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

Add iOS-specific requirements:

```
"For iOS:
- Use PKCE for secure mobile authentication
- Implement secure token storage with Keychain Services
- Show proper URL scheme configuration in Info.plist
- Include biometric authentication (Touch ID/Face ID)
- Add proper lifecycle handling for auth state
- Show App Transport Security (ATS) configuration"
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

### OIDC Libraries for iOS
- **AppAuth-iOS** - Official OpenID Connect client (recommended)
- **OAuthSwift** - OAuth library for iOS
- **Heimdall.swift** - Easy OAuth 2 library for Swift
- **SwiftyOAuth** - Swift OAuth library

### iOS Frameworks & Architecture
- **SwiftUI** - Modern declarative UI framework
- **UIKit** - Traditional imperative UI framework
- **Combine** - Reactive programming framework (iOS 13+)
- **async/await** - Modern concurrency (iOS 15+)
- **SwiftData** - Data persistence framework (iOS 17+)
- **CoreData** - Object graph and persistence framework
- **Realm** - Mobile database alternative

### Dependency Management
- **Swift Package Manager (SPM)** - Native Swift dependency manager
- **CocoaPods** - Dependency manager for iOS projects
- **Carthage** - Decentralized dependency manager
- **Manual Integration** - Direct framework integration

### Security & Storage
- **Keychain Services** - Secure credential storage
- **LocalAuthentication** - Touch ID/Face ID integration
- **CryptoKit** - Cryptographic operations (iOS 13+)
- **App Transport Security (ATS)** - Secure network connections

### Networking & Data
- **URLSession** - Native HTTP client
- **Alamofire** - Elegant HTTP networking in Swift
- **Moya** - Network abstraction layer
- **Codable** - Native JSON encoding/decoding
- **SwiftyJSON** - JSON parsing library

### Learning Resources
- [OpenID Connect Explained](https://openid.net/connect/)
- [OAuth 2.0 RFC](https://tools.ietf.org/html/rfc6749)
- [Apple Developer - Authentication](https://developer.apple.com/documentation/authenticationservices)
- [AppAuth-iOS Guide](https://github.com/openid/AppAuth-iOS)

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
