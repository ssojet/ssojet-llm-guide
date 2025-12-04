# SSOJet M2M (Machine-to-Machine) Integration Guide

This guide helps you integrate **SSOJet** (OIDC authentication) for **Machine-to-Machine (M2M)** authentication scenarios using the Client Credentials flow.

## 📋 Prerequisites

- An SSOJet account with an OIDC application configured for M2M
- Client ID and Client Secret from your SSOJet dashboard
- Basic understanding of OAuth 2.0 Client Credentials flow

## 🔧 What is M2M Authentication?

Machine-to-Machine (M2M) authentication is used when:
- A backend service needs to call another API
- No user interaction is involved
- Server-to-server communication is required
- Automated processes need authenticated access

**Flow:**
```
Service → POST /token → SSOJet → Access Token → Protected API
```

## 🌐 Supported Languages

M2M authentication can be implemented in any language that supports HTTP requests:

- **Node.js** - Using `axios`, `node-fetch`, or `got`
- **Python** - Using `requests` or `httpx`
- **Go** - Using `net/http` or `resty`
- **Java** - Using `HttpClient` or `OkHttp`
- **C#/.NET** - Using `HttpClient`
- **PHP** - Using `Guzzle` or `cURL`
- **Ruby** - Using `faraday` or `httparty`

## 📂 Directory Structure

```
m2m/
├── README.md                    # This file
├── examples/                    # Example M2M implementations
│   └── README.md
├── guides/                      # Step-by-step integration guides
│   └── README.md
└── prompts/                     # AI prompt templates for code generation
    ├── README.md
    └── ai-prompt-template.md
```

## 🔐 Client Credentials Flow

```bash
POST https://api.ssojet.com/oauth/token
Content-Type: application/x-www-form-urlencoded

grant_type=client_credentials
&client_id=YOUR_CLIENT_ID
&client_secret=YOUR_CLIENT_SECRET
&scope=api:read api:write
```

**Response:**
```json
{
  "access_token": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9...",
  "token_type": "Bearer",
  "expires_in": 3600
}
```

## 🚀 Getting Started

1. **Configure M2M Application**: Set up your SSOJet application for M2M authentication
2. **Explore Examples**: Check the `examples/` folder for code samples in various languages
3. **Read Integration Guides**: Follow the `guides/` for detailed setup instructions
4. **Use AI Prompts**: Leverage `prompts/` to generate custom integration code

## 🔗 Useful Links

- [SSOJet Dashboard](https://portal.ssojet.com)
- [SSOJet OIDC Documentation](https://docs.ssojet.com)
- [OAuth 2.0 Client Credentials](https://oauth.net/2/grant-types/client-credentials/)
- [OIDC Concepts](../../oidc-concepts.md)

## 📝 Common Use Cases

- Microservices authentication
- API-to-API communication
- Background jobs accessing protected resources
- Scheduled tasks with authenticated access
- Service accounts for automated processes

## 🛡️ Security Best Practices

1. **Never expose client secrets** in client-side code
2. **Store secrets securely** using environment variables or secret managers
3. **Rotate credentials regularly**
4. **Use least privilege** - request only necessary scopes
5. **Implement token caching** to reduce token requests
6. **Monitor token usage** for suspicious activity

## 🆘 Need Help?

- Review the [OIDC Concepts](../../oidc-concepts.md) for authentication fundamentals
- Use the AI prompt templates to generate working code
