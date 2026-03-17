# CLAUDE.md — BidDeed.AI Landing Page

## IDENTITY
You are the AI Engineer for the BidDeed.AI landing page. Single-file static site with 3D animations deployed to GitHub Pages → future Cloudflare Pages at biddeed.ai.

## REPO
- GitHub: breverdbidder/biddeed-landing
- Live Preview: https://breverdbidder.github.io/biddeed-landing/
- Production (future): https://biddeed.ai

## BRAND (MANDATORY)
- Primary: Navy #1E3A5F
- Accent/CTA: Orange #F59E0B
- Font: Space Grotesk (display) + JetBrains Mono (code)
- Background: #020617 (slate-950)
- Text: #E2E8F0 | Muted: #94A3B8
- NEVER deviate from these colors

## ARCHITECTURE
Single `index.html` — embedded CSS, Three.js r128 CDN for 3D exploding house, vanilla JS for scroll animations, particle network BG, counters, split-screen preview. Zero build step.

## KEY SECTIONS
1. Hero: 3D exploding house wireframe + radial gradient overlay
2. Stats Bar: Animated counters (10+ years, 1393 auctions, 12-stage, 64.4% ML)
3. Split-Screen Demo: Chat left + Report right (mock UI)
4. Features: Lien Discovery, ML Bids, One-Click Reports
5. Pipeline: 12-stage visual flow
6. CTA: Email capture
7. Footer: BidDeed.AI + Everest Capital USA

## 3D ASSET INTEGRATION (when Kling 3.0 videos arrive)

### Hero Video Replace Wireframe
1. Compress: `ffmpeg -i hero.mp4 -vcodec libx264 -crf 28 -preset slow -vf scale=1920:-2 -an hero_compressed.mp4` (target <500KB)
2. Replace Three.js canvas with `<video autoplay muted loop playsinline>`
3. Keep `.hero-overlay` radial gradient mask

### Scroll-Driven Frame Animation
1. Extract: `ffmpeg -i scroll.mp4 -vf fps=24 -q:v 2 frames/frame_%04d.jpg`
2. Map scroll position → frame index, preload first 10
3. Insert between Split-Screen Demo and Features sections

## SESSION RULES
- MANDATORY: Context7 + CC Status Line plugins
- 50% context → kill session, never /compact
- Commit+push after every change (Pages auto-deploys)
- $10/session MAX

## PRIORITY QUEUE
1. [ ] Integrate Kling 3.0 hero video (exploding house)
2. [ ] Add scroll-driven map pin-drop animation
3. [ ] Connect email CTA to Supabase waitlist
4. [ ] OG image + Twitter cards
5. [ ] Lighthouse 95+
6. [ ] Deploy to Cloudflare Pages (production)
