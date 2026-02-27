# Deployment Guide - AI Resume & Portfolio Builder

This guide covers **FREE** deployment options for your AI Resume & Portfolio Builder app.

---

## 🚀 Recommended Free Deployment Platforms

### Option 1: Vercel (Recommended ⭐)

**Best for**: React/Vite apps with serverless functions
**Free tier**: 100 GB bandwidth/month, unlimited projects

#### Steps:

1. **Push code to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin <your-github-repo-url>
   git push -u origin main
   ```

2. **Deploy to Vercel**
   - Go to [vercel.com](https://vercel.com)
   - Click "New Project"
   - Import your GitHub repository
   - Configure build settings (auto-detected for Vite):
     - **Framework Preset**: Vite
     - **Build Command**: `npm run build` or `bun run build`
     - **Output Directory**: `dist`
   - Add Environment Variables:
     - `VITE_SUPABASE_URL`: Your Supabase URL
     - `VITE_SUPABASE_PUBLISHABLE_KEY`: Your Supabase anon key
   - Click "Deploy"

3. **Your app will be live at**: `https://your-app-name.vercel.app`

#### Vercel CLI (Alternative):
```bash
npm i -g vercel
vercel login
vercel --prod
```

---

### Option 2: Netlify

**Best for**: Static sites with great CDN
**Free tier**: 100 GB bandwidth/month

#### Steps:

1. **Push code to GitHub** (same as Vercel)

2. **Deploy to Netlify**
   - Go to [netlify.com](https://netlify.com)
   - Click "Add new site" → "Import an existing project"
   - Connect GitHub and select your repository
   - Build settings:
     - **Build command**: `npm run build`
     - **Publish directory**: `dist`
   - Add Environment Variables (same as Vercel)
   - Click "Deploy site"

3. **Your app will be live at**: `https://your-app-name.netlify.app`

#### Netlify CLI (Alternative):
```bash
npm install -g netlify-cli
netlify login
netlify init
netlify deploy --prod
```

---

### Option 3: GitHub Pages (Static Only)

**Best for**: Simple static sites (no serverless functions)
**Free tier**: Unlimited for public repos

#### Steps:

1. **Install gh-pages package**
   ```bash
   npm install --save-dev gh-pages
   ```

2. **Update `package.json`**
   Add these scripts:
   ```json
   {
     "scripts": {
       "predeploy": "npm run build",
       "deploy": "gh-pages -d dist"
     },
     "homepage": "https://<your-username>.github.io/<repo-name>"
   }
   ```

3. **Update `vite.config.ts`**
   Add base path:
   ```typescript
   export default defineConfig({
     base: '/<repo-name>/',
     // ... rest of config
   })
   ```

4. **Deploy**
   ```bash
   npm run deploy
   ```

5. **Enable GitHub Pages**
   - Go to repo Settings → Pages
   - Source: Deploy from branch
   - Branch: `gh-pages` / `root`

---

### Option 4: Render

**Best for**: Full-stack apps with databases
**Free tier**: 400 build hours/month

#### Steps:

1. **Push code to GitHub**

2. **Deploy to Render**
   - Go to [render.com](https://render.com)
   - Click "New" → "Static Site"
   - Connect your GitHub repository
   - Build settings:
     - **Build Command**: `npm run build`
     - **Publish Directory**: `dist`
   - Add Environment Variables
   - Click "Create Static Site"

3. **Your app will be live at**: `https://your-app-name.onrender.com`

---

### Option 5: Cloudflare Pages

**Best for**: Fast global CDN, great performance
**Free tier**: Unlimited bandwidth, unlimited requests

#### Steps:

1. **Push code to GitHub**

2. **Deploy to Cloudflare**
   - Go to [pages.cloudflare.com](https://pages.cloudflare.com)
   - Click "Create a project"
   - Connect GitHub repository
   - Build settings:
     - **Framework preset**: Vite
     - **Build command**: `npm run build`
     - **Build output directory**: `dist`
   - Add Environment Variables
   - Click "Save and Deploy"

---

## 📝 Environment Variables Setup

For ALL platforms, you need to set these environment variables:

```env
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_PUBLISHABLE_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

**Where to find these**:
1. Go to your Supabase project dashboard
2. Click "Settings" → "API"
3. Copy:
   - Project URL → `VITE_SUPABASE_URL`
   - Project API keys → anon/public → `VITE_SUPABASE_PUBLISHABLE_KEY`

---

## 🗄️ Supabase Setup

1. **Create Supabase Project** (Free)
   - Go to [supabase.com](https://supabase.com)
   - Click "New Project"
   - Fill in project details
   - Wait for project to initialize (~2 minutes)

2. **Run Database Migration**
   - Go to SQL Editor in Supabase dashboard
   - Copy content from `supabase/migrations/20260215124234_*.sql`
   - Paste and click "Run"

3. **Enable Email Authentication** (Optional)
   - Go to Authentication → Providers
   - Enable Email provider
   - Configure email templates if needed

---

## 🎯 Quick Comparison

| Platform | Best For | Bandwidth | Build Time | Custom Domain |
|----------|----------|-----------|------------|---------------|
| **Vercel** | React/Vite apps | 100 GB/mo | Fast | Free |
| **Netlify** | Static sites | 100 GB/mo | Fast | Free |
| **GitHub Pages** | Simple static | Unlimited | Medium | Free |
| **Render** | Full-stack | Slow after idle | Slow | Paid |
| **Cloudflare** | Performance | Unlimited | Fast | Free |

---

## ✅ Post-Deployment Checklist

- [ ] Test signup/login functionality
- [ ] Create a test resume and portfolio
- [ ] Verify PDF download works
- [ ] Check public portfolio URLs are accessible
- [ ] Test on mobile devices
- [ ] Set up custom domain (optional)
- [ ] Configure analytics (optional)

---

## 🔧 Troubleshooting

### Build fails with "Cannot find module"
- Clear node_modules and reinstall: `rm -rf node_modules && npm install`

### Supabase connection error
- Check environment variables are correctly set
- Verify Supabase project is active
- Check RLS policies are properly configured

### Blank page after deployment
- Check browser console for errors
- Verify `base` path in vite.config.ts
- Check routing configuration (spa fallback)

### PDF download not working
- html2canvas might need CORS configuration
- Check browser console for errors

---

## 📊 Recommended Setup for This Project

**Best Free Deployment Combination**:
1. **Frontend**: Vercel or Netlify
2. **Backend/Database**: Supabase (free tier)
3. **Domain**: Use provided subdomain or connect your own

**Total Cost**: $0/month ✅

---

## 🚀 Quick Deploy Commands

### Vercel
```bash
npm i -g vercel
vercel --prod
```

### Netlify
```bash
npm i -g netlify-cli
netlify deploy --prod
```

### GitHub Pages
```bash
npm run deploy
```

---

## 📞 Need Help?

- Check the [main README](README.md) for setup instructions
- Review [Vercel docs](https://vercel.com/docs)
- Review [Netlify docs](https://docs.netlify.com)
- Review [Supabase docs](https://supabase.com/docs)

---

**Ready to deploy?** Choose your platform and follow the steps above! 🎉
