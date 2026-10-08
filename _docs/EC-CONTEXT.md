# Engaging Courses — Permanent Context File
> Upload this file to every new Claude chat session working on engagingcourses.com.
> This file changes only when something fundamental changes (new platform, domain, major redesign).
> Last updated: October 8, 2026

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
**Webinars:** NONE. As of October 8, 2026 the webinar program was dropped (the planned Oct 18, 2026 live session will not happen). All webinar banners, popups, the /webinar/ page and the "Webinars" menu item were removed from the site. Do not advertise or link to webinars anywhere. If webinars are revived later, Aaron and Claude will rebuild those pages from scratch — see "Webinar Removal (Oct 8, 2026)" below.

---

## Brand Voice & Key Phrases

Always emphasize:
- **Transformation** — courses that transform learners, not just inform them
- **Outcome-driven design** — every lesson built around what learners will be able to DO
- **Skills, not theory** — practical, immediately applicable
- **Illustrated storytelling** as a teaching tool
- Differentiate from platforms that teach software, not pedagogy

Avoid:
- Superficial feature-list language
- Overpromising ("the best", "number one")

Tone: Confident and credible, warm and approachable. Professional but never pretentious. Think Chanel aesthetic — minimal, elegant, nothing loud.

**On "Webinar":** webinars are not currently offered or advertised (decision Oct 8, 2026). Do not add webinar CTAs, banners, countdowns, or "upcoming live event" wording to the site or to new social captions. If webinars are revived, the earlier question of word choice ("Webinar" vs. "live session") should be re-decided with Aaron at that time.

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
- **Three live forms, three distinct purposes — do not conflate them.** The free plan allows 3 forms, 3 automations and 1 digital product, so all 3 form slots are in use:

  | Form ID | Purpose | Used on |
  |---|---|---|
  | `TM3AOT` | General "stay in the loop" email capture ("Engage Me!" button) | Homepage's own inline email-capture section ONLY. (It used to also power the webinar signup popups on Home/Freebies/Blog and the webinar page — all removed Oct 8, 2026.) |
  | `Fwa2AK` | Freebie gate — **Course Engagement Scorecard** | Freebies page, Scorecard download popup |
  | `yYD8Ks` | Freebie gate — **Dropout Autopsy** | Freebies page, Autopsy download popup |

- **`Vs4wxq`** — former single freebie form; **retired**, replaced by the two per-freebie forms above. Not referenced anywhere.
- **`V8INNU`** — this was a legacy Contact/Ask-a-Question form, superseded by Formspree early in the project and left dormant. **It has been deleted from MailerLite.** No longer referenced anywhere.
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
- Submissions go to MailerLite subscriber list. Thank-you emails are handled by MailerLite automations ("Completes a form" triggers), no site code involved. **To check:** any automation written for the webinar signup (TM3AOT) or the retired Vs4wxq form is now obsolete — review and retire/repurpose it. Freebie delivery by email (instead of an on-page download link) was considered but not decided; it depends on free-plan limits (see Freebie Gate below).
- **Domain authentication:** MailerLite's sending servers are authorized via the site's SPF record (see IONOS DNS Records below). A domain can only have one SPF TXT record — if MailerLite ever prompts to update it again, the new value must be merged into (replace) the existing record, never added as a second one.

---

## Formspree Details

- **Endpoint:** `https://formspree.io/f/mjgnbrlj`
- **Sends to:** engagingcourses@gmail.com
- **Used for:** Contact form and Request Demo form (both nav dropdowns + the Contact page)
- **Method:** AJAX (page does not redirect on submit)
- All fs-form class forms use the same endpoint
- `mail@engagingcourses.com` exists on IONOS but is not yet fully configured as a mailbox
- **Why Formspree and not MailerLite for these two forms:** Contact and Request Demo submissions are one-off personal messages that need a direct reply, not ongoing marketing — Formspree emails them straight to the inbox with no list enrollment. MailerLite forms are reserved for genuine opt-in marketing capture (freebies, homepage list signup). Don't merge these two systems; the split is deliberate.

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

