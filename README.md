# Become a Writer Today Blog

A comprehensive writing blog built with AstroPaper theme and Decap CMS, featuring writing advice, tips, tools, and inspiration for aspiring writers.

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ 
- Git

### Local Development
```bash
npm install
npm run dev
```

Visit `http://localhost:4321` to see your site.

## 📝 Content Management

This site uses Decap CMS for easy content management:

- **Admin Interface**: Visit `/admin` after deployment
- **Blog Posts**: Located in `src/data/blog/`
- **Git-based**: All content is stored in markdown files

## 🌐 Deployment

### Deploy to Netlify

1. **Create GitHub Repository**:
   ```bash
   # Create a new repository on GitHub, then:
   git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git
   git push -u origin main
   ```

2. **Connect to Netlify**:
   - Go to [Netlify](https://netlify.com)
   - Click "New site from Git"
   - Connect your GitHub repository
   - Build settings are automatically configured via `netlify.toml`

3. **Enable CMS Authentication**:
   - In Netlify dashboard: Site settings → Identity → Enable Identity
   - Settings → Identity → Git Gateway → Enable Git Gateway
   - Invite yourself as a user

## 🛠️ Features

- ✅ **AstroPaper Theme**: Minimal, responsive, SEO-friendly
- ✅ **Decap CMS**: Easy content management
- ✅ **TypeScript**: Type-safe development
- ✅ **Tailwind CSS**: Utility-first styling
- ✅ **Dark/Light Mode**: Built-in theme switching
- ✅ **Search**: Fuzzy search functionality
- ✅ **RSS Feed**: Automatic feed generation
- ✅ **Sitemap**: SEO optimization
- ✅ **Performance**: Optimized for speed

## 📁 Project Structure

```
/
├── public/
│   ├── admin/          # Decap CMS admin interface
│   └── assets/         # Static assets
├── src/
│   ├── data/blog/      # Blog posts (markdown)
│   ├── components/     # Astro components
│   ├── layouts/        # Page layouts
│   └── pages/          # Site pages
├── netlify.toml        # Netlify configuration
└── package.json
```

## 🎨 Customization

### Site Configuration
Edit `src/config.ts` to customize:
- Site title and description
- Author information
- Social links
- Post pagination

### CMS Configuration
Edit `public/admin/config.yml` to modify:
- Content fields
- Collection settings
- Media management

## 📚 Writing Content

### Using the CMS
1. Visit `yoursite.netlify.app/admin`
2. Log in with your Netlify Identity account
3. Create and edit posts through the web interface

### Manual Creation
Create new posts in `src/data/blog/` with this frontmatter:

```yaml
---
title: "Your Post Title"
description: "Brief description"
author: "Your Name"
pubDatetime: 2024-01-20T10:00:00Z
featured: false
draft: false
tags: ["writing", "tips"]
---

Your content here...
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📄 License

MIT License - feel free to use this setup for your own writing blog!

---

Built with ❤️ for writers by writers.
