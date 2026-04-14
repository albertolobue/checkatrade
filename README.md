# Checkatrade Growth Strategy — Vercel deploy folder

Single-page static site. Just `index.html` + a tiny `vercel.json`.

## Fastest path — one command

Open Terminal, then:

```bash
cd ~/Documents/Checkatrade/vercel_deploy
npx vercel
```

The CLI will:

1. Ask you to log in (opens your browser, sign in with GitHub / Google / email — whichever matches your Vercel account)
2. Ask "Set up and deploy?" → press Enter (yes)
3. Ask which scope → pick your personal account
4. Ask "Link to existing project?" → N
5. Ask project name → accept the default, or type something like `checkatrade-growth-strategy`
6. Ask directory → press Enter (`.` current directory)
7. Ask to override settings → N

It prints a **Preview URL** — that's the shareable link. Example:
`https://checkatrade-growth-strategy-abc123.vercel.app`

To promote to a permanent production URL:

```bash
npx vercel --prod
```

That prints the production URL (no hash suffix, e.g. `https://checkatrade-growth-strategy.vercel.app`). That's the one to share.

## What's in `vercel.json`

- `X-Robots-Tag: noindex, nofollow` — tells Google et al not to index the page, so it won't show up in search results
- `cleanUrls: true` — lets the URL work both with and without `.html`
- `Cache-Control: must-revalidate` — changes show up immediately when you redeploy

## If you want password protection

Vercel's Deployment Protection (password-gating) is a Pro feature (~$20/mo). If that matters, say the word and I'll suggest a free alternative (e.g. a simple client-side gate or host on Netlify with a basic password via a tiny function).

## To update later

Edit the original `Checkatrade_Growth_Strategy.html` in the parent folder, then:

```bash
cp ~/Documents/Checkatrade/Checkatrade_Growth_Strategy.html ~/Documents/Checkatrade/vercel_deploy/index.html
cd ~/Documents/Checkatrade/vercel_deploy
npx vercel --prod
```

Same URL, new content.