Every page uses the folder + `index.html` pattern, which gives clean URLs with no `.html` (e.g. `/freebies/`). Assets are referenced with root-relative paths (`/assets/images/...`) on every page, including blog posts.

```
/ (repo root)
├── index.html                       ← Homepage            → engagingcourses.com/
├── about/index.html                 ← Team page (Aaron first, then Tim)
├── contact/index.html               ← Contact page with Formspree form
├── freebies/index.html              ← Freebies page — 2 real freebies, email-gated downloads
├── blog/
│   ├── index.html                   ← Blog index
│   ├── why-your-course-isnt-selling/index.html
│   ├── teaching-information-vs-transforming-learners/index.html
│   └── illustrated-storytelling-in-course-design/index.html
├── sitemap.xml
├── robots.txt
├── CNAME                            ← Contains: engagingcourses.com
└── assets/
    ├── images/
    │   ├── URL-logo_engagingcourses.com.png
    │   ├── Logo_DustyGorIsaback.png
    │   ├── Logo_GorDustyIsaback.png
    │   ├── Logo_ECA_schoolhouse.png
    │   ├── aaron-tim-chef.png
    │   ├── chef-empty-kitchen-16x9.png
    │   ├── Aaron-avatar.png
    │   ├── Tim-avatar.png
    │   └── carousel/                ← All scrolling strip images live here (12 images)
    └── videos/                      ← MP4s (not used in carousel — too large)
```

**Not in the site anymore:** `/webinar/` (deleted Oct 8, 2026) and `blog/join-us-live-august-2.html` (deleted earlier). Old links or social posts pointing to either will 404.

**To verify in the repo:** if the old flat files (`about.html`, `contact.html`, `freebies.html`, `blog.html`, `blog/*.html`) are still sitting in the repo from before the clean-URL change, they are orphaned duplicates. Any social bio link still pointing to `engagingcourses.com/freebies.html` should be changed to `engagingcourses.com/freebies/`.

**Nav order:** Home / About / Academy / Freebies / Blog / Request Demo / Contact. (The "Webinars" item was removed Oct 8, 2026.)

**Freebies page** has two live downloadable PDFs hosted via GitHub Releases, each behind its own email-gated popup (see "Freebie Gate" below):
- Course Dropout Autopsy → `freebie-dropout-autopsy`
- Course Engagement Scorecard → `freebie-course-engagement-scorecard`

---

## Homepage Key Features (index.html)

