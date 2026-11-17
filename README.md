# CreatorSpace.ai

An AI-powered content creation and social publishing platform. CreatorSpace.ai lets users write and publish rich, long-form posts, enhance them with AI, transform featured images, and grow an audience through a real-time feed and social interactions.

- Live app: [faizbookx.vercel.app](https://faizbookx.vercel.app)
- Demo video: [Watch on YouTube](https://www.youtube.com/watch?v=otJTqngjOIE)

## Features

- **Authentication and profiles** — Secure sign-in with Clerk, unique usernames, and public creator profiles at `/[username]`.
- **Rich text editor** — Write posts with a React Quill editor supporting headings, lists, links, code blocks, and inline formatting. Posts can be saved as drafts or published.
- **AI content tools** — Generate a full post from a title, or improve existing content with enhance, expand, and simplify actions, powered by Google Gemini.
- **Image upload and transformation** — Upload featured images through ImageKit with AI background removal, drop shadow effects, and aspect-ratio crop and resize presets.
- **Feed** — Discover published posts with a "For You" feed and a trending feed ranked by recent engagement.
- **Social interactions** — Like posts, comment, and follow or unfollow creators.
- **Creator dashboard** — Track total views, likes, comments, and followers for your content.

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

## Available Scripts

| Command | Description |
| --- | --- |
| `npm run dev` | Start the development server with Turbopack |
| `npm run build` | Create a production build |
| `npm run start` | Serve the production build |
| `npm run lint` | Run ESLint |

## License

This project is provided for personal and educational use. Refer to the repository owner for licensing terms.
