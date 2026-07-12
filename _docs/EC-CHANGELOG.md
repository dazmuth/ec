# Engaging Courses — Session Changelog
> Paste new entries at the TOP of this file after each Claude session.
> Upload alongside EC-CONTEXT.md at the start of every new chat.
> Format: ## [Date] — [Brief topic], then bullet points of what changed.

---

## July 2025 — Session 1 (Foundation Session)

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
- `index.html` — Full homepage with social strip, countdown timer, hero, carousel, transform section, email capture, blog preview, two nav dropdowns (Contact + Request Demo)
- `about.html` — Team page with Tim and Aaron avatar placeholders + mission section
- `contact.html` — Contact page with Formspree AJAX form
- `freebies.html` — Freebies page with 3 placeholder cards + MailerLite nudge
- `blog.html` — Full blog index with featured post + 3-column grid
- `blog/why-your-course-isnt-selling.html` — Post 1
- `blog/teaching-information-vs-transforming-learners.html` — Post 2 (includes comparison table)
- `blog/illustrated-storytelling-in-course-design.html` — Post 3
- `blog/join-us-live-august-2.html` — Post 4 (featured, includes MailerLite signup form)
- `sitemap.xml` — SEO sitemap
- `robots.txt` — SEO robots file

**Key features implemented:**
- Countdown timer to August 2, 2026 11am ET (Dusty bar between social strip and hero)
- Sign Up buttons on countdown open MailerLite modal overlay (form TM3AOT)
- Two nav dropdown forms: Contact (Dusty) and Request Demo (Gor) — both Formspree AJAX
- Scrolling image carousel (12 images, 60s loop, assets/images/carousel/ subfolder)
- Social strip above nav (Instagram, YouTube, Facebook, X, TikTok)
- Dark olive Transform section between Why and Academy sections
- Full SEO/AEO markup on all pages (schema.org, OG tags, canonical URLs)

**Open items / known issues:**
- `mail@engagingcourses.com` exists on IONOS but mailbox not yet configured
- Tim and Aaron avatar images (`Tim-avatar.png`, `Aaron-avatar.png`) uploaded to GitHub but not verified displaying correctly on About page
- Freebies page has placeholder cards only — real freebie content TBD
- Blog posts need review by Tim before launch
- MailerLite welcome automation not yet set up (recommended: set up welcome email sequence)
- Social media accounts exist but some may not be fully active yet
- Request Demo dropdown had an error bug (pre-filled textarea) — fixed with JS value injection

**Decisions deferred:**
- `mail@engagingcourses.com` mailbox setup
- MailerLite welcome email automation
- IONOS WordPress blog (decided against — static HTML sufficient for now)
- Adobe Creative Cloud subscription (After Effects) — still under evaluation

---

*Add new entries above this line, newest first.*
