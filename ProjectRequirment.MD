<!-- Project overview: this file documents the portfolio's history, current implementation, and publishing workflow. -->
# Haran — Indie Hacker Portfolio

A responsive, single-page personal portfolio for Haran Naresh. The site presents a hero introduction, biography, education and experience timeline, skills, a contact chat demo, social links, and a footer.

> **Documentation comment:** This document describes the implementation currently in the project folder. Personal details and external profile URLs are provided by the site owner.

<!-- Evolution comment: the project grew from a minimal header and unfinished hero into a styled, multi-section portfolio. -->
## Project evolution

### Initial scaffold

- Started as a small HTML page with a header and navigation items.
- The first hero draft contained a greeting and an unfinished introduction paragraph.
- The stylesheet was empty, and the HTML referenced `style.css` even though the project stylesheet was named `Styles.CSS`.

### Portfolio build-out

- Added the dark, blue-accented visual design, responsive layout, portrait frame, animated typewriter greeting, and hero calls to action.
- Expanded the page into About Me, My Journey, Skills, Contact, and footer sections.
- Added a burger menu with in-page section links and a “Let’s Talk” email link.
- Added the visual chat demo and linked social profiles.
- Replaced the initial illustrative hero avatar with the owner's supplied photo and added supplied images to the About and Journey sections.
- Added the “Investigative Creator” technology profile, the Zustpe internship document link, and an SVG favicon matching the H. wordmark.

### Current content

- Biography and interests, including competitive maths, language learning, music, reading, pop culture, and coding.
- Education, current law studies, technology fellowship, fintech internship, content creation, recognition, and future goals.
- Four skills cards: Technology, Law, Tools, and Content creation.
- Investigative Creator profile with its supplied image and descriptive text.
- Seven contact destinations: Email, LinkedIn, Instagram, GitHub, Reddit, YouTube, and Substack.

<!-- Structure comment: keep HTML, CSS, favicon, and referenced image assets together in the deploy directory. -->
## Project files

```text
Personal Portfolio Website/
├── Index.HTML                           # Page markup, content, and small inline interactions
├── Styles.CSS                           # Layout, colors, animation, and responsive styles
├── favicon.svg                          # Browser tab icon based on the H. wordmark
├── Haran-Portrait.jpg                   # Hero portrait photograph
├── Haran-Illustration.jpg               # About section illustration
├── Learning-Landscape.jpg               # Journey banner image
├── Tech-Type-Investigative-Creator.png  # Investigative Creator profile image
├── Portrait.SVG                         # Original illustrated avatar; no longer used by the hero
└── ProjectRequirment.MD                 # This technical documentation
```

File paths in HTML are relative to `Index.HTML`. Keep the referenced images, favicon, and stylesheet beside the HTML file unless you also update their paths.

<!-- Stack comment: this is a static site; there is no app framework, package manager, build step, or server-side code. -->
## Technology and architecture

- **HTML5** provides semantic page structure and content.
- **CSS3** provides the dark visual theme, grid/flex layouts, hover states, animations, and responsive breakpoints.
- **Vanilla JavaScript** handles the typewriter, mobile/desktop burger-menu interaction, local chat rendering, chat input resizing, and current footer year.
- **Google Fonts** are requested from Google Fonts using a CSS `@import` for DM Sans and Space Grotesk. The generic `sans-serif` fallbacks remain available if the remote fonts cannot load.
- The site has no build tooling, package dependencies, database, server, form backend, analytics, or automated test suite configured.

To change site content, edit the HTML. To change visual design, edit the CSS variables and selectors in `Styles.CSS`. No compilation is necessary.

<!-- Design comment: the mobile layout is implemented in CSS and does not require a separate mobile page. -->
## Page sections and behavior

### Header and navigation

- The H. wordmark links to `#home`.
- Desktop displays section links and the “Let’s Talk” email link inline; the burger button is hidden.
- On screens at or below `760px`, the desktop links are hidden and the burger button opens `#site-menu`.
- The burger button reports its open state using `aria-expanded`.
- Navigation links scroll to `#home`, `#about`, `#journey`, `#skills`, and `#contact`.
- “Let’s Talk” opens a `mailto:` link to `harannaresh2004@gmail.com` on desktop and in the mobile menu.
- Selecting a menu link or pressing Escape closes the menu.

### Home / hero

