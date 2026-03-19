# Creative Brief — jondallasai.com

**Date**: 2026-03-18
**Project**: Personal website for Jon Dallas — AI consultant, developer, philosopher

---

## 1. Project Overview

A personal professional website for Jon Dallas (Jon Dallas AI, LLC). Jon builds custom AI tools for SMBs — reducing costs, automating workflows, and delivering measurable ROI. He's also the founder of Real Talk Philosophy, a TEDx speaker, and a genuine human being who has lived in Vietnam, Zimbabwe, and Thailand.

The site's job: **establish trust, show real results, give people a reason to reach out.**

The tone that makes Jon stand out: technical credibility *plus* warmth and genuine curiosity. Most AI consultant sites are cold and buzzwordy. Jon's should feel like a smart friend who actually knows their stuff.

---

## 2. Audience

**Primary**: SMB founders, startup operators, and content/marketing leads who know they should be using AI but don't know how to do it well. They've tried ChatGPT, felt underwhelmed, and want someone who can actually build something.

**Secondary**: Potential collaborators, referrers, employers, and fellow builders in the Coda/AI space.

---

## 3. Goals

1. Convert visitors to consultation bookings (Calendly) or newsletter subscribers
2. Demonstrate capability through case studies (not claims)
3. Establish Jon as a trustworthy, thoughtful voice on practical AI — not hype
4. Build an ongoing content relationship via blog and scrollystories

---

## 4. Visual Identity

**Palette:**
- Background: `#F7F5F1` (warm off-white / cream)
- Primary text: `#1A1917` (near-black, warm)
- Accent: `#C17B3B` (warm amber / terracotta) — primary CTA color
- Secondary accent: `#5C7A5A` (sage green) — secondary highlights
- Muted: `#8C8880` (warm gray) — metadata, captions, labels
- White: `#FFFFFF` for cards and clean sections

**Typography:**
- Headings: `DM Serif Display` (Google Fonts) — elegant, warm, human
- Body: `Inter` (Google Fonts) — clean, readable, modern
- Mono/code: `JetBrains Mono` — for any technical snippets
- Scale: 16px base, 1.6 line-height body

**Photography style:**
- Real photos of Jon (provided in `images/user/`)
- Editorial workspace photography (generated)
- No stock-photo smiling-at-camera corporate shots
- Candid, human, slightly imperfect is better than polished and fake

**Illustration/graphics:**
- Warm-toned abstract AI/data network illustrations for backgrounds
- Flat/minimal icons via Phosphor Icons (CDN)
- No gradients for their own sake — use sparingly for CTAs only

**Overall feel**: Like if Substack and a design-forward personal essay site had a baby. Clean whitespace, beautiful type, warm photography, real content.

---

## 5. Site Structure

### 5.1 Homepage (`index.html`)
- **Hero**: Full-viewport. Jon's photo (IMG_2555 — rooftop, direct gaze) on right, headline + subhead + CTA on left. Background: cream. Subtle.
  - Headline: *"I build AI tools that actually work."*
  - Subhead: *"Custom AI systems for SMBs — real results, no buzzwords. Based in Chiang Mai, working globally."*
  - CTA: "Book a Free Consultation" (Calendly) + "Read the Blog"
- **Results bar**: 3 stat callouts — 87% cost reduction / 80% time savings / 450 articles in 48 hrs
- **What I Do**: 3 service areas (AI Agents, Coda Systems, SEO Automation) — icon + 2 sentences each
- **Case Studies**: 3 cards — Resume Rewriter, SEO Content Engine, Property Description Generator
- **Blog Preview**: 3 most recent posts
- **About teaser**: 2-column — photo (hiking, warm) + 4-sentence bio + link to About page
- **Newsletter CTA**: Simple Coda-powered signup — "Practical AI, weekly." First name + email only.
- **Footer**: Links, Calendly, social (LinkedIn, GitHub)

### 5.2 Blog Index (`blog/index.html`)
- Header: "Practical AI" — tagline: *"No hype. No fluff. Just what actually works."*
- Post cards: hero image, title, 1-sentence teaser, date, read-time estimate, category tag
- Categories: Practical Tips / News & Takes / Case Studies / Philosophy & AI
- Each post gets its own subfolder: `blog/<slug>/index.html`

### 5.3 Blog Post Template (`blog/<slug>/index.html`)
- Full-width hero image
- Title, date, read time, category
- Body: rich prose, inline images every 1-2 paragraphs, pull quotes
- Author card at bottom
- Newsletter signup embed at bottom (Coda form)
- "Related posts" — 2 cards

### 5.4 Case Studies Index (`case-studies/index.html`)
- Header: "Real Results"
- 3 cards with stats prominently displayed

### 5.5 Case Study Pages (`case-studies/<slug>/index.html`)
- Client challenge → Solution → Tech stack → Results
- Structured like a scrollystory (advance-click) — 6-8 panels per case study
- Stats displayed as large callouts
- Screenshots/visuals of the system in action where available
- Testimonial quote if available

### 5.6 Scrollystories (`stories/index.html` + individual stories)
- **Format**: Full-screen advance-click panels — not scroll, keyboard/click to advance
- **Navigation**: Left/right click zones, keyboard arrows, progress dots at bottom
- **Transition**: Smooth fade or slide between panels
- **First story**: "How I Built an AI System That Writes 450 Articles in 48 Hours"
  - ~10 panels telling the story arc: Client problem → My approach → The architecture → The result → Key lessons
  - Each panel: full-screen background image + headline + 2-3 sentence narrative

