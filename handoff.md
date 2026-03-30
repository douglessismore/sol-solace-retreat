# El Salto Sagrado — Session Handoff

**Date:** March 29, 2026 (updated)
**Project:** Sol Solace Studio retreat landing page + ad campaign
**Repo:** github.com/douglessismore/sol-solace-retreat
**Live site:** retreat.solsolacestudio.com
**Ad cheat sheet:** retreat.solsolacestudio.com/ad-campaign-cheatsheet.html (password: solsolace)

---

## Current State

### Landing Page — LIVE
- All Square payment links wired up (all-inclusive cabin pricing with 13% lodging tax baked in)
- Meta Pixels installed: austinrevolt (431558461968055) + Doug Stienstra (629633540407763)
- Field Cabin marked SOLD OUT (grayed card, diagonal banner, disabled button)
- Luxury Cabin has "Only 3 left" urgency badge (pulsing coral)
- Early bird sold-out pricing visually shrunk (75% scale, low opacity) so active prices dominate
- Availability banner updated: "Field cabins are sold out. Only a few spots remain: 3 Luxury Cabins · Commuter Passes Available"

### Meta Ads Campaign — LIVE & ACTIVE
- Campaign: "El Salto Sagrado - Spring Retreat"
- 1 ad set: "Warm - IG Engagers + Website Visitors"
- Budget: $30/day, Mar 27 – Apr 9, 2026
- Targeting: Austin TX + 50mi, Women 25-55, interests (wellness, meditation, yoga, personal development, well-being)
- 3 ads: The Pause, Availability, The Setting (each with Story + Feed images)
- Tracking: Doug Stienstra's Pixel (629633540407763) — matches landing page
- Placements: Advantage+ (Meta decides, will lean IG based on creative format)
- Account spending limit: $250 (will cap around day 8 at $30/day — may need increase)

### Day 1-2 Performance (as of Mar 28-29)
- **129 landing page views** at $0.31/view ($39.70 spent)
- **The Setting:** 42 views, $0.22/view — BEST PERFORMER
- **The Pause:** 76 views, $0.34/view — getting most budget from Meta
- **Availability:** 11 views, $0.38/view — WEAKEST, consider pausing
- No purchases yet — expected for $675-$1,250 price point from cold audience
- Recommendation: pause Availability ad, let budget concentrate on winners

### Ad Creative Assets — READY
- 6 ad images in `/ads/` (1080px exact Meta specs, no CTA buttons baked in)
- 7 giveaway story slides in `/ads/stories/` (cream/teal alternating carousel)
- All images have text overlay with Sol Solace branding
- Ad copy in AD-CAMPAIGN.md (character-validated against Meta specs)
- Styled cheat sheet at `/ad-campaign-cheatsheet.html` with inline images per angle

---

## Key Decisions Made (and Why)

### Pricing structure
- **All-inclusive cabin links** chosen over separate base+addon purchases. Rhiann pre-calculated 13% lodging tax on accommodation portion only and baked it into the Square item price. This avoids Square taxing the full amount at checkout.
- **Pre-tax prices shown on landing page** ($1,100 / $1,250) with "Plus 13% lodging tax" note. Industry standard — lower sticker price improves conversion.

### Ad campaign approach
- **Manual targeting over Advantage+** because: hyper-local event (Austin area), small budget ($30/day needs concentration), niche audience, no conversion history for algorithm to learn from.
- **1 ad set instead of planned 2** because the custom audience (IG engagers, website visitors) was too small (<1,000). Pivoted to interest-based targeting at $30/day.
- **Traffic objective over Sales** because no purchase conversion tracking is set up (Pixel just installed, no conversion events configured). Traffic optimizes for landing page views.
- **"Learn more" CTA over "Book now"** because cold audience hasn't seen the retreat yet. Learn more gets higher CTR; the landing page does the selling.
- **Translate text left on** for Spanish-speaking Austin audience. All other AI enhancements turned off.

### What was rejected
- Advantage+ audience — too broad for local event with small budget
- AI-generated image variations — off-brand, generic wellness stock
- AI text variations — "Ready to slow down?" style copy doesn't match brand voice
- "Book now" CTA — too aggressive for cold audience
- Scarcity angle with negative framing ("Early bird is gone") — Monica found it negative. Reframed as "A few spots are still open."
- Em dashes in ad copy — flagged as AI writing tell, replaced with periods/commas
- "Not a spa, a threshold" and "sacred pause" copy — flagged as cheesy by Douglas

### Skills used
- [paid-ads](https://github.com/coreyhaines31/marketingskills/tree/main/skills/paid-ads) — campaign structure, audience targeting, budget allocation, optimization metrics
- [ad-creative](https://github.com/coreyhaines31/marketingskills/tree/main/skills/ad-creative) — copy generation, character validation, platform specs, creative testing priority

---

## Open Questions

1. **Account spending limit is $250** — campaign is $30/day x 14 days = $420. Will cap around day 8. Monica needs to increase the limit or accept the cap.
2. **Pixel mismatch** — austinrevolt pixel (431558461968055) is not connected to the ad account. Both pixels fire on the landing page, but the ad account uses Doug Stienstra's pixel. To fix: Business Settings → Data Sources → Pixels → austinrevolt → Connected Assets → add ad account.
3. **IG engagers custom audience** — needs to be created in Meta Ads Manager (Audiences → Create → Custom → Instagram account → People who engaged with account in last 90 days). Once created and populated, can be added as a second ad set.
4. **Giveaway story slides** — 7 slides ready in `/ads/stories/`. Slide 7 has "[DATE TBD]" for winner announcement date. Monica needs to set this.
5. **Giveaway "Comment READY" flow** — when people comment READY, someone needs to reply fast with the retreat link. This is the conversion engine.
6. **Ad copy references "1 field cabin"** — the Availability ad still mentions field cabin availability. Should be updated in Ads Manager since it's now sold out.

---

## Immediate Next Steps

1. **Day 1-2:** Confirm ads approved and delivering in Ads Manager
2. **Day 3-4:** Check performance — kill any ad with CTR < 0.8% or CPC > $3
3. **Increase spending limit** if Monica wants full 14-day run at $30/day
4. **Post giveaway slides** on IG when ready (stories folder has all 7)
5. **Create IG engagers audience** for potential second ad set
6. **Update Availability ad** in Ads Manager to remove field cabin mention
7. **Update landing page** when luxury cabins sell (change "Only 3 left" count, eventually mark sold out)

---

## File Structure

```
sol-solace/
├── index.html              — Landing page (live on Netlify)
├── AD-CAMPAIGN.md          — Full campaign plan + copy (reference doc)
├── ad-campaign-cheatsheet.html — Styled handoff for ad assistant (password-protected)
├── ad-generator.html       — Preview page for all 6 ads side by side
├── SETUP.md                — Original setup guide for Monica
├── handoff.md              — This file
├── images/                 — Serana property photos (hero, img1-6)
├── ads/
│   ├── ad1-pause-story.png     — The Pause, 1080x1920
│   ├── ad2-pause-feed.png      — The Pause, 1080x1080
│   ├── ad3-scarcity-story.png  — Availability, 1080x1920
│   ├── ad4-scarcity-feed.png   — Availability, 1080x1080
│   ├── ad5-setting-story.png   — The Setting, 1080x1920
│   ├── ad6-setting-feed.png    — The Setting, 1080x1080
│   ├── *.html                  — Source files for each ad image
│   └── stories/
│       ├── slide1-hook.png through slide7-urgency.png
│       └── *.html              — Source files for each slide
└── .claude/
    └── launch.json             — Dev server configs
```
