<div align="center">
  <!-- <img src="public/readme/hero-banner.png" alt="CreatorSpace.ai" width="100%"/> -->

  <h1 align="center">CreatorSpace.ai — AI-Powered Content Platform</h1>
  <p align="center"><strong></strong></p>
  <p align="center">Create, optimize, and publish long-form content with AI</p>

  <br/>

  <p align="center">
    <img src="https://img.shields.io/badge/Next.js-15-000000?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js"/>
    <img src="https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React"/>
    <img src="https://img.shields.io/badge/Clerk-Auth-6C47FF?style=flat-square&logo=clerk&logoColor=white" alt="Clerk"/>
    <img src="https://img.shields.io/badge/Convex-Backend-EE342F?style=flat-square" alt="Convex"/>
    <img src="https://img.shields.io/badge/Tailwind_CSS-4-38BDF8?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS"/>
    <img src="https://img.shields.io/badge/Google_Gemini-AI-8E75B2?style=flat-square&logo=googlegemini&logoColor=white" alt="Google Gemini"/>
    <img src="https://img.shields.io/badge/ImageKit-Media-0F62FE?style=flat-square" alt="ImageKit"/>
    <img src="https://img.shields.io/badge/license-personal%20use-999999?style=flat-square" alt="License"/>
  </p>
</div>

---

## 📺 Demo Video

<div align="center">

