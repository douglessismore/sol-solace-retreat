# El Salto Sagrado — Landing Page Setup Guide

Everything you need to get the retreat page live and accepting payments.

---

## 1. Square Payment Links (for booking buttons)

The page has "Book Now" buttons for each pricing tier. Each button needs a Square Payment Link — a hosted checkout page that Square provides. Here's how to create them:

### Steps:

1. **Log in to Square Dashboard** at [squareup.com/dashboard](https://squareup.com/dashboard)
2. Go to **Online** > **Online Checkout** (or search "Checkout Links" in the dashboard)
3. Click **Create a Checkout Link**
4. For each pricing tier, create a link:

| Link Name                        | Price    | Notes                           |
|----------------------------------|----------|---------------------------------|
| El Salto Sagrado — Base (Early Bird)    | $595     | Add note: "Commuter / Early Bird" |
| El Salto Sagrado — Base (Standard)     | $675     | Add note: "Commuter / Standard"  |
| El Salto Sagrado — Luxury Cabin (Early Bird) | $1,070   | Add note: "Base + Luxury Cabin / Early Bird" |
| El Salto Sagrado — Luxury Cabin (Standard)  | $1,250   | Add note: "Base + Luxury Cabin / Standard" |
| El Salto Sagrado — Field Cabin (Early Bird)  | $920     | Add note: "Base + Field Cabin / Early Bird" |
| El Salto Sagrado — Field Cabin (Standard)   | $1,100   | Add note: "Base + Field Cabin / Standard" |

5. For each link, under **Settings**:
   - Enable **"Collect buyer name"** and **"Collect email"**
   - Optionally add a custom field: "Any dietary restrictions or needs?"
   - Set a redirect URL (optional): back to the landing page with a thank-you anchor
6. Click **Create Link** for each one
7. **Copy each URL** — they'll look like: `https://square.link/u/XXXXXXXX`

### Once you have the links:

Send me the 6 URLs and I'll plug them into the page buttons. Or if you're comfortable editing HTML, find the lines that say:

```html
<a href="#" class="pricing-card__cta" data-booking="base">Book Now</a>
```

Replace `#` with the Square link URL for each tier.

**Simplification option:** If early bird pricing is almost gone, we can simplify to just 3 links (one per accommodation type at standard pricing) and show early bird as "contact to check availability."

---

## 2. Deploy to Netlify

### Option A: Quick deploy (drag and drop)

1. Go to [app.netlify.com](https://app.netlify.com) and sign up / log in (free)
2. On the dashboard, look for the **"Deploy manually"** section
3. Drag the entire `sol-solace` project folder onto the drop zone
4. Done! Netlify gives you a URL like `https://random-name-12345.netlify.app`

### Option B: Git-based deploy (recommended for updates)

1. Push this project to a GitHub repository
2. In Netlify, click **"Import from Git"**
3. Connect your GitHub account and select the repo
4. Deploy settings: leave defaults (no build command needed, publish directory is `/`)
5. Click **Deploy**
6. Every time you push changes to GitHub, Netlify auto-deploys

---

## 3. Custom Domain Setup (`retreat.solsolacestudio.com`)

After deploying to Netlify:

### In Netlify:
1. Go to **Site settings** > **Domain management**
2. Click **Add a custom domain**
3. Enter: `retreat.solsolacestudio.com`
4. Netlify will tell you to add a DNS record

### In your domain DNS settings:

Your domain is likely managed by Squarespace (or wherever you bought `solsolacestudio.com`).

**If Squarespace manages DNS:**
1. Go to **Squarespace** > **Settings** > **Domains** > **solsolacestudio.com** > **DNS Settings**
2. Click **Add Record**
3. Add a **CNAME** record:
   - **Host/Name:** `retreat`
   - **Value/Points to:** Your Netlify site URL (e.g., `random-name-12345.netlify.app`)
   - **TTL:** Leave default
4. Save

**If another provider manages DNS (e.g., GoDaddy, Google Domains, Cloudflare):**
- Same concept: add a CNAME record for `retreat` pointing to your Netlify URL

### After adding the DNS record:
1. Wait 5–30 minutes for DNS to propagate
2. Go back to Netlify > Domain management
3. Netlify should show a green checkmark and auto-provision an SSL certificate
4. Your page is now live at `https://retreat.solsolacestudio.com`

---

## 4. Meta Pixel Setup (optional — for Instagram/Facebook ads)

If she wants to run ads and retarget visitors:

1. Go to [business.facebook.com](https://business.facebook.com) > **Events Manager**
2. Find or create a **Pixel** (it's under Data Sources)
3. Copy the **Pixel ID** (a long number like `1234567890123456`)
4. In `index.html`, find the commented-out Meta Pixel section near the top:
   ```html
   <!-- Meta Pixel placeholder — replace YOUR_PIXEL_ID -->
   ```
5. Uncomment the block (remove `<!--` and `-->`)
6. Replace both instances of `YOUR_PIXEL_ID` with the actual Pixel ID
7. Re-deploy

---

## 5. Email Capture Setup

The "Not ready yet?" email form currently just shows a success message. To actually capture emails, pick one:

### Option A: Google Forms (simplest)
1. Create a Google Form with "Name" and "Email" fields
2. Get the form's action URL and field entry IDs
3. Update the form in `index.html` to submit to Google Forms

### Option B: Mailchimp
1. Create a Mailchimp audience/list
2. Create an embedded form
3. Replace the form HTML with Mailchimp's embed code (styled to match)

### Option C: Formspree (recommended — easiest)
1. Sign up at [formspree.io](https://formspree.io) (free tier: 50 submissions/month)
2. Create a new form, get your form endpoint (e.g., `https://formspree.io/f/XXXXXXXX`)
3. In `index.html`, update the form tag:
   ```html
   <form class="capture__form" id="captureForm" action="https://formspree.io/f/XXXXXXXX" method="POST">
   ```
4. Submissions go to your email inbox automatically

---

## 6. Photos

The page has placeholder divs where photos should go. To add real photos:

1. Create an `images/` folder in the project
2. Add photos named:
   - `hero.jpg` — Main hero background (pool, property overview — landscape, high res)
   - `property-1.jpg` through `property-4.jpg` — Gallery images
   - `og-image.jpg` — Social sharing preview (1200x630px recommended)
3. The hero image loads automatically (the code checks for `images/hero.jpg`)
4. For the gallery, update the placeholder divs in the property section with `<img>` tags

---

## 7. UTM-Tagged Share Links

Once the page is live, here are ready-to-share URLs for different channels:

```
Instagram Bio:
https://retreat.solsolacestudio.com?utm_source=instagram&utm_medium=bio

Instagram Stories:
https://retreat.solsolacestudio.com?utm_source=instagram&utm_medium=story

WhatsApp / DMs:
https://retreat.solsolacestudio.com?utm_source=whatsapp&utm_medium=dm

Email Newsletter:
https://retreat.solsolacestudio.com?utm_source=email&utm_medium=newsletter

Facebook:
https://retreat.solsolacestudio.com?utm_source=facebook&utm_medium=post
```

These help track which channel drives the most traffic (visible in Netlify Analytics or Google Analytics if added later).
