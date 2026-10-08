# Engaging Courses — Session Changelog
> Paste new entries at the TOP of this file after each Claude session.
> Upload alongside EC-CONTEXT.md at the start of every new chat.
> Format: ## [Date] — [Brief topic], then bullet points of what changed.

---

## October 8, 2026 — Webinar Removal, Site State Refresh

**Decision:** Aaron decided there will be no webinars, or at least none advertised. The planned October 18, 2026 live session is cancelled. If webinars are revived later, Aaron and Claude will rebuild the pages from scratch.

**Removed from the site:**
- Countdown/"Sign Up for Free Webinar" banner on Home, Freebies and Blog, plus its three popups (choice, signup with freebie picker, Zoom link) and their CSS/JS
- `/webinar/` page and the "Webinars" nav item on all pages
- `/webinar/` entry in `sitemap.xml`
- Blog featured card "Join Us Live October 18…"
- "upcoming live event info" wording in the homepage email-capture section (now "free resources and sample content")

**Kept:** Freebies page email-gated download popups; homepage inline TM3AOT signup.

**Bug caught during testing:** the Freebies page shares `openModal`/`closeModal` helpers with the removed popups; they were restored so the download popups still work. All 6 page types were checked in a browser (no console errors, banner gone, Freebies popup opens and closes with Escape).

**Files delivered (9):** home, about, contact, freebies, blog index, 3 blog posts, sitemap. Aaron uploads each into its folder as `index.html` and **deletes the `webinar/` folder** from the GitHub repo.

**New working rule:** delivered pages are named by page (`index-home.html`, `index-blog.html`, `index-blog-[post-slug].html` …) with a table of where each goes, so downloads don't collide as `index(1).html`. Recorded in EC-CONTEXT.md.

**Docs updated this session:** EC-CONTEXT.md (full refresh), EC-BLOG-INDEX.md (full refresh), EC-SOCIAL.md (webinar lines/CTAs retired), this changelog.

**Site changes made between the July sessions and today (summarized so this log catches up):**
- Header/footer unified across all pages; simplified footer; Aaron/Tim order swapped on About with a new Aaron bio
- Clean URLs sitewide (folder + `index.html`); Home blog cards match the Blog page and link straight to each post; blog posts dated May / June / July 2026
- Webinar page, banner and popups built, date moved Aug 2 → Sept 7 → Oct 18, then removed today
- Freebies page: real PDFs with descriptions; email gate; split into two forms (`Fwa2AK` Scorecard, `yYD8Ks` Autopsy); real download URLs kept out of page HTML; `Vs4wxq` retired
- GA4 (`G-NSXM6TD1ZR`) installed on all pages; UTM-tagged bio link in use
- Mobile fixes: popups cap height and scroll with a sticky close button; Request Demo/Contact dropdowns become centered fixed popups on phones
- MailerLite: SPF record merged for IONOS + MailerLite; legacy `V8INNU` deleted
- GitHub Releases PDF filenames use hyphens (an underscore mismatch once caused a 404)

**Open items:**
- Remove webinar wording from Instagram/TikTok bios and any scheduled captions; update the campaign doc (EC-Campaign-2026-v4)
- Review MailerLite automations tied to the webinar signup and the retired `Vs4wxq` form
- Check the repo for orphaned old flat files (`about.html`, `freebies.html`, `blog.html`, …) and update any social bio link that still points to `/freebies.html`
- Freebie delivery is still bypassable via the public GitHub Releases page; option to deliver by MailerLite email depends on free-plan limits (3 forms, 3 automations, 1 digital product; all 3 forms are in use)
- No GA4 custom events for freebie signups/downloads yet
- Replace the TikTok bio (needs problem-focused text within 80 characters)

---

## July 2026 — Session 2 (Social Media Campaign Session)

> Historical entry. The webinar plans below (Aug 2, then Sept 7, then Oct 18) were cancelled on October 8, 2026.

This was a very long session focused entirely on social media strategy, campaign execution, and content optimization leading up to the originally planned August 2 webinar. Webinar was subsequently moved to September 7, 2026.