- Displays the “Indie Hacker” heading, greeting, short biography, and profile photo.
- The typewriter animates “Hi, I'm Haran” when motion is allowed.
- The scroll cue links to About Me; the hero buttons link to Contact and Skills.
- The portrait uses `Haran-Portrait.jpg`, cropped to fit its framed presentation.

### About Me

- Includes the owner-provided biography and the “An Absolute Learner / Learning Machine” statement.
- Displays the supplied illustrated portrait, hobby chips, and leisure interests.

### My Journey

- Displays `Learning-Landscape.jpg` as a banner above the alternating timeline.
- Timeline entries cover the BBA, second-year LL.B. (Hons.) studies, NxtWave learning fellowship, Zustpe fintech internship, SpectrumSpectator content creation, awards, and future plans including The Deal Desk.
- The Zustpe internship heading links to the supplied Google Drive document.
- Dates and institution names not supplied for the entries are not fabricated.

### Skills

- Four cards group Technology, Law, Tools, and Content creation.
- The “Investigative Creator” panel displays the supplied TechType image, creative interests, and owner-provided description.
- Content links point to the InnovateXer YouTube channel and The Deal Desk Substack.

### Contact

- The chat is a **front-end demonstration only**. Submitting a message appends it to the visible chat for the current page session.
- Chat messages are not sent to Haran, submitted to Google Forms, persisted, or stored by a backend. The UI explicitly tells visitors this.
- Social links connect to the provided public profiles. The email link opens the visitor's mail application.

### Footer

- Includes the H. wordmark, tagline, back-to-top link, and a year filled in by JavaScript.

<!-- Accessibility comment: preserve the visible focus/hover affordances, accessible labels, and reduced-motion behavior when changing interactions. -->
## Accessibility and motion

- The page uses landmarks (`header`, `nav`, `main`, `section`, and `footer`), section headings, image alternative text, and accessible names for controls.
- The burger menu uses `aria-expanded` and `aria-controls`; the chat messages use a live region.
- CSS includes a `prefers-reduced-motion` media query to reduce animation and smooth scrolling.
- The typewriter checks the reduced-motion preference and leaves the full greeting visible when reduced motion is preferred.
- When adding images, write useful `alt` text for informative images; use empty alternative text only for images that are purely decorative.

<!-- Styling comment: these are the key shared tokens and breakpoint rules currently used by the stylesheet. -->
## Styling and responsive behavior

- Main background: `#08090d`; header background: `#050608`.
- Primary text: `#f6f7fb`; secondary text: `#a1a8b8`; electric accent: `#8aabff`.
- Main fonts: DM Sans for body text and Space Grotesk for prominent headings and wordmarks.
- The CSS uses a `760px` breakpoint for the stacked mobile layout and a `420px` breakpoint for narrow-screen refinements.
- The skills cards use a two-column desktop grid and collapse to one column on narrow screens.
- The About and Investigative Creator panels similarly switch from multi-column layouts to stacked mobile layouts.
- Skill-card hover/focus styling adds a blue-violet glow. Transitions and animation are disabled/reduced for visitors who request reduced motion.

<!-- Asset comment: the image assets were supplied for this portfolio and are loaded locally rather than from an image CDN. -->
## Images, favicon, and page metadata

- The favicon is `favicon.svg`, linked in the document head as `./favicon.svg?v=2`. The version query string helps browsers refresh a previously cached icon; increment it if the icon changes and browsers continue to show an older version.
- The HTML title is `Haran | Indie Hacker`.
- The meta description and theme-color are set in the document head.
- Project images are local files so they deploy with the page; ensure all four referenced image files are included when publishing.
- `Portrait.SVG` is retained as an unused original placeholder asset. It can be removed if it is no longer needed, but it is not referenced by the current page.

<!-- Contact comment: external links are public and the chat intentionally does not transmit user data. -->
## Contact and profile destinations

| Destination | Current target |
| --- | --- |
| Email | `mailto:harannaresh2004@gmail.com` |
| LinkedIn | `https://www.linkedin.com/in/haran-21az00409/` |
| Instagram | `https://www.instagram.com/xerh_aran/` |
| GitHub | `https://github.com/theHaranXer` |
| Reddit | `https://www.reddit.com/user/xer_haran_/?screen_view_count=1` |
| YouTube | `https://www.youtube.com/@InnovateXer` |
| Substack | `https://substack.com/@dealdesklimited` |

