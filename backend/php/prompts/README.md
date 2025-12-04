# AI Prompt Templates

This directory contains AI prompt templates for generating customized SSOJet integration guides for native PHP applications.

## 🎯 Overview

The AI prompt system allows you to generate tailored, step-by-step integration guides by providing context about your PHP application and requirements. Instead of following generic documentation, you get a guide specifically designed for your PHP version, framework (or vanilla PHP), and authentication architecture.

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
- PHP version (7.4+, 8.0+, 8.1+, 8.2+, 8.3+)
- Framework (Slim, Symfony, CodeIgniter, Lumen, or vanilla PHP)
- Template engine (Twig, Smarty, Blade, native PHP, or API-only)
- Current authentication setup (sessions, JWT, custom)
- Session management (native PHP sessions, Redis, database)
- Database (MySQL, PostgreSQL, SQLite) and ORM (PDO, Doctrine, none)
- Composer dependencies
- Special requirements or constraints

### Step 3: Use the Prompt

1. Open `ai-prompt-template.md`
2. Read through the entire prompt
3. Replace the placeholder variables:
   - `${PHP_VERSION}` → Your PHP version (e.g., "8.2")
   - `${FRAMEWORK}` → Framework name (e.g., "Slim", "Symfony", "Vanilla PHP")
   - `${TEMPLATE_ENGINE}` → Template engine (e.g., "Twig", "Native PHP", "None (API)")
   - `${SESSION_STORAGE}` → Session storage (e.g., "Native PHP", "Redis", "Database")
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
❌ "I'm using PHP"
✅ "I'm using PHP 8.2 with Slim Framework 4, Twig templates, native PHP sessions, and MySQL with PDO"

### 2. Provide Context
Include details about:
- Your current auth implementation (sessions, JWT, custom)
- Framework and routing structure
- Template engine and frontend architecture
- Database connection and data access layer
- Composer dependencies and autoloading

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

### Example 1: Slim Framework with Twig

```
PHP Version: 8.2
Framework: Slim Framework 4
Template Engine: Twig
Auth Library: league/oauth2-client + jumbojett/openid-connect-php
Session Storage: Native PHP sessions
Database: MySQL with PDO
Requirements: Preserve existing session-based login, add SSO option
```

### Example 2: Vanilla PHP with Sessions

```
PHP Version: 8.1
Framework: None (vanilla PHP)
Template Engine: Native PHP templates
Auth Library: jumbojett/openid-connect-php
Session Storage: Native PHP sessions with Redis
Database: MySQL with mysqli
Requirements: Simple session-based authentication, minimal dependencies
```

### Example 3: Symfony with API Platform

```
PHP Version: 8.3
Framework: Symfony 7
Template Engine: API-only (JSON)
Auth Library: league/oauth2-client + lexik/jwt-authentication-bundle
Frontend: Separate Vue.js/React SPA
Auth Type: JWT tokens (stateless)
Requirements: RESTful API, CORS configuration, token validation
```

### Example 4: CodeIgniter 4 with MVC

```
PHP Version: 8.2
Framework: CodeIgniter 4
Template Engine: CodeIgniter Views
Auth Library: Custom OIDC with league/oauth2-client
Session Storage: Database-backed sessions
Database: PostgreSQL with CodeIgniter Query Builder
Requirements: MVC pattern, preserve existing auth, integrate SSO
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

Add PHP-specific requirements:

```
"For PHP:
- Use middleware/filters for authentication checks
- Implement proper session security (secure, httponly, samesite)
- Show CSRF protection for forms
- Include error handling with try-catch blocks
- Add PSR-4 autoloading with Composer
- Show proper password hashing with password_hash()"
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

### OIDC Libraries for PHP
- **jumbojett/openid-connect-php** - Lightweight OpenID Connect client
- **league/oauth2-client** - OAuth 2.0 client with provider support
- **steverhoades/oauth2-openid-connect-client** - OIDC provider for OAuth2 client
- **firebase/php-jwt** - JWT encoding and decoding library
- **lcobucci/jwt** - Modern JWT library for PHP

### Popular PHP Frameworks
- **Slim Framework** - Micro framework for APIs and web apps
- **Symfony** - Full-stack enterprise framework
- **CodeIgniter** - Lightweight MVC framework
- **Lumen** - Laravel's micro-framework
- **Yii** - High-performance PHP framework
- **CakePHP** - Rapid development framework

### Template Engines
- **Twig** - Modern, flexible template engine
- **Smarty** - Classic PHP template engine
- **Blade** - Laravel's template engine (can be used standalone)
- **Plates** - Native PHP templates (no new syntax)
- **Mustache.php** - Logic-less template engine

### Session & Database Libraries
- **PHP Sessions** - Native session handling
- **Predis** - Redis client for PHP
- **PDO** - PHP Data Objects for database access
- **Doctrine** - Full-featured ORM
- **Illuminate/Database** - Laravel's Eloquent (standalone)

### Learning Resources
- [OpenID Connect Explained](https://openid.net/connect/)
- [OAuth 2.0 RFC](https://tools.ietf.org/html/rfc6749)
- [PHP The Right Way](https://phptherightway.com/)
- [PHP Security Guide](https://phpsecurity.readthedocs.io/)

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
