# Engaging Courses — Permanent Context File
> Upload this file to every new Claude chat session working on engagingcourses.com.
> This file changes only when something fundamental changes (new platform, domain, major redesign).
> Last updated: July 2026

---

## The Business

**Company:** Engaging Courses / Engaging Courses Academy (ECA)
**Website:** https://engagingcourses.com
**Co-founders:** Aaron (content, site, Claude liaison) and Tim (operations, early infrastructure)
**Core product:** Engaging Courses Academy — an online course creation training program hosted on Skool
**Skool URL:** https://www.skool.com/engaging-courses-academy-1697/
**Target audience:** Online course creators and content producers who have material but don't know why it isn't selling or engaging learners
**Brand positioning:** Outcome-driven, transformative course design — NOT superficial "build a course" tooling. We teach skills that transform both the creator and their learners.
**Key differentiator:** Illustrated animation and hand-drawn storytelling characters used as deliberate pedagogical tools, not just decoration. ~20 short animated videos (15–25 sec) in B&W illustrated style.
**Launch event:** Live session Sunday September 7, 2026 at 11am ET (moved from August 2, 2026)

---

## Brand Voice & Key Phrases

Always emphasize:
- **Transformation** — courses that transform learners, not just inform them
- **Outcome-driven design** — every lesson built around what learners will be able to DO
- **Skills, not theory** — practical, immediately applicable
- **Illustrated storytelling** as a teaching tool
- Differentiate from platforms that teach software, not pedagogy

Avoid:
- "Webinar" in brand copy and blog posts — use "live session" or "live event"
- EXCEPTION: "Webinar" IS used in social media captions and campaign-specific CTAs (e.g. "Join the free Webinar") because it performs better in search and is the term the audience uses
- Superficial feature-list language
- Overpromising ("the best", "number one")

Tone: Confident and credible, warm and approachable. Professional but never pretentious. Think Chanel aesthetic — minimal, elegant, nothing loud.

---

## Tech Stack

| Component | Platform | Notes |
|---|---|---|
| Domain registrar | IONOS | engagingcourses.com |
| DNS management | IONOS | A records → GitHub Pages IPs |
| Site hosting | GitHub Pages | Free, static HTML/CSS |
| GitHub repo | github.com/dazmuth/ec | username: dazmuth |
| Email hosting | IONOS Mail Basic 5 | $3/month, 3 addresses |
| Email marketing / CRM | MailerLite | Account 2504099 |
| Contact forms | Formspree | Endpoint: mjgnbrlj |
| Course community | Skool | Managed by Tim |
| SSL | GitHub Pages / Let's Encrypt | Free, auto-provisioned |

---

## MailerLite Details

- **Account:** 2504099
- **Webinar/general signup form:** `TM3AOT` — used on homepage, webinar page, blog post 4, countdown modal
  - Fields: Email, Name, Phone (optional)
  - Button text: "Engage Me!"
  - This is the primary list-building form
- **Freebies-only form:** `Vs4wxq` — used on freebies page for freebie-specific signups
- **Contact/Ask a Question form:** `V8INNU` — NOTE: replaced by Formspree for actual contact use. V8INNU may still exist in MailerLite but is not actively used.
- One form per distinct offer — do not consolidate TM3AOT and Vs4wxq
- **Universal script** (goes in `<head>` of every page that uses MailerLite):
```html
<script>
  (function(w,d,e,u,f,l,n){w[f]=w[f]||function(){(w[f].q=w[f].q||[])
  .push(arguments);},l=d.createElement(e),l.async=1,l.src=u,
  n=d.getElementsByTagName(e)[0],n.parentNode.insertBefore(l,n);})
  (window,document,'script','https://assets.mailerlite.com/js/universal.js','ml');
  ml('account', '2504099');
</script>
```
- Double opt-in: **DISABLED** (important — leave off)
- Submissions go to MailerLite subscriber list only. No email notification sent automatically.

---

## Formspree Details

- **Endpoint:** `https://formspree.io/f/mjgnbrlj`
- **Sends to:** engagingcourses@gmail.com
- **Used for:** Contact form and Request Demo form (both nav dropdowns + contact.html)
- **Method:** AJAX (page does not redirect on submit)
- All fs-form class forms use the same endpoint
- `mail@engagingcourses.com` exists on IONOS but is not yet fully configured as a mailbox

---

## Email Addresses

| Address | Status | Purpose |
|---|---|---|
| aaron@engagingcourses.com | Active on IONOS | Aaron's direct email |
| tim@engagingcourses.com | Active on IONOS | Tim's direct email |
| mail@engagingcourses.com | Exists, not fully configured | General contact — not yet set up as active mailbox |
| engagingcourses@gmail.com | Active | Receives Formspree submissions |

---

## Design System

### Colors
```css
--dusty:      #C79A8B;   /* Primary brand — Dusty rose/terracotta */
--gor:        #B6A68B;   /* Secondary — Warm gray/tan */
--isabelline: #F5F2ED;   /* Background — Warm off-white */
--olive:      #3E3E3E;   /* Text — Black olive */
--white:      #FFFFFF;
--gray:       #E1DFDF;   /* Borders, subtle backgrounds */
```

