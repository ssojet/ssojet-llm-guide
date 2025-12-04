# AI Prompt Templates

This directory contains AI prompt templates for generating customized SSOJet integration guides for various React frameworks and architectures.

## 🎯 Overview

The AI prompt system allows you to generate tailored, step-by-step integration guides by providing context about your React application and requirements. Instead of following generic documentation, you get a guide specifically designed for your stack.

## 📚 Available Templates

### Main Template
- **[ai-prompt-template.md](./ai-prompt-template.md)** - The primary prompt template for generating integration guides

### Customization Resources
- **[customization-examples.md](./customization-examples.md)** - Example customizations for different scenarios

## 🚀 How to Use

### Step 1: Choose Your LLM

You can use any of these LLMs:
- ChatGPT (GPT-4 or GPT-4 Turbo recommended)
- Claude (Claude 3 Opus or Sonnet recommended)
- Gemini Pro
- Any other capable LLM with good instruction-following abilities

### Step 2: Prepare Your Context

Gather information about your application:
- React framework (e.g., Next.js, Remix, CRA, Vite)
- Current authentication setup
- Existing login page structure
- Preferred OIDC library (if any)
- Special requirements or constraints

### Step 3: Use the Prompt

1. Open `ai-prompt-template.md`
2. Read through the entire prompt
3. Replace the placeholder variables:
   - `$React` → Your framework name (e.g., "Next.js")
   - `${FRAMEWORK_TOOLS}` → Common tools (e.g., "App Router, Server Components")
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
❌ "I'm using React"
✅ "I'm using Next.js 14 with App Router, Server Components, and server actions for authentication"

### 2. Provide Context
Include details about:
- Your current auth implementation
- UI library (Material-UI, Tailwind, etc.)
- State management (Redux, Zustand, Context API)
- Backend setup (if applicable)

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

### Example 1: Next.js with App Router

```
Framework: Next.js 14
Tools: App Router, Server Components, Server Actions
Auth Library: next-auth v5 (Auth.js)
Requirements: Preserve existing credential-based login, add SSO option
```

### Example 2: Create React App with Express Backend

```
Framework: Create React App (React 18)
Backend: Express.js with Passport.js
Auth Library: passport-openidconnect
Requirements: Separate frontend and backend, session-based auth
```

### Example 3: Remix with Supabase

```
Framework: Remix
Existing Auth: Supabase Auth
Requirements: Add SSO alongside Supabase, use Remix loaders/actions
```

### Example 4: Vite + React with Firebase

```
Framework: Vite + React 18
Existing Auth: Firebase Authentication
Requirements: Integrate SSO as additional provider, maintain Firebase session
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

Add framework-specific requirements:

```
"For Next.js:
- Use Server Components where possible
- Implement middleware for auth checks
- Show both client and server-side validation"
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
- [OIDC Endpoints](https://docs.ssojet.com/api-reference/oidc/)

### OIDC Libraries
- **Next.js**: next-auth, @auth/core
- **React (SPA)**: oidc-client-ts, react-oidc-context
- **Node.js/Express**: passport-openidconnect
- **Remix**: remix-auth-oauth2

### Learning Resources
- [OpenID Connect Explained](https://openid.net/connect/)
- [OAuth 2.0 RFC](https://tools.ietf.org/html/rfc6749)
- [React Authentication Patterns](https://react.dev/learn/sharing-state-between-components)

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
