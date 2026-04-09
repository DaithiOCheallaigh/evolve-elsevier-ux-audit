# Lovable Build Prompt — Evolve Elsevier UX Audit Report

## Purpose
Build an interactive UX heuristics presentation app for Elsevier. The app walks the Evolve product team through a dual-persona audit of evolve.elsevier.com/cs, covering 15 heuristic dimensions from two perspectives: Student and Educator.

---

## Brand & Design Spec
- Primary orange: #FF6B00
- White: #FFFFFF
- Dark grey: #2D2D2D
- Light grey background: #F5F5F5
- Success green: #1D9E75
- Warning amber: #EF9F27
- Danger red: #E24B4A
- Font: Inter (headings bold, body regular)
- All transitions: fade 300ms ease-in-out
- Keyboard navigation: left/right arrow keys advance slides
- Slide counter shown top-right throughout: "Slide X of 9"

---

## App Structure — 9 Slides

### Slide 1 — Title / Intro
- Full-screen hero with Elsevier orange top bar
- Title: "Evolve Portal UX Audit"
- Subtitle: "A heuristics review from the perspective of a Student and an Educator"
- Meta row: "Prepared by Lacuna Digital · April 2026 · evolve.elsevier.com/cs"
- Large "Begin Audit" CTA button in orange
- Elsevier logo top-left, Lacuna Digital attribution bottom-right

### Slide 2 — Context: The Three-Site Problem
- Heading: "One product. Three entry points. No clear path."
- Architecture diagram showing three boxes connected by arrows:
  - Box 1: "evolve.elsevier.com/cs" (Main Portal) — orange border
  - Box 2: "evolve.elsevier.com/studentlife" (Student Life) — blue border
  - Box 3: "evolve.elsevier.com/education" (Educator Hub) — teal border
  - External box: "elsevier.com" — grey border, dashed
  - Arrows between all four with labels: "Links off-site", "Redirects to portal", "No shared navigation"
- Annotation: "A user arriving at any entry point has no guaranteed path to their goal. This fragmentation is the root cause of most audit findings."

### Slide 3 — Methodology: 15 Heuristics
- Heading: "15 heuristic dimensions evaluated"
- 3x5 card grid, each card showing:
  - Icon (use a relevant emoji or lucide-react icon)
  - Heuristic name
  - One-line definition
- Cards:
  1. Landing Page UX — First impression and goal clarity on arrival
  2. Non-Verbal Communication — Visual cues, imagery, and tone
  3. Eye Tracking (Nielsen) — F-pattern and Z-pattern scan support
  4. The Fold — Critical content visibility without scrolling
  5. Directional Cues — Visual flow guiding the user journey
  6. White Space Cues — Intentional use of negative space
  7. Eye Direction Cue — Human gaze directing attention to CTAs
  8. Arrow / Linear Cues — Explicit directional indicators
  9. Encapsulation Cues — Grouping related content visually
  10. Attention Ratio — Single dominant action vs competing elements
  11. Paradox of Choice — Cognitive overload from too many options
  12. Principles of Landing Pages — Value prop, social proof, CTA hierarchy
  13. Form Audit — Friction, field count, progressive disclosure
  14. Checkout Abandonment — Barriers in the conversion flow
  15. Occam's Razor — Simplest solution principle applied to UX