### 5.7 About (`about/index.html`)
- Hero: warm photo (IMG_0834 — sunset smile)
- Bio: Real story. Not just skills list. Covers: built AI tools for clients, started Real Talk Philosophy, lived across the world, now in Chiang Mai with Jess and Bodhi, building things that matter.
- Skills section: Technical stack, well-organized
- Timeline: Key life/career moments (visual, horizontal scroll on mobile)
- Real Talk Philosophy mention — brief, linked
- CTA: "Want to work together?"

### 5.8 Contact (`contact/index.html`)
- Calendly embed (30-min consultation)
- Simple contact form (name, email, message — powered by Coda or mailto fallback)
- Newsletter signup
- LinkedIn + GitHub links

---

## 6. Interactive Elements

### 6.1 Scrollystory Advance Navigation
- **Location**: Stories section, case study pages
- **Format**: Full-screen panels, click to advance
- **Controls**: Click anywhere right = next, click anywhere left = prev. Keyboard: → ← arrows. Touch: swipe left/right.
- **Progress indicator**: Dots at bottom center
- **Panel types**:
  - `title` — large type, minimal, dramatic
  - `stat` — big number/result, supporting text
  - `narrative` — image background + prose overlay
  - `quote` — testimonial or pull quote, centered
  - `tech` — code/system diagram, dark background

### 6.2 Newsletter Signup
- **Location**: Homepage, blog post footer, contact page
- **Backend**: Coda.io table via Coda API (Jon's own setup)
- **Fields**: First name + email
- **Behavior**: Submit → inline success message, no page reload
- **Note**: Jon will configure the Coda API endpoint — placeholder `POST` target in the HTML with `id="newsletter-form"` and a `data-coda-endpoint` attribute for easy swap-in

### 6.3 Contact Form
- **Location**: Contact page
- **Fields**: Name, email, message, optional: "What kind of project?"
- **Behavior**: Same pattern as newsletter — POST target configurable
- **Fallback**: mailto link if JS fails

---

## 7. First Scrollystory: "How I Built an AI System That Writes 450 Articles in 48 Hours"

**Audience**: SMB owners, content marketers, anyone curious about AI content at scale
**Angle**: Behind-the-scenes engineering story — how a real production system works
**Tone**: Smart, honest, a bit irreverent — Jon tells stories well

**Panel outline**:
1. **Title panel** — "450 Articles. 48 Hours. Here's Exactly How." (image: `blog-450-articles.jpg`)
2. **The Client** — Zimbabwe's largest property portal. Good traffic. Bad content strategy. (image: abstract map/Africa)
3. **The Problem** — Ranked 2nd-6th on Google for 4,000+ keywords. No SEO direction. No EEAT. No system. (image: `ai-workflow-abstract.jpg`)
4. **The Old Way** — One freelancer. One article. Two weeks. $200 each. (image: documents pile)
5. **The Architecture** — 6-step AI pipeline: keyword analysis → competitor scrape → DB query → EEAT assembly → generation → QA (image: workflow diagram)
6. **The Stack** — Coda + Claude + GSC + ahrefs + SerpAPI + Google Maps + custom DB
7. **The Result** — 450 articles in 48 hours. Avg +2 Google ranking in 6 months. (stat panel)
8. **What Made It Work** — Not just prompting ChatGPT. Proprietary data. Dynamic guidelines. Real QA. (narrative)
9. **The Quote** — *"Genuinely amazing. Jheesh, well done. And thank you very much. Super chuffed with this."* — Client
10. **The Lesson** — The best AI content isn't faster ChatGPT. It's a system that knows things your competitors don't.

---

## 8. First Blog Posts (to be written)

### Post 1: The 450 Articles Story (long-form companion to the scrollystory)
Full written version of the above — more technical, more honest, good for SEO.
Category: Case Studies

### Post 2: "Why Most AI Projects Fail (It's Not the Technology)"
Takes: most AI failures are prompt failures, not model failures. Argues for system design over prompting tricks.
Category: Practical Tips

### Post 3: "The Coda.io Secret Most Developers Don't Know"
Jon's actual workflow — why he prototypes in Coda before coding, and why clients get better results faster.
Category: Practical Tips

---

## 9. Image Assignment Map

| Page / Section | Image File | Source |
|---|---|---|
| Homepage hero (bg) | `hero-workspace.jpg` | Generated |
| Homepage hero (Jon) | `IMG_2555.jpeg` | User |
| Homepage about teaser | `nwdn_file_temp_1610431376030.jpg` | User |
| Blog index placeholder | TBD Phase 3 | — |
| Blog: 450 articles (hero) | `blog-450-articles.jpg` | Generated |
| Case study: Resume Rewriter | `case-study-before-after.jpg` | Generated |
| Case study: Property Description | `case-study-chrome-extension.jpg` | Generated |
| Case study: SEO Engine | `ai-workflow-abstract.jpg` | Generated |
| About hero | `IMG_0834.JPG` | User |
| About body | `IMG_0243.JPG` | User (film, artistic) |
| Stories hero (first story) | `blog-450-articles.jpg` | Generated |
| Workshop image | `about-workshop.jpg` | Generated |

---

## 10. Technical Specs

- Multi-page: one HTML file per page in `output/website/<slug>/index.html`
- All CSS/JS inline per page
- Google Fonts loaded via `<link>` in `<head>`
- Icons: Phosphor Icons via CDN `<script>`
- No build system — static HTML, works offline
- Mobile-first: viewport meta, touch targets 44px+, no horizontal scroll
- Newsletter form: `id="newsletter-form"` with `data-coda-endpoint=""` attribute — Jon fills in endpoint
- Open Graph meta on every page
- Image paths: `../../images/final/<filename>` (relative from `output/website/<slug>/`)
