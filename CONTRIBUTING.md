# Contributing to SSOJet React LLM Guide

Thank you for your interest in contributing to the SSOJet React LLM Guide! We welcome contributions from the community to help improve our AI-powered integration guides.

## 🌟 Ways to Contribute

There are many ways you can contribute to this project:

### 1. **Add New Framework Guides**
- Create integration guides for additional React frameworks
- Update existing guides with new best practices
- Add support for new OIDC libraries

### 2. **Improve AI Prompts**
- Enhance the AI prompt templates for better guide generation
- Add new customization options
- Improve prompt clarity and structure

### 3. **Create Example Applications**
- Build working example apps demonstrating SSO integration
- Add edge case scenarios
- Create troubleshooting examples

### 4. **Improve Documentation**
- Fix typos and grammatical errors
- Clarify confusing sections
- Add diagrams and visual aids
- Translate documentation

### 5. **Report Issues**
- Report bugs or inconsistencies
- Suggest new features
- Provide feedback on existing guides

## 🚀 Getting Started

### Prerequisites

- Git installed on your machine
- GitHub account
- Node.js 16+ (for testing React examples)
- Familiarity with React and OIDC concepts

### Development Setup

1. **Fork the repository:**
   - Visit [ssojet-llm-guide](https://github.com/ssojet/ssojet-llm-guide)
   - Click the "Fork" button in the top-right corner

2. **Clone your fork:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/ssojet-llm-guide.git
   cd ssojet-llm-guide
   ```

3. **Add upstream remote:**
   ```bash
   git remote add upstream https://github.com/ssojet/ssojet-llm-guide.git
   ```

4. **Create a feature branch:**
   ```bash
   git checkout -b feature/your-feature-name
   ```

## 📝 Contribution Guidelines

### Code Style

- Follow existing code formatting and style
- Use meaningful variable and function names
- Add comments for complex logic
- Keep code examples simple and focused

### Documentation Style

- Use clear, concise language
- Follow Markdown best practices
- Include code examples where appropriate
- Add screenshots or diagrams for visual clarity
- Ensure all links are valid and working

### AI Prompt Guidelines

When creating or modifying AI prompts:

1. **Be Specific**: Provide clear, detailed instructions
2. **Use Placeholders**: Use variables like `$React` for customization
3. **Structure**: Follow the established template format
4. **Test**: Generate guides using the prompt to verify output
5. **Document**: Explain any complex prompt logic

### Commit Guidelines

Follow these commit message conventions:

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

**Examples:**
```bash
feat(guides): add Remix framework integration guide
fix(prompts): correct OIDC callback URL placeholder
docs(readme): update quick start instructions
```

## 🔄 Pull Request Process

### Before Submitting

1. **Update your fork:**
   ```bash
   git fetch upstream
   git rebase upstream/main
   ```

2. **Test your changes:**
   - Verify all links work
   - Test code examples
   - Check for typos and formatting issues

3. **Commit your changes:**
   ```bash
   git add .
   git commit -m "feat: your descriptive commit message"
   ```

4. **Push to your fork:**
   ```bash
   git push origin feature/your-feature-name
   ```

### Submitting the PR

1. Go to the [original repository](https://github.com/ssojet/ssojet-llm-guide)
2. Click "New Pull Request"
3. Select your fork and branch
4. Fill out the PR template with:
   - **Title**: Clear, descriptive title
   - **Description**: What changes you made and why
   - **Testing**: How you tested your changes
   - **Screenshots**: If applicable
   - **Related Issues**: Link any related issues

### PR Review Process

- A maintainer will review your PR within 3-5 business days
- Address any requested changes promptly
- Once approved, a maintainer will merge your PR

## 📋 Adding a New Framework Guide

To add a guide for a new React framework:

1. **Create the guide directory:**
   ```bash
   mkdir -p guides/your-framework
   cd guides/your-framework
   ```

2. **Use the AI prompt template:**
   - Copy `/prompts/ai-prompt-template.md`
   - Customize for your framework
   - Generate the guide using an LLM

3. **Create the guide structure:**
   ```
   guides/your-framework/
   ├── README.md          # Main integration guide
   └── examples/          # Code examples
       ├── LoginPage.jsx
       ├── callback.js
       └── config.js
   ```

4. **Follow the template structure:**
   - Introduction and prerequisites
   - SSOJet application setup
   - Framework-specific configuration
   - Login page modification
   - Callback handler implementation
   - Testing instructions
   - Additional considerations

5. **Add to main README:**
   - Update the "Available Guides" section
   - Add a link to your guide

## 🧪 Testing Guidelines

### For Documentation

- [ ] All links are valid and working
- [ ] Code examples are properly formatted
- [ ] Screenshots are clear and properly sized
- [ ] Markdown renders correctly

### For Code Examples

- [ ] Code runs without errors
- [ ] Dependencies are properly specified
- [ ] Environment variables are documented
- [ ] Error handling is included
- [ ] Security best practices are followed

### For AI Prompts

- [ ] Prompt generates valid, consistent output
- [ ] All placeholders work as expected
- [ ] Generated guide follows template structure
- [ ] Instructions are clear and unambiguous

## 🐛 Reporting Issues

### Before Creating an Issue

1. Search existing issues to avoid duplicates
2. Check if the issue exists in the latest version
3. Gather relevant information (OS, versions, etc.)

### Creating a Good Issue

Use our issue templates and include:

- **Clear Title**: Concise description of the issue
- **Description**: Detailed explanation of the problem
- **Steps to Reproduce**: How to recreate the issue
- **Expected Behavior**: What should happen
- **Actual Behavior**: What actually happens
- **Environment**: OS, Node.js version, framework version
- **Screenshots**: If applicable
- **Logs**: Any relevant error messages

## 💬 Community Guidelines

### Code of Conduct

We follow a strict Code of Conduct. Please be:

- **Respectful**: Treat everyone with respect
- **Constructive**: Provide constructive feedback
- **Inclusive**: Welcome diverse perspectives
- **Professional**: Maintain professional communication

### Getting Help

If you need help:

1. Check the [documentation](https://docs.ssojet.com)
2. Search existing [GitHub issues](https://github.com/ssojet/ssojet-llm-guide/issues)
3. Contact [support@ssojet.com](mailto:support@ssojet.com)

## 🏆 Recognition

Contributors are recognized in several ways:

- Listed in the README contributors section
- Mentioned in release notes
- Featured on SSOJet blog (for major contributions)

## 📄 License

By contributing, you agree that your contributions will be licensed under the MIT License.

## 🙏 Thank You!

Your contributions make this project better for everyone. We truly appreciate your time and effort!

---

**Questions?** Feel free to reach out to us at [support@ssojet.com](mailto:support@ssojet.com)

---

<p align="center">
  <a href="https://ssojet.com">SSOJet Website</a> •
  <a href="https://docs.ssojet.com">Documentation</a> •
  <a href="https://github.com/ssojet">GitHub</a>
</p>