### Slide 4 — Persona Selector
- Heading: "Choose a perspective"
- Two large side-by-side clickable cards (full height):
  - Left card — Student (blue accent #185FA5):
    - Large student icon
    - Title: "Student"
    - Description: "First-year healthcare student, access code in hand, arriving at the portal for the first time to access their course materials."
    - Avg score badge: "3.9 / 10"
    - CTA: "View Student Findings"
  - Right card — Educator (orange accent #FF6B00):
    - Large educator icon
    - Title: "Educator"
    - Description: "Nurse faculty member, evaluating Elsevier tools for adoption into their nursing programme and setting up student access."
    - Avg score badge: "3.3 / 10"
    - CTA: "View Educator Findings"
- Clicking either card does NOT change the slide — both persona scores are shown together in the findings slides. Instead, clicking highlights the chosen persona's scores throughout the rest of the deck.
- Default: show both. Include a toggle bar at the top of slides 5–8: "Viewing: Both | Student | Educator"

### Slide 5 — Per-Heuristic Findings (15 sub-slides, carousel within Slide 5)
This slide is itself a carousel — 15 panels, one per heuristic. Include:
- Progress bar at top showing position 1–15 with heuristic names
- Previous / Next navigation within this slide
- Each panel contains:
  - Heuristic name + category tag (e.g., "Navigation", "Visual Design", "Conversion")
  - Definition in 1 sentence (italic, grey)
  - Screenshot section: a placeholder image box labelled with the filename from /public/screenshots/ (e.g. "01-homepage-role-selector.jpg"), with a red dashed annotation overlay in the corner containing the key issue text
  - Score row: Student score pill + Educator score pill, colour coded (red=1-3, amber=4-6, green=7-10)
  - "What we observed" paragraph
  - "Why it matters" paragraph
  - "Recommendation" callout box with orange left border

Use these exact scores and content per heuristic:

**1. Landing Page UX**
- Student: 3 | Educator: 3
- Screenshot: 01-homepage-role-selector.jpg
- Observed: The portal presents three separate sub-sites as potential entry points with no unified homepage. The /cs/ hero is a rotating image carousel with two CTA buttons but no supporting value proposition copy.
- Matters: First impressions are formed in under 500ms. Without a clear value proposition above the fold, high-intent users bounce before understanding what the portal offers.
- Recommendation: Consolidate all three sub-sites behind a single role-detected landing page. Show a clear, persona-matched value proposition immediately on load.

**2. Non-Verbal Communication**
- Student: 4 | Educator: 3
- Screenshot: 09-studentlife-hero.jpg
- Observed: The StudentLife hero uses a 3D anatomical render rather than photography of real students. The Education page has almost no imagery at all — just a text-heavy link list.
- Matters: Non-verbal cues (photography, colour, iconography) communicate trust and relevance faster than text. Generic 3D renders do not create the aspirational connection healthcare students need.
- Recommendation: Replace 3D renders with contextual photography of real nursing students. The educator page needs at minimum one human face to establish trust.

**3. Eye Tracking (Nielsen F-Pattern)**
- Student: 4 | Educator: 3
- Screenshot: 02-student-store-above-fold.jpg
- Observed: The student store page has a hero, then a search bar, then the access code form — but these are not laid out along the natural F-pattern scan zones. The most critical action (redeem code) sits in the lower-left quadrant of the secondary scan band.
- Matters: Users read web pages in an F-pattern: strong horizontal scan at the top, weaker scan lower down, then a vertical scan of the left edge. Content placed outside these zones is frequently missed.
- Recommendation: Move the access code redemption field to the top horizontal scan zone — immediately below the hero, spanning full width.

**4. The Fold**
- Student: 5 | Educator: 4
- Screenshot: 05-registration-empty.jpg
- Observed: The registration page loads with two radio buttons (Student / Faculty) and then a full viewport of white space. The actual form fields only appear after role selection — and even then, they render below an unexplained white void of approximately 400px.
- Matters: Content below the fold has significantly lower engagement. A page that appears empty on load causes users to assume it is broken and abandon.
- Recommendation: Render the registration form fields immediately on load using the most common role (Student) as default, with a role switcher at the top. Investigate and fix the white void rendering issue.

**5. Directional Cues**
- Student: 4 | Educator: 3
- Screenshot: 07-training-page.jpg
- Observed: The StudentLife training page uses large decorative chevron arrows in the hero but these point left — away from the content — and have no interactive function. There is no step-based onboarding flow visible anywhere.
- Matters: Directional cues are one of the most powerful tools for reducing time-to-action. Decorative arrows that do not correspond to a user action actively mislead.
- Recommendation: Replace decorative arrows with a numbered step flow: "1. Create account → 2. Redeem your code → 3. Access your content". This alone would reduce support volume significantly.

**6. White Space Cues**
- Student: 6 | Educator: 5
- Screenshot: 10-blank-white-void.jpg
- Observed: Multiple pages contain 500–2000px of unrendered white space between sections. This is not intentional negative space — it is broken lazy-loading. On the StudentLife homepage, the page reports a scroll height of 5,329px but the vast majority is empty.
- Matters: Intentional white space improves readability and signals structure. Unintentional white space destroys trust — users assume the page is broken or incomplete.
- Recommendation: Audit and fix all lazy-loading implementations site-wide. Sections should render on scroll-approach, not leave a void. This is a P0 technical fix.

**7. Eye Direction Cue**
- Student: 3 | Educator: 2
- Screenshot: 09-studentlife-hero.jpg
- Observed: No human photography is used anywhere on the StudentLife or Education landing pages in a way that directs gaze toward a CTA. The 3D anatomical render has no directional gaze. The educator page has no human imagery at all.
- Matters: Human eye direction is one of the most evidence-backed attention-directing techniques in web UX. A person looking toward a CTA measurably increases clicks on that CTA.
- Recommendation: Use photography of a student or nurse looking toward or gesturing at the primary CTA. This is a low-cost, high-impact change.

**8. Arrow / Linear Cues**
- Student: 4 | Educator: 3
- Screenshot: 03-faculty-store-nav.jpg
- Observed: Arrow cues exist only in the carousel navigation (left/right arrows) and in external link icons (↗). There are no linear flow indicators showing users their progression through a task or journey.
- Matters: Linear cues reduce cognitive load by showing users where they are and what comes next. Without them, every page feels like an isolated destination with no path forward.
- Recommendation: Add a persistent breadcrumb and progress indicator to all multi-step flows. For the registration flow specifically, a "Step 1 of 3" indicator would reduce abandonment.

**9. Encapsulation Cues**
- Student: 5 | Educator: 4
- Screenshot: 02-student-store-above-fold.jpg
- Observed: The student store groups some content in boxes (the welcome message, the access code form) but the HESI Secured Exams section sits in a bare column with no visual container. The educator solutions section is a raw link list with no card or border.
- Matters: Encapsulation (cards, borders, background fills) signals that related items belong together and helps users parse information zones rapidly.
- Recommendation: Apply consistent card-based encapsulation to all content modules. Every distinct information zone should have a visual boundary.

**10. Attention Ratio**
- Student: 3 | Educator: 3
- Screenshot: 04-login-form.jpg
- Observed: The login page footer contains 20+ links across four columns (My Evolve, Catalog, Get Support, Learn More). These compete equally for attention with no visual hierarchy. The student store navigation offers 5 top-level items plus icon buttons plus a role switcher.
- Matters: The ideal attention ratio for a conversion page is 1:1 — one page, one goal. Every additional clickable element reduces conversion on the primary action.
- Recommendation: Strip the login page footer to 3–4 links maximum. Apply visual weight hierarchy (size, colour, contrast) to ensure the primary action always dominates.

**11. Paradox of Choice**
- Student: 2 | Educator: 3
- Screenshot: 08-training-nav-19-items.jpg
- Observed: The Training dropdown navigation on StudentLife lists 19 distinct tools in a flat alphabetical list with no grouping, no descriptions, and no visual differentiation. A first-time student has no way to know which of these 19 tools is relevant to them.
- Matters: Barry Schwartz's paradox of choice: beyond 7 (plus or minus 2) options, decision-making quality degrades and users often choose nothing. 19 ungrouped options is three times the cognitive load limit.
- Recommendation: Group the 19 tools into 4 categories: Assessment & Exams, Clinical Simulations, Learning & Study Resources, and Portal & Technical. Use a megamenu format with category headers.

**12. Principles of Landing Pages**
- Student: 4 | Educator: 3
- Screenshot: 11-education-homepage.jpg
- Observed: The education landing page has a headline and one off-site CTA. There is no visible outcome data, no testimonials, no feature list, and no demonstration of the product. The page is shorter than a typical mobile screen when the hero is collapsed.
- Matters: Effective B2B landing pages require: a clear value proposition, supporting evidence (data or social proof), a demonstration of value, and a low-friction next step. None of these are present.
- Recommendation: Rebuild the educator landing page to include: 3 outcome statistics, 1 faculty testimonial, a feature comparison snapshot, and a "Request a demo" or "Talk to your rep" primary CTA above the fold.

**13. Form Audit**
- Student: 4 | Educator: 4
- Screenshot: 06-registration-form.jpg
- Observed: The student registration form requires: first name, last name, email, confirm email, phone, password, confirm password, institution country, institution state, institution name, programme type, year of graduation — 12 fields before account creation. No progressive disclosure is used. The login form uses a staged reveal (email first, then password) which is good but the "Get a one-time code" option is visually de-emphasised.
- Matters: Each additional form field reduces completion rates by approximately 11%. A 12-field registration form is likely losing 60–80% of users who start it. Healthcare students are often on mobile with limited time between lectures.
- Recommendation: Reduce registration to 4 fields: email, password, role, institution. Collect remaining profile data progressively after first login. Add inline field validation.

**14. Checkout Abandonment**
- Student: 3 | Educator: 4
- Screenshot: 02-student-store-above-fold.jpg
- Observed: The access code redemption flow requires: (1) navigate to the correct portal, (2) sign in or create an account (12-field form), (3) locate the redemption field, (4) enter the code, (5) confirm access. Elsevier's own support documentation includes a dedicated video tutorial because the flow is non-obvious. The access code format hint uses monospace inline code styling that is difficult to read on mobile.
- Matters: Every additional step in a conversion flow increases abandonment. A 5-step flow to access already-purchased content is a retention risk — students who cannot access their materials on day one are likely to seek alternatives or disengage.
- Recommendation: Surface the access code redemption field as the #1 priority action for unauthenticated users arriving at the student store. Move it above the search bar and make it the first thing a new visitor sees.

**15. Occam's Razor**
- Student: 2 | Educator: 2
- Screenshot: 01-homepage-role-selector.jpg
- Observed: The Evolve ecosystem consists of: the main portal (/cs/), a WordPress student life site, a WordPress education site, external elsevier.com product pages, the HESI sub-system, VitalSource eBook integration, Canvas/LMS integrations, and a dedicated support centre. A student completing their first week of nursing school must navigate across at least 3–4 of these to access their materials.
- Matters: Occam's Razor applied to UX: the simplest solution that achieves the goal is the best solution. Complexity accumulates over time and is rarely removed deliberately. This ecosystem has grown without pruning.
- Recommendation: Conduct a full information architecture audit with a goal of consolidating to one authenticated portal experience. The public-facing sites (/studentlife, /education) should serve as marketing pages that funnel to the single portal — not parallel destinations.

### Slide 6 — Spider Diagram: Comparative Radar
- Heading: "Score overview — all 15 heuristics"
- Subtitle: "Scores out of 10. Lower is worse."
- Recharts RadarChart component with two datasets:
  - Student: [3,4,4,5,4,6,3,4,5,3,2,4,4,3,2] — blue fill rgba(55,138,221,0.25), blue stroke #378ADD
  - Educator: [3,3,3,4,3,5,2,3,4,3,3,3,4,4,2] — orange fill rgba(255,107,0,0.2), orange stroke #FF6B00
- Labels (in order): Landing UX, Non-Verbal, Eye Tracking, The Fold, Directional, White Space, Eye Direction, Arrow Cues, Encapsulation, Attention, Choice Paradox, Landing Principles, Form Audit, Checkout, Occams Razor
- Custom legend below chart: blue square = Student (avg 3.9), orange square = Educator (avg 3.3)
- Four summary metric cards below the chart in a 2x2 grid:
  - Student Average: 3.9/10
  - Educator Average: 3.3/10
  - Critical failures (score 1-3): 6
  - Shared pain points: 11

### Slide 7 — Priority Recommendations
- Heading: "8 priority recommendations"
- Left-bordered cards, three severity tiers:

**Critical (red border #E24B4A):**
1. Consolidate the three-site architecture — Unify /cs/, /studentlife/, and /education/ behind one role-detected portal. A visitor arriving at the wrong entry point has no clear path to their goal.
2. Collapse the 19-item training navigation — Group into 4 categories with progressive disclosure. 19 flat options exceeds cognitive load limits by 3x.
3. Redesign the access code redemption flow — Surface code redemption as the #1 priority action for new unauthenticated students. The current 5-step flow causes measurable day-one abandonment.

**Major (amber border #EF9F27):**
4. Add value proposition and social proof to educator landing — The current page has one off-site CTA and no evidence of outcomes. Rebuild with 3 stats, 1 testimonial, and a demo CTA.
5. Fix the blank white void rendering bug — Multiple pages show 400–2000px of empty space between sections. This is a P0 trust issue — users assume the page is broken.
6. Apply directional and encapsulation cues — Add numbered step flows to all onboarding journeys. Apply card-based encapsulation consistently across all content modules.

**Moderate (green border #1D9E75):**
7. Reduce registration form from 12 to 4 fields — Collect profile data progressively post-login. Each removed field improves completion rates by ~11%.
8. Add eye-direction cues in hero imagery — Replace 3D renders with photography of students/nurses whose gaze directs attention toward the primary CTA.

### Slide 8 — Full Scorecard Table
- Heading: "Complete score breakdown"
- Full-width table with columns: Heuristic | Student Score | Educator Score | Delta | Severity
- Severity column uses colour-coded pills: Critical (red, score avg 1-3), Major (amber, 3-5), Moderate (green, 5-7)
- Rows (in order):
  1. Landing Page UX | 3 | 3 | 0 | Critical
  2. Non-Verbal Communication | 4 | 3 | -1 | Critical
  3. Eye Tracking | 4 | 3 | -1 | Critical
  4. The Fold | 5 | 4 | -1 | Major
  5. Directional Cues | 4 | 3 | -1 | Critical
  6. White Space | 6 | 5 | -1 | Major
  7. Eye Direction | 3 | 2 | -1 | Critical
  8. Arrow Cues | 4 | 3 | -1 | Critical
  9. Encapsulation | 5 | 4 | -1 | Major
  10. Attention Ratio | 3 | 3 | 0 | Critical
  11. Paradox of Choice | 2 | 3 | +1 | Critical
  12. Landing Principles | 4 | 3 | -1 | Critical
  13. Form Audit | 4 | 4 | 0 | Major
  14. Checkout Abandonment | 3 | 4 | +1 | Critical
  15. Occams Razor | 2 | 2 | 0 | Critical
- Footer row: Averages | 3.9 | 3.3 | -0.6 | —

### Slide 9 — Next Steps
- Heading: "Recommended action plan"
- Three column cards:

  **Quick wins — 0 to 4 weeks** (orange accent)
  - Fix blank white void rendering bug across all three sub-sites
  - Move access code redemption field above the fold on student store
  - Add eye-direction photography to StudentLife hero
  - Collapse Training nav to 4 grouped categories

  **Medium-term — 1 to 3 months** (blue accent)
  - Reduce registration form to 4 fields with progressive profile completion
  - Rebuild educator landing page with value prop, stats, testimonial, demo CTA
  - Add numbered step onboarding flow to all first-time user journeys
  - Apply consistent card-based encapsulation across all page templates

  **Strategic — 3 to 6 months** (teal accent)
  - Commission information architecture audit with goal of single-portal consolidation
  - Define and implement a unified design system across all three sub-sites
  - Instrument conversion funnel analytics from landing to content access
  - Conduct usability testing with 5 nursing students and 5 faculty members

- Final callout box: "Prepared by Lacuna Digital — lacunadigital.io | For more information contact dave@lacunadigital.io"

---

## Technical Requirements

- Framework: React with Tailwind CSS
- Charts: Recharts (RadarChart for slide 6)
- Icons: lucide-react
- Screenshots: Load from /public/screenshots/ with filenames 01-homepage-role-selector.jpg through 11-education-homepage.jpg. If a screenshot is missing, show a grey placeholder box with the filename as label.
- Navigation: Previous/Next buttons on every slide, keyboard arrow keys, slide counter "Slide X of 9" top-right
- Slide transitions: CSS fade transition 300ms
- All scores hardcoded as specified above — no API calls
- Mobile responsive — all slides must work on tablet (768px+)
- Print-friendly: add a "Print / Export PDF" button on the final slide that triggers window.print()
- Persona toggle: persistent toggle bar on slides 5–8 allowing "Both | Student | Educator" view
- Color-coded score pills: 1-3 = red background, 4-6 = amber background, 7-10 = green background