### Typography
```css
--font-head: -apple-system, BlinkMacSystemFont, 'Helvetica Neue', Arial, sans-serif;
--font-body: 'Inter', sans-serif;  /* Google Fonts */
--font-logo: 'TeX Gyre Adventor', serif;  /* Google Fonts — logo only */
```
- H1: Helvetica Neue (system stack)
- H2: Inter Bold
- H3 + Body: Inter
- Logo text: TeX Gyre Adventor

### Logo conventions
- Top of pages: `Logo_DustyGorIsaback.png` (Dusty "e" in front)
- Bottom/footer: `URLlogo_engagingcourses_com.png` (URL text logo)
- ECA logo: `Logo_ECA_schoolhouse.png` (schoolhouse icon — used in Academy section)
- All logos use `mix-blend-mode: multiply` on light backgrounds to handle white backgrounds

---

## Site File Structure

```
/ (repo root)
├── index.html          ← Homepage (most complex — countdown, carousel, forms, social)
├── about.html          ← Team page (Tim + Aaron avatars, mission section)
├── contact.html        ← Contact page with Formspree form
├── freebies.html       ← Freebies page (placeholder cards, MailerLite nudge)
├── blog.html           ← Blog index page
├── sitemap.xml
├── robots.txt
├── CNAME               ← Contains: engagingcourses.com
├── assets/
│   ├── images/
│   │   ├── URL-logo_engagingcourses.com.png
│   │   ├── Logo_DustyGorIsaback.png
│   │   ├── Logo_GorDustyIsaback.png
│   │   ├── Logo_ECA_schoolhouse.png
│   │   ├── aaron-tim-chef.png
│   │   ├── chef-empty-kitchen-16x9.png
│   │   ├── Aaron-avatar.png
│   │   ├── Tim-avatar.png
│   │   └── carousel/          ← All scrolling strip images live here
│   │       ├── Joe-sploshing-onto-canvas-project.png
│   │       ├── bar-chef-tablet.png
│   │       ├── chef-big-storyboard.png
│   │       ├── chef-cpo.jpg
│   │       ├── chef-heather-stirring-mixture.png
│   │       ├── chef-kitchen-script-storyboard-floating.png
│   │       ├── chef-pointing-3-milestones.png
│   │       ├── chef-site-headline-good.png
│   │       ├── jenna-joe-holding-hands.jpg
│   │       ├── robot-centered-bored-room.png
│   │       ├── zhao-paris-bistro.jpg
│   │       └── zoom-screen.png
│   └── videos/                ← MP4s (not used in carousel — too large)
├── webinar/
│   └── index.html             ← Webinar landing page (bio link destination for social media)
└── blog/
    ├── why-your-course-isnt-selling.html
    ├── teaching-information-vs-transforming-learners.html
    ├── illustrated-storytelling-in-course-design.html
    └── join-us-live-august-2.html  ← Post-Sept 7: archive or replace
```

**Nav order:** Home / About / Academy / Freebies / Blog / Webinars / Request Demo / Contact

**Freebies page** has two live downloadable PDFs hosted via GitHub Releases:
- Course Dropout Autopsy → freebie-dropout-autopsy
- Course Engagement Scorecard → freebie-course-engagement-scorecard
Freebies page shows webinar banner at top — strong secondary CTA destination for social posts with diagnostic/problem-aware themes.

---

## Homepage Key Features (index.html)

1. **Social strip** — Dark olive bar above nav. Icons for Instagram, YouTube, Facebook, X, TikTok
2. **Sticky nav** — Logo left, links right. Two dropdown buttons: "Request Demo" (Gor color) and "Contact" (Dusty color). Both use Formspree AJAX forms that open inline dropdowns.
3. **Countdown bar** — Dusty background. Counts to September 7, 2026 11am ET (updated from August 2). Desktop: Sign Up buttons flanking countdown (Isabelline style). Mobile: single Black Olive Sign Up button below countdown. Sign Up opens MailerLite modal overlay.
4. **Hero** — "Engaging Courses" H1, tagline H2, Join Academy CTA, portrait YouTube video (no autoplay). Video: https://youtube.com/shorts/d4-ggbGcFRA
5. **Scrolling carousel** — 12 images from assets/images/carousel/, duplicated for seamless loop, 60s animation, pauses on hover
6. **Why section** — 3 cards: Outcome-Driven Design, Creative & Distinctive, Real Skills Real Results
7. **Transform section** — Dark olive background. 3 cards: For you / For your learners / For your business
8. **Academy section** — ECA schoolhouse logo, copy, Skool link
9. **Email capture** — MailerLite TM3AOT embed
10. **Blog preview** — 3 blog card previews
11. **Footer** — URL logo, nav links, social icons, connect info

---

## Social Media URLs

| Platform | URL |
|---|---|
| Instagram | https://www.instagram.com/engaging.courses/ |
| YouTube | https://www.youtube.com/@EngagingCourses |
| Facebook | https://www.facebook.com/1JozYGqpBR/ |
| X (Twitter) | https://www.x.com/engagingcourses/ |
| TikTok | https://www.tiktok.com/@engagingcourses |

