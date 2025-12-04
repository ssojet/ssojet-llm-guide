# AI Prompt Templates

This directory contains AI prompt templates for generating customized SSOJet integration guides for Go (Golang) applications.

## 🎯 Overview

The AI prompt system allows you to generate tailored, step-by-step integration guides by providing context about your Go application and requirements. Instead of following generic documentation, you get a guide specifically designed for your backend architecture, web framework, and authentication needs.

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
- Go version (1.20+, 1.21+, 1.22+, 1.23+)
- Web framework (Gin, Echo, Fiber, Chi, Gorilla Mux, net/http)
- Template engine (html/template, templ, or API-only)
- Current authentication setup (JWT, sessions, OAuth)
- Session storage (memory, Redis, database)
- Frontend type (server-rendered, SPA, or both)
- Preferred OIDC library (coreos/go-oidc, oauth2, custom)
- Special requirements or constraints

### Step 3: Use the Prompt

1. Open `ai-prompt-template.md`
2. Read through the entire prompt
3. Replace the placeholder variables:
   - `${GO_VERSION}` → Your Go version (e.g., "1.22")
   - `${WEB_FRAMEWORK}` → Web framework (e.g., "Gin", "Echo", "Fiber")
   - `${TEMPLATE_ENGINE}` → Template engine (e.g., "html/template", "templ", "None (API)")
   - `${SESSION_STORE}` → Session storage (e.g., "Redis", "PostgreSQL", "Memory")
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
❌ "I'm using Go"
✅ "I'm using Go 1.22 with Gin framework, JWT authentication, Redis session store, and PostgreSQL database"

### 2. Provide Context
Include details about:
- Your current auth implementation (JWT, sessions, OAuth)
- Web framework and middleware setup
- Template engine and frontend architecture
- Database and ORM (GORM, sqlx, pgx)
- API structure (REST, gRPC, GraphQL)

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

### Example 1: Gin with Session-Based Authentication

```
Go Version: 1.22
Framework: Gin
Auth Library: coreos/go-oidc + golang.org/x/oauth2
Template Engine: html/template
Session Store: Redis (go-redis)
Database: PostgreSQL with GORM
Requirements: Server-side sessions, preserve existing local auth
```

### Example 2: Echo API with JWT Tokens

```
Go Version: 1.22
Framework: Echo
Auth Library: coreos/go-oidc + golang.org/x/oauth2
Frontend: Separate React SPA
Auth Type: JWT tokens (stateless)
Requirements: API-only backend, CORS configuration, token validation middleware
```

### Example 3: Fiber with MongoDB

```
Go Version: 1.21
Framework: Fiber
Auth Library: coreos/go-oidc
Database: MongoDB with mongo-go-driver
Session Store: MongoDB sessions
Template Engine: html/template
Requirements: Store user profiles in MongoDB, fast response times
```

### Example 4: Standard net/http with Chi Router

```
Go Version: 1.22
Framework: Chi router + net/http
Auth Library: coreos/go-oidc + golang.org/x/oauth2
Architecture: Microservice
Auth Type: JWT validation middleware
Requirements: Minimal dependencies, clean architecture, API gateway pattern
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

Add Go-specific requirements:

```
"For Go with Gin:
- Use middleware for authentication checks
- Implement route groups for protected endpoints
- Show proper error handling with structured logging
- Include context timeout and cancellation
- Add graceful shutdown handling"
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

### OIDC Libraries for Go
- **coreos/go-oidc** - OpenID Connect client library (most popular)
- **golang.org/x/oauth2** - Official Go OAuth 2.0 library
- **ory/fosite** - OAuth 2.0 and OpenID Connect server library
- **caos/oidc** - OpenID Connect SDK

### Popular Go Web Frameworks
- **Gin** - Fast HTTP web framework with middleware support
- **Echo** - High performance, minimalist web framework
- **Fiber** - Express-inspired web framework built on Fasthttp
- **Chi** - Lightweight, idiomatic router for building HTTP services
- **Gorilla Mux** - Powerful URL router and dispatcher

### Session & Storage Libraries
- **go-redis/redis** - Redis client for Go
- **gorilla/sessions** - Session management
- **scs** - HTTP session management for Go
- **GORM** - ORM library for Go

### Learning Resources
- [OpenID Connect Explained](https://openid.net/connect/)
- [OAuth 2.0 RFC](https://tools.ietf.org/html/rfc6749)
- [Go Web Authentication](https://www.alexedwards.net/blog/authentication-in-go)
- [Go by Example](https://gobyexample.com/)

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