1. **Social strip** — Dark olive bar above nav. Icons for Instagram, YouTube, Facebook, X, TikTok
2. **Sticky nav** — Logo left, links right: Home / About / Academy / Freebies / Blog / Request Demo / Contact. Request Demo and Contact are dropdown popups with Formspree AJAX forms — each has an explicit close (×) button, and on mobile they render centered-and-fixed on screen (not anchored to the button) with a capped height and internal scroll, to avoid a bug where they'd render unreachably far down a tall stacked mobile menu.
3. **(Removed Oct 8, 2026)** — the countdown/webinar banner and its popups used to sit here, below the nav. The hero now follows the nav directly.
4. **Hero** — "Engaging Courses" H1, tagline H2, Join Academy CTA, portrait YouTube video (no autoplay). Video: https://youtube.com/shorts/d4-ggbGcFRA
5. **Scrolling carousel** — 12 images from assets/images/carousel/, duplicated for seamless loop, 60s animation, pauses on hover
6. **Why section** — 3 cards: Outcome-Driven Design, Creative & Distinctive, Real Skills Real Results
7. **Transform section** — Dark olive background. 3 cards: For you / For your learners / For your business
8. **Academy section** — ECA schoolhouse logo, copy, Skool link
9. **Email capture** — MailerLite TM3AOT embed (the homepage's own permanent capture section; copy reads "free resources and sample content" — no live-event wording)
10. **Blog preview** — 3 blog card previews, matching blog.html verbatim, each linking directly to its own post
11. **Footer** — simplified: logo, one-line tagline, social icons, copyright. (Not the older multi-column Navigate/Connect footer — that was replaced across every page for consistency.)

The same nav (item 2, including Request Demo/Contact dropdown behavior) and footer (item 11) are shared identically across every page on the site: About, Contact, Freebies, Blog, and all blog posts.

---

## Webinar Removal (Oct 8, 2026)

**Decision:** Aaron decided there will be no webinars, or at least none advertised. Everything webinar-related was removed from the site.

**Removed:**
- The countdown/"Sign Up for Free Webinar" banner on Home, Freebies and Blog, plus its three popups (choice popup, signup popup with freebie picker, Zoom-link popup) and all their CSS/JS.
- The `/webinar/` page (`webinar/index.html`) and the "Webinars" nav link on every page.
- `/webinar/` from `sitemap.xml`.
- The Blog featured card "Join Us Live October 18…" (it linked to `/webinar/`).
- "upcoming live event info" wording on the homepage email-capture section.
- The staged post-event replay files (`POST-AUG2-UPLOAD-ONLY`) are obsolete and should not be uploaded.

**Kept (not webinar-related):** the Freebies page's own email-gated download popups, and the homepage's inline TM3AOT email signup.

**Outside the site files, still to do on Aaron's side:**
- Remove "Free live session / Join the free Webinar" lines from the Instagram and TikTok bios and from any scheduled or future captions (see EC-SOCIAL.md).
- Review MailerLite automations tied to the webinar signup.
- The Zoom meeting link used for the Oct 18 session can simply be left unused.

**Reference material kept:** `Engaging_Courses_Webinar_Deck.md` (20-slide deck) is retained as content to reuse for a future live session, course sales page, or Academy intro; it is not tied to any live page.

**If webinars come back:** rebuild from scratch with Claude (new page, banner and signup flow) rather than trying to restore the old code.

---

## Freebie Gate (how the Freebies page works)

- Each freebie card opens its own popup with its own MailerLite form (Scorecard → `Fwa2AK`, Autopsy → `yYD8Ks`).
- The real GitHub Release download URLs live only inside a JavaScript `freebieConfig` object — they are NOT in the page HTML. The download button's `href` stays empty until the script detects the MailerLite success message (`.ml-form-successBody`), then sets it.
- **Known limits:** the GitHub Releases page for the repo is public, so a determined visitor can find the PDFs without giving an email. GitHub's download counter is also unreliable as a measure of signups; trust MailerLite subscriber counts instead.
- **Open option (not decided):** deliver the freebie by email through MailerLite instead of an on-page link, which would make the gate real. Blocked on checking free-plan limits (3 forms, 3 automations and 1 digital product are available; all 3 forms are in use).

---

## Analytics

- **GA4** property tag `G-NSXM6TD1ZR` is installed on every page. It records page views only.
- No custom GA4 events exist for freebie signups or downloads. Building them is an open option.
- Bio links and other shared links use UTM tags (source / medium / campaign), which show up in GA4 as traffic sources.

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
- **`.html`-free URLs:** every page now uses the folder + `index.html` trick (e.g. `/freebies/index.html` serves at `/freebies/`, no `.html`, no server config needed). Use this for any new page or blog post.
- **File naming for downloads (standing rule from Aaron, Oct 8, 2026):** because every page is named `index.html` and the browser renames duplicates to `index(1).html`, Claude delivers updated pages as flat files named by page: `index-home.html`, `index-about.html`, `index-contact.html`, `index-freebies.html`, `index-blog.html`, and `index-blog-[post-slug].html` for posts (e.g. `index-blog-why-your-course-isnt-selling.html`). `sitemap.xml` and `robots.txt` keep their names. Each delivery includes a short table saying which repo path each file replaces. Aaron renames each to `index.html` when uploading it into the right folder.
- **Deleting pages:** removing a page from the repo means deleting its whole folder on GitHub (e.g. the `webinar/` folder) — otherwise the old page stays live.

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
9. Tell Claude the URL — Claude will update the Freebies page (and its MailerLite form/popup) with the new download button

### When Replacing an Existing Freebie
Do NOT edit the existing release. Create a new release with a versioned tag:
- Example: `freebie-dropout-autopsy-v2` or `freebie-dropout-autopsy-2026-09`
- Old release stays archived with its historical download count intact
- Tell Claude the new URL and Claude will update the link on the site

### Why This System
Stable slugs mean download URLs never change unless a freebie is retired. The date goes in the release title for record-keeping, not in the tag where it would appear in the URL. URLs are shareable in bio links, blog posts, and email campaigns without ever silently breaking.

### Tracking Note
Download counts are aggregate only — GitHub shows "how many times" a file was downloaded, not "who" downloaded it. This is intentional: there's no need to link a specific email to a specific freebie choice, since visitors self-select which one they want.

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
- **Formspree vs. MailerLite is a deliberate split**, not overlapping tools: Formspree for one-off personal messages needing a direct reply (Contact, Request Demo); MailerLite for genuine opt-in list-building (freebies, homepage signup). Don't consolidate these.
- **A domain can only have one SPF TXT record.** If MailerLite (or any future service) asks you to add SPF authorization, the new value must be merged into the existing record, not added as a second, separate TXT record — two `v=spf1` records is invalid and can break deliverability for everything on the domain, including regular mailboxes.
- **Mobile modal scroll bug (fixed):** any modal/popup whose content can grow taller than the phone screen needs `max-height` + `overflow-y: auto` on the modal box, plus a `position: sticky; top: 0;` close button — otherwise on mobile the box can grow past the viewport with the close button scrolling out of reach and no way to dismiss it. This pattern is now used everywhere on the site; apply it to any new modal.
- **Mobile dropdown-anchored-to-button bug (fixed):** popups that use `position: absolute` anchored to their trigger button (like the old Request Demo/Contact dropdowns) can render unreachably far down the page on mobile if the button sits deep in a long stacked hamburger menu. Fix: on mobile, switch such popups to `position: fixed`, centered on screen, rather than anchored to the button.
- **Webinars dropped (Oct 8, 2026)** — all webinar pages, banners and popups removed; see "Webinar Removal". Do not re-add without Aaron asking.
- **Freebie URLs never appear in page HTML** — only inside the JS `freebieConfig`, applied after a confirmed form success. Keep it that way when editing the Freebies page.
- **Shared modal CSS/JS:** the Freebies page reuses `.signup-modal-*` styles, `.zoom-link-btn` (now just the download button style) and the `openModal`/`closeModal` helpers. Don't delete them when cleaning up — an earlier cleanup nearly did.
- **V8INNU (legacy MailerLite contact form) has been deleted** — Formspree fully handles Contact/Request Demo; no MailerLite form needed for that purpose.

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
| TXT | @ | v=spf1 include:_spf.mlsend.com include:_spf-us.ionos.com ~all | Email SPF — merged to authorize both IONOS mail and MailerLite sending. Do not add a second SPF TXT record; always merge new authorizations into this one. |
| CNAME | _dmarc | dmarc.ionos.com | DMARC |

---

## What Claude Should Always Do

- Match existing code style — all CSS in `<style>` tags in `<head>`, no external stylesheets
- Use CSS variables (--dusty, --gor, etc.) never hardcoded hex values in CSS rules
- Add `mix-blend-mode: multiply` to all logo images
- Include full SEO/AEO markup on every page: meta description, OG tags, schema.org JSON-LD, canonical URL
- Keep nav and footer identical across all pages
- Blog posts live at `/blog/[post-slug]/index.html` and every page references assets with root-relative paths (`/assets/images/...`)
- Internal links use clean folder URLs (`/freebies/`, `/blog/`), never `.html`
- Deliver updated pages as flat, page-named files (`index-home.html`, `index-blog.html`, …) with a table of where each goes — see GitHub Workflow
- Never use autoplay on videos
- Always use AJAX for Formspree forms (never let page redirect on submit)
- Filenames: hyphens only, no parentheses, no spaces
- Any new modal/popup must be tested (or at minimum designed) for mobile: capped height + internal scroll + reachable close button — see "Key Technical Decisions" above
- Never add a second SPF TXT record — always merge new authorizations into the existing one
- Do not add webinar content, banners, countdowns or live-event CTAs unless Aaron asks to revive webinars
- Before finishing any change, sweep every page for leftovers (links, nav items, CSS/JS, sitemap) and test pages in a browser for console errors
