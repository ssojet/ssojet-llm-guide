# AI Prompt Template for SSOJet Angular Integration Guide

## AI-Powered Integration Guide
Let our LLM AI prompts guide you in creating a secure and seamless SSO integration, tailored specifically to your application's needs.

---

You are an expert AI assistant tasked with creating a detailed, step-by-step guide for developers to integrate "Sign in with SSO" functionality into an existing login page in a $Angular application using SSOJet as an OIDC identity provider. The goal is to modify the existing login flow to add SSO support without disrupting the current traditional login functionality (e.g., email/password). Below is the step-by-step instruction set for you to follow. Use the provided details and examples to generate a Markdown-formatted guide similar to the structure of previous guides.

---

## Task Requirements  

**Objective**: Modify an existing $Angular login page to add a "Sign in with SSO" link. When clicked, the password field (if present) hides, only the email field shows, the login button changes to "Continue with SSO", and an OIDC request is triggered with the `login_hint` parameter set to the entered email. After successful authentication, handle the authorization code response and redirect to an existing post-login page (e.g., `/dashboard`).  

**Target Audience**: Developers familiar with $Angular and its common frameworks/tools (e.g., ${FRAMEWORK_TOOLS}).  

**SSO Provider**: Use SSOJet, an OIDC-compliant identity provider.  

**Existing Setup**: Assume the application has a login page with a form (email and password fields) and a backend handler for traditional login. Modify this setup, not replace it.

---

## Step-by-Step Instructions for the AI  

### Step 1: Set the Context  
- Start by defining the title, description, and sidebar metadata in the Markdown header. Use placeholders for customization.  
- Provide an introductory paragraph explaining the guide's purpose, referencing the modification of an existing login page and the SSOJet OIDC integration.  

### Step 2: Define Prerequisites  
List prerequisites tailored to $Angular, including:  
- An existing $Angular application with a login page.  
- Basic knowledge of $Angular and its common tools/frameworks (e.g., ${FRAMEWORK_TOOLS}).  
- An active SSOJet account.  
- A reference to the SSOJet connection setup guide:  
  - [SSO Connection Setup Guide](/how-to-guides/sso/integrations/)  
- Required libraries or packages specific to $Angular for OIDC (e.g., "oidc-client-ts" for JavaScript, "passport-openidconnect" for Node.js, "goth" for Golang).

### Step 3: Step-by-Step Implementation  

#### Step 3.1: Create Application in SSOJet  
Replicate the SSOJet application setup section from previous guides, keeping it consistent:  
1. Log in to the SSOJet Dashboard.  
2. Navigate to **Applications**.  
3. Create a new application (e.g., "My$AngularApp", type **Regular Web App**).  
4. Configure the callback URI (e.g., '$/auth/callback' specific to $Angular, like 'http://localhost:3000/auth/callback' for Node.js).  
5. Retrieve **Client ID** and **Client Secret**.  
6. Copy the **Issuer URL** from the **Advanced > Endpoints** section.  
7. Include placeholder images (e.g., 'ssojet-applications-stepX.png') with captions matching previous guides.

#### Step 3.2: Modify the Existing $Angular Project  

##### Substep 3.2.1: Install Dependencies  
- Specify the OIDC library installation command for $Angular (e.g., 'npm install' for Node.js, 'go get' for Golang, 'dotnet add package' for .NET).  

##### Substep 3.2.2: Configure OIDC  
- Provide a code snippet to configure the OIDC provider with SSOJet credentials:
  - **Client ID**: ${cli_d4msncam6ljs71nsj520.f4c805ddbab54710bbaa915753121afb.pUmFsrGxUWks4mFqVZnNF}
  - **Client Secret**: ${CLIENT_SECRET}
  - **Issuer URL**: ${ISSUER_URL}
  - **Callback URL**: $/auth/callback
  - **Scopes**: openid profile email
- Tailor to $Angular conventions (e.g., **Passport** for Node.js, **OpenIdConnect middleware** for .NET, **Goth** for Golang).  

##### Substep 3.2.3: Update Login Page/UI  
Modify the existing login template or component to:  
- Add the "Sign in with SSO" link/button to toggle between traditional and SSO modes.  
- When SSO mode is activated: hide password field, change button text to "Continue with SSO".  
- Update form submission logic: detect mode and call appropriate authentication handler.  
- For **SSO mode**, pass `login_hint` parameter with the email to the OIDC library's sign-in method.  
- Use $Angular-specific templating or UI logic (e.g., **Angular components** for Next.js, **EJS** for Node.js, **Razor** for .NET, **html/template** for Golang).  
- Include basic CSS styling for form, buttons, and toggle element.

##### Substep 3.2.4: Handle OIDC Callback  
Explain that callback handling is automatic in most OIDC libraries, but may require:  
- Creating a dedicated callback route/page (e.g., `/callback` or `/auth/callback`).  
- Ensuring the callback URL matches the one configured in SSOJet dashboard.  
- Redirecting authenticated users to the post-login page (e.g., `/dashboard`).

### Step 3.3: Test the Integration  
Outline testing steps:  
1. Run the app and navigate to the login page.  
2. Test **traditional login** to ensure it still works.  
3. Test **SSO flow**:  
   - Click **"Sign in with SSO"**.  
   - Verify UI toggle (password hides, button text changes).  
   - Enter an email, trigger **OIDC flow**, check redirect and logs after authentication.  

---

## Step 4: Additional Considerations  

List considerations tailored to $Angular:  
- **Error Handling**: Suggest adding error responses matching existing patterns.  
- **Styling**: Recommend CSS adjustments for UI consistency.  
- **Security**: Advise integrating SSO user data with existing session/auth systems.  
- **Dynamic Redirect URI**: Note updating the callback URL for production.  
- **Session Management**: Suggest adding session support if not present (e.g., 'express-session', 'gorilla/sessions').

---

## Step 5: Support Section  

Provide support resources:  
- **Contact SSOJet support**.  
- **Check application logs**.  
- Link to relevant $Angular-specific OIDC library docs (e.g., **Passport for Node.js**, **Goth for Golang**).

---

## Customization Instructions  
- Replace '$Angular' with the target language (e.g., **Node.js**, **ASP.NET Core**, **Golang**).  
- Replace '${FRAMEWORK_TOOLS}' with common tools (e.g., **Express** for Node.js, **Razor Pages** for .NET, **Gorilla Mux** for Golang).  
- Replace '$/auth/callback' with a language-appropriate callback (e.g., '/auth/callback', '/signin-oidc').  
- Reference an **existing guide** (e.g., **"Node.js guide above"**) for structural consistency.

---

<p align="center">
  <strong>This prompt template is maintained by <a href="https://ssojet.com">SSOJet</a></strong><br>
  <a href="https://ssojet.com">Website</a> •
  <a href="https://docs.ssojet.com">Documentation</a> •
  <a href="https://portal.ssojet.com">Dashboard</a>
</p>
