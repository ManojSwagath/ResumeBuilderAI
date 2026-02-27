# Quick Start Guide

Follow these steps to get your AI Resume & Portfolio Builder up and running.

---

## 🚀 5-Minute Quick Start

### Step 1: Install Dependencies
```bash
npm install
# or
bun install
```

### Step 2: Set Up Supabase

1. Go to [supabase.com](https://supabase.com) and create a free account
2. Click "New Project"
3. Fill in:
   - **Name**: AIResumeBuilder
   - **Database Password**: Choose a strong password
   - **Region**: Select closest to you
4. Wait ~2 minutes for initialization

### Step 3: Configure Database

1. In your Supabase dashboard, click "SQL Editor"
2. Click "New Query"
3. Copy the entire content from your local file:  
   `supabase/migrations/20260215124234_b9637ad5-fd29-48bb-b5c1-4648e336b712.sql`
4. Paste into SQL Editor and click "Run"
5. You should see: "Success. No rows returned"

### Step 4: Get API Keys

1. In Supabase, click "Settings" (gear icon) → "API"
2. Copy these two values:
   - **Project URL** (looks like: `https://xxxxx.supabase.co`)
   - **anon/public key** (under "Project API keys")

### Step 5: Configure Environment

1. Copy the example file:
   ```bash
   cp .env.example .env
   ```

2. Edit `.env` and paste your values:
   ```env
   VITE_SUPABASE_URL=https://xxxxx.supabase.co
   VITE_SUPABASE_PUBLISHABLE_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
   ```

### Step 6: Run Development Server

```bash
npm run dev
# or
bun dev
```

Open [http://localhost:8080](http://localhost:8080) 🎉

---

## ✅ Verify Everything Works

### 1. Test Authentication
- Click "Get Started" or "Log in"
- Create a new account with your email
- Check your email for confirmation (if required)
- Log in successfully

### 2. Test Wizard Flow
- Click "Create New" from dashboard
- Fill in Step 1 (Personal Details)
- Click "Next" through all 8 steps
- Select "Resume" on final step
- Click "Save & Preview"

### 3. Test PDF Download
- On preview page, click "Download PDF"
- Verify PDF downloads with your information

### 4. Test Portfolio (Optional)
- Go back to Builder
- Create new document or edit existing
- Select "Portfolio" or "Both" on step 8
- Save & Preview
- Click "View Live Portfolio"
- Verify your portfolio is publicly accessible

---

## 🐛 Troubleshooting

### "Cannot connect to Supabase"
- Check `.env` file exists and has correct values
- Verify Supabase project is active (not paused)
- Check no extra spaces in environment variables

### "Build fails"
```bash
# Clear and reinstall
rm -rf node_modules
rm package-lock.json
npm install
```

### "Port 8080 already in use"
Edit `vite.config.ts`:
```typescript
server: {
  port: 3000, // Change to any available port
}
```

### "Blank page after signup"
- Check browser console for errors
- Verify RLS policies were created (check Supabase → Authentication → Policies)
- Try logging out and back in

---

## 📱 Next Steps

1. ✅ App running locally
2. 🎨 Customize branding/colors (edit `src/index.css`)
3. 📝 Add more templates (see `src/components/templates/`)
4. 🚀 Deploy (see [DEPLOYMENT.md](DEPLOYMENT.md))

---

## 🆘 Still Having Issues?

1. Check [PROJECT_STATUS.md](PROJECT_STATUS.md) for known issues
2. Review [README.md](README.md) for detailed documentation
3. Check browser console for error messages
4. Verify all dependencies installed: `npm list`

---

## 🎯 Quick Commands Reference

```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview

# Run tests
npm run test

# Lint code
npm run lint
```

---

**Ready!** Your AI Resume & Portfolio Builder should now be running at `http://localhost:8080` 🚀
