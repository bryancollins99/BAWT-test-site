# 🚀 Deployment Guide: GitHub + Netlify + Decap CMS

Follow these steps to deploy your writing blog to Netlify with full CMS functionality.

## Step 1: Create GitHub Repository

1. **Go to GitHub.com** and create a new repository:
   - Repository name: `become-a-writer-today` (or your preferred name)
   - Make it **Public** (required for free Netlify)
   - Don't initialize with README (we already have one)

2. **Push your code to GitHub**:
   ```bash
   # Replace YOUR_USERNAME and REPO_NAME with your actual details
   git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git
   git push -u origin main
   ```

## Step 2: Deploy to Netlify

1. **Go to [Netlify.com](https://netlify.com)** and sign up/login
2. **Click "New site from Git"**
3. **Choose GitHub** and authorize Netlify to access your repositories
4. **Select your repository** (`become-a-writer-today`)
5. **Configure build settings** (auto-filled from `netlify.toml`):
   - Build command: `npm run build`
   - Publish directory: `dist`
   - Click **"Deploy site"**

## Step 3: Configure Decap CMS Authentication

1. **In your Netlify dashboard**, go to:
   - **Site settings** → **Identity** → **Enable Identity**

2. **Configure Git Gateway**:
   - **Identity** → **Services** → **Git Gateway** → **Enable Git Gateway**

3. **Set registration preferences**:
   - **Identity** → **Settings** → **Registration** → **Invite only** (recommended)

4. **Invite yourself as a user**:
   - **Identity** → **Invite users** → Enter your email → **Send**
   - Check your email and accept the invitation
   - Set your password

## Step 4: Test Your CMS

1. **Visit your site**: `https://your-site-name.netlify.app`
2. **Access the admin**: `https://your-site-name.netlify.app/admin`
3. **Log in** with your Netlify Identity credentials
4. **Create a test blog post** to verify everything works

## Step 5: Customize Your Domain (Optional)

1. **In Netlify dashboard**: **Domain settings** → **Add custom domain**
2. **Update DNS** with your domain provider
3. **Enable HTTPS** (automatic with Netlify)

## 🎉 You're Live!

Your writing blog is now deployed with:
- ✅ Automatic builds from GitHub pushes
- ✅ Content management via Decap CMS
- ✅ SSL certificate and CDN
- ✅ Admin interface at `/admin`

## Troubleshooting

### CMS Login Issues
- Ensure Git Gateway is enabled in Netlify
- Check that you've been invited as a user
- Clear browser cache and try again

### Build Errors
- Check the build logs in Netlify dashboard
- Ensure all dependencies are in `package.json`
- Verify Node.js version (18+)

### Content Not Showing
- Check that markdown files have correct frontmatter
- Ensure files are in `src/data/blog/` directory
- Verify date format in `pubDatetime` field

## Next Steps

1. **Customize the site** by editing `src/config.ts`
2. **Add your own content** via the CMS or by editing markdown files
3. **Customize the theme** by modifying components and styles
4. **Set up analytics** (Google Analytics, Plausible, etc.)
5. **Configure SEO** settings and social media links

Happy writing! 🎯 