# CLAUDE.md — BidDeed.AI Landing Page

## Project
BidDeed.AI marketing landing page with 3D exploding house wireframe, 12-stage pipeline visualization, split-screen chat+report preview, and scroll-driven animations.

## Brand (MANDATORY)
- Primary: Navy `#1E3A5F`
- Accent/CTA: Orange `#F59E0B`
- Font: Space Grotesk (display) + JetBrains Mono (code/data)
- Background: `#020617` (slate-950)
- Text: `#E2E8F0` (slate-200)
- BID: `#16A34A` (green) | REVIEW: `#D97706` (amber) | SKIP: `#DC2626` (red)
- Reference: BRAND_COLORS.md in biddeed-ai repo

## Architecture
- Single `index.html` file (self-contained HTML/CSS/JS)
- Three.js r128 for 3D exploding house wireframe (CDN loaded)
- CSS scroll-driven reveals + IntersectionObserver
- Dynamic pipeline stage animation (12 stages with sequential activation)
- Zero build step — static file deployment

## Key Sections
1. **Hero**: Three.js exploding wireframe house (base, walls, roof, interior rooms separate on scroll), left-aligned text, particle field background
2. **Stats Bar**: Animated counters (10+ years, 1,300+ auctions, 12 stages, 78K+ parcels)
3. **Split-Screen Preview**: Live chat pane (left) + auction report pane (right) showing BID/REVIEW/SKIP cards with real data examples
4. **Pipeline Visualization**: 12 horizontal stages with sequential glow animation (Discovery → Scraping → Title → Lien Priority → Tax Certs → Demographics → ML Score → Max Bid → Decision Log → Report → Disposition → Archive)
5. **Features Grid**: 6 cards (Lien Discovery, ML Predictions, One-Click Reports, Tax Certs, Demographics, Risk Detection)
6. **How It Works**: 3-step flow (Upload → AI Analyzes → Get BID/REVIEW/SKIP)
7. **CTA**: Email capture with gradient card
8. **Footer**: BidDeed.AI + Everest Capital USA

## Enhancement Priorities (for Claude Code sessions)
1. **Kling 3.0 Video Integration**: Replace Three.js hero with exploding house video background + gradient mask. Add scroll-driven JPEG frame extraction for map pin drop animation between features and CTA.
2. **Data Pipeline Animation**: Add a data-flow canvas animation showing glowing particles moving through the 12 pipeline stages.
3. **Performance**: Compress everything, lazy-load split preview, target Lighthouse 90+.
4. **Mobile**: Stack split-screen to vertical, collapse pipeline to vertical stepper, touch-friendly.
5. **Chat Demo**: Add typing animation to chat messages, sequential reveal on scroll intersection.

## Deployment
- **Preview**: GitHub Pages — `breverdbidder.github.io/biddeed-landing/`
- **Production**: Cloudflare Pages — `biddeed.ai` (DNS on Cloudflare)
- **CI**: Push to `main` auto-deploys to GitHub Pages. CF Pages connects to same repo.

## Session Hygiene
- MANDATORY plugins: Context7 + CC Status Line
- Kill session at 50% context. NEVER /compact.
- Cost discipline: $10/session MAX. ONE attempt per approach.

## Testing
- Open in browser, verify exploding house renders, pipeline stages animate sequentially
- Check split-screen preview renders both panes
- Verify BID/REVIEW/SKIP color coding matches brand spec
- Mobile viewport (375px width)
- No console errors
- Lighthouse: Performance ≥ 90, Accessibility ≥ 90

## DO NOT
- Change brand colors or BID/REVIEW/SKIP color scheme
- Add npm/build dependencies — single static HTML file
- Use Inter, Roboto, or Arial fonts
- Remove any auction data examples from the split-screen preview
- Break the Three.js wireframe or pipeline animation
