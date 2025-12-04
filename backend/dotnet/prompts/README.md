# AI Prompt Templates

This directory contains AI prompt templates for generating customized SSOJet integration guides for ASP.NET Core applications.

## 🎯 Overview

The AI prompt system allows you to generate tailored, step-by-step integration guides by providing context about your ASP.NET Core application and requirements. Instead of following generic documentation, you get a guide specifically designed for your stack and architecture.

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
- ASP.NET Core version (6.0, 7.0, 8.0, 9.0)
- Project type (MVC, Razor Pages, Web API, Blazor Server/WASM)
- Current authentication setup (Cookie, JWT, Identity)
- Existing login page structure
- Authentication library (Microsoft.Identity.Web, IdentityServer, custom)
- Special requirements or constraints

### Step 3: Use the Prompt

1. Open `ai-prompt-template.md`
2. Read through the entire prompt
3. Replace the placeholder variables:
   - `${DOTNET_VERSION}` → Your ASP.NET Core version (e.g., "8.0")
   - `${PROJECT_TYPE}` → Project type (e.g., "MVC", "Razor Pages", "Web API")
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
❌ "I'm using ASP.NET Core"
✅ "I'm using ASP.NET Core 8.0 MVC with Cookie Authentication, Entity Framework Core, and Identity"

### 2. Provide Context
Include details about:
- Your current auth implementation (Cookie, JWT, Identity)
- Database provider (SQL Server, PostgreSQL, SQLite)
- UI framework (Bootstrap, Tailwind, Razor Views)
- API endpoints (if applicable)
- Middleware configuration

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

### Example 1: ASP.NET Core MVC with Identity

```
Version: ASP.NET Core 8.0
Project Type: MVC
Auth Library: Microsoft.AspNetCore.Identity
Database: SQL Server with Entity Framework Core
Requirements: Preserve existing username/password login, add SSO option
```

### Example 2: ASP.NET Core Web API with JWT

```
Version: ASP.NET Core 8.0
Project Type: Web API
Auth Library: Microsoft.AspNetCore.Authentication.JwtBearer
Frontend: Separate React SPA
Requirements: JWT-based authentication, stateless API
```

### Example 3: Blazor Server with Cookie Authentication

```
Version: ASP.NET Core 8.0
Project Type: Blazor Server
Auth Library: Microsoft.AspNetCore.Authentication.OpenIdConnect
Requirements: Server-side authentication, maintain session state
```

### Example 4: Razor Pages with Custom Authentication

```
Version: ASP.NET Core 8.0
Project Type: Razor Pages
Existing Auth: Custom cookie-based authentication
Requirements: Add SSO as additional authentication scheme
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

Add ASP.NET Core-specific requirements:

```
"For ASP.NET Core MVC:
- Use middleware for authentication
- Implement authorization policies
- Show controller-level authorization attributes
- Include proper error handling and redirects"
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

### OIDC Libraries for ASP.NET Core
- **Microsoft.AspNetCore.Authentication.OpenIdConnect** - Official OIDC authentication
- **Microsoft.Identity.Web** - Microsoft Identity platform integration
- **IdentityServer** - Open-source OIDC and OAuth 2.0 framework
- **Duende.IdentityServer** - Commercial version of IdentityServer

### Learning Resources
- [OpenID Connect Explained](https://openid.net/connect/)
- [OAuth 2.0 RFC](https://tools.ietf.org/html/rfc6749)
- [ASP.NET Core Authentication](https://learn.microsoft.com/en-us/aspnet/core/security/authentication/)
- [Microsoft.Identity.Web Documentation](https://learn.microsoft.com/en-us/azure/active-directory/develop/microsoft-identity-web)

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
