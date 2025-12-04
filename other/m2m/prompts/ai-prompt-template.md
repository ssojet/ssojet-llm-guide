# AI Prompt Template for SSOJet Vue Integration Guide

## AI-Powered Integration Guide
Let our LLM AI prompts guide you in creating a secure and seamless SSO integration, tailored specifically to your application's needs.


You are an expert AI assistant tasked with creating a detailed, step-by-step guide for developers to integrate "Sign in with SSO" functionality into an existing login page in a $Any application using SSOJet as an OIDC identity provider. The goal is to modify the existing login flow to add SSO support without disrupting the current traditional login functionality (e.g., email/password). Below is the step-by-step instruction set for you to follow. Use the provided details and examples to generate a Markdown-formatted guide similar to the structure of previous guides.

---

## Task Requirements  

**Objective**: Modify an existing $Any login page to add a "Sign in with SSO" link. When clicked, the password field (if present) hides, only the email field shows, the login button changes to "Continue with SSO", and an OIDC request is triggered with the `login_hint` parameter set to the entered email. After successful authentication, handle the authorization code response and redirect to an existing post-login page (e.g., `/dashboard`).  

**Target Audience**: Developers familiar with $Any and its common frameworks/tools (e.g., ${FRAMEWORK_TOOLS}).  

**SSO Provider**: Use SSOJet, an OIDC-compliant identity provider.  

**Existing Setup**: Assume the application has a login page with a form (email and password fields) and a backend handler for traditional login. Modify this setup, not replace it.  

---

## Step-by-Step Instructions for the AI  

### Step 1: Set the Context  
- Start by defining the title, description, and sidebar metadata in the Markdown header. Use placeholders for customization.  
- Provide an introductory paragraph explaining the guide's purpose, referencing the modification of an existing login page and the SSOJet OIDC integration.  

### Step 2: Define Prerequisites  
List prerequisites tailored to $Any, including:  
- An existing $Any application with a login page.  
- Basic knowledge of $Any and its common tools/frameworks (e.g., ${FRAMEWORK_TOOLS}).  
- An active SSOJet account.  
- A reference to the SSOJet connection setup guide:  
  - [SSO Connection Setup Guide](/how-to-guides/sso/integrations/)  
- Required libraries or packages specific to $Any for OIDC (e.g., "oidc-client-ts" for JavaScript, "passport-openidconnect" for Node.js, "goth" for Golang).  

### Step 3: Step-by-Step Implementation  

#### Step 3.1: Create Application in SSOJet  
Replicate the SSOJet application setup section from previous guides, keeping it consistent:  
1. Log in to the SSOJet Dashboard.  
2. Navigate to **Applications**.  
3. Create a new application (e.g., "My$AnyApp", type **Regular Web App**).  
4. Configure the callback URI (e.g., '$N/A' specific to $Any, like 'http://localhost:3000/auth/callback' for Node.js).  
5. Retrieve **Client ID** and **Client Secret**.  
6. Copy the **Issuer URL** from the **Advanced > Endpoints** section.  
7. Include placeholder images (e.g., 'ssojet-applications-stepX.png') with captions matching previous guides.  

#### Step 3.2: Modify the Existing $Any Project  

##### Substep 3.2.1: Install Dependencies  
- Specify the OIDC library installation command for $Any (e.g., 'npm install' for Node.js, 'go get' for Golang, 'dotnet add package' for .NET).  

##### Substep 3.2.2: Configure OIDC  
- Provide a code snippet to configure the OIDC provider with SSOJet credentials:
  - **Client ID**: ${cli_d4msncam6ljs71nsj520.f4c805ddbab54710bbaa915753121afb.pUmFsrGxUWks4mFqVZnNF}
  - **Client Secret**: ${CLIENT_SECRET}
  - **Issuer URL**: ${ISSUER_URL}
  - **Callback URL**: $N/A
  - **Scopes**: openid profile email
- Tailor to $Any conventions (e.g., **Passport** for Node.js, **OpenIdConnect middleware** for .NET, **Goth** for Golang).  

##### Substep 3.2.3: Update Login Page/UI  
Modify the existing login template or component to:  
- Add the "Sign in with SSO" link.  
- Toggle UI elements when clicked (hide password, change button text).  
- Use $Any-specific templating or UI logic (e.g., **EJS** for Node.js, **Razor** for .NET, **html/template** for Golang).  

Example UI structure:  
- **If not SSO mode**: Show email, password, "Sign In" button, and "Sign in with SSO" link.  
- **If SSO mode**: Show email only, "Continue with SSO" button.  

##### Substep 3.2.4: Update Backend Logic  
Modify the existing login handler to:  
- Detect **SSO mode** (e.g., via query param 'sso=true' or form data).  
- For **SSO mode**, trigger an OIDC request with 'login_hint' set to the email.  
- Add a **callback handler** to process the OIDC response and redirect to the existing post-login page (e.g., '/dashboard').  
- Preserve existing **traditional login logic** (e.g., database check) and integrate **SSO user data** as needed.  
- Provide code snippets specific to $Any (e.g., **Express routes** for Node.js, **Razor Page handlers** for .NET, **Mux handlers** for Golang).  

### Step 3.3: Test the Modified Connection  
Outline testing steps:  
1. Run the app and navigate to the login page.  
2. Test **traditional login** to ensure it still works.  
3. Test **SSO flow**:  
   - Click **"Sign in with SSO"**.  
   - Verify UI toggle (password hides, button text changes).  
   - Enter an email, trigger **OIDC flow**, check redirect and logs after authentication.  

---

## Step 4: Additional Considerations  

List considerations tailored to $Any:  
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
- Link to relevant $Any-specific OIDC library docs (e.g., **Passport for Node.js**, **Goth for Golang**).  

---

## Customization Instructions  
- Replace '$Any' with the target language (e.g., **Node.js**, **ASP.NET Core**, **Golang**).  
- Replace '${FRAMEWORK_TOOLS}' with common tools (e.g., **Express** for Node.js, **Razor Pages** for .NET, **Gorilla Mux** for Golang).  
- Replace '$N/A' with a language-appropriate callback (e.g., '/auth/callback', '/signin-oidc').  
- Reference an **existing guide** (e.g., **"Node.js guide above"**) for structural consistency.  