**Key decisions made:**
- Platform strategy finalized: Instagram + TikTok (Tier 1), Facebook via auto-crosspost (Tier 2), X/YouTube/Bluesky deprioritized
- Hashtag strategy: 5 niche tags per post, no generic tags (#engaging, #course, #training deprecated)
- Caption formula established: hook → body → expand hook questions → CTA → webinar line (red, pre-event only) → hashtags
- Standard hashtag set: #coursecreator #onlinecoursecreator #elearning #instructionaldesign #coursecreation
- EngineMailer evaluated and rejected — staying on MailerLite
- No paid ads before September 7 — organic only
- No follow-back policy for brand accounts
- TikTok job = awareness/reach only; Instagram = conversion platform
- "Webinar" word approved for social media captions despite general brand preference for "live session"
- Webinar moved from August 2 to September 7, 2026

**Documents created this session:**
- EC-Campaign-2026-v3.docx — 25-page Word document: all 27 captions (Courier New, red webinar line), day-by-day posting calendar July 13-August 3, email campaign outline
- EC-AltText-Reference.md — Alt text for all 26 videos extracted from Google Drive scripts
- EC-SOCIAL.md — NEW: complete social media strategy reference document for future sessions
- EC-CONTEXT.md — Updated: webinar date, MailerLite forms, nav order, freebies page, GitHub Releases section added

**Campaign executed (July 13-31, 2026):**
- 3 videos posted before campaign paused: AI8, E6, E9
- Instagram views: 76 → 135 → 167 (upward trend)
- TikTok views: 82 → 50 → 62 (honeymoon dip, normal for new account)
- Instagram: 63 profile views, 7 link taps to site
- TikTok: 2 profile views
- Email signups: 0 (expected for niche organic-only campaign)
- Meta Business Suite connected for Instagram → Facebook auto-crosspost
- TikTok Studio set up for scheduling

**Social media asset library:**
- 26 videos total (per Revised Social Media Clips Descriptions RTF in Google Drive)
- ~22 videos remaining to post for September campaign
- 2 webinar videos (W1, W2) still to be produced — update date to September 7
- I9 is post-event only — no webinar line
- Full video list, bucket classifications, and alt text status documented in EC-SOCIAL.md

**Site updates made this session:**
- Freebies page updated with two live PDF downloads (Dropout Autopsy, Course Engagement Scorecard)
- Freebies page has webinar banner at top — strong secondary social CTA destination
- GitHub Releases system established for PDF hosting (documented in EC-CONTEXT.md)
- Blog Post 4 (join-us-live-august-2.html) — needs date update for September 7
- Countdown timer on homepage needs update from August 2 to September 7

**Open items going into next session:**
- Update countdown timer target date to September 7, 2026
- Update blog post 4 date and content for September 7
- Update webinar line in all captions from 8/2/26 to September date
- Produce W1 and W2 webinar videos with September 7 date
- Update TikTok bio to problem-focused language within 80 chars
- Build MailerLite email sequence (5 emails outlined in EC-SOCIAL.md)
- Add UTM tracking to freebies page bio link swaps before September campaign
- Develop post-September 7 evergreen content strategy

---

## July 2026 — Session 1 (Foundation Session)

This was a very long foundational session covering the entire site build from scratch.

**Infrastructure decisions made:**
- Cancelled Showit ($34/month) — replaced with GitHub Pages (free)
- Domain stays at IONOS ($3/month existing plan)
- Email hosting stays at IONOS Mail Basic 5 ($3/month existing)
- MailerLite chosen for email marketing/CRM (free tier, account 2504099)
- Formspree chosen for contact form submissions (endpoint mjgnbrlj → engagingcourses@gmail.com)
- Blog implemented as static HTML (no CMS) — Claude writes posts, uploaded to /blog/ folder
- Showit was explored extensively before being cancelled — not relevant going forward

**Files created/updated:**
- index.html — Full homepage with social strip, countdown timer, hero, carousel, transform section, email capture, blog preview, two nav dropdowns (Contact + Request Demo)
- about.html — Team page with Tim and Aaron avatar placeholders + mission section
- contact.html — Contact page with Formspree AJAX form
- freebies.html — Freebies page with 3 placeholder cards + MailerLite nudge
- blog.html — Full blog index with featured post + 3-column grid
- blog/why-your-course-isnt-selling.html — Post 1
- blog/teaching-information-vs-transforming-learners.html — Post 2 (includes comparison table)
- blog/illustrated-storytelling-in-course-design.html — Post 3
- blog/join-us-live-august-2.html — Post 4 (featured, includes MailerLite signup form)
- sitemap.xml — SEO sitemap
- robots.txt — SEO robots file

**Key features implemented:**
- Countdown timer to August 2, 2026 11am ET (Dusty bar between social strip and hero)
- Sign Up buttons on countdown open MailerLite modal overlay (form TM3AOT)
- Two nav dropdown forms: Contact (Dusty) and Request Demo (Gor) — both Formspree AJAX
- Scrolling image carousel (12 images, 60s loop, assets/images/carousel/ subfolder)
- Social strip above nav (Instagram, YouTube, Facebook, X, TikTok)
- Dark olive Transform section between Why and Academy sections
- Full SEO/AEO markup on all pages (schema.org, OG tags, canonical URLs)

**Open items / known issues:**
- mail@engagingcourses.com exists on IONOS but mailbox not yet configured
- Tim and Aaron avatar images (Tim-avatar.png, Aaron-avatar.png) uploaded to GitHub but not verified displaying correctly on About page
- Freebies page has placeholder cards only — real freebie content TBD
- Blog posts need review by Tim before launch
- MailerLite welcome automation not yet set up (recommended: set up welcome email sequence)
- Social media accounts exist but some may not be fully active yet
- Request Demo dropdown had an error bug (pre-filled textarea) — fixed with JS value injection

**Decisions deferred:**
- mail@engagingcourses.com mailbox setup
- MailerLite welcome email automation
- IONOS WordPress blog (decided against — static HTML sufficient for now)
- Adobe Creative Cloud subscription (After Effects) — still under evaluation

---

*Add new entries above this line, newest first.*
