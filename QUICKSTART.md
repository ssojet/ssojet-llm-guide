# Quick Start Guide

Get started with SSOJet React integration in minutes!

## 🎯 For Developers: Integrate SSO Now

### Option 1: Use Pre-Generated Guides (Fastest)

**If you're using Next.js 14+ with App Router:**

1. **Visit the guide:**
2. **Follow the steps:** Complete setup in ~30 minutes
3. **Test it out:** Your SSO integration is ready!

### Option 2: Generate Custom Guide with AI

**Perfect if:**
- Your framework isn't covered
- You have specific requirements
- You want a tailored approach

**Steps:**

1. **Open the prompt template:**
   ```bash
   # Navigate to prompts directory
   cd prompts
   open ai-prompt-template.md
   ```

2. **Customize the placeholders:**
   - Replace `$React` with your framework name
   - Replace `${FRAMEWORK_TOOLS}` with your tools/patterns
   - Add your SSOJet credentials

3. **Use with your favorite LLM:**
   - ChatGPT (GPT-4 recommended)
   - Claude (Claude 3 Opus/Sonnet recommended)
   - Gemini Pro
   - Any capable LLM

4. **Get your guide instantly!**
   - Copy the generated guide
   - Follow the steps
   - Test your integration

**Example prompt:**
```
I want to integrate SSOJet SSO into my existing Next.js 14 
application using App Router and NextAuth v5. Generate a 
complete step-by-step guide.
```

---

## 📚 For Contributors: Add New Guides

Want to contribute a guide for a new framework?

### Quick Contribution Steps

1. **Fork the repository:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/ssojet-llm-guide.git
   ```

2. **Generate guide using AI prompt:**
   - Use `prompts/ai-prompt-template.md`
   - Customize for your target framework
   - Generate with LLM

3. **Test the integration:**
   - Build a working example
   - Test all steps
   - Verify authentication flow

4. **Add to repository:**
   ```bash
   # Create guide directory
   mkdir -p guides/your-framework
   
   # Add your guide
   cp your-generated-guide.md guides/your-framework/README.md
   
   # Add examples
   mkdir -p guides/your-framework/examples
   # Add code examples
   ```

5. **Submit pull request:**
   ```bash
   git add .
   git commit -m "Add [Framework] integration guide"
   git push origin your-branch
   # Create PR on GitHub
   ```

See [CONTRIBUTING.md](./CONTRIBUTING.md) for detailed guidelines.

---

## 🚀 For Repository Maintainers: Initial Setup

### Setting up this repository for the first time

1. **Run the setup script:**
   ```bash
   chmod +x setup.sh
   ./setup.sh
   ```

2. **Create GitHub repository:**
   - Go to https://github.com/new
   - Name: `ssojet-llm-guide`
   - Make it public
   - Don't initialize with files

3. **Push to GitHub:**
   ```bash
   git remote add origin https://github.com/ssojet/ssojet-llm-guide.git
   git branch -M main
   git push -u origin main
   ```

4. **Configure repository settings:**
   - Add description: "AI-powered integration guides for SSOJet SSO in React applications"
   - Add topics: `ssojet`, `oidc`, `react`, `authentication`, `sso`
   - Enable Issues and Discussions
   - Add repository website: https://ssojet.com

5. **Add assets:**
   ```bash
   # Add SSOJet screenshots to assets/images/
   # Add logos to assets/logos/
   ```

6. **Create initial examples:**
   ```bash
   # Build working examples in examples/
   # Each example should have its own README
   ```

---

## ⚡ Quick Reference

### Repository Structure
```
├── README.md                    # Main repository overview
├── prompts/                     # AI prompt templates
│   └── ai-prompt-template.md   # Main template
├── guides/                      # Framework-specific guides
│   └── nextjs-app-router/      # Next.js guide
├── examples/                    # Working code examples
├── docs/                        # Additional documentation
│   ├── ssojet-setup.md         # SSOJet configuration
│   ├── oidc-concepts.md        # OIDC fundamentals
│   └── troubleshooting.md      # Common issues
└── assets/                      # Images and logos
```

### Essential Links

**Documentation:**
- [Main README](./README.md)
- [AI Prompt Guide](./prompts/README.md)

**SSOJet Resources:**
- [SSOJet Website](https://ssojet.com)
- [SSOJet Docs](https://docs.ssojet.com)
- [SSOJet Dashboard](https://portal.ssojet.com)
- [SSO Setup Guide](https://docs.ssojet.com/how-to-guides/sso/integrations/)

**Support:**
- Email: [support@ssojet.com](mailto:support@ssojet.com)
- Issues: [GitHub Issues](https://github.com/ssojet/ssojet-llm-guide/issues)

---

## 🎓 Learning Path

### New to OIDC?
1. Read [OIDC Concepts](https://ssojet.com/blog/openid-connect-explained)
2. Getting Started [SSOJet Account](https://docs.ssojet.com/en/getting-started/)

### Experienced with OIDC?
1. Jump to [integration guides](https://docs.ssojet.com/en/sso/quickstart/)

### Troubleshooting?
1. Check [common issues](./docs/troubleshooting.md)
2. Search [GitHub issues](https://github.com/ssojet/ssojet-llm-guide/issues)

---

## 📞 Need Help?

- **Technical Issues:** [GitHub Issues](https://github.com/ssojet/ssojet-llm-guide/issues)
- **SSOJet Support:** [support@ssojet.com](mailto:support@ssojet.com)
- **Documentation Feedback:** Open an issue or PR

---

<p align="center">
  <strong>Ready to get started?</strong><br>
  <a href="./guides/">Browse Integration Guides</a> •
  <a href="./prompts/">Use AI Prompt</a> •
  <a href="https://portal.ssojet.com">Sign Up for SSOJet</a>
</p>

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
