# Cursor clone — Landing Page Recreation

A static HTML/CSS recreation of the **Cursor** AI code editor marketing site.

---

## 🔗 Live Demo


---

## 📸 Preview

![Cursor landing page – desktop](assets/desktop.png)

---

## Sections Rebuilt

| Section | Details |
|---------|---------|
| **Header & Nav** | Sticky top bar with the Cursor logo, product links (Product, Enterprise, Pricing, Resources), and Sign in / Download action buttons. |
| **Hero** | Bold headline, primary `Download for macOS` CTA with a pill-style button, and a full-width hero product screenshot. |
| **Social Proof** | Horizontal strip of company logos (Stripe, OpenAI, Linear, Datadog, NVIDIA, Figma, Ramp, Adobe) displayed in dark card tiles. |
| **Product Features** | Three alternating feature bands Agent, Tab autocomplete, and cross-tool integration each with a heading, subtext, orange learn-more link, and product image. |
| **Testimonials** | Six-card grid of developer and executive quotes with avatar images, cited names, and roles. |
| **Use Cases** | Three-column card layout covering model selection, codebase understanding, and enterprise-scale development, each with a tall visual. |
| **Changelog** | Four-column card grid of versioned release entries with optional version badges, dates, and a link to the full changelog. |
| **Team / Research** | Wide two-column panel introducing Cursor as an applied research team, with a large team photo on the right. |
| **Recent Posts** | Labeled two-column layout listing three recent blog/research highlights with title, excerpt, and category/date metadata. |
| **Bottom CTA** | Centered oversized headline ("Try Cursor now.") with a rounded download button. |
| **Footer** | Five-column nav grid (Product, Resources, Company, Legal, Connect), followed by a bottom bar with copyright, SOC 2 badge, theme toggle, and language selector. |

---

## Fonts

| Font | Role | Source |
|------|------|--------|
| **Cursor Gothic** | All UI text headings, body, nav, buttons, footer | Local `@font-face` from `assets/fonts/CursorGothic-*.woff2` |
| **System fallbacks** | Fallback stack | `system-ui`, `-apple-system`, `BlinkMacSystemFont`, `"Segoe UI"`, `Roboto`, `sans-serif` |

All type is set via the `--font-brand` CSS variable.

---

## Colors

### Backgrounds

| Token | Value | Usage |
|-------|-------|-------|
| `--bg` | `#13120A` | Page background |
| `--card-bg` | `#18160d` | Feature cards, testimonial cards, use case cards, team panel |
| `--surface-mid` | `#1B1912` | Changelog cards, posts section, footer |
| `--surface-raised` | `#201E18` | Post cards (nested on mid surface) |
| `--surface-overlay` | `#26241E` | Theme toggle, language button |
| `--card-bg-hover` | `#1d1b15` | Hover state for interactive cards |

### Text

| Token | Value | Usage |
|-------|-------|-------|
| `--fg` | `#ffffff` | Primary text |
| `--fg-muted` | `#a3a3a3` | Secondary / supporting text |

### Buttons & Accent

| Token | Value | Usage |
|-------|-------|-------|
| `--btn-light-bg` | `#EDECEC` | Primary button fill (Download, hero CTA) |
| `--btn-light-text` | `#0d0d0d` | Text on light buttons |
| `--btn-light-hover-alt` | `#d7d5d5` | Hover state for primary buttons |
| `--accent` | `rgb(245, 78, 0)` | All in-section links (features, use cases, changelog, posts) |
| `--accent-soft` | `75% accent mix` | Hover state for accent links |
| `--border-subtle` | `20% white mix` | Outline button border, nav ghost button |

---

## Project Structure

```
project/
├── index.html            # Full single-page markup
├── styles.css            # All styles — tokens, layout, components
├── README.md             # This file
└── assets/
    ├── favicon.ico
    ├── cursor-logo.svg
    ├── cursor-gothic.css         # @font-face declarations
    ├── fonts/
    │   ├── CursorGothic-*.woff2  # Custom brand typeface
    │   └── ...
    └── images/
        ├── hero-image.png
        ├── product-1.png
        ├── product-2.png
        ├── product-3.png
        ├── usecase-1.png
        ├── usecase-2.png
        ├── usecase-3.png
        ├── homepage-team-photo.webp
        ├── diana-hu-avatar.webp
        ├── jensen-huang-avatar.webp
        ├── andrej-karpathy-avatar.webp
        ├── patrick-collison-avatar.webp
        ├── shadcn-avatar.webp
        ├── greg-brockman-avatar.webp
        └── desktop.png           # Preview screenshot
```

---

## Running Locally

No build step needed. Open `index.html` directly in a browser:

```bash
# Option 1 — open file directly
open index.html

# Option 2 — VS Code Live Server (right-click → Open with Live Server)

# Option 3 — Python local server
python3 -m http.server 8080
# then visit http://localhost:8080
```

---

## Implementation Notes

- **No frameworks or dependencies** plain HTML and CSS only.
- **CSS custom properties** drive all colors, spacing, typography, and radii for easy theming.
- **Feature row flipping** is handled by `product-feature-row--flipped`, which swaps the grid column order via `grid-template-columns` rather than `order` or `flex-direction` hacks.
- **Card hover states** use a single `background-color` transition on the `--card-bg-hover` token, keeping interactions lightweight.
- **Theme toggle and language selector** in the footer are markup-only no JS behavior is wired up.
- **Trusted-by logos** load from an external Vercel blob storage URL matching the original site's asset host.