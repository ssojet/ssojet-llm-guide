# SSOJet Setup Guide

This guide walks you through setting up a new application in SSOJet for OIDC authentication.

## 📚 Overview

SSOJet is an OpenID Connect (OIDC) compliant identity provider that enables Single Sign-On (SSO) for your applications. This guide covers the initial setup process.

## 🚀 Quick Setup

### Step 1: Create a SSOJet Account

1. Visit [ssojet.com](https://portal.ssojet.com/)
2. Sign up with your email or use social login
3. Verify your email address
4. Complete your profile

### Step 2: Access the Dashboard

1. Log in to [portal.ssojet.com](https://portal.ssojet.com)
2. You'll see the main dashboard overview

![SSOJet Dashboard](https://cdn.ssojet.com/common/ssojet-dashboard.png)

## 🔧 Creating an Application

### Step 2.1: Navigate to Applications

1. Click **"Applications"** in the left sidebar
2. Click **"+ Create Application"** or **"New Application"** button

![Applications Page](https://cdn.ssojet.com/common/ssojet-applications.png)

### Step 2.2: Configure Application Details

Fill in the application details:

| Field | Description | Example |
|-------|-------------|---------|
| **Application Name** | A descriptive name for your app | "My React App" |
| **Application Type** | Type of application | "Regular Web App" or "Single Page Application" |
| **Description** | Optional description | "Main customer portal" |

**Application Types:**
- **Regular Web App**: Server-side rendered apps (Next.js, Remix)
- **Single Page Application**: Client-side apps (React SPA, Vite)
- **Native App**: Mobile or desktop apps (React Native, Electron)
- **Machine to Machine**: Backend services without user interaction

Click **"Create"** to proceed.

![Create Application Form](https://cdn.ssojet.com/common/ssojet-application-create.png)

### Step 2.3: Configure Callback URLs

Callback URLs (also called Redirect URIs) are where SSOJet redirects users after authentication.

1. In the application settings, find **"Allowed Callback URLs"**
2. Add your callback URLs (one per line):

**Development URLs:**
```
http://localhost:3000/api/auth/callback/ssojet
http://localhost:3000/auth/callback
http://localhost:3000/callback
```

**Production URLs:**
```
https://yourdomain.com/api/auth/callback/ssojet
https://yourdomain.com/auth/callback
```

3. Click **"Save Changes"**

![Configure Callback URLs](https://cdn.ssojet.com/common/ssojet-application-callbackurl.png)

**💡 Tip:** You can add multiple callback URLs for different environments.

### Step 2.4: Configure Logout URLs (Optional)

If you want to redirect users after logout:

1. Find **"Allowed Logout URLs"**
2. Add your logout redirect URLs:

```
http://localhost:3000
https://yourdomain.com
```

### Step 2.5: Configure Web Origins (For SPAs)

If you're building a Single Page Application:

1. Find **"Allowed Web Origins"**
2. Add your application URLs:

```
http://localhost:3000
https://yourdomain.com
```

This is required for CORS to work properly with token refresh.

## 🔑 Retrieving Credentials

### Step 3.1: Get Client ID and Secret

1. In your application's details page, locate the **"Credentials"** section
2. Copy the **Client ID**:
   ```
   cli_d4msncam6ljs71nsj520
   ```
3. Click **"Show"** next to **Client Secret** and copy it:
   ```
   your_secret_here_keep_secure
   ```

**⚠️ Security Warning:**
- Never commit your Client Secret to version control
- Store it securely in environment variables
- Rotate secrets periodically
- For SPAs, consider using PKCE flow instead (no secret needed)

![Application Credentials](https://cdn.ssojet.com/common/ssojet-application-credentials.png)

### Step 3.2: Get OIDC Endpoints

1. Navigate to **"Advanced"** tab in your application settings
2. Click **"Endpoints"**
3. Copy the **Issuer URL**:
   ```
   https://api.ssojet.com/oidc
   ```

You'll also see other endpoints:
- **Authorization Endpoint**: `https://api.ssojet.com/oidc/authorize`
- **Token Endpoint**: `https://api.ssojet.com/oidc/token`
- **UserInfo Endpoint**: `https://api.ssojet.com/oidc/userinfo`
- **JWKS URI**: `https://api.ssojet.com/oidc/.well-known/jwks.json`

**💡 Tip:** Most OIDC libraries only need the Issuer URL and will discover the other endpoints automatically.

## 🔐 Security Settings

### Enable PKCE (Recommended for SPAs)

PKCE (Proof Key for Code Exchange) adds extra security for public clients:

1. Navigate to **"Advanced"** → **"Grant Types"**
2. Enable **"Authorization Code with PKCE"**
3. Disable **"Authorization Code"** (without PKCE) for SPAs
4. Save changes

### Configure Token Expiration

Customize token lifetimes:

1. Navigate to **"Token Settings"**
2. Configure expiration times:
   - **Access Token**: 3600 seconds (1 hour) - default
   - **Refresh Token**: 2592000 seconds (30 days) - default
   - **ID Token**: 3600 seconds (1 hour) - default

### Enable Refresh Tokens

Allow long-lived sessions:

1. Navigate to **"Advanced"** → **"Grant Types"**
2. Enable **"Refresh Token"**
3. Save changes

## 🌐 SSO Connection Setup

To allow users from an organization to log in via their corporate SSO:

1. Navigate to **"SSO Connections"** in the dashboard
2. Click **"+ Add Connection"**
3. Choose the connection type:
   - **SAML 2.0**
   - **OIDC/OAuth 2.0**
   - **LDAP**
   - **Active Directory**

For detailed SSO setup instructions, see:
📘 [SSO Connection Setup Guide](https://docs.ssojet.com/how-to-guides/sso/integrations/)

## ✅ Testing Your Setup

### Test with SSOJet's OIDC Playground

1. Visit the OIDC playground: [playground.ssojet.com](https://playground.ssojet.com)
2. Enter your Client ID
3. Enter your Callback URL
4. Click "Start Flow"
5. Verify you can authenticate successfully

### Manual Testing

Build a simple test page:

```html
<!DOCTYPE html>
<html>
<body>
  <h1>Test SSOJet OIDC</h1>
  <button onclick="login()">Login with SSOJet</button>
  
  <script>
    function login() {
      const clientId = 'YOUR_CLIENT_ID'
      const redirectUri = 'http://localhost:3000/callback'
      const issuer = 'https://api.ssojet.com/oidc'
      
      const authUrl = `${issuer}/authorize?` +
        `client_id=${clientId}&` +
        `redirect_uri=${redirectUri}&` +
        `response_type=code&` +
        `scope=openid profile email&` +
        `state=${Math.random().toString(36)}`
      
      window.location.href = authUrl
    }
  </script>
</body>
</html>
```

## 📊 Monitoring & Logs

### View Authentication Logs

1. Navigate to **"Logs"** in the dashboard
2. Filter by:
   - Application
   - Event type (login, logout, error)
   - Date range
   - User email

### Set Up Webhooks (Optional)

Get notified of authentication events:

1. Navigate to **"Webhooks"** in settings
2. Click **"+ Add Webhook"**
3. Enter your webhook URL
4. Select events to subscribe to:
   - User login
   - User logout
   - Login failure
   - User created

## 🆘 Troubleshooting

### Common Issues

**Error: "Redirect URI mismatch"**
- **Solution**: Verify the callback URL in your application matches exactly what's configured in SSOJet (including protocol, port, and path)

**Error: "Invalid client"**
- **Solution**: Check that your Client ID and Client Secret are correct

**Error: "Unauthorized client"**
- **Solution**: Ensure your application type matches your implementation (SPA vs Web App)

**Token expires too quickly**
- **Solution**: Adjust token expiration settings or implement refresh token flow

### Getting Help

- 📧 Email: [support@ssojet.com](mailto:support@ssojet.com)
- 📚 Documentation: [docs.ssojet.com](https://docs.ssojet.com)
- 🐛 Report Issues: [github.com/ssojet/issues](https://github.com/ssojet/issues)

## 📚 Next Steps

Now that your SSOJet application is configured:

1. **Choose your framework guide:**
   - [Next.js Guide](/guides/nextjs-app-router/)
   - [React SPA Guide](/guides/react-cra/)
   - [Remix Guide](/guides/remix/)

2. **Integrate with your application:**
   - Follow the framework-specific integration guide
   - Test both traditional and SSO login flows
   - Set up proper error handling

3. **Configure SSO connections:**
   - Follow the [SSO Connection Setup Guide](https://docs.ssojet.com/how-to-guides/sso/integrations/)
   - Test with real user accounts

4. **Deploy to production:**
   - Update callback URLs for production
   - Secure your environment variables
   - Monitor authentication logs

## 🔗 Additional Resources

### SSOJet Resources
- [Official Documentation](https://docs.ssojet.com)
- [API Reference](https://docs.ssojet.com/api-reference/)
- [SDKs & Libraries](https://docs.ssojet.com/sdks/)
- [Blog & Tutorials](https://ssojet.com/blog)

### OIDC Resources
- [OpenID Connect Specification](https://openid.net/connect/)
- [OAuth 2.0 RFC](https://tools.ietf.org/html/rfc6749)
- [OIDC Playground](https://ssojet.com/oidc-playground/)

---

<p align="center">
  Made with ❤️ by the <a href="https://ssojet.com">SSOJet</a> team
</p>