[![Watch the CreatorSpace.ai Demo](https://img.youtube.com/vi/otJTqngjOIE/maxresdefault.jpg)](https://www.youtube.com/watch?v=otJTqngjOIE)

</div>

---

## Overview

**CreatorSpace.ai** is a modern, AI-powered content platform where creators write, enhance, and publish long-form posts — then grow an engaged audience. Authors compose in a rich text editor, generate or refine copy with AI, and transform featured images, all before sharing their work to a real-time discovery feed and public profile.

Built on Next.js and Convex with Clerk for authentication and ImageKit for media, CreatorSpace.ai delivers a fast, real-time experience from first draft to published post.

---

## Key Features

### ✍️ Creator Studio

| Feature | Description |
|---------|-------------|
| **Rich Text Editor** | Compose posts with headings, lists, links, code blocks, and inline formatting |
| **AI Content Generation** | Generate a complete draft from a title, or refine existing content with enhance, expand, and simplify actions |
| **Featured Image Studio** | Upload an image and apply AI background removal, drop shadow, and crop/resize presets |
| **Draft & Publish** | Save work as a draft or publish instantly from the editor |
| **Analytics** | Track total views, likes, comments, and followers for your content |
| **Profile Settings** | Claim a unique username that powers your public profile |

### 🌐 Social & Discovery

| Feature | Description |
|---------|-------------|
| **Discovery Feed** | Browse a "For You" feed of recent posts and a trending feed ranked by engagement |
| **Public Profiles** | Share a personal page at `/[username]` listing a creator's published work and stats |
| **Post Pages** | Read full posts with a featured image, author details, and a live view count |
| **Likes** | Like or unlike posts, with counts updating in real time |
| **Comments** | Join the discussion with comment posting and deletion |
| **Following** | Follow and unfollow creators to personalize your feed |

---

## How It Works

### Content Creation Pipeline
```
Title Input → Gemini Generation → Rich Text Editor → Autosave Draft → Publish
```
- **Generation**: Google Gemini produces structured HTML content from the post title
- **Refinement**: Enhance, expand, and simplify actions rewrite existing content on demand
- **Storage**: Drafts and published posts are persisted in Convex with automatic timestamps

### Image Transformation Pipeline
```
Upload → ImageKit → Background Removal → Drop Shadow → Crop / Resize → CDN URL
```
- **Upload**: Authenticated server route streams the file to ImageKit
- **Transforms**: AI background removal, drop shadow, and aspect-ratio presets chain into a single delivery URL
- **Delivery**: Optimized images served from the ImageKit CDN

### Feed & Engagement Pipeline
```
Published Post → For You / Trending Feed → Likes · Comments · Follows → Dashboard Analytics
```
- **Ranking**: Trending score weights views and likes over a rolling 7-day window
- **Engagement**: Likes, comments, and follows update in real time through Convex subscriptions
- **Insights**: Views, likes, comments, and follower totals surface on the creator dashboard

---

## Tech Stack

<p align="center">
  <img src="https://skillicons.dev/icons?i=nextjs,react,tailwindcss,javascript" />
</p>

| Layer | Technology |
|-------|-----------|
| **Framework** | [Next.js 15](https://nextjs.org) (App Router, Turbopack) + [React 19](https://react.dev) |
| **Authentication** | [Clerk](https://clerk.com) |
| **Backend & Database** | [Convex](https://convex.dev) |
| **AI** | [Google Gemini](https://ai.google.dev) (`@google/generative-ai`) |
| **Media** | [ImageKit](https://imagekit.io) |
| **Styling & UI** | Tailwind CSS v4, Radix UI, Lucide, Motion |
| **Forms & Validation** | React Hook Form + Zod |
| **Editor** | React Quill (`react-quill-new`) |
| **Deployment** | Vercel |

---

## Project Structure

```
creatr/
├── app/
│   ├── (auth)/                  # Clerk sign-in and sign-up routes
│   ├── (public)/
│   │   └── [username]/          # Public profile and post pages
│   ├── actions/
│   │   └── gemini.js            # Server actions for AI content generation
│   ├── api/
│   │   └── imagekit/upload/     # ImageKit upload route handler
│   ├── dashboard/               # Creator dashboard, editor, and settings
│   ├── feed/                    # For You and Trending feed
│   └── layout.js                # Root layout and providers
├── components/
│   ├── sections/                # Landing page sections
│   ├── ui/                      # Reusable UI primitives
│   ├── post-editor.jsx          # Rich text post editor
│   └── image-upload-modal.jsx   # Upload and transform dialog
├── convex/
│   ├── schema.js                # Database schema and indexes
│   ├── users.js                 # User sync and profiles
│   ├── posts.js                 # Post CRUD
│   ├── feed.js                  # Feed and trending queries
│   ├── likes.js                 # Like system
│   ├── comments.js              # Comment system
│   ├── follows.js               # Follow system
│   └── dashboard.js             # Analytics aggregation
├── hooks/                       # Convex query and mutation hooks
├── lib/                         # ImageKit helpers and utilities
├── middleware.js                # Clerk route protection
└── package.json
```

---

## Quick Start

### Prerequisites
- Node.js 18.18+
- npm
- Accounts and API keys for [Convex](https://convex.dev), [Clerk](https://clerk.com), [ImageKit](https://imagekit.io), and [Google Gemini](https://ai.google.dev)

### Setup

```bash
# Clone the repo
git clone https://github.com/faizjamadar18/AI-content-creator-app.git
cd AI-content-creator-app

# Install dependencies
npm install

# Configure environment variables
# Create a .env.local file with the values listed below

# Start the Convex development backend
npx convex dev

# In a second terminal, run the app
npm run dev
```

### Environment Variables

Create a `.env.local` file in the project root:

| Variable | Description |
|----------|-------------|
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

---

## Data Model

| Table | Purpose | Key Fields |
|-------|---------|------------|
| `users` | Creator accounts synced from Clerk | `tokenIdentifier`, `name`, `email`, `username`, `imageUrl` |
| `posts` | Long-form content | `title`, `content`, `status` (draft/published), `authorId` (FK), `featuredImage`, `viewCount`, `likeCount` |
| `comments` | Discussion on posts | `postId` (FK), `authorId` (FK), `content` |
| `likes` | Post likes | `postId` (FK), `userId` (FK) |
| `follows` | Follower relationships | `followerId` (FK), `followingId` (FK) |
| `dailyStats` | Per-day view analytics | `postId` (FK), `date`, `views` |

---

## Deployment

CreatorSpace.ai deploys on **Vercel** with a **Convex** production deployment:

1. Push the repository to GitHub
2. Deploy the Convex backend with `npx convex deploy` and note the production URL
3. Import the repository into [Vercel](https://vercel.com)
4. Add all environment variables in the Vercel dashboard
5. Deploy — then point your Clerk and ImageKit domains at the production URL

---

## Roadmap

- [ ] Real-time notifications for likes, comments, and new followers
- [ ] Saved posts and bookmarking
- [ ] Search across creators, titles, and content
- [ ] Multi-image galleries per post
- [ ] Scheduled publishing
- [ ] Content moderation tools

---

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

<div align="center">
  <sub>Built with ❤️ for creators</sub>
  <br/>
  <sub>© 2026 CreatorSpace.ai — <a href="https://faizbookx.vercel.app">faizbookx.vercel.app</a></sub>
</div>
