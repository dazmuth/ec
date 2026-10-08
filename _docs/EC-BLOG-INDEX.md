# Engaging Courses — Blog Index
> Running list of all published blog posts.
> Update this file whenever a new post is added or an existing post is edited.
> Upload alongside EC-CONTEXT.md at the start of any Claude session involving blog work.
> Last updated: October 8, 2026

---

## Published Posts

Every post lives in its own folder as `index.html`, so the URL has no `.html`.

| # | Title | Repo path | URL | Tag | Date | Status |
|---|---|---|---|---|---|---|
| 1 | Why Your Online Course Isn't Selling — And It Has Nothing to Do With Your Content | `blog/why-your-course-isnt-selling/index.html` | /blog/why-your-course-isnt-selling/ | Course Design | May 2026 | Published |
| 2 | The Difference Between Teaching Information and Transforming Learners | `blog/teaching-information-vs-transforming-learners/index.html` | /blog/teaching-information-vs-transforming-learners/ | Instructional Design | June 2026 | Published |
| 3 | Why We Use Illustrated Storytelling to Teach Course Design — And Why It Works | `blog/illustrated-storytelling-in-course-design/index.html` | /blog/illustrated-storytelling-in-course-design/ | Content Strategy | July 2026 | Published |

**Removed:**
- Former Post 4, "Join Us Live August 2" (`blog/join-us-live-august-2.html`) — deleted earlier; its content moved to the `/webinar/` page.
- The blog index's "Join Us Live October 18" featured card — removed Oct 8, 2026 along with the whole webinar program (see EC-CONTEXT.md, "Webinar Removal").

---

## Post Details

### Post 1 — Why Your Online Course Isn't Selling
- **URL:** https://engagingcourses.com/blog/why-your-course-isnt-selling/
- **Summary:** Addresses the core pain point — course creators with good content that isn't selling. Argues the problem is delivery not expertise. Introduces outcome-driven design concept. CTA → Skool Academy.
- **Key phrases:** outcome-driven, transformation, delivery vs. content, information trap
- **CTA:** Explore the Academy → Skool

### Post 2 — Teaching Information vs. Transforming Learners
- **URL:** https://engagingcourses.com/blog/teaching-information-vs-transforming-learners/
- **Summary:** Makes the explicit philosophical argument differentiating ECA from superficial course platforms. Includes a side-by-side comparison table. Positions outcome-driven design as a learnable skill.
- **Key phrases:** transform vs. inform, outcome-driven, capability vs. comprehension, learnable skill
- **Special elements:** Comparison table (6 rows, information-based vs transformation-based)
- **CTA:** Join the Academy → Skool

### Post 3 — Illustrated Storytelling in Course Design
- **URL:** https://engagingcourses.com/blog/illustrated-storytelling-in-course-design/
- **Summary:** Explains the pedagogical reasoning behind ECA's animated illustrated character approach. Argues that the medium models the message — using engaging content to teach engagement. Includes practical takeaways for any course creator.
- **Key phrases:** illustrated storytelling, cognitive load, animation as teaching tool, short-form clarity, medium models the message
- **Special elements:** Highlight box callout, pull quote
- **CTA:** See the method in action → Skool

---

## Blog Index Page (`blog/index.html`, URL /blog/)

- Layout: page header, then the three posts in a three-column grid (one column on mobile). There is currently **no featured card**.
- The Home page's blog preview shows the same three cards, word for word, each linking directly to its post.
- When adding a new post: add its card to the grid (and to the Home preview if it should appear there), add a folder under `blog/`, add it to `sitemap.xml`, and add a row to this file.
- If a featured slot is wanted again, bring back a `.featured-post` card — but do not use it for webinar or live-event promotion unless webinars are revived.

---

## Post Template Notes

All blog posts use identical structure:
- Same nav and footer as the rest of the site (nav has no Webinars item)
- Asset paths are root-relative (`/assets/images/...`)
- Schema.org BlogPosting JSON-LD in head
- GA4 tag in head, same as every page
- Back link: `← Back to blog` → `/blog/`
- Article tag (category label in Dusty color)
- Pull quote style: left border Dusty, white background
- CTA box: dark olive background at bottom of article
- Date format: "Month YYYY" (e.g. "July 2026")
- Deliver edited posts as `index-blog-[post-slug].html` (see EC-CONTEXT.md, GitHub Workflow)

---

## Suggested Future Posts

These topics align with the brand voice and have not yet been written:

- "What completion rates actually tell you about your course (and what they don't)"
- "The five-second test: how to know if your course intro is losing people"
- "How to write a learning objective that actually means something"
- "Why your course needs a villain (and how to find yours)"
- "The anatomy of a lesson that creates real skill"
