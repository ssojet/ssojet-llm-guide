# AI Prompt Templates

This directory contains AI prompt templates for generating customized SSOJet integration guides for Python applications.

## 🎯 Overview

The AI prompt system allows you to generate tailored, step-by-step integration guides by providing context about your Python application and requirements. Instead of following generic documentation, you get a guide specifically designed for your Python version, web framework, and authentication architecture.

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
- Python version (3.8+, 3.9+, 3.10+, 3.11+, 3.12+)
- Web framework (Django, Flask, FastAPI, Pyramid, Tornado, or vanilla)
- Template engine (Jinja2, Django templates, or API-only)
- Current authentication setup (Django auth, Flask-Login, custom)
- Session management (server-side, Redis, database)
- Database (PostgreSQL, MySQL, SQLite) and ORM (Django ORM, SQLAlchemy)
- Preferred OIDC library (Authlib, PyOIDC, social-auth-app-django)
- Special requirements or constraints

### Step 3: Use the Prompt

1. Open `ai-prompt-template.md`
2. Read through the entire prompt
3. Replace the placeholder variables:
   - `${PYTHON_VERSION}` → Your Python version (e.g., "3.11")
   - `${FRAMEWORK}` → Web framework (e.g., "Django", "Flask", "FastAPI")
   - `${TEMPLATE_ENGINE}` → Template engine (e.g., "Jinja2", "Django", "None (API)")
   - `${SESSION_STORE}` → Session storage (e.g., "Redis", "Database", "Server-side")
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
❌ "I'm using Python"
✅ "I'm using Python 3.11 with Django 5.0, Django templates, PostgreSQL, and Redis for session storage"

### 2. Provide Context
Include details about:
- Your current auth implementation (Django auth, Flask-Login, custom)
- Web framework and middleware configuration
- Template engine and frontend architecture
- Database and ORM (Django ORM, SQLAlchemy, Peewee)
- API structure (REST, GraphQL, async)

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

### Example 1: Django with Session Authentication

```
Python Version: 3.11
Framework: Django 5.0
Auth Library: social-auth-app-django + Authlib
Template Engine: Django templates
Session Storage: Redis with django-redis
Database: PostgreSQL with Django ORM
Requirements: Preserve existing Django auth, add SSO option
```

### Example 2: Flask with Flask-Login

```
Python Version: 3.10
Framework: Flask 3.0
Auth Library: Authlib + Flask-Login
Template Engine: Jinja2
Session Storage: Server-side sessions with Flask-Session (Redis)
Database: PostgreSQL with SQLAlchemy
Requirements: Session-based authentication, preserve existing login
```

### Example 3: FastAPI with JWT Tokens

```
Python Version: 3.12
Framework: FastAPI 0.108
Auth Library: Authlib + python-jose
Frontend: Separate React/Vue SPA
Auth Type: JWT tokens (stateless)
Database: PostgreSQL with SQLAlchemy (async)
Requirements: API-only backend, CORS configuration, token validation
```

### Example 4: Django REST Framework API

```
Python Version: 3.11
Framework: Django 5.0 + Django REST Framework
Auth Library: djangorestframework-simplejwt + Authlib
Frontend: Separate SPA
Auth Type: JWT authentication
Database: PostgreSQL
Requirements: RESTful API, token-based auth, DRF serializers
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

Add Python-specific requirements:

```
"For Django:
- Use middleware for authentication checks
- Implement custom authentication backends
- Show proper URL configuration and view decorators
- Include Django signals for auth events
- Add proper CSRF protection and security settings"
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

### OIDC Libraries for Python
- **Authlib** - Comprehensive OAuth/OIDC library (most popular)
- **social-auth-app-django** - Django social authentication
- **python-social-auth** - Social authentication for Flask/Pyramid
- **PyOIDC** - OpenID Connect client library
- **oauthlib** - Generic OAuth implementation
- **python-jose** - JOSE implementation for JWT handling

### Popular Python Web Frameworks
- **Django** - Full-stack web framework with ORM, admin, auth
- **Flask** - Lightweight, flexible micro-framework
- **FastAPI** - Modern, fast, async framework with automatic docs
- **Pyramid** - Flexible, scalable web framework
- **Tornado** - Async web framework and networking library
- **Sanic** - Async Python web server and framework

### Authentication Extensions
- **Django**: django-allauth, social-auth-app-django, dj-rest-auth
- **Flask**: Flask-Login, Flask-Security, Flask-HTTPAuth, Authlib
- **FastAPI**: fastapi-users, python-jose, passlib

### Session & Database Libraries
- **django-redis** - Redis cache backend for Django
- **Flask-Session** - Server-side session support for Flask
- **SQLAlchemy** - SQL toolkit and ORM
- **Django ORM** - Built-in Django ORM
- **Redis-py** - Redis client for Python
- **asyncpg** - Async PostgreSQL driver

### Learning Resources
- [OpenID Connect Explained](https://openid.net/connect/)
- [OAuth 2.0 RFC](https://tools.ietf.org/html/rfc6749)
- [Django Authentication](https://docs.djangoproject.com/en/stable/topics/auth/)
- [Real Python - Authentication](https://realpython.com/tutorials/authentication/)

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
