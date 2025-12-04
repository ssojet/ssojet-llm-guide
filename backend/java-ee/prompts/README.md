# AI Prompt Templates

This directory contains AI prompt templates for generating customized SSOJet integration guides for Java EE (Jakarta EE) applications.

## 🎯 Overview

The AI prompt system allows you to generate tailored, step-by-step integration guides by providing context about your Java EE application and requirements. Instead of following generic documentation, you get a guide specifically designed for your enterprise architecture, application server, and authentication needs.

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
- Java version (Java 8, 11, 17, 21)
- Java EE/Jakarta EE version (Java EE 7/8 or Jakarta EE 8/9/10)
- Application server (WildFly, Payara, GlassFish, TomEE, WebLogic, WebSphere)
- Application type (WAR, EAR, microservice)
- View technology (JSF, JSP, Thymeleaf, or REST API)
- Current authentication setup (JAAS, container security, custom)
- Security framework (Java EE Security API, Apache Shiro, custom)
- Special requirements or constraints

### Step 3: Use the Prompt

1. Open `ai-prompt-template.md`
2. Read through the entire prompt
3. Replace the placeholder variables:
   - `${JAVA_VERSION}` → Your Java version (e.g., "Java 17")
   - `${JEE_VERSION}` → Java EE/Jakarta EE version (e.g., "Jakarta EE 10")
   - `${APP_SERVER}` → Application server (e.g., "WildFly 30", "Payara 6")
   - `${VIEW_TECH}` → View technology (e.g., "JSF", "JSP", "REST API")
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
❌ "I'm using Java EE"
✅ "I'm using Jakarta EE 10 on WildFly 30 with JSF 4.0, CDI, JPA, and container-managed security"

### 2. Provide Context
Include details about:
- Your current auth implementation (JAAS, container security, custom)
- Application server configuration and version
- View technology and UI framework (PrimeFaces, BootsFaces, etc.)
- Database and JPA provider (Hibernate, EclipseLink)
- Deployment type (WAR, EAR, Docker)

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

### Example 1: Jakarta EE with JSF and WildFly

```
Java Version: Java 17
Platform: Jakarta EE 10
App Server: WildFly 30
View Technology: JSF 4.0 with PrimeFaces 13
Auth Library: Jakarta Security API + MicroProfile JWT
Database: PostgreSQL with JPA/Hibernate
Requirements: Container-managed security, preserve existing form-based auth
```

### Example 2: Java EE REST API with Payara

```
Java Version: Java 11
Platform: Jakarta EE 8
App Server: Payara Server 6
View Technology: JAX-RS REST API
Auth Library: MicroProfile JWT + Jose4j
Frontend: Separate Angular/React SPA
Requirements: JWT-based authentication, stateless API, CORS configuration
```

### Example 3: Java EE with JSP and TomEE

```
Java Version: Java 11
Platform: Java EE 8
App Server: Apache TomEE 9
View Technology: JSP with JSTL
Auth Library: Custom OIDC with Apache CXF
Database: MySQL with JPA
Requirements: Session-based authentication, legacy JSP support
```

### Example 4: Jakarta EE Microservice with Liberty

```
Java Version: Java 17
Platform: Jakarta EE 10 / MicroProfile 6
App Server: Open Liberty
Architecture: Microservices
Auth Library: MicroProfile JWT + Social Login
Requirements: JWT validation, stateless services, Docker deployment
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

Add Java EE-specific requirements:

```
"For Jakarta EE:
- Use CDI for dependency injection
- Implement JAX-RS filters for authentication
- Show proper security constraints in web.xml or annotations
- Include EJB security roles and method-level security
- Add proper exception handling with ExceptionMapper"
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

### OIDC Libraries for Java EE
- **Jakarta Security API** - Built-in security for Jakarta EE 8+
- **MicroProfile JWT** - JWT authentication for microservices
- **Keycloak Java Adapter** - Keycloak integration for Java EE
- **Apache CXF** - OIDC support for JAX-RS services
- **Jose4j** - JWT/JWS/JWE library for Java
- **Nimbus JOSE+JWT** - Popular JWT library

### Popular Application Servers
- **WildFly** - JBoss community server (Jakarta EE 10)
- **Payara Server** - Enterprise-grade server based on GlassFish
- **Open Liberty** - IBM's lightweight Jakarta EE runtime
- **Apache TomEE** - Tomcat + Java EE
- **GlassFish** - Reference implementation for Jakarta EE
- **WebLogic** - Oracle's enterprise Java server
- **WebSphere** - IBM's enterprise platform

### Java EE/Jakarta EE Components
- **CDI** - Context and Dependency Injection
- **JAX-RS** - RESTful web services
- **JSF** - JavaServer Faces for UI
- **JPA** - Java Persistence API
- **EJB** - Enterprise JavaBeans
- **Security API** - Jakarta Security specification

### Learning Resources
- [OpenID Connect Explained](https://openid.net/connect/)
- [OAuth 2.0 RFC](https://tools.ietf.org/html/rfc6749)
- [Jakarta EE Tutorial](https://eclipse-ee4j.github.io/jakartaee-tutorial/)
- [MicroProfile JWT](https://microprofile.io/specifications/microprofile-jwt-auth/)

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
