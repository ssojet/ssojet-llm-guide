# AI Prompt Templates

This directory contains AI prompt templates for generating customized SSOJet integration guides for Express.js (Node.js) applications.

## 🎯 Overview

The AI prompt system allows you to generate tailored, step-by-step integration guides by providing context about your Express.js application and requirements. Instead of following generic documentation, you get a guide specifically designed for your backend architecture and authentication needs.

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
- Node.js version (16+, 18+, 20+, 22+)
- Express.js version (4.x or 5.x)
- View engine (EJS, Pug, Handlebars, or API-only)
- Current authentication setup (sessions, JWT, OAuth)
- Session store (memory, Redis, MongoDB, PostgreSQL)
- Frontend type (server-rendered, SPA, or both)
- Preferred OIDC library (Passport.js, openid-client, etc.)
- Special requirements or constraints

### Step 3: Use the Prompt

1. Open `ai-prompt-template.md`
2. Read through the entire prompt
3. Replace the placeholder variables:
   - `${NODE_VERSION}` → Your Node.js version (e.g., "20.x")
   - `${EXPRESS_VERSION}` → Your Express version (e.g., "4.18.x")
   - `${VIEW_ENGINE}` → Template engine (e.g., "EJS", "Pug", "None (API)")
   - `${SESSION_STORE}` → Session storage (e.g., "Redis", "MongoDB", "Memory")
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
❌ "I'm using Express"
✅ "I'm using Express 4.18 with Passport.js, session-based auth, EJS templates, and Redis session store"

### 2. Provide Context
Include details about:
- Your current auth implementation (JWT, sessions, OAuth)
- Template engine and frontend architecture
- Session management and storage
- Database and ORM (Mongoose, Sequelize, Prisma)
- API structure (REST, GraphQL)

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

### Example 1: Express with Passport.js and Sessions

```
Node.js: 20.x
Express: 4.18.x
Auth Library: Passport.js with passport-openidconnect
View Engine: EJS
Session Store: Redis (connect-redis)
Requirements: Server-side sessions, preserve existing local auth strategy
```

### Example 2: Express API with JWT Tokens

```
Node.js: 20.x
Express: 4.18.x
Auth Library: openid-client
Frontend: Separate React/Vue SPA
Auth Type: JWT tokens (stateless)
Requirements: API-only backend, CORS configuration, token validation
```

### Example 3: Express with MongoDB and Mongoose

```
Node.js: 18.x
Express: 4.18.x
Auth Library: Passport.js with passport-openidconnect
Database: MongoDB with Mongoose
Session Store: connect-mongo
View Engine: Pug
Requirements: Store user profiles in MongoDB, session persistence
```

### Example 4: Express Microservice with OAuth2

```
Node.js: 20.x
Express: 4.18.x
Auth Library: openid-client
Architecture: Microservice
Requirements: Client credentials flow, M2M authentication, no UI
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

Add Express-specific requirements:

```
"For Express.js:
- Use middleware for authentication checks
- Implement route protection with custom middleware
- Show session management with Redis
- Include error handling and logging (Winston/Morgan)
- Add CSRF protection for forms"
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

### OIDC Libraries for Express.js
- **passport-openidconnect** - Passport strategy for OIDC (session-based)
- **openid-client** - Certified OpenID Connect client library
- **express-openid-connect** - Auth0's Express OIDC middleware
- **passport-oauth2** - Generic OAuth 2.0 strategy for Passport

### Session Stores
- **connect-redis** - Redis session store
- **connect-mongo** - MongoDB session store
- **express-session** - Default in-memory session store
- **connect-pg-simple** - PostgreSQL session store

### Learning Resources
- [OpenID Connect Explained](https://openid.net/connect/)
- [OAuth 2.0 RFC](https://tools.ietf.org/html/rfc6749)
- [Express.js Authentication](https://expressjs.com/en/advanced/best-practice-security.html)
- [Passport.js Documentation](https://www.passportjs.org/)

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
