# AI Prompt Templates

This directory contains AI prompt templates for generating customized SSOJet integration guides for Laravel (PHP) applications.

## 🎯 Overview

The AI prompt system allows you to generate tailored, step-by-step integration guides by providing context about your Laravel application and requirements. Instead of following generic documentation, you get a guide specifically designed for your Laravel version, authentication setup, and architectural needs.

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
- PHP version (8.1+, 8.2+, 8.3+)
- Laravel version (9.x, 10.x, 11.x)
- Frontend stack (Blade, Livewire, Inertia.js, or API-only)
- Current authentication setup (Laravel Breeze, Jetstream, Fortify, Sanctum)
- Session driver (file, database, Redis, Memcached)
- Database (MySQL, PostgreSQL, SQLite)
- Preferred OIDC library (Laravel Socialite, league/oauth2-client, custom)
- Special requirements or constraints

### Step 3: Use the Prompt

1. Open `ai-prompt-template.md`
2. Read through the entire prompt
3. Replace the placeholder variables:
   - `${PHP_VERSION}` → Your PHP version (e.g., "8.2")
   - `${LARAVEL_VERSION}` → Laravel version (e.g., "11.x")
   - `${FRONTEND_STACK}` → Frontend technology (e.g., "Blade", "Livewire", "Inertia.js")
   - `${AUTH_PACKAGE}` → Auth package (e.g., "Breeze", "Jetstream", "Socialite")
   - `${CLIENT_ID}` → Your SSOJet Client ID
   - `${CLIENT_SECRET}` → Your SSOJet Client Secret
   - `${ISSUER_URL}` → Your SSOJet Issuer URL
4. Copy the customized prompt to your LLM
5. Review and refine the generated guide

### Step 4: Refine and Iterate

- Ask follow-up questions to clarify specific sections
- Request code examples for edge cases
- Adapt the generated guide to your specific needs

## 💡 Best Practices

### 1. Be Specific
❌ "I'm using Laravel"
✅ "I'm using Laravel 11 with Breeze, Blade templates, Tailwind CSS, and Redis session storage"

### 2. Provide Context
Include details about:
- Your current auth implementation (Breeze, Jetstream, Fortify, custom)
- Frontend stack (Blade, Livewire, Inertia.js with Vue/React)
- UI framework (Tailwind CSS, Bootstrap, Alpine.js)
- Database and Eloquent models
- API requirements (Sanctum, Passport)

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

### Example 1: Laravel Breeze with Blade Templates

```
PHP Version: 8.2
Laravel Version: 11.x
Auth Package: Laravel Breeze
Frontend: Blade templates with Tailwind CSS
Session Driver: Redis
Database: MySQL with Eloquent ORM
Requirements: Preserve existing email/password login, add SSO option
```

### Example 2: Laravel Jetstream with Livewire

```
PHP Version: 8.3
Laravel Version: 11.x
Auth Package: Laravel Jetstream (Livewire stack)
Frontend: Livewire + Alpine.js + Tailwind
Session Driver: Database
Requirements: Team-based SSO, integrate with existing Jetstream features
```

### Example 3: Laravel API with Sanctum

```
PHP Version: 8.2
Laravel Version: 10.x
Auth Package: Laravel Sanctum
Frontend: Separate Vue.js/React SPA
Auth Type: Token-based (SPA authentication)
Requirements: API-only backend, CORS configuration, token management
```

### Example 4: Laravel Inertia.js with Vue

```
PHP Version: 8.2
Laravel Version: 11.x
Auth Package: Laravel Breeze (Inertia stack)
Frontend: Inertia.js with Vue 3 + Tailwind
Session Driver: Redis
Requirements: SSR support, preserve Inertia routing, maintain session state
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

Add Laravel-specific requirements:

```
"For Laravel:
- Use middleware for authentication checks
- Implement service providers for OIDC configuration
- Show proper route protection with auth middleware
- Include controller-level authorization
- Add custom guards and providers
- Show event listeners for authentication events"
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

### OIDC Libraries for Laravel
- **Laravel Socialite** - Official OAuth/OIDC authentication for Laravel
- **league/oauth2-client** - OAuth 2.0 client library for PHP
- **jumbojett/openid-connect-php** - OpenID Connect client library
- **steverhoades/oauth2-openid-connect-client** - OIDC provider for OAuth2 client

### Laravel Authentication Packages
- **Laravel Breeze** - Minimal authentication scaffolding
- **Laravel Jetstream** - Feature-rich authentication with teams support
- **Laravel Fortify** - Headless authentication backend
- **Laravel Sanctum** - Token-based API authentication
- **Laravel Passport** - Full OAuth2 server implementation

### Frontend Stacks for Laravel
- **Blade** - Laravel's native templating engine
- **Livewire** - Full-stack framework for dynamic interfaces
- **Inertia.js** - Modern monolith with Vue/React/Svelte
- **Alpine.js** - Lightweight JavaScript framework

### Session Drivers
- **File** - File-based sessions (default)
- **Database** - Database-backed sessions
- **Redis** - High-performance Redis sessions
- **Memcached** - Distributed caching system

### Learning Resources
- [OpenID Connect Explained](https://openid.net/connect/)
- [OAuth 2.0 RFC](https://tools.ietf.org/html/rfc6749)
- [Laravel Authentication](https://laravel.com/docs/authentication)
- [Laravel Socialite](https://laravel.com/docs/socialite)

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
