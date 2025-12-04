# AI Prompt Templates

This directory contains AI prompt templates for generating customized SSOJet integration guides for Spring Boot applications.

## 🎯 Overview

The AI prompt system allows you to generate tailored, step-by-step integration guides by providing context about your Spring Boot application and requirements. Instead of following generic documentation, you get a guide specifically designed for your Spring version, architecture, and authentication needs.

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
- Java version (Java 11, 17, 21)
- Spring Boot version (2.7.x, 3.0+, 3.1+, 3.2+)
- Application type (MVC, WebFlux, REST API, microservice)
- View technology (Thymeleaf, JSP, React/Vue frontend, or API-only)
- Current authentication setup (Spring Security, custom)
- Session management (server-side, Redis, database, JWT)
- Database (PostgreSQL, MySQL, H2) and ORM (JPA/Hibernate, R2DBC)
- Build tool (Maven, Gradle)
- Special requirements or constraints

### Step 3: Use the Prompt

1. Open `ai-prompt-template.md`
2. Read through the entire prompt
3. Replace the placeholder variables:
   - `${JAVA_VERSION}` → Your Java version (e.g., "Java 17")
   - `${SPRING_BOOT_VERSION}` → Spring Boot version (e.g., "3.2.0")
   - `${APP_TYPE}` → Application type (e.g., "MVC", "WebFlux", "REST API")
   - `${VIEW_TECH}` → View technology (e.g., "Thymeleaf", "REST API", "React")
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
❌ "I'm using Spring Boot"
✅ "I'm using Spring Boot 3.2 with Java 17, Spring Security OAuth2, Thymeleaf templates, and PostgreSQL with JPA"

### 2. Provide Context
Include details about:
- Your current auth implementation (Spring Security, custom)
- Application architecture (MVC, WebFlux, microservices)
- View technology and frontend framework
- Database and data access layer (JPA, JDBC, R2DBC)
- Build configuration (Maven, Gradle)

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

### Example 1: Spring Boot MVC with Thymeleaf

```
Java Version: Java 17
Spring Boot: 3.2.0
App Type: Spring MVC
View Technology: Thymeleaf
Auth Library: Spring Security OAuth2 Client
Session Management: Server-side sessions with Spring Session (Redis)
Database: PostgreSQL with Spring Data JPA
Build Tool: Maven
Requirements: Preserve existing form-based login, add SSO option
```

### Example 2: Spring Boot REST API with JWT

```
Java Version: Java 17
Spring Boot: 3.2.0
App Type: REST API
Auth Library: Spring Security OAuth2 Resource Server
Frontend: Separate React/Angular SPA
Auth Type: JWT tokens (stateless)
Database: PostgreSQL with Spring Data JPA
Build Tool: Gradle
Requirements: API-only backend, CORS configuration, token validation
```

### Example 3: Spring WebFlux with Reactive Auth

```
Java Version: Java 21
Spring Boot: 3.2.0
App Type: Spring WebFlux (reactive)
View Technology: API-only (JSON)
Auth Library: Spring Security WebFlux + OAuth2
Database: PostgreSQL with Spring Data R2DBC
Build Tool: Gradle (Kotlin DSL)
Requirements: Reactive streams, non-blocking authentication, microservice
```

### Example 4: Spring Boot with Keycloak Integration

```
Java Version: Java 17
Spring Boot: 3.1.0
App Type: Spring MVC + REST API
View Technology: Thymeleaf + REST endpoints
Auth Library: Spring Security + Keycloak Adapter
Session Management: Keycloak sessions
Database: MySQL with Spring Data JPA
Build Tool: Maven
Requirements: Integration with existing Keycloak, role-based access control
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

Add Spring Boot-specific requirements:

```
"For Spring Boot:
- Use SecurityFilterChain for configuration
- Implement custom OAuth2UserService for user mapping
- Show proper @PreAuthorize and @Secured annotations
- Include configuration properties in application.yml
- Add proper exception handling with @ControllerAdvice
- Show integration tests with @SpringBootTest"
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

### OIDC Libraries for Spring Boot
- **Spring Security OAuth2 Client** - Official OAuth2/OIDC client support
- **Spring Security OAuth2 Resource Server** - JWT validation for APIs
- **Spring Authorization Server** - OAuth2 authorization server
- **Nimbus JOSE+JWT** - JWT library (used by Spring Security)
- **Keycloak Adapter** - Keycloak integration for Spring Boot

### Spring Boot Components
- **Spring Security** - Authentication and authorization framework
- **Spring MVC** - Traditional web applications with server-side rendering
- **Spring WebFlux** - Reactive, non-blocking web framework
- **Spring Data JPA** - JPA-based data access with Hibernate
- **Spring Data R2DBC** - Reactive database access
- **Spring Session** - Session management with Redis, JDBC, etc.

### View Technologies
- **Thymeleaf** - Modern server-side Java template engine
- **JSP** - Classic JavaServer Pages
- **Mustache** - Logic-less templates
- **Freemarker** - Template engine for Spring Boot
- **REST API** - JSON responses for SPA frontends

### Build Tools & Dependencies
- **Maven** - Project management and build tool
- **Gradle** - Flexible build automation (Groovy or Kotlin DSL)
- **Spring Initializr** - Bootstrap Spring Boot projects
- **Spring Boot Starter** - Pre-configured dependency bundles

### Learning Resources
- [OpenID Connect Explained](https://openid.net/connect/)
- [OAuth 2.0 RFC](https://tools.ietf.org/html/rfc6749)
- [Spring Security OAuth2](https://spring.io/guides/tutorials/spring-boot-oauth2/)
- [Spring Boot Documentation](https://docs.spring.io/spring-boot/)

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
