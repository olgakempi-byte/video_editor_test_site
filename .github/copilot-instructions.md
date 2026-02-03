# Copilot Instructions for Video Editor Portfolio Site

## Project Overview
This is a **single-page portfolio website** for Ольга Кемпи, a professional video editor specializing in social media and motion graphics content. Built with vanilla HTML + embedded CSS (no build tools, frameworks, or JavaScript).

**File structure:**
- `index2.html` – Single monolithic file containing all HTML, CSS, and structure
- `ава канала футаж в монтаж.jpg` – Hero image (profile photo)

## Architecture & Design Patterns

### Design System (CSS Variables)
All colors defined in `:root` custom properties at the top of `<style>`:
```css
--bg: #0b0f14              /* Main dark background */
--accent: #ff8b3d          /* Primary orange CTA color */
--accent-2: #3dd6c6        /* Secondary teal/cyan accent */
--text: #eef3f7            /* Primary text color */
--muted: #9fb0c0           /* Secondary text/descriptions */
--card: #141b24            /* Card backgrounds */
--line: rgba(255, 255, 255, 0.08)  /* Border colors */
--shadow: 0 20px 60px rgba(0, 0, 0, 0.45)  /* Shadows */
```

### Typography & Fonts
- **Headlines:** `Bebas Neue` (uppercase, bold) for logo; `Manrope` bold/800 for section titles
- **Body text:** `Manrope` 400/600 weight
- Import via Google Fonts (preconnect for performance)

### Grid & Layout
- **Container:** `min(1200px, 92vw)` – responsive max-width with padding
- **Grids:** Use `grid-template-columns: repeat(auto-fit, minmax(Xpx, 1fr))` for responsive cards
  - Service cards: `minmax(220px, 1fr)`
  - Price cards: `minmax(240px, 1fr)`
  - Process steps: `minmax(230px, 1fr)`
  - Contact items: `minmax(200px, 1fr)`
- **Hero section:** 2-column grid on desktop, stacked on mobile

### Responsive Breakpoints
- **900px:** Header flex-direction changes, hero becomes single column
- **600px:** Tighter padding, smaller hero h1, name-tag repositioned

### Component Conventions

**Buttons (`.cta`):**
- Gradient background `linear-gradient(120deg, var(--accent), #ffb56b)`
- Dark text `#17120c` on gradient
- Hover: slight scale/translate up, enhanced shadow
- Rounded: `border-radius: 999px`

**Cards (`.card`, `.price`, `.step`, `.about-card`):**
- `background: rgba(255, 255, 255, X%)` – semi-transparent over dark backdrop
- `border: 1px solid rgba(255, 255, 255, 0.08)` – subtle borders
- `border-radius: 22px` (or 24px for larger cards)
- Box-shadow for depth

**Animations:**
- Entrance: `@keyframes floatIn`, `riseIn`, `fadeUp` – duration 0.8–1s, `ease` timing
- All applied with `animation: [name] [duration]s ease both` (or with delay `0.2s`)

## Content & Information Architecture

1. **Header:** Logo + CTA (Telegram link) – fixed across all sections
2. **Hero:** Name, value proposition, experience card, skill pills, dual CTAs (primary + portfolio)
3. **Services Section:** 4-card grid describing editing capabilities
4. **Pricing Section:** 3 tiered packages with featured state + revision policy explainer
5. **Process Section:** 4-step workflow with detailed descriptions
6. **Contacts Section:** 3 contact channels (TG channel, Instagram, DM)
7. **Footer:** Single tagline

## Key Details for Modifications

- **Revision Policy:** Embedded in `.rules` div after pricing – "2 free iterations, then 50% of package cost"
- **Process Instructions:** Step 4 includes detailed revision rules with bullet list requirements
- **External Links:** All CTAs point to `t.me/` for Telegram or Yandex Disk portfolio
- **Russian Language:** All copy is in Russian; maintain language consistency

## Performance & Best Practices

- Single CSS-in-HTML file (no external stylesheets)
- Grid background via CSS gradients, not image
- `loading="lazy"` on hero image
- Radial + linear gradients for animated background effect
- No JavaScript – pure HTML/CSS
- Preconnect fonts for early delivery

## Common Edits

**Add new service card:** Duplicate `.card` div inside `.service-grid`  
**Adjust pricing:** Modify `<span>` values in `.price` divs; update `.price-meta` details  
**Update links:** Search for `https://t.me/` or `@` handles  
**Change colors:** Update `:root` variables; affects all components globally  
**Responsive tweaks:** Add new `@media` rules at the end of `<style>`
