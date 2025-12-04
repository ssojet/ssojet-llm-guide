# AI Prompt Template for SSOJet Express (Node.js) Integration Guide

## AI-Powered Integration Guide
Let our LLM AI prompts guide you in creating a secure and seamless SSO integration, tailored specifically to your application's needs.

---

You are an expert AI assistant tasked with creating a detailed, step-by-step guide for developers to integrate "Sign in with SSO" functionality into an existing login page in an Express (Node.js) application using SSOJet as an OIDC identity provider. The goal is to modify the existing login flow to add SSO support without disrupting the current traditional login functionality (e.g., email/password). Below is the step-by-step instruction set for you to follow. Use the provided details and examples to generate a Markdown-formatted guide similar to the structure of previous guides.

---

## Task Requirements  

**Objective**: Modify an existing Express login page to add a "Sign in with SSO" link. When clicked, the password field (if present) hides, only the email field shows, the login button changes to "Continue with SSO", and an OIDC request is triggered with the `login_hint` parameter set to the entered email. After successful authentication, handle the authorization code response and redirect to an existing post-login page (e.g., `/dashboard`).  

**Target Audience**: Developers familiar with Express (Node.js) and its common tools (e.g., Express.js, EJS/Pug/Handlebars, express-session, body-parser).  

**SSO Provider**: Use SSOJet, an OIDC-compliant identity provider.  

**Existing Setup**: Assume the application has a login page with a form (email and password fields) and a backend handler for traditional login. Modify this setup, not replace it.

---

## Step-by-Step Instructions for the AI  

### Step 1: Set the Context  
- Start by defining the title, description, and sidebar metadata in the Markdown header. Use placeholders for customization.  
- Provide an introductory paragraph explaining the guide's purpose, referencing the modification of an existing login page and the SSOJet OIDC integration.  

### Step 2: Define Prerequisites  
List prerequisites tailored to Express (Node.js), including:  
- An existing Express application with a login page.  
- Basic knowledge of Express (Node.js) and its common tools (Express.js, template engines, middleware).  
- An active SSOJet account.  
- A reference to the SSOJet connection setup guide:  
  - [SSO Connection Setup Guide](/how-to-guides/sso/integrations/)  
- Required libraries or packages specific to Express for OIDC (e.g., "passport", "passport-openidconnect", "openid-client", "express-openid-connect").

### Step 3: Step-by-Step Implementation  

#### Step 3.1: Create Application in SSOJet  
Replicate the SSOJet application setup section from previous guides, keeping it consistent:  
1. Log in to the SSOJet Dashboard.  
2. Navigate to **Applications**.  
3. Create a new application (e.g., "MyExpressApp", type **Regular Web App**).  
4. Configure the callback URI (e.g., 'http://localhost:3000/auth/callback' for Express).  
5. Retrieve **Client ID** and **Client Secret**.  
6. Copy the **Issuer URL** from the **Advanced > Endpoints** section.  
7. Include placeholder images (e.g., 'ssojet-applications-stepX.png') with captions matching previous guides.

#### Step 3.2: Modify the Existing Express Project  

##### Substep 3.2.1: Install Dependencies  
- Specify the OIDC library installation command for Express (e.g., 'npm install passport passport-openidconnect express-session' or 'npm install openid-client').  

##### Substep 3.2.2: Configure OIDC  
- Provide a code snippet to configure the OIDC provider with SSOJet credentials:
  - **Client ID**: ${CLIENT_ID}
  - **Client Secret**: ${CLIENT_SECRET}
  - **Issuer URL**: ${ISSUER_URL}
  - **Callback URL**: /auth/callback
  - **Scopes**: openid profile email
- Configure Passport.js strategy or OpenID Client for Express middleware.  

##### Substep 3.2.3: Update Login Page/UI  
Modify the existing login template (EJS/Pug/Handlebars) to:  
- Add the "Sign in with SSO" link/button to toggle between traditional and SSO modes.  
- When SSO mode is activated: hide password field, change button text to "Continue with SSO".  
- Update form submission logic: detect mode and call appropriate authentication handler.  
- For **SSO mode**, pass `login_hint` parameter with the email to the OIDC library's sign-in method.  
- Include basic CSS styling for form, buttons, and toggle element.

##### Substep 3.2.4: Handle OIDC Callback  
Explain callback handling for Express:  
- Create a dedicated callback route (e.g., `app.get('/auth/callback', ...)`).  
- Use Passport.js authenticate middleware or manual token exchange.  
- Ensure the callback URL matches the one configured in SSOJet dashboard.  
- Store user session using express-session.  
- Redirect authenticated users to the post-login page (e.g., `/dashboard`).

### Step 3.3: Test the Integration  
Outline testing steps:  
1. Run the app (`npm start` or `node app.js`) and navigate to the login page.  
2. Test **traditional login** to ensure it still works.  
3. Test **SSO flow**:  
   - Click **"Sign in with SSO"**.  
   - Verify UI toggle (password hides, button text changes).  
   - Enter an email, trigger **OIDC flow**, check redirect and logs after authentication.  

---

## Step 4: Additional Considerations  

List considerations tailored to Express (Node.js):  
- **Error Handling**: Suggest adding error middleware for OIDC failures.  
- **Styling**: Recommend CSS adjustments for UI consistency.  
- **Security**: Advise integrating SSO user data with existing session/auth systems, use helmet.js for security headers.  
- **Dynamic Redirect URI**: Note updating the callback URL for production environments.  
- **Session Management**: Configure express-session with secure settings (secure cookies, httpOnly, etc.).

---

## Step 5: Support Section  

Provide support resources:  
- **Contact SSOJet support**.  
- **Check application logs**.  
- Link to relevant OIDC library docs (e.g., **Passport.js**, **OpenID Client for Node.js**).

---

## Customization Instructions  
- Replace placeholders with actual values (e.g., CLIENT_ID, CLIENT_SECRET, ISSUER_URL).  
- Adjust template engine examples based on project (EJS, Pug, Handlebars, etc.).  
- Customize middleware configuration based on existing Express setup.  
- Reference **existing Node.js/Express guides** for structural consistency.

---

<p align="center">
  <strong>This prompt template is maintained by <a href="https://ssojet.com">SSOJet</a></strong><br>
  <a href="https://ssojet.com">Website</a> •
  <a href="https://docs.ssojet.com">Documentation</a> •
  <a href="https://portal.ssojet.com">Dashboard</a>
</p>
