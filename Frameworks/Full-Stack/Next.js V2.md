# ▲ THE ULTIMATE NEXT.JS ROADMAP
### From Zero to Production-Grade Full-Stack Next.js Mastery

> **Structure:** Phase → Modules → Sections
> **Estimated Duration:** ~6-9 Months (Dedicated Study)
> **Prerequisites:** HTML, CSS, JavaScript (ES6+), basic React knowledge helpful but not required
> *Next.js is not just a React framework. It's a full-stack platform that blurred the line between frontend and backend forever.*

---

## ⚡ PHASE 0 — PREREQUISITES & NEXT.JS ORIENTATION
> *"Next.js sits on top of React. You must understand the foundation before you build the skyscraper."*

---

### 📦 Module 0.1: Understanding Next.js

#### § 0.1.1 — What is Next.js & Why It Dominates
  - Created by Vercel (formerly ZEIT), first released in 2016
  - A React framework for building full-stack web applications
  - What Next.js adds on top of React: routing, server-side rendering, API routes, data fetching, optimization, middleware, deployment
  - "The SDK for the Web" — Vercel's vision
  - Who uses Next.js: Vercel, Netflix, TikTok, Twitch, Hulu, Nike, Target, Washington Post, Notion

#### § 0.1.2 — The Problems Next.js Solves
  - **React alone**: client-side only, no routing, no SSR, no file-based routing, no built-in optimization
  - **SEO**: server-side rendering for search engine crawling
  - **Performance**: automatic code splitting, image optimization, font optimization
  - **Routing**: file-system based routing (no React Router needed)
  - **Full-stack**: API routes, Server Components, Server Actions — no separate backend needed
  - **Developer Experience**: fast refresh, TypeScript support, built-in CSS/Sass, ESLint
  - **Deployment**: optimized for Vercel, but runs anywhere (Node.js, Docker, static export)

#### § 0.1.3 — Rendering Paradigms (The Core Concept)
  - **CSR (Client-Side Rendering)** — React default: blank HTML → JavaScript renders everything
  - **SSR (Server-Side Rendering)** — HTML generated on server per request
  - **SSG (Static Site Generation)** — HTML generated at build time
  - **ISR (Incremental Static Regeneration)** — static pages that revalidate periodically
  - **RSC (React Server Components)** — components that run ONLY on the server (Next.js 13+ default)
  - **Streaming** — progressive rendering with Suspense
  - Next.js lets you choose per-page, per-component — the ultimate flexibility

#### § 0.1.4 — Next.js Version History & Architecture Shift
  - **Next.js 1–12** — Pages Router era (`pages/` directory)
  - **Next.js 13** (2022) — App Router introduced (`app/` directory), React Server Components
  - **Next.js 14** (2023) — Server Actions stable, Turbopack improvements, Partial Prerendering preview
  - **Next.js 15** (2024) — Async request APIs, enhanced caching, Turbopack stable for dev
  - This roadmap focuses on **App Router** (the future) with Pages Router awareness for legacy

#### § 0.1.5 — Next.js vs Alternatives
  - Next.js vs Create React App: Next.js has SSR, routing, optimization — CRA is bare React
  - Next.js vs Remix: different data loading philosophy, Remix is more web-standards-focused
  - Next.js vs Nuxt: Next.js is React-based, Nuxt is Vue-based (similar concepts)
  - Next.js vs Astro: Astro is content-focused (islands), Next.js is app-focused
  - Next.js vs SvelteKit: SvelteKit uses Svelte (compiler-based), similar full-stack model

---

### 📦 Module 0.2: JavaScript & TypeScript Prerequisites

#### § 0.2.1 — Essential JavaScript (ES6+)
  - `let`, `const` (never `var`)
  - Arrow functions, template literals, destructuring, spread/rest operators
  - `Array` methods: `map`, `filter`, `reduce`, `find`, `some`, `every`, `flatMap`
  - Promises, `async/await`, `try/catch`
  - Modules: `import`/`export`, named vs default exports
  - Optional chaining `?.`, nullish coalescing `??`
  - `fetch` API for HTTP requests

#### § 0.2.2 — TypeScript Essentials (Non-Negotiable for Modern Next.js)
  - Basic types: `string`, `number`, `boolean`, `null`, `undefined`
  - Arrays and objects: `string[]`, `{ name: string; age: number }`
  - Interfaces vs types: `interface User {}` vs `type User = {}`
  - Union types: `string | number`, discriminated unions
  - Generics: `Array<T>`, `Promise<T>`, custom generics
  - Utility types: `Partial<T>`, `Required<T>`, `Pick<T, K>`, `Omit<T, K>`, `Record<K, V>`
  - Type narrowing, type guards, `as const`
  - Function types: `(param: Type) => ReturnType`
  - `unknown` vs `any` — prefer `unknown`
  - Next.js is TypeScript-first — all examples and docs use TypeScript

---

### 📦 Module 0.3: React Fundamentals (Required Foundation)

#### § 0.3.1 — Core React Concepts
  - Components: function components (class components are legacy)
  - JSX: HTML-like syntax in JavaScript
  - Props: passing data to components, typing props with TypeScript
  - Children prop: `children: React.ReactNode`
  - Conditional rendering: ternary, `&&`, early return
  - List rendering: `map()` with `key` prop
  - Event handling: `onClick`, `onChange`, `onSubmit`
  - Forms: controlled components, form submission

#### § 0.3.2 — React Hooks
  - `useState` — state management
  - `useEffect` — side effects (data fetching, subscriptions, DOM manipulation)
  - `useRef` — mutable references, DOM access
  - `useContext` — consuming context (global state without props drilling)
  - `useMemo` — memoize expensive computations
  - `useCallback` — memoize functions
  - `useReducer` — complex state logic
  - Custom hooks: extract reusable logic

#### § 0.3.3 — React Patterns for Next.js
  - Component composition over prop drilling
  - Container vs presentational components
  - Render props and higher-order components (awareness)
  - Error boundaries: `ErrorBoundary` component
  - `React.Suspense` — loading states for lazy components
  - `React.lazy` — code splitting (less relevant in Next.js, it auto-splits)
  - Context API: creating and consuming context for global state

---

### 📦 Module 0.4: Setting Up the Development Environment

#### § 0.4.1 — Installing Prerequisites
  - Node.js 18+ (LTS recommended): `node --version`
  - npm / pnpm / yarn — package managers (`pnpm` recommended for speed)
  - Git for version control
  - VS Code with extensions: ESLint, Prettier, Tailwind CSS IntelliSense, Pretty TypeScript Errors

#### § 0.4.2 — Creating a Next.js Project
  - `npx create-next-app@latest` — the official scaffolding tool
  - Prompts: TypeScript (yes), ESLint (yes), Tailwind CSS (yes), `src/` directory (preference), App Router (yes), import alias (yes)
  - Project structure walkthrough: `app/`, `public/`, `next.config.js`, `tsconfig.json`, `tailwind.config.ts`
  - `npm run dev` — start development server (Fast Refresh enabled)
  - Turbopack: `next dev --turbo` — faster development builds

#### § 0.4.3 — Essential Configuration Files
  - `next.config.ts` — Next.js configuration (images, redirects, headers, env)
  - `tsconfig.json` — TypeScript configuration (path aliases: `@/`)
  - `tailwind.config.ts` — Tailwind CSS configuration
  - `.env.local` — environment variables (local development)
  - `.eslintrc.json` — ESLint configuration (extends `next/core-web-vitals`)

> ### 🛠️ Phase 0 Project: **"React Foundations Playground"**
> Build a React application (using `create-next-app` as the scaffold) that demonstrates:
> - Component hierarchy: `App` → `Header` → `Navigation`, `Main` → `CardList` → `Card`
> - Props with TypeScript interfaces for every component
> - `useState` for filtering/sorting a list of items
> - `useEffect` for fetching data from a public API on mount
> - `useContext` for a theme toggle (light/dark mode)
> - `useReducer` for a shopping cart state
> - Custom hook: `useFetch(url)` that handles loading, error, and data states
> - Responsive layout with Tailwind CSS
> - This is pure React within Next.js — no Next.js-specific features yet

---

## ⚡ PHASE 1 — NEXT.JS FUNDAMENTALS & ROUTING
> *"In Next.js, the file system IS your router. No configuration needed."*

---

### 📦 Module 1.1: App Router Fundamentals

#### § 1.1.1 — File-System Based Routing
  - `app/page.tsx` → `/` (home page)
  - `app/about/page.tsx` → `/about`
  - `app/blog/page.tsx` → `/blog`
  - Only files named `page.tsx` are publicly accessible routes
  - Each route segment = a folder in the `app/` directory
  - Colocation: other files in the folder (components, styles, tests) are NOT routes

#### § 1.1.2 — Special Files in App Router
  - `page.tsx` — the UI for a route (required to make route accessible)
  - `layout.tsx` — shared UI that wraps child pages (persists across navigation)
  - `loading.tsx` — loading UI shown while page is loading (Suspense boundary)
  - `error.tsx` — error UI shown when page throws (error boundary)
  - `not-found.tsx` — 404 UI for the route segment
  - `template.tsx` — like layout but re-renders on navigation (no state persistence)
  - `default.tsx` — fallback for parallel routes
  - `route.ts` — API endpoint (Route Handler)
  - `middleware.ts` — runs before request (at the edge)

