<div align="center">

<img src="public/readme/hero-banner.png" alt="CreatorSpace.ai — AI-powered content creation and social publishing" width="100%" />

**AI-Powered Content Creation and Social Publishing Platform**

<img src="https://img.shields.io/badge/Next.js-15-000000?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js" />
<img src="https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="React" />
<img src="https://img.shields.io/badge/Clerk-Auth-6C47FF?style=for-the-badge&logo=clerk&logoColor=white" alt="Clerk" />
<img src="https://img.shields.io/badge/Convex-Backend-EE342F?style=for-the-badge" alt="Convex" />
<img src="https://img.shields.io/badge/Tailwind_CSS-4-38BDF8?style=for-the-badge&logo=tailwindcss&logoColor=white" alt="Tailwind CSS" />
<img src="https://img.shields.io/badge/Google_Gemini-AI-8E75B2?style=for-the-badge&logo=googlegemini&logoColor=white" alt="Google Gemini" />
<img src="https://img.shields.io/badge/ImageKit-Media-0F62FE?style=for-the-badge" alt="ImageKit" />
<img src="https://img.shields.io/badge/PRs-welcome-brightgreen?style=for-the-badge" alt="PRs welcome" />

</div>

---

## Demo Video

<div align="center">

<a href="https://www.youtube.com/watch?v=otJTqngjOIE">
  <img src="https://img.youtube.com/vi/otJTqngjOIE/maxresdefault.jpg" alt="CreatorSpace.ai demo video" width="80%" />
</a>

</div>

---

## Overview

CreatorSpace.ai is an AI-powered content platform where creators write, enhance, and publish long-form posts, then grow an engaged audience. Authors compose in a rich text editor, generate or refine copy with AI, transform featured images, and share their work to a real-time feed and public profile.

It is built on Next.js and Convex with Clerk for authentication and ImageKit for media, delivering a fast, real-time experience from first draft to published post.

---

## Key Features

### Creator Dashboard

| Feature | Description |
| --- | --- |
| Rich Text Editor | Compose posts with headings, lists, links, code blocks, and inline formatting. |
| AI Content Generation | Generate a complete draft from a title, or refine existing content with enhance, expand, and simplify actions. |
| Featured Image Studio | Upload an image and apply AI background removal, drop shadow, and crop/resize presets. |
| Draft and Publish | Save work as a draft or publish instantly from the editor. |
| Analytics | Track total views, likes, comments, and followers for your content. |
| Profile Settings | Claim a unique username that powers your public profile. |

### Public and Social

| Feature | Description |
| --- | --- |
| Discovery Feed | Browse a "For You" feed of recent posts and a trending feed ranked by engagement. |
| Public Profiles | Share a personal page at `/[username]` listing a creator's published work and stats. |
| Post Pages | Read full posts with a featured image, author details, and a live view count. |
| Likes | Like or unlike posts, with counts updating in real time. |
| Comments | Join the discussion with comment posting and deletion. |
| Following | Follow and unfollow creators to personalize your feed. |

---

## How It Works

1. **Create** — Write in the rich editor, or generate a draft from a title with AI.
2. **Optimize** — Refine the copy with AI actions and transform the featured image.
3. **Share** — Publish to your public profile and the discovery feed.
4. **Grow** — Follow other creators and track engagement from your dashboard.

---

## Tech Stack

| Area | Technology |
| --- | --- |
| Framework | Next.js 15 (App Router, Turbopack), React 19 |
| Authentication | Clerk |
| Backend and database | Convex |
| AI | Google Gemini (`@google/generative-ai`) |
| Media | ImageKit |
| Styling and UI | Tailwind CSS v4, Radix UI, Lucide, Motion |
| Forms and validation | React Hook Form, Zod |
| Editor | React Quill (`react-quill-new`) |

---

## Getting Started

### Prerequisites

- Node.js 18.18 or later
- npm
- Accounts and API keys for Clerk, Convex, ImageKit, and Google Gemini

### Installation

```bash
git clone https://github.com/faizjamadar18/AI-content-creator-app.git
cd AI-content-creator-app
npm install
```

### Environment Variables

Create a `.env.local` file in the project root and provide the following values:

| Variable | Description |
| --- | --- |
| `NEXT_PUBLIC_CONVEX_URL` | Convex deployment URL |
| `CONVEX_DEPLOYMENT` | Convex deployment identifier (set by `npx convex dev`) |
| `CONVEX_DEPLOY_KEY` | Convex deploy key (for CI or production deploys) |
| `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY` | Clerk publishable key |
| `CLERK_SECRET_KEY` | Clerk secret key |
| `NEXT_PUBLIC_CLERK_SIGN_IN_URL` | Sign-in route, for example `/sign-in` |
| `NEXT_PUBLIC_CLERK_SIGN_UP_URL` | Sign-up route, for example `/sign-up` |
| `CLERK_JWT_ISSUER_DOMAIN` | Clerk JWT issuer domain, used by the Convex auth config |
| `NEXT_PUBLIC_IMAGEKIT_URL_ENDPOINT` | ImageKit URL endpoint |
| `NEXT_PUBLIC_IMAGEKIT_PUBLIC_KEY` | ImageKit public key |
| `IMAGEKIT_PRIVATE_KEY` | ImageKit private key |
| `GEMINI_API_KEY` | Google Gemini API key |

### Run Locally

Start the Convex development backend in one terminal:

```bash
npx convex dev
```

Start the Next.js development server in another:

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) to view the app.

---

## Project Structure

```
app/
  (auth)/            Clerk sign-in and sign-up routes
  (public)/          Public profile and post pages
  dashboard/         Creator dashboard, post editor, and settings
  feed/              For You and Trending feed
  actions/           Server actions for Gemini AI content
  api/imagekit/      ImageKit upload route handler
components/          Post editor, image modal, UI primitives, landing sections
convex/              Schema and backend functions (users, posts, feed, likes, comments, follows)
hooks/               Convex query and mutation hooks
lib/                 ImageKit helpers and shared utilities
middleware.js        Clerk route protection for dashboard and feed
```

---

## Available Scripts

| Command | Description |
| --- | --- |
| `npm run dev` | Start the development server with Turbopack |
| `npm run build` | Create a production build |
| `npm run start` | Serve the production build |
| `npm run lint` | Run ESLint |

---

## License

This project is provided for personal and educational use. Refer to the repository owner for licensing terms.