The external social links open a new tab. Review all profile URLs and publicly displayed personal information before sharing the live site.

<!-- Local-run comment: open the project folder, not an individual asset, when starting a local preview server. -->
## Run locally

### VS Code Live Server

1. Open the `Personal Portfolio Website` folder in VS Code.
2. Install/enable the **Live Server** extension if it is not already available.
3. Open `Index.HTML` and choose **Open with Live Server** (or use the editor's **Go Live** action).
4. Visit the local URL Live Server opens, commonly `http://127.0.0.1:5500/Index.HTML`.
5. Test a mobile viewport using browser DevTools: **Ctrl+Shift+I**, then **Ctrl+Shift+M**.

If the favicon appears stale, hard-refresh with **Ctrl+Shift+R**. Check that the site is served from this project folder and that `favicon.svg` is available at the same directory level as `Index.HTML`.

### Python static server (optional)

Python is not a project dependency; this is an optional way to serve the folder locally:

```powershell
Set-Location "C:\path\to\Personal Portfolio Website"
python -m http.server 8000
```

Then open `http://localhost:8000/Index.HTML`. Stop the server with **Ctrl+C** in its terminal.

<!-- Deployment comment: upload the static files together; no build command or environment variables are required. -->
## Deploy / production hosting

This site can be deployed to any static hosting provider, such as Netlify, GitHub Pages, Cloudflare Pages, or a static web host.

1. Include the HTML, CSS, favicon, and every referenced image in the deployed directory.
2. Configure the host's site root to the directory containing `Index.HTML`.
3. If the host requires a lowercase default document named `index.html`, rename `Index.HTML` to `index.html` and ensure the host is configured for it. File names and case can matter on Linux-based hosts.
4. No build command or output directory is required for the current plain HTML/CSS/JavaScript project.
5. After deployment, open the public URL on desktop and mobile and test navigation, images, external links, and favicon.
6. For automatic deployments, store the project in a Git repository and connect the host to the repository's production branch.
7. Add a custom domain and HTTPS through the hosting provider if desired.

### Production checklist

- [ ] Confirm the deployed directory includes all page, style, favicon, and image files.
- [ ] Check the hosting root / default document configuration.
- [ ] Check the browser console and network panel for missing files or other runtime errors.
- [ ] Test the burger menu, menu-close behavior, all section anchors, and hero buttons.
- [ ] Test image loading and layout at narrow mobile and desktop widths.
- [ ] Confirm contact destinations and social profile URLs are correct.
- [ ] Ensure visitors understand that chat messages are not sent or saved.
- [ ] Review the public page for personal details you do not want indexed or shared.
- [ ] Confirm HTTPS is enabled and the favicon updates after a hard refresh.

<!-- Known-limitations comment: a visually complete static portfolio is not a backend-enabled contact service. -->
## Known limitations and future work

- The chat is intentionally local-only and does not contact the site owner. To receive messages, integrate a backend or a reputable hosted form service, define a privacy notice, and test delivery and spam protection.
- The page has no automated tests, build pipeline, deployment workflow, analytics, or content management system.
- Social icons are inline SVG or text-style marks; no icon framework is installed.
- Google Fonts require an internet connection; fallback fonts are used when they are unavailable.
- Add Open Graph/social preview metadata, a canonical URL, and a `robots.txt`/sitemap if needed for a custom-domain SEO setup.

<!-- Change-history comment: update this section when substantial page features, dependencies, or deployment behavior change. -->
## Change history

| Stage | Summary |
| --- | --- |
| Initial version | Basic portfolio header/navigation and an unfinished hero placeholder. |
| Visual hero | Added dark-blue hero styling, typewriter greeting, portrait frame, responsive styles, and hero actions. |
| Multi-section portfolio | Added About, Journey, Skills, Contact, burger navigation, chat demo, social links, and footer. |
| Personal content and assets | Added biography, education and experience milestones, skill groups, owner-provided profile images, and social profile URLs. |
| Production polish | Added the “Investigative Creator” profile card, Zustpe document link, and matching SVG favicon. |
| Responsive header update | Desktop now displays inline section links and “Let’s Talk” with no burger button; at widths of `760px` and below, the inline navigation is hidden and the burger menu is shown instead. |