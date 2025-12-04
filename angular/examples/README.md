# Code Examples

This directory contains working code examples for various React frameworks and scenarios.

## 📁 Structure

Each example is a complete, working demonstration of SSOJet integration:

```
examples/
├── nextjs-app-router-example/     # Next.js 14+ with App Router
├── nextjs-pages-router-example/   # Next.js with Pages Router
├── react-cra-example/             # Create React App
├── vite-react-example/            # Vite + React
└── remix-example/                 # Remix framework
```

## 🚀 Running Examples

Each example includes:
- Complete source code
- README with setup instructions
- Environment variable template
- Working configuration

### Quick Start

```bash
# Clone the repository
git clone https://github.com/ssojet/ssojet-react-llm-guide.git
cd ssojet-react-llm-guide

# Navigate to an example
cd examples/nextjs-app-router-example

# Install dependencies
npm install

# Configure environment variables
cp .env.example .env.local
# Edit .env.local with your SSOJet credentials

# Run the example
npm run dev
```

## 📚 Available Examples

### Next.js App Router
**Path:** `nextjs-app-router-example/`
- Next.js 14+ with App Router
- NextAuth v5 integration
- Server Components
- Middleware protection

### Next.js Pages Router
**Path:** `nextjs-pages-router-example/`
- Next.js 13 with Pages Router
- NextAuth v4 integration
- API routes
- getServerSideProps authentication

### Create React App
**Path:** `react-cra-example/`
- Create React App setup
- oidc-client-ts integration
- React Router v6
- PKCE flow

### Vite + React
**Path:** `vite-react-example/`
- Modern Vite setup
- Fast HMR
- oidc-client-ts integration
- React Router v6

### Remix
**Path:** `remix-example/`
- Remix v2
- remix-auth integration
- Loaders and Actions
- Server-side sessions

## 🛠️ Customization

These examples are starting points. Customize them for your needs:
- Modify UI/styling
- Add additional authentication providers
- Integrate with your database
- Add role-based access control
- Implement custom user provisioning

## 🐛 Issues

Found an issue with an example? [Report it here](https://github.com/ssojet/ssojet-react-llm-guide/issues)

## 📖 Documentation

For detailed integration guides, see the [/guides](/guides) directory.

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