---

## GitHub Workflow

- **Repo:** github.com/dazmuth/ec
- **Deployment:** Push to main branch → GitHub Pages auto-deploys (usually < 60 seconds)
- **Process:** Claude edits HTML → AJ downloads files → uploads to GitHub via web interface
- **Image rule:** All images must have web-safe filenames — no parentheses, no spaces. Hyphens and underscores only.
- **Carousel images:** Always go in `assets/images/carousel/` subfolder
- **Blog posts:** Always go in `/blog/` subfolder

---

## GitHub Releases — Freebie PDF Hosting

PDFs are hosted via GitHub Releases in the dazmuth/ec repo. This gives stable, permanent download URLs and tracks download counts per release.

### Naming Convention
One release per freebie. Tag uses a stable descriptive slug — never a date in the tag.

**Current releases:**
- Tag: `freebie-dropout-autopsy` → file: `Dropout-Autopsy.pdf`
- Tag: `freebie-course-engagement-scorecard` → file: `Course-Engagement-Scorecard.pdf`

**URL structure:**
```
https://github.com/dazmuth/ec/releases/download/freebie-dropout-autopsy/Dropout-Autopsy.pdf
https://github.com/dazmuth/ec/releases/download/freebie-course-engagement-scorecard/Course-Engagement-Scorecard.pdf
```

### How to Add a New Freebie — Step by Step
1. Go to github.com/dazmuth/ec → click "Releases" in right sidebar
2. Click "Draft a new release"
3. In "Choose a tag" field, type the new slug and select "Create new tag"
   - Format: `freebie-[descriptive-name]`
   - Examples: `freebie-module-structure-template`, `freebie-25-second-formula`, `freebie-engagement-checklist`
4. Set release title to human-readable name with date: "Module Structure Template — added August 2026"
5. Add release notes: brief description of what the freebie is
6. Upload the PDF by dragging into the "Attach binaries" area
   - Filename must be web-safe: hyphens only, no spaces, no parentheses
   - Example: `Module-Structure-Template.pdf`
7. Click "Publish release" (not "Save draft")
8. Copy the resulting download URL
9. Tell Claude the URL — Claude will update freebies.html with the new download button

### When Replacing an Existing Freebie
Do NOT edit the existing release. Create a new release with a versioned tag:
- Example: `freebie-dropout-autopsy-v2` or `freebie-dropout-autopsy-2026-09`
- Old release stays archived with its historical download count intact
- Tell Claude the new URL and Claude will update the link on the site

### Why This System
Stable slugs mean download URLs never change unless a freebie is retired. The date goes in the release title for record-keeping, not in the tag where it would appear in the URL. URLs are shareable in bio links, blog posts, and email campaigns without ever silently breaking.

---

## Key Technical Decisions & Lessons Learned

- **Parentheses in filenames** cause browser loading failures. Always use hyphens.
- **mix-blend-mode: multiply** required on all logo PNGs to handle white backgrounds on Isabelline background
- **MailerLite double opt-in is OFF** — critical, do not re-enable
- **Formspree AJAX** — all fs-form submissions use fetch() with Accept: application/json header. Page never redirects.
- **Blog is static HTML** — no CMS needed at this stage. Claude writes posts, AJ uploads to /blog/ folder.
- **No autoplay video** on homepage — AJ specifically does not want autoplay
- **MP4 files not used in carousel** — too large, performance impact on mobile
- **Social strip is above the nav**, not inside it — deliberate layout decision
- **MailerLite CSS overrides** use !important throughout to override MailerLite's injected styles
- **Showit was cancelled** — all infrastructure moved off Showit entirely

---

## IONOS DNS Records (for reference)

| Type | Host | Value | Purpose |
|---|---|---|---|
| A | @ | 185.199.108.153 | GitHub Pages |
| A | @ | 185.199.109.153 | GitHub Pages |
| A | @ | 185.199.110.153 | GitHub Pages |
| A | @ | 185.199.111.153 | GitHub Pages |
| CNAME | www | dazmuth.github.io | GitHub Pages www |
| MX | @ | mx00.ionos.com | Email |
| MX | @ | mx01.ionos.com | Email |
| TXT | @ | v=spf1 include:_spf-us.ionos.com ~all | Email SPF |
| CNAME | _dmarc | dmarc.ionos.com | DMARC |

---

## What Claude Should Always Do

- Match existing code style — all CSS in `<style>` tags in `<head>`, no external stylesheets
- Use CSS variables (--dusty, --gor, etc.) never hardcoded hex values in CSS rules
- Add `mix-blend-mode: multiply` to all logo images
- Include full SEO/AEO markup on every page: meta description, OG tags, schema.org JSON-LD, canonical URL
- Keep nav and footer identical across all pages
- Blog posts live at `/blog/filename.html` and reference assets as `../assets/images/`
- Root-level pages reference assets as `assets/images/`
- Never use autoplay on videos
- Always use AJAX for Formspree forms (never let page redirect on submit)
- Filenames: hyphens only, no parentheses, no spaces