#### § 1.1.3 — The Root Layout
  - `app/layout.tsx` — required, wraps ALL pages
  - Must include `<html>` and `<body>` tags
  - Shared UI: navigation, footer, providers (theme, auth, query client)
  - `metadata` export: title, description, Open Graph (SEO)
  - Root layout is a Server Component by default

---

### 📦 Module 1.2: Dynamic & Advanced Routing

#### § 1.2.1 — Dynamic Routes
  - `app/blog/[slug]/page.tsx` → `/blog/my-first-post`
  - Access params: `params` prop → `{ slug: "my-first-post" }`
  - Multiple dynamic segments: `app/[category]/[id]/page.tsx`
  - `generateStaticParams()` — pre-render dynamic routes at build time (SSG)

#### § 1.2.2 — Catch-All & Optional Catch-All Routes
  - `app/docs/[...slug]/page.tsx` → `/docs/a`, `/docs/a/b`, `/docs/a/b/c`
  - `params.slug` is an array: `["a", "b", "c"]`
  - Optional catch-all: `app/docs/[[...slug]]/page.tsx` → also matches `/docs`

#### § 1.2.3 — Route Groups
  - `app/(marketing)/about/page.tsx` → `/about` (parentheses excluded from URL)
  - `app/(auth)/login/page.tsx` → `/login`
  - Use case: organize routes without affecting URL, apply different layouts
  - Multiple root layouts: `(marketing)/layout.tsx` vs `(dashboard)/layout.tsx`

#### § 1.2.4 — Parallel Routes
  - `app/@sidebar/page.tsx` + `app/@main/page.tsx` — render simultaneously
  - Slots: `@slotName` directories
  - Layout receives slots as props: `{ children, sidebar, main }`
  - Use case: dashboards, split views, modals
  - `default.tsx` — fallback when a slot doesn't match

#### § 1.2.5 — Intercepting Routes
  - `app/feed/(..)photo/[id]/page.tsx` — intercept `/photo/[id]` from `/feed`
  - Convention: `(.)` same level, `(..)` one level up, `(..)(..)` two levels up, `(...)` root
  - Use case: modals that overlay content, Instagram-style photo preview
  - On hard navigation (direct URL): shows the full page instead

---

### 📦 Module 1.3: Navigation

#### § 1.3.1 — Link Component
  - `<Link href="/about">` — client-side navigation (no full page reload)
  - Automatic prefetching: visible links are prefetched in production
  - `prefetch={false}` — disable prefetching
  - Active link detection: `usePathname()` hook
  - Dynamic href: `<Link href={`/blog/${slug}`}>`
  - `scroll={false}` — prevent scroll to top on navigation
  - `replace` — replace current history entry instead of pushing

#### § 1.3.2 — `useRouter` Hook (Client Components)
  - `router.push("/dashboard")` — navigate programmatically
  - `router.replace("/login")` — replace without history entry
  - `router.back()` — go back
  - `router.forward()` — go forward
  - `router.refresh()` — refresh current route (re-fetch server components)
  - `router.prefetch("/about")` — manual prefetching

#### § 1.3.3 — `redirect()` Function (Server Components)
  - `redirect("/login")` — server-side redirect (in Server Components, Route Handlers, Server Actions)
  - `permanentRedirect("/new-path")` — 308 permanent redirect
  - `notFound()` — trigger 404 page
  - `next.config.ts` redirects: permanent redirects at the config level

#### § 1.3.4 — Navigation Hooks
  - `usePathname()` — current URL path
  - `useSearchParams()` — URL query parameters
  - `useParams()` — dynamic route parameters
  - `useSelectedLayoutSegment()` — active child segment (for navigation highlighting)
  - `useSelectedLayoutSegments()` — all active child segments

---

### 📦 Module 1.4: Layouts, Templates & Metadata

