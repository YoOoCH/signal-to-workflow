# Design

## Source of truth
- Status: Active
- Last refreshed: 2026-06-22
- Primary product surfaces: `index.html`, `styles.css`
- Evidence reviewed:
  - `index.html`: candidate homepage and portfolio reel.
  - `styles.css`: shared visual system.
  - `assets/water-dispatch-*.jpg`: water dispatch / digital twin screenshots.
  - `assets/industrial-*.png`, `assets/energy-*.png`, `assets/community-*.png`: industry visualization screenshots.
  - `ai-writing-workflow.html`: AI workflow experiment detail page.
  - External reference: `https://www.siena.film/` for cinematic portfolio tone, black canvas, image-first rhythm, warm ivory type, and editorial project treatment.

## Brand
- Personality: cinematic, field-aware, quiet, sharp, credible.
- Trust signals: real screenshots as film stills, project numbering, role-fit metadata, resume/contact access, restrained motion.
- Avoid: generic AI SaaS landing page, beige resume page, cyberpunk dashboard overload, random gradient blobs, noisy neon, icon decoration, fake startup copy, abstract self-praise.

## Product goals
- Goals:
  - Make Yang Chenghui feel memorable as an AI product / digital twin / ToB delivery candidate.
  - Turn project screenshots into a cinematic portfolio reel instead of ordinary dashboard thumbnails.
  - Show front-end taste through motion, layout, image handling, and responsive craft.
- Non-goals:
  - Do not imitate Siena content or brand.
  - Do not make the page hard to scan for HR.
  - Do not hide resume/contact.
- Success signals:
  - First viewport has film-poster impact.
  - Project evidence feels curated.
  - The page is distinctive without looking gimmicky.
  - Mobile still reads clearly.

## Personas and jobs
- Primary personas: HR, product lead, delivery lead, digital twin / industrial software hiring manager.
- User jobs: decide interview fit, inspect evidence, open resume, contact candidate.
- Key contexts of use: BOSS直聘, WeChat mobile browser, Chrome desktop, interview pre-read.

## Information architecture
- Primary navigation: Fit, Portfolio, Method, AI Note, Resume.
- Core routes/screens:
  - Homepage: cinematic candidate dossier.
  - AI workflow detail: product-thinking artifact.
- Content hierarchy:
  1. Hero: name, role, cinematic project still, metadata.
  2. Fit: three reasons to interview.
  3. Portfolio reel: water, industrial, energy, community, AI workflow.
  4. Method: workflow from business field to product delivery.
  5. Business system case: ERP automation.
  6. Contact.

## Design principles
- Principle 1: Screenshots are film stills. Give them scale.
- Principle 2: Use typography like a film catalogue: title, quote, metadata, numbering.
- Principle 3: Motion is editorial: slow reveal, image fade, slight zoom, subtle grain.
- Tradeoffs:
  - Dark cinematic layouts can feel premium but need high text contrast.
  - Large images add page weight but are the core proof.
  - Motion should be visible enough to show front-end craft, but not become a demo reel.

## Visual language
- Color:
  - Base: black / near-black.
  - Text: warm ivory.
  - Secondary text: muted warm gray.
  - Accent: restrained archival gold.
  - Avoid dominant neon green/cyan.
- Typography:
  - Modern Chinese sans display for hero and project titles; editorial, but not poster-sized.
  - System sans for body and metadata.
  - Uppercase small labels with generous spacing.
- Spacing/layout rhythm:
  - Full-height hero.
  - Wide cinematic image frames.
  - Alternating image/text project records.
  - Dense metadata rows, not decorative cards.
- Shape/radius/elevation:
  - Mostly square or very small radius.
  - Minimal shadows.
  - Use overlays and contrast instead of card piles.
- Motion:
  - Hero still fades and slowly scales in.
  - Scroll reveal for project records.
  - Hover zoom on stills.
  - Subtle grain overlay.
  - Respect `prefers-reduced-motion`.
- Imagery/iconography:
  - No stock images.
  - No decorative SVG illustrations.
  - Real project screenshots only.

## Components
- Existing components to reuse: header, buttons, lightbox, image links.
- New/changed components:
  - `hero-still`: cinematic screenshot panel.
  - `film-meta`: role/contact/project metadata strip.
  - `case`: large project record with still, number, and role-fit metadata.
  - `proof-strip`: three concise principles.
  - `reveal-item`: scroll reveal behavior.
- Variants and states:
  - Image links reveal “查看大图” on hover/focus.
  - Project stills gently zoom on hover.
  - Reveal items fade upward on scroll.
- Token/component ownership: CSS custom properties in `styles.css`.

## Accessibility
- Target standard: strong contrast, semantic HTML, keyboard-friendly links/lightbox.
- Keyboard/focus behavior: existing lightbox focus and Escape close behavior must remain.
- Contrast/readability: body text must be readable on black.
- Screen-reader semantics: meaningful alt text for screenshots; decorative layered images use empty alt.
- Reduced motion and sensory considerations: animation reduced under `prefers-reduced-motion`.

## Responsive behavior
- Supported breakpoints/devices: desktop 1280+, tablet, mobile 390px.
- Layout adaptations:
  - Hero becomes image + text stack on mobile.
  - Nav links hide on mobile.
  - Project records become single-column.
  - Metadata wraps cleanly.
- Touch/hover differences: hover effects are additive; all information is always visible.

## Interaction states
- Loading: text should be useful before images finish loading.
- Empty: N/A.
- Error: broken image paths are unacceptable.
- Success: user can scan fit, inspect project stills, open resume, or email quickly.
- Disabled: N/A.
- Offline/slow network: static HTML remains readable.

## Content voice
- Tone: cinematic but concrete; confident, not inflated.
- Terminology: 数字孪生, 水利水调, 工业可视化, ToB交付, ERP自动化, AI工具链, Demo, PRD, 原型, 数据口径, 验收.
- Microcopy rules:
  - Say what was structured, coordinated, designed, or delivered.
  - Prefer project-specific portfolio language.
  - Avoid “赋能”, “颠覆”, “AI时代”, and generic enthusiasm.

## Implementation constraints
- Framework/styling system: plain HTML/CSS/vanilla JS.
- Design-token constraints: use variables in `styles.css`; no new package dependency.
- Performance constraints: GitHub Pages static hosting; avoid remote assets and heavy JS.
- Compatibility constraints: modern Chrome/Edge/Safari mobile.
- Test/screenshot expectations:
  - Validate no broken asset refs.
  - Validate no horizontal overflow on desktop/mobile.
  - Validate images load.
  - Validate reveal/lightbox does not break content.

## Open questions
- [ ] 是否补充每个项目中“我负责的部分”一句话 / owner: Yang / impact: stronger recruiter trust.
