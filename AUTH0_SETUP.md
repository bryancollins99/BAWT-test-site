# 🔐 Auth0 Setup Guide for Decap CMS

Since Netlify Identity is deprecated, we need to configure Auth0 for authentication with Decap CMS. Follow these steps carefully.

## Step 1: Create Auth0 Account

1. **Go to [Auth0.com](https://auth0.com)**
2. **Sign up** for a free account
3. **Create a new tenant** (choose a region close to your users)

## Step 2: Configure Auth0 Application

1. **In Auth0 Dashboard:**
   - Go to **Applications** → **Create Application**
   - Name: `BAWT Blog CMS`
   - Type: **Single Page Web Applications**
   - Click **Create**

2. **Configure Application Settings:**
   - **Allowed Callback URLs**: `https://your-site.netlify.app/admin/`
   - **Allowed Logout URLs**: `https://your-site.netlify.app/admin/`
   - **Allowed Web Origins**: `https://your-site.netlify.app`
   - **Allowed Origins (CORS)**: `https://your-site.netlify.app`

3. **Save Changes**

## Step 3: Get Auth0 Credentials

From your Auth0 application settings, copy:
- **Domain** (e.g., `your-tenant.us.auth0.com`)
- **Client ID** (e.g., `abc123def456ghi789`)

## Step 4: Configure Netlify Environment Variables

1. **In Netlify Dashboard:**
   - Go to **Site settings** → **Environment variables**
   - Add these variables:

```
AUTH0_DOMAIN=your-tenant.us.auth0.com
AUTH0_CLIENT_ID=your-client-id-from-auth0
```

## Step 5: Update CMS Configuration

The CMS configuration has been updated to use GitHub authentication with PKCE flow, which works with Auth0.

## Step 6: Set Up GitHub OAuth App (Alternative Method)

If you prefer direct GitHub authentication:

1. **Go to GitHub Settings:**
   - **Settings** → **Developer settings** → **OAuth Apps**
   - **New OAuth App**

2. **Configure OAuth App:**
   - **Application name**: `BAWT Blog CMS`
   - **Homepage URL**: `https://your-site.netlify.app`
   - **Authorization callback URL**: `https://api.netlify.com/auth/done`

3. **Get Credentials:**
   - Copy **Client ID** and **Client Secret**

4. **Add to Netlify:**
   - **Site settings** → **Access control** → **OAuth**
   - **Install provider** → **GitHub**
   - Enter your Client ID and Secret

## Step 7: Test Authentication

1. **Deploy your site** (it should auto-deploy from the GitHub push)
2. **Visit** `https://your-site.netlify.app/admin`
3. **Log in** using GitHub (or Auth0 if configured)
4. **Create a test blog post** to verify everything works

## Troubleshooting

### CMS Login Issues
- Verify callback URLs match exactly (including trailing slashes)
- Check environment variables are set correctly
- Ensure OAuth app is configured properly

### Build Issues
- Check Netlify build logs for errors
- Verify all dependencies are installed
- Ensure Node.js version is correct (20)

## Recommended Approach

For simplicity, I recommend using the **GitHub OAuth method** since:
- ✅ Easier to set up
- ✅ Direct integration with your repository
- ✅ No additional Auth0 configuration needed
- ✅ Works seamlessly with Decap CMS

The configuration has been updated to use `auth_type: pkce` which provides secure authentication without requiring a server.

## Next Steps

1. **Choose your authentication method** (GitHub OAuth recommended)
2. **Follow the setup steps** for your chosen method
3. **Test the admin interface** at `/admin`
4. **Start creating content** through the CMS

Need help? Check the [Auth0 documentation](https://auth0.com/docs) or [Decap CMS authentication docs](https://decapcms.org/docs/authentication-backends/). 