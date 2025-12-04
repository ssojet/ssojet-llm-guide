# AI Prompt Templates

This directory contains AI prompt templates for generating customized SSOJet integration guides for Machine-to-Machine (M2M) authentication.

## 🎯 Overview

The AI prompt system allows you to generate tailored, step-by-step integration guides by providing context about your M2M service and requirements. Instead of following generic documentation, you get a guide specifically designed for your platform, OAuth 2.0 Client Credentials flow, and service architecture.

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

Gather information about your service:
- Platform/Language (Node.js, Python, Go, Java, .NET, PHP, Ruby, etc.)
- Service type (microservice, API gateway, background worker, cron job)
- Authentication flow (Client Credentials, Service Account)
- Current authentication setup (API keys, existing OAuth, none)
- Token storage (memory, Redis, database, file system)
- Deployment environment (Docker, Kubernetes, serverless, VM)
- HTTP client library preferences
- Special requirements or constraints

### Step 3: Use the Prompt

1. Open `ai-prompt-template.md`
2. Read through the entire prompt
3. Replace the placeholder variables:
   - `${PLATFORM}` → Your platform (e.g., "Node.js", "Python", "Go")
   - `${SERVICE_TYPE}` → Service type (e.g., "Microservice", "Background Worker")
   - `${AUTH_FLOW}` → OAuth 2.0 flow (typically "Client Credentials")
   - `${TOKEN_STORAGE}` → Token storage (e.g., "Redis", "Memory", "Database")
   - `${CLIENT_ID}` → Your SSOJet Client ID
   - `${CLIENT_SECRET}` → Your SSOJet Client Secret
   - `${TOKEN_URL}` → Your SSOJet Token URL
4. Copy the customized prompt to your LLM
5. Review and refine the generated guide

### Step 4: Refine and Iterate

- Ask follow-up questions to clarify specific sections
- Request code examples for edge cases
- Adapt the generated guide to your specific needs

## 💡 Best Practices

### 1. Be Specific
❌ "I need M2M authentication"
✅ "I'm using Node.js microservice with Express, Client Credentials flow, Redis token caching, and calling protected APIs"

### 2. Provide Context
Include details about:
- Your current auth implementation (API keys, basic auth, none)
- Service architecture (microservices, monolith, serverless)
- Token caching strategy and TTL requirements
- Scope requirements and API permissions
- Rate limiting and retry logic needs

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

### Example 1: Node.js Microservice with Redis

```
Platform: Node.js 20.x
Service Type: Express.js Microservice
Auth Flow: OAuth 2.0 Client Credentials
HTTP Client: axios
Token Storage: Redis with automatic refresh
Deployment: Docker on Kubernetes
Requirements: High availability, token caching, automatic retry, scope management
```

### Example 2: Python Background Worker

```
Platform: Python 3.11
Service Type: Celery background worker
Auth Flow: OAuth 2.0 Client Credentials
HTTP Client: requests library
Token Storage: Redis with TTL management
Deployment: Docker Compose
Requirements: Scheduled tasks, token refresh before expiry, error handling
```

### Example 3: Go API Gateway

```
Platform: Go 1.22
Service Type: API Gateway (microservice proxy)
Auth Flow: OAuth 2.0 Client Credentials
HTTP Client: net/http with retry middleware
Token Storage: In-memory cache with sync.Map
Deployment: Kubernetes with autoscaling
Requirements: Low latency, high throughput, token caching, health checks
```

### Example 4: .NET Core Service

```
Platform: .NET 8.0
Service Type: Windows Service / Background Worker
Auth Flow: OAuth 2.0 Client Credentials
HTTP Client: HttpClient with IHttpClientFactory
Token Storage: Memory cache with IMemoryCache
Deployment: Windows Server / Docker
Requirements: Scheduled operations, automatic token renewal, logging
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

### Platform-Specific Requests

Add M2M-specific requirements:

```
"For M2M Service:
- Implement token caching with automatic refresh
- Show retry logic with exponential backoff
- Include scope validation and management
- Add health check endpoints
- Show proper secret management (environment variables, vault)
- Include monitoring and metrics collection"
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

### OAuth 2.0 Client Libraries by Platform
- **Node.js**: axios, node-fetch, got, simple-oauth2, client-oauth2
- **Python**: requests, httpx, authlib, oauthlib, requests-oauthlib
- **Go**: net/http, resty, go-oauth2, golang.org/x/oauth2
- **Java**: OkHttp, Apache HttpClient, Spring RestTemplate, Nimbus OAuth 2.0
- **.NET**: HttpClient, RestSharp, IdentityModel, Microsoft.Identity.Client
- **PHP**: Guzzle, league/oauth2-client, PHP cURL
- **Ruby**: faraday, httparty, oauth2 gem, rest-client

### Token Storage Solutions
- **In-Memory**: Simple, fast, suitable for single-instance services
- **Redis**: Distributed caching, high performance, automatic expiry
- **Database**: Persistent storage, SQL/NoSQL options
- **Memcached**: Distributed memory caching system
- **Vault**: Secure secret and credential management
- **File System**: Local storage for development/testing

### M2M Authentication Patterns
- **Client Credentials Flow** - Standard OAuth 2.0 M2M flow
- **Service Account Keys** - Long-lived credentials for automation
- **Certificate-based Auth** - Mutual TLS for enhanced security
- **API Keys** - Simple token-based authentication

### Best Practices for M2M
- **Token Caching**: Cache tokens until expiry to reduce requests
- **Automatic Refresh**: Refresh tokens before expiry (e.g., 5 min buffer)
- **Retry Logic**: Implement exponential backoff for failures
- **Secret Management**: Use environment variables or secret managers
- **Scope Management**: Request only necessary scopes
- **Monitoring**: Log auth requests, failures, and token lifecycle

### Learning Resources
- [OpenID Connect Explained](https://openid.net/connect/)
- [OAuth 2.0 RFC](https://tools.ietf.org/html/rfc6749)
- [Client Credentials Grant](https://oauth.net/2/grant-types/client-credentials/)
- [RFC 6749 - OAuth 2.0](https://datatracker.ietf.org/doc/html/rfc6749)

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
