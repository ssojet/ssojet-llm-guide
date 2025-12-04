# Customization Examples

This document provides practical examples of how to customize the AI prompt template for different React frameworks and scenarios.

## 📚 Table of Contents

1. [Next.js App Router Example](#nextjs-app-router)
2. [Next.js Pages Router Example](#nextjs-pages-router)
3. [Create React App Example](#create-react-app)
4. [Vite + React Example](#vite-react)
5. [Remix Example](#remix)
6. [React Native Example](#react-native)
7. [Advanced Customizations](#advanced-customizations)

---

## Next.js App Router

### Input Customizations

```markdown
**Framework:** Next.js 14 with App Router
**Tools:** App Router, Server Components, Server Actions, React Server Components
**Auth Library:** NextAuth v5 (@auth/core)
**Callback Route:** /api/auth/callback/ssojet
**Special Requirements:**
- Use Server Components where possible
- Implement middleware for protected routes
- Use server actions for form handling
- Show both client and server-side examples
```

### Key Points to Emphasize

- Server Components vs Client Components
- Middleware for route protection
- Server Actions for mutations
- App Router file structure
- `use client` directive usage

---

## Next.js Pages Router

### Input Customizations

```markdown
**Framework:** Next.js 13 with Pages Router
**Tools:** Pages Router, API Routes, getServerSideProps
**Auth Library:** NextAuth v4
**Callback Route:** /api/auth/callback/ssojet
**Special Requirements:**
- Use traditional pages/ directory structure
- API routes for backend logic
- getServerSideProps for SSR authentication checks
- Session management with NextAuth
```

### Key Points to Emphasize

- Pages directory structure
- API routes for callbacks
- getServerSideProps for auth checks
- useSession hook usage
- SessionProvider wrapper

---

## Create React App

### Input Customizations

```markdown
**Framework:** Create React App (React 18)
**Tools:** React Router v6, Context API, oidc-client-ts
**Auth Library:** oidc-client-ts with react-oidc-context
**Callback Route:** /callback
**Backend:** Separate Express.js API
**Special Requirements:**
- Pure SPA architecture
- PKCE flow for security
- Token storage in browser
- Protected routes with React Router
- Proxy API calls to backend
```

### Key Points to Emphasize

- SPA security considerations
- PKCE implementation
- Token storage best practices
- React Router protected routes
- Proxy configuration for development

### Additional Configuration

**package.json proxy setup:**
```json
{
  "proxy": "http://localhost:5000"
}
```

**Protected Route Example:**
```typescript
import { useAuth } from "react-oidc-context"
import { Navigate } from "react-router-dom"

function ProtectedRoute({ children }) {
  const auth = useAuth()
  
  if (auth.isLoading) {
    return <div>Loading...</div>
  }
  
  if (!auth.isAuthenticated) {
    return <Navigate to="/login" />
  }
  
  return children
}
```

---

## Vite + React

### Input Customizations

```markdown
**Framework:** Vite + React 18
**Tools:** Vite, React Router v6, TanStack Query, oidc-client-ts
**Auth Library:** oidc-client-ts with react-oidc-context
**Callback Route:** /callback
**Special Requirements:**
- Fast HMR with Vite
- Environment variables with VITE_ prefix
- Modern build tooling
- Optimized production builds
```

### Key Points to Emphasize

- Vite environment variables (`import.meta.env.VITE_*`)
- Fast development experience
- Build optimization
- Modern JavaScript features

### Environment Variables

```env
VITE_SSOJET_CLIENT_ID=cli_d4msncam6ljs71nsj520
VITE_SSOJET_ISSUER_URL=https://api.ssojet.com/oidc
VITE_APP_URL=http://localhost:5173
```

### Accessing Variables

```typescript
const oidcConfig = {
  authority: import.meta.env.VITE_SSOJET_ISSUER_URL,
  client_id: import.meta.env.VITE_SSOJET_CLIENT_ID,
  redirect_uri: `${import.meta.env.VITE_APP_URL}/callback`,
}
```

---

## Remix

### Input Customizations

```markdown
**Framework:** Remix v2
**Tools:** Remix Routes, Loaders, Actions, Form, remix-auth
**Auth Library:** remix-auth with remix-auth-oauth2
**Callback Route:** /auth/callback
**Special Requirements:**
- Server-side session management
- Use Remix loaders for auth checks
- Use Remix actions for mutations
- Cookie-based sessions
- Progressive enhancement
```

### Key Points to Emphasize

- Loaders for data fetching
- Actions for mutations
- Form component for submissions
- Server-side session storage
- Progressive enhancement philosophy

### Session Storage Configuration

```typescript
// app/services/session.server.ts
import { createCookieSessionStorage } from "@remix-run/node"

export const sessionStorage = createCookieSessionStorage({
  cookie: {
    name: "__session",
    httpOnly: true,
    maxAge: 60 * 60 * 24 * 7, // 7 days
    path: "/",
    sameSite: "lax",
    secrets: [process.env.SESSION_SECRET!],
    secure: process.env.NODE_ENV === "production",
  },
})

export const { getSession, commitSession, destroySession } = sessionStorage
```

### Protected Route Loader

```typescript
// app/routes/dashboard.tsx
import type { LoaderFunctionArgs } from "@remix-run/node"
import { redirect } from "@remix-run/node"
import { authenticator } from "~/services/auth.server"

export async function loader({ request }: LoaderFunctionArgs) {
  const user = await authenticator.isAuthenticated(request, {
    failureRedirect: "/login",
  })
  
  return { user }
}
```

---

## React Native

### Input Customizations

```markdown
**Framework:** React Native with Expo
**Tools:** Expo, React Navigation, expo-auth-session
**Auth Library:** expo-auth-session
**Callback Route:** exp://localhost:19000/--/auth/callback
**Special Requirements:**
- Mobile-specific OIDC flow
- Deep linking configuration
- Secure storage for tokens
- Platform-specific considerations (iOS/Android)
```

### Key Points to Emphasize

- Deep linking setup
- Platform-specific configurations
- Secure token storage (expo-secure-store)
- Mobile UX considerations

### Deep Linking Configuration

**app.json:**
```json
{
  "expo": {
    "scheme": "myapp",
    "web": {
      "bundler": "metro"
    }
  }
}
```

### Authentication Flow

```typescript
import * as AuthSession from 'expo-auth-session'
import * as SecureStore from 'expo-secure-store'

const discovery = {
  authorizationEndpoint: 'https://api.ssojet.com/oidc/authorize',
  tokenEndpoint: 'https://api.ssojet.com/oidc/token',
}

const redirectUri = AuthSession.makeRedirectUri({
  scheme: 'myapp',
  path: 'auth/callback',
})

// Use AuthSession.useAuthRequest()
```

---

## Advanced Customizations

### 1. Multi-Tenant Application

```markdown
**Special Requirements:**
- Support multiple SSOJet tenants
- Dynamic OIDC configuration per organization
- Organization-specific login pages
- Tenant detection from subdomain or parameter
```

**Customization:**
```typescript
// Dynamic OIDC config based on tenant
const getTenantConfig = (tenantId: string) => ({
  client_id: process.env[`TENANT_${tenantId}_CLIENT_ID`],
  client_secret: process.env[`TENANT_${tenantId}_CLIENT_SECRET`],
  issuer: `https://api.ssojet.com/oidc/${tenantId}`,
})
```

### 2. Hybrid Authentication

```markdown
**Special Requirements:**
- Support both SSO and traditional login
- Allow users to link SSO with existing accounts
- Account merging logic
- Multiple authentication providers
```

**Customization:**
```typescript
// Account linking logic
const linkSSOAccount = async (userId: string, ssoProfile: any) => {
  // Check if SSO account already exists
  const existing = await db.ssoAccounts.findOne({
    provider: 'ssojet',
    providerAccountId: ssoProfile.sub,
  })
  
  if (existing && existing.userId !== userId) {
    throw new Error('SSO account already linked to another user')
  }
  
  // Link SSO account to user
  await db.ssoAccounts.create({
    userId,
    provider: 'ssojet',
    providerAccountId: ssoProfile.sub,
    email: ssoProfile.email,
  })
}
```

### 3. Custom Claims and Scopes

```markdown
**Special Requirements:**
- Request custom OIDC scopes
- Access custom claims from ID token
- Map claims to application roles
- Handle different user types
```

**Customization:**
```typescript
// Request custom scopes
authorization: {
  params: {
    scope: "openid profile email groups roles organization",
  },
}

// Map claims to app roles
callbacks: {
  async jwt({ token, profile }) {
    if (profile) {
      token.roles = profile.roles || []
      token.organization = profile.organization
      token.groups = profile.groups || []
    }
    return token
  },
  async session({ session, token }) {
    session.user.roles = token.roles
    session.user.organization = token.organization
    session.user.groups = token.groups
    return session
  },
}
```

### 4. Just-In-Time (JIT) User Provisioning

```markdown
**Special Requirements:**
- Auto-create users on first SSO login
- Sync user attributes from OIDC profile
- Update user data on each login
- Handle user activation workflow
```

**Customization:**
```typescript
callbacks: {
  async signIn({ user, account, profile }) {
    if (account.provider === "ssojet") {
      // Check if user exists in database
      let dbUser = await db.users.findOne({ email: profile.email })
      
      if (!dbUser) {
        // Create new user (JIT provisioning)
        dbUser = await db.users.create({
          email: profile.email,
          name: profile.name,
          picture: profile.picture,
          ssoProvider: "ssojet",
          ssoId: profile.sub,
          emailVerified: true,
          createdAt: new Date(),
        })
      } else {
        // Update existing user attributes
        await db.users.update(dbUser.id, {
          name: profile.name,
          picture: profile.picture,
          lastLogin: new Date(),
        })
      }
      
      user.id = dbUser.id
    }
    return true
  },
}
```

### 5. Role-Based Access Control (RBAC)

```markdown
**Special Requirements:**
- Enforce role-based permissions
- Protect routes based on user roles
- Handle permission checks in API
- Show/hide UI based on roles
```

**Customization:**
```typescript
// Middleware for role-based protection
export function withRoles(allowedRoles: string[]) {
  return async (req, res, next) => {
    const session = await getSession(req, res)
    
    if (!session?.user) {
      return res.status(401).json({ error: "Unauthorized" })
    }
    
    const userRoles = session.user.roles || []
    const hasPermission = allowedRoles.some(role => 
      userRoles.includes(role)
    )
    
    if (!hasPermission) {
      return res.status(403).json({ error: "Forbidden" })
    }
    
    next()
  }
}

// Usage
app.get("/api/admin", withRoles(["admin", "superadmin"]), (req, res) => {
  // Admin-only logic
})
```

### 6. Token Refresh Implementation

```markdown
**Special Requirements:**
- Implement automatic token refresh
- Handle refresh token expiration
- Silent token renewal
- Logout on refresh failure
```

**Customization:**
```typescript
callbacks: {
  async jwt({ token, account }) {
    // Initial sign in
    if (account) {
      return {
        ...token,
        accessToken: account.access_token,
        refreshToken: account.refresh_token,
        accessTokenExpires: Date.now() + account.expires_in * 1000,
      }
    }

    // Return previous token if not expired
    if (Date.now() < token.accessTokenExpires) {
      return token
    }

    // Access token has expired, try to refresh
    return await refreshAccessToken(token)
  },
}

async function refreshAccessToken(token) {
  try {
    const response = await fetch(
      `${process.env.SSOJET_ISSUER_URL}/token`,
      {
        method: "POST",
        headers: { "Content-Type": "application/x-www-form-urlencoded" },
        body: new URLSearchParams({
          client_id: process.env.SSOJET_CLIENT_ID,
          client_secret: process.env.SSOJET_CLIENT_SECRET,
          grant_type: "refresh_token",
          refresh_token: token.refreshToken,
        }),
      }
    )

    const refreshedTokens = await response.json()

    if (!response.ok) throw refreshedTokens

    return {
      ...token,
      accessToken: refreshedTokens.access_token,
      accessTokenExpires: Date.now() + refreshedTokens.expires_in * 1000,
      refreshToken: refreshedTokens.refresh_token ?? token.refreshToken,
    }
  } catch (error) {
    return {
      ...token,
      error: "RefreshAccessTokenError",
    }
  }
}
```

### 7. Email Domain-Based Auto-Detection

```markdown
**Special Requirements:**
- Auto-detect SSO-enabled domains
- Automatically trigger SSO for company emails
- Show SSO option only for valid domains
- Maintain domain whitelist
```

**Customization:**
```typescript
// Domain detection
const SSO_ENABLED_DOMAINS = [
  "acmecorp.com",
  "example.com",
  // Add more domains
]

const checkSSODomain = (email: string): boolean => {
  const domain = email.split("@")[1]
  return SSO_ENABLED_DOMAINS.includes(domain)
}

// In login component
const handleEmailChange = (email: string) => {
  setEmail(email)
  const isSSOEnabled = checkSSODomain(email)
  setShowSSOButton(isSSOEnabled)
  if (isSSOEnabled) {
    setIsSSOMode(true)
  }
}
```

---

## Testing Different Scenarios

### Local Development
```bash
SSOJET_CALLBACK_URL=http://localhost:3000/auth/callback
```

### Staging Environment
```bash
SSOJET_CALLBACK_URL=https://staging.myapp.com/auth/callback
```

### Production Environment
```bash
SSOJET_CALLBACK_URL=https://myapp.com/auth/callback
```

### Multiple Environments in SSOJet
Add all callback URLs to your SSOJet application:
```
http://localhost:3000/auth/callback
http://localhost:3000/api/auth/callback/ssojet
https://staging.myapp.com/auth/callback
https://myapp.com/auth/callback
```

---

## Framework Comparison Matrix

| Feature | Next.js (App) | Next.js (Pages) | CRA | Vite | Remix |
|---------|---------------|-----------------|-----|------|-------|
| SSR | ✅ Built-in | ✅ Built-in | ❌ | ❌ | ✅ Built-in |
| Server Actions | ✅ | ❌ | ❌ | ❌ | ✅ (Loaders/Actions) |
| Client-Side Auth | ✅ | ✅ | ✅ | ✅ | ✅ |
| PKCE Required | ⚠️ Optional | ⚠️ Optional | ✅ Yes | ✅ Yes | ⚠️ Optional |
| Session Storage | Server | Server | Client | Client | Server |
| Best Auth Library | NextAuth v5 | NextAuth v4 | oidc-client-ts | oidc-client-ts | remix-auth |

---

## Additional Resources

- [SSOJet Documentation](https://docs.ssojet.com)
- [OpenID Connect Spec](https://openid.net/connect/)
- [OAuth 2.0 Best Practices](https://tools.ietf.org/html/draft-ietf-oauth-security-topics)

---

<p align="center">
  <strong>Need help with customization?</strong><br>
  <a href="mailto:support@ssojet.com">Contact SSOJet Support</a>
</p>