#### § 1.4.1 — Nested Layouts
  - Each route segment can have its own `layout.tsx`
  - Layouts wrap children: `app/layout.tsx` → `app/dashboard/layout.tsx` → `app/dashboard/page.tsx`
  - Layouts preserve state across navigation (sidebar doesn't re-render)
  - Layouts cannot access `pathname` (use Client Components for active state)

#### § 1.4.2 — Templates
  - `template.tsx` — like layout but creates new instance on each navigation
  - Use case: entrance/exit animations, per-page analytics logging
  - Renders between layout and page in the component tree

#### § 1.4.3 — Metadata API
  - Static metadata: `export const metadata: Metadata = { title: "...", description: "..." }`
  - Dynamic metadata: `export async function generateMetadata({ params }): Promise<Metadata>`
  - Title template: `title: { template: "%s | MySite", default: "MySite" }`
  - Open Graph: `openGraph: { title, description, images }`
  - Twitter Cards: `twitter: { card, title, description, images }`
  - Favicon: `icons: { icon: "/favicon.ico" }`
  - Canonical URL, robots, sitemap
  - JSON-LD structured data: `<script type="application/ld+json">`
  - `generateMetadata` can fetch data for dynamic SEO (product pages, blog posts)

> ### 🛠️ Phase 1 Project: **"DevBlog — A Multi-Section Blog Platform"**
> Build a blog platform demonstrating all routing features:
> - **Routes**: Home, Blog (list), Blog Post (dynamic `[slug]`), About, Contact, Dashboard
> - **Route groups**: `(marketing)` for public pages, `(dashboard)` for admin pages
> - **Nested layouts**: root layout (nav + footer), dashboard layout (sidebar + main)
> - **Dynamic routes**: `/blog/[slug]` with `generateStaticParams` for 5 sample posts
> - **Catch-all route**: `/docs/[...slug]` for documentation pages
> - **Loading states**: `loading.tsx` with skeleton UI for every route
> - **Error handling**: `error.tsx` with retry button, `not-found.tsx` with custom 404
> - **Navigation**: `<Link>` with active state highlighting using `usePathname()`
> - **Metadata**: unique title, description, Open Graph for every page
> - **Dynamic metadata**: blog post title and description from post data
> - **Intercepting routes**: click blog post → modal preview, direct URL → full page
> - Static content (no database yet) — focus on routing architecture

---

## ⚡ PHASE 2 — SERVER COMPONENTS & CLIENT COMPONENTS
> *"The most important mental model shift in modern React. If you don't understand this, you don't understand Next.js 13+."*

---

### 📦 Module 2.1: React Server Components (RSC)

#### § 2.1.1 — What Are Server Components
  - Components that render ONLY on the server
  - Never sent to the client as JavaScript (zero client bundle impact)
  - Can directly access databases, file systems, environment variables
  - Can use `async/await` at the component level (no `useEffect` for data fetching!)
  - Cannot use hooks (`useState`, `useEffect`, etc.)
  - Cannot use browser APIs (`window`, `document`, `localStorage`)
  - Cannot use event handlers (`onClick`, `onChange`)
  - **Default in Next.js App Router**: every component is a Server Component unless marked otherwise

#### § 2.1.2 — Benefits of Server Components
  - **Smaller client bundle**: server-only code never reaches the browser
  - **Direct data access**: query database directly in the component
  - **Security**: API keys, tokens, queries stay on the server
  - **Performance**: no client-side waterfall for data fetching
  - **SEO**: fully rendered HTML sent to the browser
  - **Streaming**: progressive rendering with Suspense

#### § 2.1.3 — What You CAN Do in Server Components
  - Fetch data with `async/await`
  - Access backend resources (database, filesystem, secrets)
  - Import and render other Server Components
  - Import and render Client Components
  - Pass serializable props to Client Components
  - Use server-only utilities: `import "server-only"`

---

### 📦 Module 2.2: Client Components

#### § 2.2.1 — What Are Client Components
  - Components that render on the client (AND pre-render on the server!)
  - Marked with `"use client"` directive at the top of the file
  - CAN use hooks: `useState`, `useEffect`, `useRef`, `useContext`, etc.
  - CAN use browser APIs: `window`, `document`, `localStorage`
  - CAN use event handlers: `onClick`, `onChange`, `onSubmit`
  - Pre-rendered on server for initial HTML, then hydrated on client

#### § 2.2.2 — The `"use client"` Boundary
  - `"use client"` — first line of the file, creates a client boundary
  - Everything imported INTO a client component becomes client code
  - Client Components CAN render Server Components as `children` (composition pattern)
  - `"use client"` doesn't mean "client-only" — it means "client + server pre-render"
  - Place `"use client"` as deep in the tree as possible (minimize client JavaScript)

---

### 📦 Module 2.3: The Server/Client Composition Pattern

#### § 2.3.1 — Deciding Server vs Client
  - Server Component: data fetching, backend access, static rendering, no interactivity
  - Client Component: interactivity (clicks, forms, inputs), browser APIs, hooks, state
  - Decision flowchart: Does it need interactivity? → Client. Does it need data? → Server. Both? → Compose them.

#### § 2.3.2 — Composition Patterns
  - **Pattern 1**: Server Component fetches data, passes to Client Component as props
  - **Pattern 2**: Server Component renders Client Component as child (children slot)
  - **Pattern 3**: Client Component wraps Server Components (providers pattern)
  - **Anti-pattern**: importing a Server Component INTO a Client Component (it becomes client!)
  - **Fix**: pass Server Component as `children` prop to Client Component

#### § 2.3.3 — Serialization Boundary
  - Props passed from Server to Client must be serializable (JSON-compatible)
  - Allowed: strings, numbers, booleans, arrays, plain objects, null, Date, BigInt, Map, Set
  - NOT allowed: functions, class instances, DOM nodes, Symbols
  - Server Actions are an exception: functions that can be passed to Client Components

#### § 2.3.4 — Third-Party Components & Providers
  - Most third-party components use hooks → need `"use client"`
  - Wrapper pattern: create a Client Component that wraps the third-party component
  - Context Providers: must be Client Components (they use `useContext`)
  - Provider pattern: wrap providers around `children` in layout

---

### 📦 Module 2.4: Rendering Deep Dive

#### § 2.4.1 — Static Rendering (Default)
  - Routes rendered at build time (or on first request and cached)
  - Automatic for routes with no dynamic data
  - Result: HTML file served from CDN (fastest possible)
  - `generateStaticParams()` — pre-render dynamic routes statically

#### § 2.4.2 — Dynamic Rendering
  - Routes rendered on every request (not cached)
  - Triggered by: dynamic functions (`cookies()`, `headers()`, `searchParams`), uncached data fetches
  - Equivalent to SSR in Pages Router
  - `export const dynamic = "force-dynamic"` — opt into dynamic rendering

#### § 2.4.3 — Streaming & Suspense
  - Stream HTML progressively — show content as it becomes ready
  - `loading.tsx` — automatic Suspense boundary at the route level
  - Manual: wrap components in `<Suspense fallback={<Loading />}>`
  - Each Suspense boundary streams independently
  - User sees content faster — no waiting for slowest data source
  - Critical for perceived performance

#### § 2.4.4 — Partial Prerendering (PPR) — Experimental
  - Combine static shell with dynamic holes
  - Static parts served instantly from CDN
  - Dynamic parts stream in when ready
  - Best of both worlds: static speed + dynamic data
  - The future of Next.js rendering

> ### 🛠️ Phase 2 Project: **"ProductShowcase — Server/Client Architecture"**
> Build a product showcase demonstrating the Server/Client mental model:
> - **Server Components**: product list page (fetches from mock data/JSON), product detail page, category page, footer
> - **Client Components**: search bar (useState), filter panel (useState), shopping cart (useReducer + useContext), theme toggle, image carousel, "Add to Cart" button
> - **Composition**:
>   - Server Component fetches products → passes to Client Component for filtering
>   - Cart Provider (Client) wraps the entire app via layout (children pattern)
>   - Product Card: Server Component with a nested "Add to Cart" Client Component
> - **Streaming**: `<Suspense>` boundaries around slow data fetches with skeleton loaders
> - **`loading.tsx`**: route-level loading states
> - **No `useEffect` for data fetching** — all data fetched in Server Components
> - **`server-only`** package to protect server-only code
> - Measure: count Client Components, ensure minimum `"use client"` boundaries

---

## ⚡ PHASE 3 — DATA FETCHING & CACHING
> *"Data fetching in Next.js is completely different from traditional React. Unlearn useEffect for data."*

---

### 📦 Module 3.1: Server-Side Data Fetching

#### § 3.1.1 — Fetching in Server Components
  - `async` Server Components: `async function Page()` — top-level `await`
  - Native `fetch` with Next.js extensions: caching and revalidation
  - Direct database queries: call Prisma, Drizzle, or raw SQL directly in components
  - Direct file system access: read files in Server Components
  - No API layer needed for same-app data — call functions directly

#### § 3.1.2 — `fetch` with Next.js Caching Options
  - `fetch(url)` — cached by default (static)
  - `fetch(url, { cache: "no-store" })` — never cache (dynamic)
  - `fetch(url, { next: { revalidate: 3600 } })` — revalidate every hour (ISR)
  - `fetch(url, { next: { tags: ["posts"] } })` — tag-based revalidation
  - Deduplication: same `fetch` URL called multiple times → only one request

#### § 3.1.3 — Data Fetching Patterns
  - **Sequential**: fetch one after another (when second depends on first)
  - **Parallel**: `Promise.all([fetch1(), fetch2()])` — fetch simultaneously
  - **Preloading**: `preload()` pattern — start fetch before component renders
  - Avoid waterfalls: fetch data as high in the tree as possible, pass down as props
  - Parallel data fetching with multiple `<Suspense>` boundaries

---

### 📦 Module 3.2: Caching (Next.js Caching Architecture)

#### § 3.2.1 — Request Memoization
  - Same `fetch` request in multiple components during one render → deduplicated
  - Automatic for `fetch` — manual for database queries using `React.cache()`
  - Only during server rendering of a single request

#### § 3.2.2 — Data Cache
  - Server-side cache for `fetch` responses
  - Persists across requests and deployments (until revalidated)
  - Revalidation: time-based (`revalidate: 60`) or on-demand (`revalidateTag`, `revalidatePath`)

#### § 3.2.3 — Full Route Cache
  - Static routes cached as HTML + RSC Payload at build time
  - Served directly without hitting the server
  - Invalidated when data cache is invalidated

#### § 3.2.4 — Router Cache (Client-Side)
  - In-memory cache of visited routes on the client
  - Prefetched routes stored in browser memory
  - Duration: session-based (cleared on page refresh)
  - `router.refresh()` — invalidate the router cache

#### § 3.2.5 — Opting Out of Caching
  - `export const dynamic = "force-dynamic"` — page level
  - `export const revalidate = 0` — page level
  - `fetch(url, { cache: "no-store" })` — fetch level
  - Dynamic functions: `cookies()`, `headers()`, `searchParams` — auto-opt out
  - `unstable_noStore()` — function level (for database queries)

---

### 📦 Module 3.3: Revalidation

#### § 3.3.1 — Time-Based Revalidation
  - `fetch(url, { next: { revalidate: 3600 } })` — per-fetch
  - `export const revalidate = 3600` — per-route segment
  - Stale-while-revalidate: serves cached version, regenerates in background
  - Minimum value wins when multiple revalidation times in one route

#### § 3.3.2 — On-Demand Revalidation
  - `revalidateTag("posts")` — invalidate all fetches tagged with "posts"
  - `revalidatePath("/blog")` — invalidate a specific path
  - Called from: Server Actions, Route Handlers, webhooks
  - Use case: CMS publishes new content → webhook triggers revalidation

---

### 📦 Module 3.4: Database Access

#### § 3.4.1 — ORM Choices for Next.js
  - **Prisma** — most popular, great DX, schema-first, auto-generated client
  - **Drizzle ORM** — lightweight, SQL-like syntax, better edge compatibility
  - **Kysely** — type-safe SQL query builder
  - Direct database drivers: `pg` (PostgreSQL), `mysql2`, `better-sqlite3`
  - Serverless databases: Vercel Postgres, Neon, PlanetScale, Supabase, Turso

#### § 3.4.2 — Prisma Integration
  - `prisma init` — create schema, configure database
  - Schema definition: models, relations, types
  - `prisma migrate dev` — create and apply migrations
  - `prisma generate` — generate type-safe client
  - Singleton pattern for Prisma Client in development (prevent hot-reload connection exhaustion)
  - Direct queries in Server Components: `const posts = await prisma.post.findMany()`
  - No API layer needed — query directly in the component

#### § 3.4.3 — Drizzle ORM Integration
  - Schema in TypeScript: `export const users = pgTable("users", { ... })`
  - SQL-like queries: `db.select().from(users).where(eq(users.id, id))`
  - Drizzle Kit: migrations and schema management
  - Edge-compatible: works in middleware, Vercel Edge Functions
  - Growing rapidly in the Next.js ecosystem

---

### 📦 Module 3.5: Data Fetching for Client Components

#### § 3.5.1 — SWR (Stale-While-Revalidate)
  - `useSWR(key, fetcher)` — React hook for client-side data fetching
  - Auto-revalidation on focus, interval, reconnect
  - Caching, deduplication, pagination support
  - Optimistic updates, mutation
  - Developed by Vercel — first-class Next.js integration

#### § 3.5.2 — TanStack Query (React Query)
  - `useQuery`, `useMutation` — declarative data fetching and mutations
  - Advanced: infinite queries, prefetching, optimistic updates
  - `QueryClient` and `QueryClientProvider` (Client Component wrapper)
  - Server-side prefetching: hydrate query cache from Server Components
  - When to use: complex client-side data requirements, real-time, polling

#### § 3.5.3 — When to Fetch Where
  - Server Components: initial page data, SEO-critical data, sensitive queries
  - Client Components (SWR/React Query): real-time data, user-specific data, interactive features
  - Route Handlers: when you need a traditional API endpoint
  - Server Actions: mutations (create, update, delete)

> ### 🛠️ Phase 3 Project: **"NewsAggregator — Data Fetching Mastery"**
> Build a news aggregation platform:
> - **Server-side fetch**: news articles from a public API (News API, Hacker News)
> - **Caching strategies**:
>   - Homepage: revalidate every 5 minutes (ISR)
>   - Breaking news: no cache (dynamic)
>   - Archive pages: cache forever (static)
> - **Tag-based revalidation**: revalidate specific categories on demand
> - **Database**: Prisma with SQLite/PostgreSQL for saved articles and user preferences
> - **Parallel fetching**: multiple news sources fetched simultaneously with `Promise.all`
> - **Streaming**: `<Suspense>` for each news category section (independent loading)
> - **Client-side data**: SWR for live updates (polling every 30 seconds for breaking news)
> - **Pagination**: server-side paginated list with "Load More" client interaction
> - **Search**: client-side search with debounced API calls
> - **`React.cache()`** for deduplicating database queries
> - Demonstrate caching behavior with logging and timestamps

---

## ⚡ PHASE 4 — SERVER ACTIONS & MUTATIONS
> *"Server Actions are Next.js's answer to the full-stack dream. No API routes needed for mutations."*

---

### 📦 Module 4.1: Server Actions Fundamentals

#### § 4.1.1 — What Are Server Actions
  - Functions that run on the server, callable from the client
  - Defined with `"use server"` directive
  - Can be called from: forms, event handlers, `useEffect`
  - Replace API routes for mutations in most cases
  - Type-safe: TypeScript types flow from server to client
  - Progressive enhancement: forms work even without JavaScript

#### § 4.1.2 — Defining Server Actions
  - **Inline**: `"use server"` inside an `async` function in a Server Component
  - **Module-level**: `"use server"` at top of file — ALL exports become Server Actions
  - Separate file pattern: `app/actions/users.ts` with `"use server"` at top
  - Server Actions MUST be `async` functions
  - Parameters: form data (`FormData`), or regular arguments
  - Return value: any serializable data (or void)

#### § 4.1.3 — Server Actions in Forms
  - `<form action={serverAction}>` — native form submission
  - `FormData` parameter: `async function createPost(formData: FormData)`
  - `formData.get("title")` — extract form values
  - Progressive enhancement: works without JavaScript (form posts to server)
  - `<button formAction={deletePost}>` — different action per button
  - Hidden inputs for additional data: `<input type="hidden" name="id" value={id} />`

---

### 📦 Module 4.2: Advanced Server Actions

#### § 4.2.1 — `useFormStatus` Hook
  - `const { pending } = useFormStatus()` — track form submission state
  - Must be used in a component INSIDE the form (not the form itself)
  - Use case: disable submit button, show loading spinner

#### § 4.2.2 — `useFormState` / `useActionState` Hook
  - Connect Server Action to form state (validation errors, success messages)
  - Returns `[state, formAction]` — state updated after action completes
  - Use case: display server-side validation errors inline

#### § 4.2.3 — Optimistic Updates
  - `useOptimistic` hook — update UI before server confirms
  - Rollback on error
  - Use case: like button, todo completion, comment posting

#### § 4.2.4 — Revalidation After Mutations
  - `revalidatePath("/posts")` — revalidate a page after mutation
  - `revalidateTag("posts")` — revalidate tagged data
  - `redirect("/posts")` — redirect after successful mutation
  - Pattern: mutate → revalidate → redirect

#### § 4.2.5 — Server Action Security
  - Server Actions create POST endpoints — treat them like API endpoints
  - Always validate input (never trust client data)
  - Always authorize (check user permissions)
  - Use Zod for schema validation
  - Rate limiting: protect against abuse
  - CSRF protection: built into Next.js (origin checking)

---

### 📦 Module 4.3: Form Validation

#### § 4.3.1 — Server-Side Validation with Zod
  - Define schemas: field types, constraints, custom messages
  - Parse in Server Action: validation errors returned to client
  - `safeParse` — returns success/error without throwing
  - Return validation errors via `useActionState`

#### § 4.3.2 — Client-Side Validation
  - HTML5 validation attributes: `required`, `minLength`, `pattern`, `type="email"`
  - React Hook Form + Zod: `@hookform/resolvers/zod`
  - Libraries: React Hook Form, Formik (legacy)
  - Client + server validation: client for UX, server for security (both required!)

---

### 📦 Module 4.4: Route Handlers (API Routes)

#### § 4.4.1 — When to Use Route Handlers
  - Webhooks from external services
  - Third-party API proxy
  - Server Actions don't fit (need specific HTTP methods/headers)
  - Public API for other consumers
  - File generation (PDF, CSV)

#### § 4.4.2 — Defining Route Handlers
  - `app/api/users/route.ts` → `/api/users`
  - Export functions named by HTTP method: `GET`, `POST`, `PUT`, `PATCH`, `DELETE`
  - Request: `NextRequest` (extends `Request`)
  - Response: `NextResponse` (extends `Response`)
  - Dynamic routes: `app/api/users/[id]/route.ts`
  - Caching: `GET` handlers are cached by default (same as pages)

#### § 4.4.3 — Route Handler Patterns
  - JSON responses: `NextResponse.json(data, { status: 200 })`
  - Headers and cookies access
  - Streaming responses: `ReadableStream`
  - CORS handling
  - File upload handling
  - Webhook signature verification

> ### 🛠️ Phase 4 Project: **"TaskMaster — Full-Stack Task Management"**
> Build a complete task management app with Server Actions:
> - **CRUD operations**: all via Server Actions (no API routes for mutations)
>   - Create task (form with validation)
>   - Update task (inline editing)
>   - Delete task (with confirmation)
>   - Toggle completion (optimistic update)
> - **Forms**: `<form action={...}>` with progressive enhancement
> - **Validation**: Zod schemas, server-side validation, errors displayed via `useActionState`
> - **`useFormStatus`**: loading states on submit buttons
> - **`useOptimistic`**: instant toggle for task completion
> - **Revalidation**: `revalidatePath` after every mutation
> - **Database**: Prisma with PostgreSQL (or SQLite for dev)
> - **Route Handlers**: webhook endpoint for external integrations, CSV export
> - **Categories/Tags**: server-side filtered lists
> - Test: all Server Actions tested, form submission without JavaScript verified

---

## ⚡ PHASE 5 — STYLING & UI COMPONENT SYSTEMS
> *"Next.js is agnostic about styling. But the ecosystem has clear winners."*

---

### 📦 Module 5.1: Tailwind CSS (The Default Choice)

#### § 5.1.1 — Tailwind CSS Fundamentals
  - Utility-first CSS: classes directly in JSX
  - Responsive design: `sm:`, `md:`, `lg:`, `xl:`, `2xl:` prefixes
  - State variants: `hover:`, `focus:`, `active:`, `disabled:`, `group-hover:`
  - Dark mode: `dark:` variant, class-based or media-based
  - Flexbox and Grid: `flex`, `grid`, `gap-4`, `items-center`, `justify-between`
  - Spacing, typography, colors, borders, shadows, transitions, animations

#### § 5.1.2 — Advanced Tailwind
  - Custom theme: `tailwind.config.ts` — colors, fonts, spacing, breakpoints
  - `@apply` in CSS files — extract repeated utility patterns (use sparingly)
  - Arbitrary values: `w-[calc(100%-2rem)]`, `bg-[#1a1a2e]`
  - `cn()` utility: `clsx` + `tailwind-merge` for conditional class names
  - Plugins: `@tailwindcss/typography`, `@tailwindcss/forms`, `@tailwindcss/container-queries`
  - Tailwind CSS v4: CSS-first configuration, zero-config mode (emerging)

---

### 📦 Module 5.2: Component Libraries

#### § 5.2.1 — shadcn/ui (The Community Standard)
  - NOT a component library — a collection of copy-paste components
  - Built on Radix UI primitives (accessible) + Tailwind CSS (styled)
  - `npx shadcn@latest add button` — adds component to your project
  - Full control: components live in your codebase, customize freely
  - Components: Button, Dialog, Dropdown, Form, Table, Toast, Sheet, Tabs, Command, etc.
  - Theme system: CSS variables for consistent theming
  - Best choice for new Next.js projects

#### § 5.2.2 — Other UI Options
  - **Radix UI** — unstyled, accessible primitives (used by shadcn/ui)
  - **Headless UI** — unstyled, accessible components (from Tailwind team)
  - **MUI (Material UI)** — Google Material Design (heavy, fully styled)
  - **Chakra UI** — styled, accessible components
  - **Mantine** — comprehensive React component library
  - **Ant Design** — enterprise-oriented (popular in Asia)

---

### 📦 Module 5.3: Other Styling Approaches

#### § 5.3.1 — CSS Modules
  - `styles.module.css` — scoped CSS per component
  - Built into Next.js, zero configuration
  - `import styles from "./page.module.css"` → `className={styles.container}`
  - Good for: teams familiar with CSS, avoiding utility classes

#### § 5.3.2 — Global CSS
  - `app/globals.css` — imported in root layout
  - CSS custom properties (variables) for theming
  - CSS reset / normalize
  - Tailwind's `@tailwind` directives live here

#### § 5.3.3 — CSS-in-JS Considerations
  - Styled-components, Emotion — work in Client Components only
  - Server Components don't support CSS-in-JS (no runtime)
  - Trend: moving away from CSS-in-JS toward Tailwind + CSS Modules
  - If needed: `styled-components` with Next.js requires specific configuration

---

### 📦 Module 5.4: Fonts, Icons & Assets

#### § 5.4.1 — `next/font` — Optimized Fonts
  - `next/font/google` — Google Fonts with zero layout shift
  - `next/font/local` — local font files
  - Fonts loaded at build time, self-hosted (no external request)
  - `variable` fonts for Tailwind integration: `className` or CSS variable
  - Zero CLS (Cumulative Layout Shift) — fonts don't cause layout jumps

#### § 5.4.2 — Icons
  - `lucide-react` — beautiful icon library (used by shadcn/ui)
  - `react-icons` — aggregated icon library (FontAwesome, Heroicons, etc.)
  - `@heroicons/react` — Tailwind team's icon library
  - SVG icons as React components

#### § 5.4.3 — Images & Media
  - `next/image` — optimized image component
  - Automatic: lazy loading, responsive sizing, format conversion (WebP/AVIF)
  - `width`, `height` required (prevents layout shift)
  - `fill` prop for unknown dimensions (with sized container)
  - `priority` prop for above-the-fold images (LCP optimization)
  - Remote images: configure domains in `next.config.ts`
  - `placeholder="blur"` — blurred placeholder while loading
  - Static imports: `import hero from "./hero.png"` (auto-sized)

> ### 🛠️ Phase 5 Project: **"TaskMaster v2 — Beautiful & Responsive UI"**
> Redesign TaskMaster with a polished UI:
> - **Tailwind CSS**: complete responsive design (mobile → tablet → desktop)
> - **shadcn/ui**: Button, Dialog, Form, Input, Select, Table, Toast, Sheet, DropdownMenu, Command Palette
> - **Dark mode**: toggle with system preference detection and manual override
> - **Theme**: custom color palette via CSS variables, consistent across all components
> - **`next/font`**: Google Font loaded with zero CLS
> - **`next/image`**: user avatars, task attachments with optimized images
> - **Responsive sidebar**: full sidebar on desktop, sheet/drawer on mobile
> - **Animations**: Framer Motion for page transitions, list animations, modal enter/exit
> - **`cn()` utility**: conditional styling throughout
> - **Accessible**: keyboard navigation, screen reader support, focus management
> - **Loading skeletons**: shadcn/ui Skeleton component for all loading states
> - **Design system**: documented color tokens, spacing scale, typography scale

---

## ⚡ PHASE 6 — AUTHENTICATION & AUTHORIZATION
> *"Auth in Next.js is uniquely complex because of Server Components, Server Actions, Middleware, and Route Handlers."*

---

### 📦 Module 6.1: Authentication Fundamentals in Next.js

#### § 6.1.1 — Where Auth Runs in Next.js
  - **Middleware**: check auth before request reaches the page (edge runtime)
  - **Server Components**: check auth to render protected UI
  - **Server Actions**: check auth before mutations
  - **Route Handlers**: check auth for API endpoints
  - **Client Components**: read session for UI state (logged in/out)
  - Auth must be checked at EVERY layer — defense in depth

#### § 6.1.2 — Session Strategies
  - **JWT (JSON Web Tokens)**: stateless, stored in cookies, verified on each request
  - **Database sessions**: session ID in cookie, session data in database
  - **OAuth**: delegate authentication to providers (Google, GitHub, etc.)
  - JWT: faster (no DB lookup), harder to revoke
  - Database sessions: revocable, more storage, requires DB query per request

---

### 📦 Module 6.2: NextAuth.js / Auth.js

#### § 6.2.1 — NextAuth.js Fundamentals
  - The most popular auth library for Next.js
  - `next-auth` (v4) → `@auth/nextjs` (v5 / Auth.js — rebranded)
  - Supports: OAuth (Google, GitHub, Discord, etc.), email/magic link, credentials (username/password)
  - Session management: JWT or database
  - `auth()` — get session in Server Components
  - `signIn()`, `signOut()` — client-side auth actions

#### § 6.2.2 — Configuration
  - Auth configuration file: providers, callbacks, pages
  - OAuth providers: client ID and secret from provider
  - Database adapter: Prisma adapter for database sessions
  - Callbacks: `jwt`, `session`, `signIn`, `redirect` — customize auth behavior
  - Custom pages: login, error, verify-request, new-user

#### § 6.2.3 — Using Auth Across the App
  - Server Components: `const session = await auth()`
  - Client Components: `useSession()` hook (requires `SessionProvider`)
  - Middleware: protect routes before they render
  - Server Actions: `const session = await auth()` — verify before mutation
  - Route Handlers: `const session = await auth()` — verify API access

---

### 📦 Module 6.3: Clerk (Managed Auth)

#### § 6.3.1 — Clerk Integration
  - Managed authentication service — handles UI, sessions, user management
  - `@clerk/nextjs` — full Next.js integration
  - `<ClerkProvider>` — wrapper component
  - `<SignIn />`, `<SignUp />` — pre-built UI components
  - `auth()` — server-side auth helper
  - `currentUser()` — get full user object
  - `clerkMiddleware()` — protect routes
  - `useUser()`, `useAuth()` — client-side hooks
  - Webhook events for user lifecycle
  - When to use: rapid development, don't want to build auth UI

---

### 📦 Module 6.4: Authorization Patterns

#### § 6.4.1 — Role-Based Access Control (RBAC)
  - User roles: admin, editor, viewer
  - Check role in Server Components, Server Actions, Middleware
  - Protected routes: redirect unauthorized users
  - Protected UI: conditionally render based on role

#### § 6.4.2 — Middleware-Based Protection
  - `middleware.ts` at project root
  - `NextResponse.redirect()` — redirect unauthenticated users
  - `matcher` config: specify which routes middleware runs on
  - Edge runtime: limited API access (no database queries)
  - Pattern: verify JWT in middleware, full auth check in page/action

#### § 6.4.3 — Resource-Based Authorization
  - Check ownership: user can only edit their own resources
  - Check in Server Actions: before mutation
  - Check in Server Components: before rendering

> ### 🛠️ Phase 6 Project: **"TaskMaster v3 — Multi-User with Auth"**
> Add authentication and authorization:
> - **Auth provider**: NextAuth.js (Auth.js v5) with multiple providers
>   - OAuth: GitHub + Google login
>   - Credentials: email/password with hashed passwords (bcrypt)
> - **Database sessions**: Prisma adapter for session storage
> - **Protected routes**: middleware redirects unauthenticated users from `/dashboard/*`
> - **Roles**: Admin (manage all tasks, manage users), Member (manage own tasks)
> - **Authorization checks**: Server Components (conditional UI), Server Actions (permission check before mutation), Middleware (route protection)
> - **User-scoped data**: users only see their own tasks (unless admin)
> - **Profile page**: view and update profile, change password
> - **Session display**: show user avatar and name in header
> - **Sign in/out**: custom styled sign-in page, sign-out functionality
> - **Invite system**: admin can invite users via email

---

## ⚡ PHASE 7 — PERFORMANCE OPTIMIZATION
> *"Next.js gives you performance by default. Mastery is knowing when you're accidentally opting out."*

---

### 📦 Module 7.1: Core Web Vitals

#### § 7.1.1 — Understanding Core Web Vitals
  - **LCP (Largest Contentful Paint)** — how fast the main content loads (<2.5s good)
  - **INP (Interaction to Next Paint)** — how responsive to user input (<200ms good)
  - **CLS (Cumulative Layout Shift)** — visual stability (<0.1 good)
  - Google ranking factor: Core Web Vitals affect SEO
  - Tools: Lighthouse, PageSpeed Insights, Chrome DevTools Performance tab, Web Vitals extension

#### § 7.1.2 — Next.js Built-in Optimizations
  - Automatic code splitting: each page only loads its own JavaScript
  - `next/image`: lazy loading, responsive, modern formats, prevents CLS
  - `next/font`: zero-CLS font loading, self-hosted
  - `next/script`: control script loading strategy (`beforeInteractive`, `afterInteractive`, `lazyOnload`)
  - Prefetching: `<Link>` automatically prefetches visible links
  - Server Components: zero client-side JavaScript by default
  - Streaming: show content progressively

---

### 📦 Module 7.2: Bundle Optimization

#### § 7.2.1 — Analyzing Bundle Size
  - `@next/bundle-analyzer` — visualize bundle composition
  - `ANALYZE=true next build` — generate bundle report
  - Identify large dependencies and unnecessary client-side imports

#### § 7.2.2 — Reducing Client JavaScript
  - Push `"use client"` boundary as deep as possible
  - Dynamic imports: `next/dynamic` — lazy load heavy components
  - `{ ssr: false }` option for client-only components (maps, editors)
  - Barrel file optimization: `optimizePackageImports` in `next.config.ts`
  - Tree shaking: import only what you need from libraries
  - Replace heavy libraries: `date-fns` over `moment`, `lucide-react` over `react-icons`

#### § 7.2.3 — `next/dynamic` — Dynamic Imports
  - Lazy load components: `const Chart = dynamic(() => import("./Chart"))`
  - Loading component: `dynamic(() => import("./Chart"), { loading: () => <Skeleton /> })`
  - `ssr: false` — skip server rendering for client-only components
  - Use case: charts, maps, rich text editors, heavy visualization libraries

---

### 📦 Module 7.3: Image & Media Optimization

#### § 7.3.1 — `next/image` Best Practices
  - Always set `width` and `height` (or use `fill`)
  - `priority` on hero images and above-the-fold content
  - `sizes` prop for responsive images: `sizes="(max-width: 768px) 100vw, 50vw"`
  - `quality` prop: default 75, balance quality vs file size
  - External images: configure `remotePatterns` in `next.config.ts`
  - `placeholder="blur"` with `blurDataURL` for custom blur

#### § 7.3.2 — Video & Large Media
  - Self-host or use a CDN (Cloudinary, Vercel Blob, AWS S3)
  - Lazy load videos below the fold
  - Poster images for video elements

---

### 📦 Module 7.4: Caching & Rendering Optimization

#### § 7.4.1 — Static vs Dynamic Decisions
  - Default to static — let Next.js optimize
  - Only opt into dynamic when needed (user-specific data, real-time)
  - Partial Prerendering (PPR): static shell + dynamic holes
  - `generateStaticParams` for pre-rendering dynamic routes

#### § 7.4.2 — Monitoring Performance
  - `next/web-vitals` — report Web Vitals to analytics
  - Vercel Analytics — real-user performance monitoring
  - Vercel Speed Insights — Core Web Vitals tracking
  - Custom performance monitoring: track Server Action duration, data fetch time

> ### 🛠️ Phase 7 Project: **"TaskMaster v4 — Performance Optimized"**
> Optimize TaskMaster for production performance:
> - **Bundle analysis**: run bundle analyzer, identify and fix oversized dependencies
> - **Dynamic imports**: lazy load chart/analytics components, rich text editor
> - **Image optimization**: all images through `next/image` with proper `sizes` and `priority`
> - **Font optimization**: `next/font` with `display: "swap"` and CSS variable
> - **Minimize Client Components**: audit every `"use client"`, push boundaries deeper
> - **Static generation**: pre-render public pages with `generateStaticParams`
> - **Streaming**: independent `<Suspense>` boundaries for dashboard sections
> - **Lighthouse audit**: achieve 90+ on all four categories (Performance, Accessibility, Best Practices, SEO)
> - **Web Vitals**: LCP < 2s, INP < 150ms, CLS < 0.05
> - Document before/after metrics for every optimization

---

## ⚡ PHASE 8 — STATE MANAGEMENT & ADVANCED PATTERNS
> *"With Server Components, you need less client-side state than you think."*

---

### 📦 Module 8.1: State Management Philosophy in Next.js

#### § 8.1.1 — Rethinking State with Server Components
  - Server Components eliminate the need for client-side state for fetched data
  - URL as state: search params, path segments replace much of client state
  - Server-side state: database IS the state, revalidation refreshes it
  - Client state is only for: UI interactions, optimistic updates, ephemeral state
  - "The best state management is no state management"

#### § 8.1.2 — URL State Management
  - `useSearchParams()` — read query parameters
  - `useRouter().push("?query=value")` — update query parameters
  - `nuqs` library — type-safe search params state management
  - Use case: filters, sorting, pagination, search, tabs
  - Benefits: shareable URLs, browser back/forward works, SSR-compatible

---

### 📦 Module 8.2: Client-Side State Solutions

#### § 8.2.1 — React Context
  - Provider pattern in layouts (Client Component wrapping Server children)
  - Use case: theme, auth session, locale, global UI state
  - Limitation: causes re-renders of all consumers on state change
  - Best for: infrequently changing global data

#### § 8.2.2 — Zustand
  - Lightweight state management library (3KB)
  - No providers needed — `create` a store, use anywhere
  - `zustand` with Next.js: hydration handling for SSR
  - Persist middleware: save state to localStorage
  - Devtools middleware: Redux DevTools integration
  - Use case: shopping cart, multi-step forms, complex UI state

#### § 8.2.3 — Jotai
  - Atomic state management (bottom-up)
  - `atom()` — create primitive atoms
  - `useAtom()` — read/write atom value
  - Derived atoms, async atoms
  - Granular re-renders: only components reading changed atoms re-render
  - Use case: fine-grained state, form state, feature toggles

#### § 8.2.4 — Redux Toolkit (When Really Needed)
  - Complex state with many reducers and middleware
  - `@reduxjs/toolkit` + `react-redux`
  - `next-redux-wrapper` for SSR hydration
  - When to use: very large applications with complex state interactions
  - Often overkill for Next.js — Server Components + Zustand covers most cases

---

### 📦 Module 8.3: Advanced Patterns

#### § 8.3.1 — Parallel Data Fetching Pattern
  - Multiple `<Suspense>` boundaries loading independently
  - `Promise.all` for parallel server-side fetches
  - Avoid sequential waterfalls

#### § 8.3.2 — Search & Filter Pattern
  - Search params in URL: `?q=search&category=tech&sort=date`
  - Server Component reads search params, fetches filtered data
  - Client Component updates URL (debounced input)
  - Result: server-rendered, shareable, back-button compatible

#### § 8.3.3 — Infinite Scroll / Load More Pattern
  - Initial data from Server Component
  - Client Component loads more via SWR/React Query or Server Action
  - Intersection Observer for infinite scroll trigger
  - Cursor-based pagination for performance

#### § 8.3.4 — Multi-Step Form Pattern
  - URL-based steps: `/onboarding?step=1`
  - OR client-side state: Zustand for multi-step form data
  - Server Action on final submission
  - Validation per step with Zod

#### § 8.3.5 — Real-Time Updates Pattern
  - Server-Sent Events (SSE) for one-way server → client
  - WebSocket for bidirectional real-time
  - Polling with SWR: `refreshInterval: 5000`
  - Libraries: `Pusher`, `Ably`, `Socket.io`, `PartyKit`
  - Supabase Realtime for database-level real-time

> ### 🛠️ Phase 8 Project: **"CollabBoard — A Real-Time Collaboration Tool"**
> Build a collaborative project board (like simplified Trello):
> - **URL state**: board filters, search, view mode in URL search params
> - **Zustand**: drag-and-drop state, board UI state, optimistic updates
> - **Server Components**: board data fetching, column rendering
> - **Server Actions**: create/update/delete cards, move between columns
> - **Optimistic updates**: `useOptimistic` for card moves
> - **Real-time**: live updates when other users modify the board (SSE or WebSocket)
> - **Infinite scroll**: load older cards as user scrolls
> - **Search & filter**: server-rendered results with URL-based filters
> - **Multi-step modal**: create card wizard (title → description → labels → assignee)
> - **Drag and drop**: `@hello-pangea/dnd` or `dnd-kit` for card reordering
> - **No unnecessary state**: audit every `useState` — could it be URL state or server state instead?

---

## ⚡ PHASE 9 — TESTING
> *"Testing Next.js is unique: Server Components, Server Actions, and Middleware each need different strategies."*

---

### 📦 Module 9.1: Testing Fundamentals

#### § 9.1.1 — Testing Pyramid for Next.js
  - **Unit tests**: utility functions, hooks, Server Actions (fastest)
  - **Component tests**: render and interact with components (React Testing Library)
  - **Integration tests**: test pages with data fetching (slower)
  - **E2E tests**: full browser testing (Playwright — slowest but most realistic)

#### § 9.1.2 — Testing Setup
  - **Vitest** — fast test runner (Vite-based, modern, recommended)
  - **Jest** — traditional test runner (still widely used)
  - **React Testing Library** — component testing
  - **Playwright** — end-to-end browser testing
  - **MSW (Mock Service Worker)** — mock API responses
  - Configuration: `vitest.config.ts` with Next.js environment

---

### 📦 Module 9.2: Unit & Component Testing

#### § 9.2.1 — Testing Utilities & Helpers
  - Pure functions, formatters, validators
  - Zod schemas: test validation rules
  - Custom hooks: `renderHook` from React Testing Library

#### § 9.2.2 — Testing Client Components
  - `render(<Component />)` — render component
  - `screen.getByRole()`, `screen.getByText()` — query DOM
  - `userEvent.click()`, `userEvent.type()` — simulate interactions
  - `waitFor()` — wait for async updates
  - Mock context providers
  - Mock `useRouter`, `usePathname`, `useSearchParams`

#### § 9.2.3 — Testing Server Components
  - Server Components can be tested as async functions
  - Mock database calls and external APIs
  - Test returned JSX structure
  - Use `next/testmode` utilities (experimental)
  - Integration approach: test via E2E instead of unit tests

#### § 9.2.4 — Testing Server Actions
  - Call Server Actions as plain functions in tests
  - Mock database operations
  - Test: validation, authorization, revalidation
  - Verify database state after action

---

### 📦 Module 9.3: End-to-End Testing

#### § 9.3.1 — Playwright for Next.js
  - `npx playwright init` — setup
  - `page.goto("/")` — navigate to routes
  - `page.getByRole("button", { name: "Submit" }).click()` — interact
  - `expect(page).toHaveURL("/dashboard")` — assert navigation
  - `expect(page.getByText("Success")).toBeVisible()` — assert content
  - Visual regression testing: `page.screenshot()`
  - API testing: `request.get("/api/users")` — test Route Handlers
  - Authentication: store session state, reuse across tests

#### § 9.3.2 — E2E Test Patterns
  - Test critical user flows: signup → login → create resource → verify
  - Test form submissions: validation errors, success, loading states
  - Test navigation: links, breadcrumbs, back button
  - Test responsive design: mobile viewport testing
  - Database seeding: reset database state before tests

---

### 📦 Module 9.4: Mocking Strategies

#### § 9.4.1 — MSW (Mock Service Worker)
  - Intercept network requests at the service worker level
  - Define handlers for API routes
  - Works in: unit tests, component tests, Storybook
  - `rest.get("/api/users", (req, res, ctx) => res(ctx.json(users)))`

#### § 9.4.2 — Database Mocking
  - Mock Prisma client: `jest-mock-extended`, `vitest-mock-extended`
  - Or: use a test database (SQLite in-memory for Prisma tests)
  - Docker-based test database for full integration tests

> ### 🛠️ Phase 9 Project: **"TaskMaster v5 — Fully Tested"**
> Add comprehensive testing:
> - **Unit tests** (Vitest): utility functions, Zod schemas, formatters
> - **Component tests** (React Testing Library): all Client Components — interactions, state changes, form validation
> - **Server Action tests**: test all actions as functions — validation, authorization, database operations
> - **E2E tests** (Playwright):
>   - Auth flow: sign up → login → protected page → sign out
>   - Task CRUD: create → view → edit → delete
>   - Search and filter: enter query → verify results
>   - Responsive: test mobile and desktop layouts
> - **MSW**: mock external API calls
> - **Coverage**: 80%+ for unit/component, critical flows for E2E
> - **CI**: GitHub Actions running all test suites on every PR
> - **Visual regression**: Playwright screenshots for key pages

---

## ⚡ PHASE 10 — DEPLOYMENT, INFRASTRUCTURE & PRODUCTION
> *"Deployment is not the last step. It's the context in which every other decision should be made."*

---

### 📦 Module 10.1: Deployment Platforms

#### § 10.1.1 — Vercel (First-Class)
  - Built by the Next.js team — zero-configuration deployment
  - Git push → automatic deployment
  - Edge network: global CDN for static assets
  - Serverless functions: API routes and Server Components
  - Edge Functions: middleware runs at the edge
  - Preview deployments: every PR gets a unique URL
  - Analytics, Speed Insights, Web Vitals monitoring
  - Vercel Postgres, Blob, KV, Edge Config — integrated services
  - Free tier for personal projects

#### § 10.1.2 — Self-Hosted (Node.js Server)
  - `next build` → `next start` — run as Node.js server
  - Docker: multi-stage build for production container
  - Reverse proxy: Nginx, Caddy, Traefik
  - Process manager: PM2 for Node.js process management
  - Platforms: AWS (EC2, ECS, App Runner), Google Cloud Run, DigitalOcean, Railway, Fly.io

#### § 10.1.3 — Static Export
  - `output: "export"` in `next.config.ts` — generate static HTML
  - No server needed — deploy to any static host (Netlify, GitHub Pages, S3)
  - Limitations: no Server Components at runtime, no API routes, no middleware, no ISR
  - Use case: landing pages, documentation, static sites

#### § 10.1.4 — Serverless / Edge Platforms
  - AWS Lambda with `serverless-next.js` or SST (OpenNext)
  - Cloudflare Workers: `@opennextjs/cloudflare`
  - Netlify: built-in Next.js support
  - Edge considerations: limited Node.js API, no filesystem access

---

### 📦 Module 10.2: Docker for Next.js

#### § 10.2.1 — Production Dockerfile
  - Multi-stage build: deps → build → production
  - Standalone output: `output: "standalone"` in `next.config.ts`
  - Minimal production image: only necessary files
  - `sharp` for image optimization in production
  - Health check endpoint
  - Environment variables: build-time vs runtime
  - `.dockerignore`: exclude `node_modules`, `.next`, `.git`

#### § 10.2.2 — Docker Compose
  - Next.js + PostgreSQL + Redis for local development
  - Volume mounts for development hot-reload
  - Network configuration

---

### 📦 Module 10.3: Environment Variables & Configuration

#### § 10.3.1 — Environment Variable System
  - `.env.local` — local development (not committed)
  - `.env.development` — development defaults
  - `.env.production` — production defaults
  - `.env.test` — test environment
  - `NEXT_PUBLIC_*` prefix: exposed to client (public)
  - Without prefix: server-only (secret)
  - Runtime vs build-time: `NEXT_PUBLIC_*` are inlined at build time
  - Validation: `@t3-oss/env-nextjs` for type-safe environment variables

---

### 📦 Module 10.4: CI/CD Pipeline

#### § 10.4.1 — GitHub Actions for Next.js
  - Lint: ESLint (`next lint`)
  - Type check: `tsc --noEmit`
  - Test: Vitest, Playwright
  - Build: `next build`
  - Deploy: push to Vercel, build Docker image, or deploy to cloud
  - Preview: comment with preview URL on PRs
  - Caching: cache `node_modules`, `.next/cache` for faster builds

---

### 📦 Module 10.5: Monitoring & Error Tracking

#### § 10.5.1 — Error Tracking
  - **Sentry**: most popular error tracking for Next.js
  - `@sentry/nextjs` — auto-instruments Server Components, Client Components, API Routes
  - Source maps: upload for readable stack traces
  - Error boundaries: catch and report React errors
  - Server Action errors: automatic capture

#### § 10.5.2 — Analytics
  - **Vercel Analytics**: first-party, privacy-focused
  - **PostHog**: product analytics, feature flags, session replay
  - **Plausible**: privacy-focused analytics
  - **Google Analytics**: via `next/script` with `afterInteractive`

#### § 10.5.3 — Monitoring
  - Uptime monitoring: BetterUptime, Checkly, UptimeRobot
  - Performance monitoring: Vercel Speed Insights, Lighthouse CI
  - Log aggregation: Vercel Logs, Datadog, Axiom

---

### 📦 Module 10.6: Security

#### § 10.6.1 — Security Best Practices
  - Environment variables for secrets — never hardcode
  - `NEXT_PUBLIC_*` — be aware of what's exposed to the client
  - Server Actions: always validate, always authorize
  - CSRF: built into Server Actions (origin checking)
  - Content Security Policy (CSP): `next.config.ts` headers
  - Rate limiting: middleware or edge-based
  - Input sanitization: prevent XSS in user-generated content
  - SQL injection: parameterized queries (Prisma handles this)
  - Dependency scanning: `npm audit`, Snyk, Dependabot

#### § 10.6.2 — Security Headers
  - `next.config.ts` → `headers()` function
  - `X-Content-Type-Options: nosniff`
  - `X-Frame-Options: DENY`
  - `X-XSS-Protection: 1; mode=block`
  - `Referrer-Policy: strict-origin-when-cross-origin`
  - `Content-Security-Policy`: script-src, style-src, img-src
  - `Strict-Transport-Security` for HTTPS enforcement

> ### 🛠️ Phase 10 Project: **"TaskMaster v6 — Production Deployed"**
> Deploy TaskMaster to production:
> - **Vercel deployment**: connected to GitHub, auto-deploy on push
> - **Environment variables**: properly configured for dev, preview, production
> - **Docker**: production Dockerfile with standalone output, Docker Compose for self-hosting option
> - **CI/CD**: GitHub Actions pipeline — lint → type check → test → build → deploy
> - **Sentry**: error tracking in both client and server
> - **Analytics**: Vercel Analytics or PostHog for user behavior
> - **Security headers**: CSP, HSTS, X-Frame-Options configured
> - **Environment validation**: `@t3-oss/env-nextjs` for type-safe env vars
> - **Database**: production PostgreSQL (Vercel Postgres, Neon, or Supabase)
> - **Monitoring**: uptime check, performance monitoring
> - **Custom domain**: configured with SSL
> - **Production checklist**: every item verified and documented

---

## ⚡ PHASE 11 — FULL-STACK PATTERNS & ECOSYSTEM
> *"Next.js is not just a frontend framework. It's a full-stack platform."*

---

### 📦 Module 11.1: Full-Stack Architecture Patterns

#### § 11.1.1 — The T3 Stack
  - Next.js + TypeScript + Tailwind + tRPC + Prisma + NextAuth
  - `create-t3-app` — popular full-stack scaffold
  - tRPC: type-safe API layer without REST/GraphQL
  - End-to-end type safety from database to UI

#### § 11.1.2 — Feature-Based Architecture
  - Organize by feature, not by type
  - `app/(features)/projects/` — components, actions, queries, types per feature
  - Shared code in `lib/`, `components/ui/`, `hooks/`
  - Separation: data access layer, business logic, presentation

#### § 11.1.3 — Data Access Layer Pattern
  - Centralize database queries: `data-access/users.ts`
  - Repository functions: `getUserById()`, `createUser()`, `updateUser()`
  - Called from: Server Components, Server Actions, Route Handlers
  - Single source of truth for data access logic (authorization, validation, transformation)
  - Never query the database directly in components — use data access functions

---

### 📦 Module 11.2: File Upload & Storage

#### § 11.2.1 — File Upload Strategies
  - `uploadthing` — file upload for Next.js (simple, popular)
  - Vercel Blob — serverless file storage
  - AWS S3 + presigned URLs — direct upload to S3
  - Cloudinary — image/video management and transformation
  - Server Action for metadata + presigned URL for upload

---

### 📦 Module 11.3: Email

#### § 11.3.1 — Sending Emails
  - `resend` — modern email API (popular in Next.js ecosystem)
  - `react-email` — build emails with React components
  - `nodemailer` — traditional Node.js email library
  - Email templates: React components rendered to HTML
  - Transactional email: welcome, password reset, notifications
  - Server Actions or Route Handlers as email triggers

---

### 📦 Module 11.4: Payments

#### § 11.4.1 — Stripe Integration
  - `stripe` Node.js SDK — server-side payment processing
  - `@stripe/stripe-js` + `@stripe/react-stripe-js` — client-side elements
  - Checkout Session: redirect to Stripe-hosted checkout
  - Payment Intents: custom checkout UI
  - Webhooks: `app/api/webhooks/stripe/route.ts` — handle payment events
  - Subscriptions: recurring billing with Stripe Billing
  - Server Actions for creating checkout sessions
  - Webhook signature verification for security

---

### 📦 Module 11.5: Content Management

#### § 11.5.1 — Headless CMS Integration
  - **Contentful**, **Sanity**, **Strapi** — headless CMS platforms
  - Data fetching: CMS API → Server Components
  - Preview mode: draft content for editors
  - Webhook revalidation: CMS publish → revalidate Next.js pages
  - `next/og` — dynamic Open Graph image generation

#### § 11.5.2 — MDX for Content
  - `@next/mdx` — Markdown with JSX components
  - Blog posts, documentation as MDX files
  - `contentlayer` (legacy) or `velite` — type-safe content management
  - Remote MDX: `next-mdx-remote` — MDX from database/CMS
  - Syntax highlighting: `rehype-pretty-code`, `shiki`

---

### 📦 Module 11.6: Internationalization (i18n)

#### § 11.6.1 — Multi-Language Support
  - `next-intl` — popular i18n library for App Router
  - Locale-based routing: `/en/about`, `/fr/about`
  - Middleware: detect user locale, redirect
  - Server Components: translations loaded server-side
  - Message format: ICU message syntax
  - Locale detection: browser preference, geo-IP, cookie

---

### 📦 Module 11.7: AI Integration

#### § 11.7.1 — Vercel AI SDK
  - `ai` package — build AI features in Next.js
  - `useChat` hook — chat interface
  - `useCompletion` hook — text generation
  - Streaming AI responses to the UI
  - Server Actions for AI operations
  - Providers: OpenAI, Anthropic, Google, Hugging Face, local models
  - Use case: chatbots, content generation, search, summarization

> ### 🛠️ Phase 11 Capstone Project: **"SaaSForge — A Complete SaaS Application"**
> Build a production-grade SaaS application:
> - **Stack**: Next.js + TypeScript + Tailwind + shadcn/ui + Prisma + PostgreSQL
> - **Auth**: NextAuth.js with OAuth (GitHub, Google) + email/password
> - **Core Features** (choose a domain — e.g., project management, invoicing, content platform):
>   - Multi-tenant: workspace/organization support
>   - CRUD for core resources with Server Actions
>   - Real-time updates (SSE or WebSocket)
>   - File upload (uploadthing or Vercel Blob)
>   - Email notifications (Resend + React Email)
> - **Payments**: Stripe Checkout for subscriptions (free, pro, enterprise tiers)
>   - Webhook handling for payment events
>   - Feature gating based on subscription plan
> - **Content**: MDX blog/changelog with syntax highlighting
> - **AI feature**: AI-powered content generation or search (Vercel AI SDK)
> - **i18n**: support for 2 languages (English + one more)
> - **Dashboard**: analytics with charts (Recharts or Tremor)
> - **Architecture**:
>   - Feature-based organization
>   - Data access layer pattern
>   - Type-safe environment variables
>   - Zod validation on all inputs
> - **Quality**:
>   - Vitest unit tests, Playwright E2E tests
>   - Sentry error tracking
>   - Vercel Analytics
>   - 90+ Lighthouse score
> - **Deployment**: Vercel with preview deployments, custom domain, production database
> - **Documentation**: README with architecture diagram, setup guide, contributing guide

---

## 📊 PHASE MAP (Visual Summary)

```
Phase 0   ██░░░░░░░░░░░░░░░░  Prerequisites (JS, TS, React)
Phase 1   ████░░░░░░░░░░░░░░  Routing & Navigation (App Router)
Phase 2   ██████░░░░░░░░░░░░  Server Components & Client Components
Phase 3   ████████░░░░░░░░░░  Data Fetching & Caching
Phase 4   █████████░░░░░░░░░  Server Actions & Mutations
Phase 5   ██████████░░░░░░░░  Styling & UI (Tailwind, shadcn/ui)
Phase 6   ███████████░░░░░░░  Authentication & Authorization
Phase 7   ████████████░░░░░░  Performance Optimization
Phase 8   █████████████░░░░░  State Management & Advanced Patterns
Phase 9   ██████████████░░░░  Testing (Vitest, Playwright)
Phase 10  ███████████████░░░  Deployment & Production
Phase 11  ████████████████░░  Full-Stack Patterns & Ecosystem
```

---

## 🎯 DIFFICULTY & SKILL PROGRESSION

```
       BEGINNER              INTERMEDIATE              ADVANCED                 EXPERT
    ┌────────────┐        ┌────────────────┐       ┌──────────────┐       ┌──────────────┐
    │  Phase 0   │───────▶│    Phase 3     │──────▶│   Phase 7    │──────▶│   Phase 10   │
    │  Phase 1   │        │    Phase 4     │       │   Phase 8    │       │   Phase 11   │
    │  Phase 2   │        │    Phase 5     │       │   Phase 9    │       │              │
    │            │        │    Phase 6     │       │              │       │              │
    └────────────┘        └────────────────┘       └──────────────┘       └──────────────┘
    "I can build           "I build full-stack      "I build performant,   "I architect
     Next.js pages          apps with auth,          tested, production-    production SaaS
     with routing"          data, and styling"       ready applications"    applications"
```

---

## ⚠️ THE EVOLVING TASKMASTER PROJECT

```
Phase 4:   TaskMaster v1 — Full-stack with Server Actions
Phase 5:   TaskMaster v2 — Beautiful UI with shadcn/ui
Phase 6:   TaskMaster v3 — Multi-user with authentication
Phase 7:   TaskMaster v4 — Performance optimized
Phase 9:   TaskMaster v5 — Fully tested
Phase 10:  TaskMaster v6 — Production deployed
Phase 11:  SaaSForge     — Complete SaaS application
```

> **One project, seven iterations.** Each phase adds a new dimension of production readiness.

---

## 📚 RECOMMENDED RESOURCES

| Resource | Type | Phase |
|----------|------|-------|
| **Next.js Official Docs** (nextjs.org/docs) | 🌐 Official (START HERE) | ALL |
| **Next.js Learn** (nextjs.org/learn) | 🌐 Interactive Course | 0–5 |
| **React.dev** (react.dev) | 🌐 React Docs | 0 |
| **Total TypeScript** — Matt Pocock | 🌐 TypeScript Course | 0 |
| *Next.js in Action* — upcoming titles | 📖 Book | ALL |
| *Fullstack React with TypeScript* | 📖 Book | 0 |
| **Theo — t3.gg** (YouTube) | 🎥 Video (Opinions + Ecosystem) | ALL |
| **Lee Robinson** (YouTube) | 🎥 Video (Vercel VP, Next.js core) | ALL |
| **Jack Herrington** (YouTube) | 🎥 Video (Advanced Patterns) | 2–8 |
| **Web Dev Simplified** (YouTube) | 🎥 Video (Fundamentals) | 0–4 |
| **Josh tried coding** (YouTube) | 🎥 Video (Full-Stack Projects) | 4–11 |
| **Vercel Templates** (vercel.com/templates) | 🧪 Starter Projects | ALL |
| **shadcn/ui Docs** (ui.shadcn.com) | 📄 Component Library | 5 |
| **Prisma Docs** (prisma.io/docs) | 📄 ORM | 3–4 |
| **Auth.js Docs** (authjs.dev) | 📄 Authentication | 6 |
| **Playwright Docs** (playwright.dev) | 📄 E2E Testing | 9 |
| **Sentry Next.js Docs** | 📄 Error Tracking | 10 |

---

## 🗺️ WHERE NEXT.JS TAKES YOU (Career Paths)

```
                                  ┌───────────────────────────┐
                                  │   Full-Stack Developer    │
                           ┌─────▶│   (SaaS, Web Apps,        │
                           │      │    Internal Tools)         │
                           │      └───────────────────────────┘
                           │      ┌───────────────────────────┐
                           │      │   Frontend Engineer       │
                   ┌───────┤─────▶│   (React Specialist,      │
                   │       │      │    Design Systems, UI)     │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
   ┌────────────┐  │       │      │   Indie Hacker / Solopreneur│
   │            │  │       ├─────▶│   (Ship SaaS products      │
   │  Master    ├──┤       │      │    end-to-end, alone)      │
   │  Next.js   │  │       │      └───────────────────────────┘
   │            │  │       │      ┌───────────────────────────┐
   └────────────┘  │       │      │   Jamstack / Content      │
                   │       ├─────▶│   Engineering              │
                   │       │      │   (CMS, Blogs, Marketing)  │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
                   │       │      │   AI / LLM Application    │
                   └───────┴─────▶│   Developer               │
                                  │   (AI-powered web apps)    │
                                  └───────────────────────────┘
```

---

> ### 💡 Final Advice
> **"Next.js evolves fast. The mental model matters more than the API. Understand WHY things work, not just HOW."**
>
> Five non-negotiable rules for your Next.js journey:
>
> 1. **Understand Server Components deeply.** This is the single biggest mental model shift. Every component is a Server Component by default. `"use client"` is the exception, not the rule. If you're putting `"use client"` everywhere, you're writing React, not Next.js.
>
> 2. **Stop using `useEffect` for data fetching.** In Next.js, data fetching happens in Server Components with `async/await`. No `useEffect`, no loading state management, no client-side waterfalls. `useEffect` is for browser-side effects only (DOM manipulation, subscriptions, third-party widgets).
>
> 3. **TypeScript is mandatory.** The Next.js ecosystem assumes TypeScript. shadcn/ui, Prisma, tRPC, Zod, Auth.js — everything is TypeScript-first. Starting without TypeScript is starting wrong.
>
> 4. **Master the caching model.** Next.js's caching is powerful but complex. Understand: Request Memoization, Data Cache, Full Route Cache, Router Cache. Know how to opt in and out. Most bugs in Next.js apps are caching bugs.
>
> 5. **Ship early, ship often.** Next.js + Vercel makes deployment trivial. Deploy on day one. Every PR gets a preview URL. Don't wait for "done" — deploy continuously and iterate.
>
> The difference between a *Next.js developer* and a *Next.js engineer* is:
> - **Understanding the rendering model** (when is static, when is dynamic, why)
> - **Composing Server and Client Components correctly** (minimal `"use client"`, maximum server rendering)
> - **Caching mastery** (knowing when data is stale and how to revalidate)
> - **Full-stack thinking** (database to browser in one framework, one language, one deploy)

---

*This roadmap takes you from "What's SSR?" to "I can architect, build, test, and deploy production-grade full-stack SaaS applications — with authentication, payments, real-time features, AI integration, and perfect Lighthouse scores — all in Next.js."* ▲🚀