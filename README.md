# Boostberry Digital website

React + TypeScript + Vite, React Router, plain CSS, Lucide icons. Seven routes: `/ /services /work /about /pricing /faq /contact` plus a 404 page.

## Run locally
```
npm install
npm run dev        # http://localhost:5173
npm run build      # production build into dist/
npm run preview
```

## Enquiry form (NOT connected yet)
Until you add a real endpoint the form validates but does **not** send anything. It tells the visitor so and points them to WhatsApp.
1. Create a free account at formspree.io, make a form, set the notification email, and copy its endpoint (`https://formspree.io/f/xxxxxxxx`). Check current free-plan limits on their pricing page.
2. Set `VITE_FORM_ENDPOINT` in a local `.env` and in Vercel → Project → Settings → Environment Variables.
3. Redeploy, submit a test enquiry, and confirm it appears in the dashboard and your inbox.
Spam protection: a hidden honeypot field is included; enable Formspree's own spam filtering/reCAPTCHA in its dashboard if needed.

## Logo and images
Logo: `src/assets/boostberry-logo.png` (an 900px resized copy of your original, unaltered otherwise). The full-size original is `src/assets/boostberry-logo-original.png`. Favicon: `public/favicon.png`. Replace the files keeping the same names.
Our Work: replace the "Concept Preview" cards in the `Work` function in `src/pages/Pages.tsx` with real projects when available.

## Domain, canonical URL and sitemap
Set `VITE_SITE_URL` (e.g. `https://yourdomain.com`, no trailing slash) in `.env` and in Vercel. `npm run build` regenerates `public/sitemap.xml` and `public/robots.txt`, and canonical/Open Graph/schema URLs use it. Until set, a placeholder (`your-domain.example`) is used.

## Deploy to Vercel via GitHub
1. Push this folder to a GitHub repo (`.env` is git-ignored).
2. In Vercel: Add New → Project → import the repo. Framework: Vite; build `npm run build`; output `dist`.
3. Add the two environment variables, then Deploy. `vercel.json` rewrites routes so refreshes work.
4. Custom domain: Project → Settings → Domains → add it and follow the DNS instructions; then update `VITE_SITE_URL` and redeploy.

## Needs your confirmation
- Privacy notice on `/contact#privacy` is a draft; review it and the form provider.
- Budget ranges in the form are illustrative INR ranges, not your prices.
- No analytics are included. Add one later via an optional script and update the privacy notice.
