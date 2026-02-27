# AI Resume & Portfolio Builder 🚀

A colorful, friendly, step-by-step wizard app where students/professionals in the AI/ML field can create polished resumes and portfolio pages. Users create accounts to save and revisit their data. Resumes download as PDF, and portfolios get a shareable live URL.

![Built with](https://img.shields.io/badge/Built%20with-React%20%7C%20TypeScript%20%7C%20Tailwind-blue)
![Database](https://img.shields.io/badge/Database-Supabase-green)

## ✨ Features

- 🎨 **AI-Domain Focused**: Built specifically for AI/ML professionals with tailored roles, skills, and templates
- 📝 **Step-by-Step Wizard**: 8-step guided form with progress tracking
- 📄 **ATS-Ready Resume Templates**: Download professional PDF resumes
- 🌐 **Live Portfolio Pages**: Get shareable public URLs for your portfolio
- 🔐 **User Authentication**: Secure signup/login with Supabase Auth
- 💾 **Auto-Save**: Automatically saves progress as you build
- 📱 **Responsive Design**: Works seamlessly on mobile and desktop

## 🏗️ Tech Stack

- **Frontend**: React 18, TypeScript, Vite
- **UI Framework**: Tailwind CSS, shadcn/ui components
- **Animation**: Framer Motion
- **Backend**: Supabase (PostgreSQL database + Auth)
- **PDF Generation**: html2canvas + jsPDF
- **State Management**: React Query (TanStack Query)
- **Routing**: React Router v6
- **Form Handling**: React Hook Form + Zod validation

## 📁 Project Structure

```
AIResumeAndPortfolioMaker/
├── .Plan/                      # Project planning documents
│   └── plan.md                 # Complete project plan
├── public/                     # Static assets
│   └── robots.txt
├── src/
│   ├── components/
│   │   ├── templates/          # Resume & Portfolio templates
│   │   │   └── ResumeClassicATS.tsx
│   │   ├── ui/                 # shadcn/ui components
│   │   │   ├── button.tsx
│   │   │   ├── card.tsx
│   │   │   ├── input.tsx
│   │   │   └── ... (50+ components)
│   │   └── wizard/             # 8 wizard step components
│   │       ├── StepPersonal.tsx
│   │       ├── StepEducation.tsx
│   │       ├── StepRole.tsx
│   │       ├── StepSkills.tsx
│   │       ├── StepProjects.tsx
│   │       ├── StepExperience.tsx
│   │       ├── StepCertifications.tsx
│   │       └── StepOutput.tsx
│   ├── hooks/                  # Custom React hooks
│   │   ├── use-mobile.tsx
│   │   └── use-toast.ts
│   ├── integrations/
│   │   └── supabase/           # Supabase client & types
│   │       ├── client.ts
│   │       └── types.ts
│   ├── lib/                    # Utilities & type definitions
│   │   ├── auth.tsx            # Auth context & protected routes
│   │   ├── utils.ts            # Helper functions
│   │   └── wizard-types.ts     # TypeScript types for wizard data
│   ├── pages/                  # Main application pages
│   │   ├── Index.tsx           # Landing page
│   │   ├── Auth.tsx            # Login/Signup page
│   │   ├── Dashboard.tsx       # User dashboard
│   │   ├── Builder.tsx         # Wizard builder
│   │   ├── Preview.tsx         # Preview & download
│   │   ├── PublicPortfolio.tsx # Public portfolio view
│   │   └── NotFound.tsx        # 404 page
│   ├── test/                   # Test configuration
│   ├── App.tsx                 # Main app component
│   ├── main.tsx                # Entry point
│   └── index.css               # Global styles
├── supabase/
│   ├── config.toml             # Supabase config
│   └── migrations/             # Database migrations
│       └── 20260215124234_*.sql
├── .env                        # Environment variables (not in git)
├── .env.example                # Example environment variables
├── .gitignore
├── package.json
├── vite.config.ts              # Vite configuration
├── tailwind.config.ts          # Tailwind configuration
└── README.md

```

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ or Bun
- Supabase account (free tier available)

### Installation

1. **Clone the repository**
```bash
git clone <your-repo-url>
cd AIResumeAndPortfolioMaker
```

2. **Install dependencies**
```bash
npm install
# or
bun install
```

3. **Set up Supabase**
   - Create a new project at [supabase.com](https://supabase.com)
   - Copy your project URL and anon key
   - Run the migration from `supabase/migrations/` in your Supabase SQL editor

4. **Configure environment variables**
```bash
cp .env.example .env
```
Edit `.env` and add your Supabase credentials:
```env
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_PUBLISHABLE_KEY=your-anon-key
```

5. **Run the development server**
```bash
npm run dev
# or
bun dev
```

The app will be available at `http://localhost:8080`

## 📊 Database Schema

The app uses 3 main tables:

- **profiles**: User profile information (auto-created on signup)
- **resumes**: Saved resume data with template choice
- **portfolios**: Portfolio data with public URL slug

All tables have Row Level Security (RLS) enabled for data protection.

## 🎯 Usage Flow

1. **Landing Page** → Sign up or log in
2. **Dashboard** → View saved documents or create new
3. **Builder Wizard** → Complete 8 steps:
   - Personal Details
   - Education
   - Target Role (AI-specific roles)
   - Skills (Languages, ML skills, tools, frameworks)
   - Projects (AI/ML projects)
   - Experience (optional)
   - Certifications
   - Choose Output (Resume/Portfolio/Both + templates)
4. **Preview** → Review and download PDF or get live portfolio URL
5. **Share** → Send portfolio URL to employers/recruiters

## 📦 Build for Production

```bash
npm run build
# or
bun run build
```

This creates an optimized build in the `dist/` folder.

## 🧪 Running Tests

```bash
npm run test
# or
bun test
```

## 📝 License

This project is open source and available under the MIT License.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📞 Support

For issues and questions, please open an issue on GitHub.

---

Built with ❤️ for the AI/ML community
