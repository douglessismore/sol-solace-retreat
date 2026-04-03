# El Salto Sagrado — Session Handoff

**Date:** April 3, 2026 (updated)
**Project:** Sol Solace Studio retreat landing page + ad campaign
**Repo:** github.com/douglessismore/sol-solace-retreat
**Live site:** retreat.solsolacestudio.com
**Ad cheat sheet:** retreat.solsolacestudio.com/ad-campaign-cheatsheet.html (password: solsolace)

---

## Current State

### Landing Page — LIVE
- Luxury Cabin Square payment link updated to Sol Solace business location (was personal Monica Castillo account)
- Luxury Cabin now shows "Only 2 left" (1 sold Apr 2-3)
- Availability banner: "2 Luxury Cabins · Commuter Passes Available"
- Field Cabin marked SOLD OUT (grayed card, diagonal banner, disabled button)
- Meta Pixels installed: austinrevolt (431558461968055) + Doug Stienstra (629633540407763)
- Early bird sold-out pricing visually shrunk (75% scale, low opacity) so active prices dominate

### Square Payment Links
- **Luxury Cabin ($1,250):** https://square.link/u/cidSxf0W — Sol Solace location (FIXED Apr 3)
- **Commuter Pass ($675):** https://square.link/u/xwM3x16G — STILL POINTING TO MONICA CASTILLO PERSONAL ACCOUNT. Needs new link created under Sol Solace location.
- First luxury cabin sale came through on Monica's personal Square account (wrong location). Transaction needs manual reconciliation.

### Meta Ads Campaign — LIVE & ACTIVE
- Campaign: "El Salto Sagrado - Spring Retreat"
- Account spending limit: **$500** (raised from $250 on Apr 2)
- Total budget: **$45/day** ($30 original + $15 retargeting)

**Ad Set 1: "Warm - IG Engagers + Website Visitors"** — $30/day
- Targeting: Austin TX + 50mi, Women 25-55, interests (wellness, meditation, yoga, personal development, well-being)
- 3 ads: The Pause, Availability, The Setting (each with Story + Feed images)
- Availability ad has outdated image ("3 luxury cabins · 1 field cabin") — should be paused

**Ad Set 2: "Retargeting - Website + IG Engagers"** — $15/day (NEW, created Apr 1)
- Targeting: Custom audiences (Retreat Page Visitors 14 days + IG Engagers 90 days), Austin TX + 50mi, Women 25-55, Advantage+ audience
- 1 ad: "Retarget - Only 2 Left" using The Setting images
- Copy: "Only 2 luxury cabins remain for El Salto Sagrado..." with "Book now" CTA
- Audience is small (<1,000) — may deliver slowly
- Some Meta enhancements may be pulling in other creative (Availability image seen in preview). Tried to disable but Meta UI makes it difficult. Left as-is.

### Performance
- Day 1-2 (Mar 28-29): 129 landing page views at $0.31/view ($39.70 spent)
- The Setting: best performer at $0.22/view
- The Pause: $0.34/view, getting most budget
- Availability: worst at $0.38/view — recommend pausing
- Retargeting ad set: $0 spent as of Apr 2 (audience too small to deliver, or still populating)
- **1 luxury cabin SOLD** (came through on wrong Square account)

---

## Key Decisions Made (and Why)

### Pricing structure
- **All-inclusive cabin links** chosen over separate base+addon purchases. Rhiann pre-calculated 13% lodging tax on accommodation portion only and baked it into the Square item price.
- **Pre-tax prices shown on landing page** ($1,100 / $1,250) with "Plus 13% lodging tax" note.

### Ad campaign approach
- **Manual targeting for original ad set** because: hyper-local event, small budget, niche audience, no conversion history.
- **Advantage+ audience for retargeting ad set** — custom audiences are the primary filter, Advantage+ extends reach if Meta finds similar people.
- **Traffic objective** because no purchase conversion tracking is set up.
- **"Learn more" CTA for cold audience**, **"Book now" CTA for retargeting** (warm audience).
- **Translate text left on** for Spanish-speaking Austin audience. All other AI enhancements should be off (some may have persisted due to Meta UI complexity).

### Square payment link fix
- First sale came through on Monica Castillo personal location instead of Sol Solace business location. Luxury cabin link was recreated under Sol Solace. Commuter pass link still needs fixing.

### LinkedIn assessment (Apr 3)
- LinkedIn ads: NOT recommended. 2-3x cost of Meta, targeting is job/industry focused not wellness, wrong mindset for retreat buyers.
- LinkedIn organic: NOT useful for this retreat (8 days out, 46 connections, stale profile). Useful long-term for Monica's personal brand as a practitioner.
- Recommendation: update Monica's personal LinkedIn profile (not a business page) to reflect Sol Solace, connect with Austin wellness community, post 1-2x/week. Profile rewrite offered but not yet done — needs screenshot of current profile.

### What was rejected
- Advantage+ audience for cold targeting — too broad for local event with small budget
- AI-generated image variations — off-brand, generic wellness stock
- AI text variations — "Ready to slow down?" / "LAST CHANCE!" / "sauna bliss" don't match brand voice
- "You looked. Something resonated." retargeting opener — felt creepy/surveillance-y, dropped in favor of leading with scarcity
- Em dashes in ad copy — flagged as AI writing tell
- "Not a spa, a threshold" and "sacred pause" copy — flagged as cheesy by Douglas
- LinkedIn ads for this retreat — wrong platform, wrong timeline, wrong cost

---

## Open Questions

1. **Commuter pass Square link** still points to Monica Castillo personal account. Monica/Rhiann need to create new Payment Link under Sol Solace location and send URL for update.
2. **Day pass** — Monica wants to add a new day pass option. Need details (name, price, description) + Square Payment Link to add to landing page.
3. **Retargeting ad delivery** — audience may be too small to deliver meaningfully. Monitor for another 24h; if still $0 spent, consider widening audience window or reallocating budget.
4. **Availability ad** should be paused (outdated image, worst performer).
5. **First sale reconciliation** — luxury cabin purchase on Monica's personal Square. Needs manual handling (leave it or refund/re-charge through Sol Solace).
6. **Pixel mismatch** — austinrevolt pixel still not connected to ad account.

---

## Immediate Next Steps

1. **Pause Availability ad** in the original ad set (outdated image + worst performer)
2. **Fix Commuter pass Square link** — Monica creates new link under Sol Solace location
3. **Add Day Pass** to landing page when details are ready
4. **Monitor retargeting ad** — check if it starts delivering by Apr 4
5. **Update landing page** when more luxury cabins sell (change count, eventually mark sold out)
6. **LinkedIn profile rewrite** for Monica (long-term, not retreat-urgent) — send screenshot to start

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
