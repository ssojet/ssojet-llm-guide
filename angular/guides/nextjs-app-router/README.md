# Sign in with SSO Integration - Next.js (App Router)

Complete guide for integrating SSOJet SSO authentication into your existing Next.js application using the App Router.

## 📚 Overview

This guide walks you through integrating [SSOJet](https://ssojet.com)'s "Sign in with SSO" functionality into your existing Next.js 14+ login page using the App Router. You'll preserve your current email/password authentication while adding enterprise SSO capabilities using the OpenID Connect (OIDC) standard.

**What you'll build:**
- ✅ Add "Sign in with SSO" option to existing login page
- ✅ Dynamic UI that toggles between password and SSO modes
- ✅ OIDC authentication flow with login hint
- ✅ Secure session management
- ✅ Non-disruptive integration (existing auth still works)

## 🎯 Prerequisites

Before starting, ensure you have:

- ✅ An existing Next.js 14+ application with App Router
- ✅ A login page with email/password form
- ✅ Basic knowledge of Next.js, React Server Components, and TypeScript
- ✅ Node.js 18+ installed
- ✅ An active [SSOJet account](https://portal.ssojet.com)

**Recommended Knowledge:**
- Understanding of OIDC/OAuth 2.0 concepts
- Familiarity with Next.js App Router patterns
- Experience with environment variables

## 📦 Required Libraries

We'll use **NextAuth.js v5** (Auth.js) for OIDC integration:

- `next-auth@beta` - Authentication library with OIDC support
- Built-in OIDC provider configuration
- Server-side session management
- Type-safe API

---

## 🚀 Step 1: Create Application in SSOJet

### 1.1 Access SSOJet Dashboard

1. Log in to [SSOJet Dashboard](https://portal.ssojet.com)
2. Navigate to **Applications** in the left sidebar
3. Click **"+ Create Application"**

### 1.2 Configure Application

**Application Details:**
- **Name**: `My Next.js App` (or your preferred name)
- **Type**: Select **"Regular Web App"**
- Click **"Create"**

### 1.3 Configure Callback URLs

Add your callback URLs in the application settings:

**Development:**
```
http://localhost:3000/api/auth/callback/ssojet
```

**Production:**
```
https://yourdomain.com/api/auth/callback/ssojet
```

Click **"Save Changes"**

### 1.4 Retrieve Credentials

Copy the following from your application settings:

1. **Client ID**: `cli_d4msncam6ljs71nsj520`
2. **Client Secret**: Click "Show" and copy (keep secure!)
3. Navigate to **Advanced** → **Endpoints**
4. Copy **Issuer URL**: `https://api.ssojet.com/oidc`

**⚠️ Security:** Never commit your Client Secret to version control!

---

## 🔧 Step 2: Install Dependencies

Install NextAuth v5:

```bash
npm install next-auth@beta
# or
yarn add next-auth@beta
# or
pnpm add next-auth@beta
```

---

## ⚙️ Step 3: Configure Environment Variables

Create or update `.env.local` in your project root:

```bash
# SSOJet OIDC Configuration
SSOJET_CLIENT_ID=cli_d4msncam6ljs71nsj520
SSOJET_CLIENT_SECRET=your_client_secret_here
SSOJET_ISSUER_URL=https://api.ssojet.com/oidc

# NextAuth Configuration
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=your_generated_secret_here

# Post-login redirect
REDIRECT_AFTER_LOGIN=/dashboard
```

**Generate a secure secret:**

```bash
openssl rand -base64 32
```

**Add to `.gitignore`:**

```gitignore
# Environment Variables
.env*.local
.env
```

---

## 🔐 Step 4: Configure NextAuth with SSOJet

### 4.1 Create Auth Configuration

Create `auth.ts` in your project root:

```typescript
import NextAuth from "next-auth"

export const { handlers, signIn, signOut, auth } = NextAuth({
  providers: [
    {
      id: "ssojet",
      name: "SSO",
      type: "oidc",
      issuer: process.env.SSOJET_ISSUER_URL,
      clientId: process.env.SSOJET_CLIENT_ID,
      clientSecret: process.env.SSOJET_CLIENT_SECRET,
      authorization: {
        params: {
          scope: "openid profile email",
        },
      },
      profile(profile) {
        return {
          id: profile.sub,
          name: profile.name,
          email: profile.email,
          image: profile.picture,
        }
      },
    },
  ],
  callbacks: {
    async signIn({ user, account, profile }) {
      // Custom logic: check if user exists in your database
      // Add your user provisioning logic here
      console.log("User signed in:", user.email)
      return true
    },
    async redirect({ url, baseUrl }) {
      // Redirect to dashboard after successful login
      if (url.startsWith(baseUrl)) return url
      return `${baseUrl}${process.env.REDIRECT_AFTER_LOGIN || "/dashboard"}`
    },
    async session({ session, token }) {
      // Add user ID to session
      if (token?.sub) {
        session.user.id = token.sub
      }
      return session
    },
    async jwt({ token, account, profile }) {
      // Store additional info in JWT
      if (account && profile) {
        token.accessToken = account.access_token
      }
      return token
    },
  },
  pages: {
    signIn: "/login", // Your existing login page
  },
  session: {
    strategy: "jwt",
  },
})
```

### 4.2 Create API Route Handler

Create `app/api/auth/[...nextauth]/route.ts`:

```typescript
import { handlers } from "@/auth"

export const { GET, POST } = handlers
```

### 4.3 Update TypeScript Types (Optional)

Create `types/next-auth.d.ts`:

```typescript
import { DefaultSession } from "next-auth"

declare module "next-auth" {
  interface Session {
    user: {
      id: string
    } & DefaultSession["user"]
  }
}
```

---

## 🎨 Step 5: Modify Login Page

Update your existing login page to support SSO mode.

### 5.1 Create Login Page Component

Create or update `app/login/page.tsx`:

```typescript
"use client"

import { useState } from "react"
import { signIn } from "next-auth/react"
import { useRouter } from "next/navigation"
import "./login.css"

export default function LoginPage() {
  const [email, setEmail] = useState("")
  const [password, setPassword] = useState("")
  const [isSSOMode, setIsSSOMode] = useState(false)
  const [isLoading, setIsLoading] = useState(false)
  const [error, setError] = useState<string | null>(null)
  const router = useRouter()

  // Traditional login handler (your existing logic)
  const handleTraditionalLogin = async (e: React.FormEvent) => {
    e.preventDefault()
    setIsLoading(true)
    setError(null)

    try {
      // Your existing traditional login API call
      const response = await fetch("/api/auth/login", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ email, password }),
      })

      if (response.ok) {
        router.push("/dashboard")
      } else {
        const data = await response.json()
        setError(data.message || "Login failed")
      }
    } catch (error) {
      console.error("Login error:", error)
      setError("An unexpected error occurred")
    } finally {
      setIsLoading(false)
    }
  }

  // SSO login handler
  const handleSSOLogin = async (e: React.FormEvent) => {
    e.preventDefault()
    setIsLoading(true)
    setError(null)

    try {
      // Trigger OIDC flow with login_hint parameter
      const result = await signIn("ssojet", {
        callbackUrl: "/dashboard",
        redirect: true,
        login_hint: email, // Pre-fill email in SSOJet
      })

      if (result?.error) {
        setError("SSO login failed. Please try again.")
        setIsLoading(false)
      }
    } catch (error) {
      console.error("SSO login error:", error)
      setError("SSO login failed. Please try again.")
      setIsLoading(false)
    }
  }

  return (
    <div className="login-container">
      <div className="login-card">
        <h1>Welcome Back</h1>
        <p className="subtitle">Sign in to your account</p>

        {error && (
          <div className="error-message" role="alert">
            {error}
          </div>
        )}

        <form onSubmit={isSSOMode ? handleSSOLogin : handleTraditionalLogin}>
          {/* Email Field - Always visible */}
          <div className="form-group">
            <label htmlFor="email">Email</label>
            <input
              id="email"
              type="email"
              value={email}
              onChange={(e) => setEmail(e.target.value)}
              required
              placeholder="your.email@company.com"
              disabled={isLoading}
              autoComplete="email"
            />
          </div>

          {/* Password Field - Hidden in SSO mode */}
          {!isSSOMode && (
            <div className="form-group">
              <label htmlFor="password">Password</label>
              <input
                id="password"
                type="password"
                value={password}
                onChange={(e) => setPassword(e.target.value)}
                required
                placeholder="••••••••"
                disabled={isLoading}
                autoComplete="current-password"
              />
              <a href="/forgot-password" className="forgot-password">
                Forgot password?
              </a>
            </div>
          )}

          {/* Submit Button */}
          <button
            type="submit"
            disabled={isLoading || !email || (!isSSOMode && !password)}
            className="btn-primary"
          >
            {isLoading ? (
              <span className="loading-spinner">Signing in...</span>
            ) : isSSOMode ? (
              "Continue with SSO"
            ) : (
              "Sign In"
            )}
          </button>
        </form>

        {/* SSO Toggle */}
        <div className="divider">
          <span>or</span>
        </div>

        <div className="sso-toggle">
          {!isSSOMode ? (
            <button
              type="button"
              onClick={() => {
                setIsSSOMode(true)
                setError(null)
              }}
              className="btn-link"
              disabled={isLoading}
            >
              Sign in with SSO →
            </button>
          ) : (
            <button
              type="button"
              onClick={() => {
                setIsSSOMode(false)
                setError(null)
              }}
              className="btn-link"
              disabled={isLoading}
            >
              ← Back to password login
            </button>
          )}
        </div>

        {/* Sign up link */}
        <div className="signup-link">
          Don't have an account?{" "}
          <a href="/signup" className="link">
            Sign up
          </a>
        </div>
      </div>
    </div>
  )
}
```

### 5.2 Add CSS Styling

Create `app/login/login.css`:

```css
.login-container {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  padding: 1rem;
}

.login-card {
  background: white;
  border-radius: 12px;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  padding: 2.5rem;
  width: 100%;
  max-width: 420px;
}

.login-card h1 {
  margin: 0 0 0.5rem 0;
  font-size: 1.75rem;
  color: #1a202c;
  font-weight: 700;
}

.subtitle {
  margin: 0 0 2rem 0;
  color: #718096;
  font-size: 0.95rem;
}

.error-message {
  background-color: #fed7d7;
  color: #c53030;
  padding: 0.75rem 1rem;
  border-radius: 6px;
  margin-bottom: 1.5rem;
  font-size: 0.9rem;
  border: 1px solid #fc8181;
}

.form-group {
  margin-bottom: 1.25rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: 600;
  color: #2d3748;
  font-size: 0.9rem;
}

.form-group input {
  width: 100%;
  padding: 0.75rem 1rem;
  border: 2px solid #e2e8f0;
  border-radius: 8px;
  font-size: 1rem;
  transition: border-color 0.2s, box-shadow 0.2s;
}

.form-group input:focus {
  outline: none;
  border-color: #667eea;
  box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
}

.form-group input:disabled {
  background-color: #f7fafc;
  cursor: not-allowed;
}

.forgot-password {
  display: block;
  margin-top: 0.5rem;
  font-size: 0.85rem;
  color: #667eea;
  text-decoration: none;
  text-align: right;
}

.forgot-password:hover {
  text-decoration: underline;
}

.btn-primary {
  width: 100%;
  padding: 0.875rem;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: transform 0.2s, box-shadow 0.2s;
  margin-top: 0.5rem;
}

.btn-primary:hover:not(:disabled) {
  transform: translateY(-2px);
  box-shadow: 0 10px 20px rgba(102, 126, 234, 0.3);
}

.btn-primary:active:not(:disabled) {
  transform: translateY(0);
}

.btn-primary:disabled {
  background: #cbd5e0;
  cursor: not-allowed;
  transform: none;
}

.loading-spinner {
  display: inline-block;
}

.divider {
  margin: 1.5rem 0;
  text-align: center;
  position: relative;
}

.divider::before {
  content: "";
  position: absolute;
  top: 50%;
  left: 0;
  right: 0;
  height: 1px;
  background-color: #e2e8f0;
}

.divider span {
  background: white;
  padding: 0 1rem;
  color: #718096;
  font-size: 0.85rem;
  position: relative;
  z-index: 1;
}

.sso-toggle {
  text-align: center;
}

.btn-link {
  background: none;
  border: none;
  color: #667eea;
  cursor: pointer;
  font-size: 0.95rem;
  font-weight: 500;
  padding: 0.5rem;
  transition: color 0.2s;
}

.btn-link:hover:not(:disabled) {
  color: #764ba2;
  text-decoration: underline;
}

.btn-link:disabled {
  color: #cbd5e0;
  cursor: not-allowed;
}

.signup-link {
  margin-top: 1.5rem;
  text-align: center;
  font-size: 0.9rem;
  color: #718096;
}

.signup-link .link {
  color: #667eea;
  text-decoration: none;
  font-weight: 600;
}

.signup-link .link:hover {
  text-decoration: underline;
}
```

---

## 🔒 Step 6: Protect Routes with Middleware

Create `middleware.ts` in your project root:

```typescript
import { auth } from "@/auth"
import { NextResponse } from "next/server"

export default auth((req) => {
  const isLoggedIn = !!req.auth
  const isOnDashboard = req.nextUrl.pathname.startsWith("/dashboard")
  const isOnLogin = req.nextUrl.pathname.startsWith("/login")

  // Redirect to login if accessing protected route while not logged in
  if (isOnDashboard && !isLoggedIn) {
    return NextResponse.redirect(new URL("/login", req.url))
  }

  // Redirect to dashboard if accessing login while logged in
  if (isOnLogin && isLoggedIn) {
    return NextResponse.redirect(new URL("/dashboard", req.url))
  }

  return NextResponse.next()
})

export const config = {
  matcher: ["/((?!api|_next/static|_next/image|favicon.ico).*)"],
}
```

---

## 🧪 Step 7: Test the Integration

### 7.1 Start Development Server

```bash
npm run dev
```

### 7.2 Test Traditional Login

1. Navigate to `http://localhost:3000/login`
2. Enter email and password
3. Click **"Sign In"**
4. ✅ Verify you're redirected to dashboard
5. ✅ Confirm traditional login still works

### 7.3 Test SSO Flow

1. Navigate to `http://localhost:3000/login`
2. Click **"Sign in with SSO"**
3. Verify:
   - ✅ Password field disappears
   - ✅ Button text changes to "Continue with SSO"
   - ✅ "Back to password login" link appears
4. Enter an email (e.g., `user@company.com`)
5. Click **"Continue with SSO"**
6. Verify:
   - ✅ Redirected to SSOJet authentication page
   - ✅ Email is pre-filled (login_hint working)
7. Complete authentication on SSOJet
8. Verify:
   - ✅ Redirected back to your app
   - ✅ Landed on `/dashboard`
   - ✅ User session is active

### 7.4 Check Browser Console

- ✅ No JavaScript errors
- ✅ Network tab shows OIDC requests
- ✅ Tokens are received

---

## 📊 Step 8: Access User Data

### In Server Components

```typescript
import { auth } from "@/auth"

export default async function DashboardPage() {
  const session = await auth()

  if (!session?.user) {
    return <div>Not authenticated</div>
  }

  return (
    <div>
      <h1>Welcome, {session.user.name}!</h1>
      <p>Email: {session.user.email}</p>
      <img src={session.user.image || ""} alt="Profile" />
    </div>
  )
}
```

### In Client Components

```typescript
"use client"

import { useSession } from "next-auth/react"

export default function ProfileComponent() {
  const { data: session, status } = useSession()

  if (status === "loading") {
    return <div>Loading...</div>
  }

  if (!session) {
    return <div>Not authenticated</div>
  }

  return (
    <div>
      <h2>Profile</h2>
      <p>Name: {session.user?.name}</p>
      <p>Email: {session.user?.email}</p>
    </div>
  )
}
```

### In API Routes

```typescript
import { auth } from "@/auth"
import { NextResponse } from "next/server"

export async function GET() {
  const session = await auth()

  if (!session) {
    return NextResponse.json({ error: "Unauthorized" }, { status: 401 })
  }

  return NextResponse.json({ user: session.user })
}
```

---

## 🚀 Step 9: Deploy to Production

### 9.1 Update Environment Variables

In your production environment (Vercel, AWS, etc.), set:

```bash
SSOJET_CLIENT_ID=cli_d4msncam6ljs71nsj520
SSOJET_CLIENT_SECRET=your_production_secret
SSOJET_ISSUER_URL=https://api.ssojet.com/oidc
NEXTAUTH_URL=https://yourdomain.com
NEXTAUTH_SECRET=your_production_secret
REDIRECT_AFTER_LOGIN=/dashboard
```

### 9.2 Update SSOJet Callback URLs

In SSOJet Dashboard, add production callback URL:

```
https://yourdomain.com/api/auth/callback/ssojet
```

### 9.3 Deploy

```bash
# Vercel
vercel --prod

# Or your deployment command
npm run build
```

---

## 🔧 Additional Considerations

### Error Handling

Add comprehensive error handling:

```typescript
// app/api/auth/error/page.tsx
export default function AuthErrorPage({
  searchParams,
}: {
  searchParams: { error?: string }
}) {
  const errorMessages: Record<string, string> = {
    Configuration: "There is a problem with the server configuration.",
    AccessDenied: "You do not have permission to sign in.",
    Verification: "The verification token has expired or has already been used.",
    Default: "An error occurred during authentication.",
  }

  const error = searchParams.error || "Default"
  const message = errorMessages[error] || errorMessages.Default

  return (
    <div className="error-container">
      <h1>Authentication Error</h1>
      <p>{message}</p>
      <a href="/login">Back to Login</a>
    </div>
  )
}
```

### Session Management

Implement logout:

```typescript
"use client"

import { signOut } from "next-auth/react"

export function LogoutButton() {
  return (
    <button onClick={() => signOut({ callbackUrl: "/login" })}>
      Sign Out
    </button>
  )
}
```

### Security Best Practices

- ✅ Use HTTPS in production
- ✅ Never expose Client Secret in frontend
- ✅ Implement CSRF protection (handled by NextAuth)
- ✅ Set secure cookie flags
- ✅ Validate tokens on backend
- ✅ Rotate secrets periodically

---

## 🆘 Troubleshooting

### Common Issues

**Error: "Redirect URI mismatch"**
- **Solution**: Verify callback URL in SSOJet exactly matches your configuration

**Error: "Invalid client"**
- **Solution**: Check Client ID and Secret in `.env.local`

**Login hint not working**
- **Solution**: Ensure `login_hint` parameter is passed correctly

**Session not persisting**
- **Solution**: Check `NEXTAUTH_SECRET` is set properly

---

## 📚 Resources

### SSOJet
- [SSOJet Documentation](https://docs.ssojet.com)
- [SSOJet Dashboard](https://portal.ssojet.com)
- [SSO Connection Setup](https://docs.ssojet.com/how-to-guides/sso/integrations/)

### NextAuth
- [NextAuth Documentation](https://next-auth.js.org)
- [NextAuth v5 Migration Guide](https://authjs.dev/getting-started/migrating-to-v5)

### Support
- 📧 [support@ssojet.com](mailto:support@ssojet.com)

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
