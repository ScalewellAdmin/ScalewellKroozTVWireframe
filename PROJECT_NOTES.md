# KroozTV Redesign — Project Notes

## Brand system (locked)
- **Mode:** Light-mode first. Page `#F6F6F7`, surface `#FFFFFF`, ink `#14141A`, muted `#71717A`, border `#E6E6EA`.
- **Primary:** Signal Orange `#FF6A2C` (press `#F2540B`, tint `#FF9159`). Accent gradient `#FF9159 → #F2540B`.
- **Fonts:** Display = Clash Display (Fontshare); Body/UI = Satoshi (Fontshare).
- **Logo:** "Krooz" ink + "TV" orange wordmark; orange TV-screen mark with play glyph (favicon/app icon); tagline **TOP RATED IPTV** in letter-spaced caps beneath. Reversed (white) lockup for dark bands.
- Files: `KroozTV Brand System.dc.html`, `KroozTV Brand Motifs.dc.html` (14 motifs), `KroozTV Pricing.dc.html`, `KroozTV All Wireframes.dc.html` (master explorer: 9 pages + Motifs / Brand System / Hero ×3).

## Pricing (real matrix — 4 terms × 5 connections)
| Conn | 1mo | 3mo | 6mo | 12mo |
|---|---|---|---|---|
|1|$15|$30|$55|$85|
|2|$22|$40|$65|$100|
|3|$28|$50|$75|$115|
|4|$35|$60|$85|$125|
|5|$45|$70|$95|$140|
- UI: 4 cards + connections dropdown (live price / per-month / savings% / WHMCS link). **6-Month = visual hero (Most Popular)**; 12-Month standard. No money-back line.

## SEO
- Keep `<h1>` = **"The Best IPTV Subscription Provider"** (exact-match keyword); brand line "Everything You Love. One Subscription." as visual H2/eyebrow.

## Client web stack — deliver a STATIC frontend theme/template that drops into this
- **WordPress** + **Elementor 3.26.2** + **Kadence theme 1.2.14** + **Yoast SEO Premium 27.8**.
- **Crisp Live Chat** (website_id `e06f97ef-e8cc-4aa7-a45b-863fc4d6ca01`) — keep existing embed; "24/7 / contact" CTAs open Crisp.
- **particles.js** already in stack → reuse it for the globe/particle hero (no new dependency).
- **Google Analytics / Site Kit 1.181.0** + **Statcounter** — keep tracking scripts in layout.
- **LiteSpeed** cache + **HTTP/3** + jQuery/jQuery Migrate + PHP/MySQL.

### Integration rules
- Do **not** hardcode `<head>` titles/meta — leave to **Yoast** (provide recommended values as reference only, overridable).
- Build sections so they can map to **Kadence/Elementor blocks** OR ship as clean standalone HTML/CSS — confirm preferred path with client.
- Commerce stays in **WHMCS**: plan CTAs → `/billing/store/<term>/<n>connection-iptv`; sign-in → `/billing/login`.
- Keep dependencies light (LiteSpeed-cache friendly); avoid render-blocking; reuse jQuery/particles.js already present.
