# b4Help — Design Specification

**Purpose:** This document is the single source of truth for reproducing the look and feel of [b4help.com](https://b4help.com). Hand it to any developer, designer, or coding agent and they should be able to build HTML pages that match the site's visual identity exactly.

**Brand in one line:** Practical, secure AI consulting for small & mid-sized businesses — *"From Infrastructure to Intelligence."*

**Aesthetic:** Modern dark "deep-navy" SaaS theme. Premium, calm, trustworthy, slightly technical. High-contrast light text on near-black navy, with electric-blue and emerald-green accents, soft glows, generous spacing, and rounded "card" surfaces.

---

## 1. Design Tokens

Copy these into `:root` verbatim. Every color, radius, and easing value on the site derives from these.

```css
:root{
  /* Backgrounds (darkest → lighter) */
  --bg:#060d1f;            /* page background, near-black navy */
  --bg-2:#0a1530;          /* secondary background band */
  --navy:#0c1d3d;          /* brand navy, used in gradients */

  /* Surfaces (cards / panels, dark → light) */
  --surface:#0f1f3d;
  --surface-2:#15264a;
  --surface-3:#1b3057;

  /* Text */
  --text:#eaf1ff;          /* primary text, near-white blue-tint */
  --muted:#94a8ca;         /* secondary text */
  --muted-2:#6f86ab;       /* tertiary / captions / labels */

  /* Accents — blue (primary) */
  --accent:#5b9bff;
  --accent-2:#4f8df9;
  --accent-soft:rgba(91,155,255,.14);  /* tinted fill / chips */

  /* Accents — green (success / results) */
  --green:#34d399;
  --green-2:#10b981;
  --green-soft:rgba(52,211,153,.13);

  /* Additional accents */
  --teal:#2dd4bf;
  --amber:#fbbf24;
  --red:#f87171;

  /* Borders (hairlines on dark) */
  --border:rgba(124,158,214,.14);
  --border-2:rgba(124,158,214,.26);

  /* Geometry & motion */
  --r:18px;                                /* default card radius */
  --maxw:1200px;                           /* content container width */
  --ease:cubic-bezier(.22,.61,.36,1);      /* standard easing */
}
```

### Color usage rules
- **Page background** is `--bg`. Alternate sections may sit on `--bg-2` or a subtle vertical gradient to create rhythm.
- **Cards/panels** use `--surface` → `--surface-3` (often a `linear-gradient(180deg, ...)` between two surface tints) with a `--border` hairline.
- **Blue** is the primary brand/CTA accent. **Green** signals results, savings, "done," and success states. Don't mix them on the same element except in the hero/feature gradient.
- **Never** use pure black (`#000`) or pure white (`#fff`) for large areas — use `--bg` and `--text`. Pure white only appears inside gradients and tiny highlights.

---

## 2. Typography

Load from Google Fonts (single request):

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Space+Grotesk:wght@500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
```

| Role | Family | Weights | Used for |
|------|--------|---------|----------|
| **Body / UI** | `'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif` | 300–900 | All body copy, buttons, nav, labels |
| **Display / Headings** | `'Space Grotesk', 'Inter', sans-serif` | 500–700 | H1–H3, big stat numbers, eyebrows |
| **Mono / Technical** | `'JetBrains Mono', monospace` | 400–500 | Code/UI mock chips, timers ("Done in 4 seconds"), step labels, small caps tech tags |

### Type scale (fluid — use `clamp()`)
Headings scale with viewport so they look right on mobile and desktop. Use these exact clamps:

```css
.h-hero   { font-size:clamp(36px,6.4vw,72px); font-weight:700; line-height:1.04; letter-spacing:-.02em; font-family:'Space Grotesk','Inter',sans-serif; }
.h-xl     { font-size:clamp(34px,5vw,58px);   font-weight:700; line-height:1.06; }
.h-section{ font-size:clamp(30px,4.6vw,52px);  font-weight:700; line-height:1.08; letter-spacing:-.015em; } /* section headlines */
.h-2      { font-size:clamp(26px,3.4vw,40px);  font-weight:700; }
.h-3      { font-size:clamp(22px,2.6vw,30px);  font-weight:600; }
.lead     { font-size:clamp(17px,2vw,21px);    font-weight:400; color:var(--muted); line-height:1.55; }
body      { font-size:16px; line-height:1.6; font-weight:400; color:var(--text); }
.small    { font-size:13.5px; color:var(--muted-2); }
.eyebrow  { font-size:12.5px; font-weight:600; letter-spacing:.14em; text-transform:uppercase; color:var(--accent); font-family:'JetBrains Mono',monospace; }
```

### Typography rules
- Headings: **Space Grotesk**, tight tracking (`letter-spacing:-.015em` to `-.02em`), tight line-height (1.04–1.1).
- Body: **Inter**, comfortable `line-height:1.6`, color `--muted` for paragraphs, `--text` for emphasis.
- **Eyebrows / kickers** above section headings: uppercase, letter-spaced, mono or 600 Inter, colored `--accent`.
- **Big stat numbers** (e.g., `25+`, `500+`, `99.9%`) use Space Grotesk 700 at large sizes, often with a gradient text fill (see §4).

---

## 3. Layout & Spacing

- **Container:** `max-width: var(--maxw)` (1200px), centered with `margin:0 auto`, side padding `padding:0 24px` (drop to `0 18px` on mobile).
- **Section vertical rhythm:** large sections use roughly `padding:96px 0` desktop / `64px 0` mobile. The hero uses `padding:150px 0 60px` (extra top to clear the fixed header).
- **Section width caps for readable text:** constrain headline+lead blocks to `max-width:640px–760px`, centered. Full cards/grids may use the full container.
- **Grids:**
  - Service / feature cards: responsive grid, `repeat(auto-fit, minmax(280px,1fr))`, `gap:18px–24px`.
  - Pricing tiers: 3-up on desktop, collapsing to 1-up on mobile.
  - Two-column "split" layouts (e.g., hero copy + visual) use `grid-template-columns:1.15fr .85fr; gap` and collapse to a single column under ~860px.
- **Breakpoints:** mobile-first; primary collapse around `max-width:860px`, with finer tweaks at `600px`. At `≤600px` the bottom sticky CTA appears and nav collapses.

```css
.wrap{ max-width:var(--maxw); margin:0 auto; padding:0 24px; }
section{ padding:96px 0; }
@media (max-width:860px){ section{ padding:64px 0; } .split{ grid-template-columns:1fr; } }
@media (max-width:600px){ .wrap{ padding:0 18px; } }
```

---

## 4. Gradients, Shadows & Effects

These are what make the site feel premium. Use them deliberately, not everywhere.

### Signature gradients
```css
/* Brand blue text/accent gradient (headline highlight words) */
--grad-blue-text: linear-gradient(110deg,#ffffff 6%,#bcd4ff 46%,#5b9bff 104%);
/* Brand green text gradient (results / savings highlight) */
--grad-green-text: linear-gradient(110deg,#fff 10%,#a7f3d0 60%,#34d399 105%);
/* Blue → green diagonal (feature accents, icons, dividers) */
--grad-duo: linear-gradient(150deg,#4f8df9,#34d399);
/* Card surface gradient */
--grad-card: linear-gradient(180deg,#143055,#0c1d3d);
/* Dark section band */
--grad-band: linear-gradient(180deg,#0c1b38,#0a1428);
/* Button fills */
--grad-btn-blue:  linear-gradient(180deg,#6ba6ff,#4f8df9);
--grad-btn-green: linear-gradient(180deg,#3ee0a0,#10b981);
```

**Gradient text helper:**
```css
.grad-text{
  background:var(--grad-blue-text);
  -webkit-background-clip:text; background-clip:text;
  color:transparent;
}
.grad-text.green{ background:var(--grad-green-text); -webkit-background-clip:text; background-clip:text; }
```
Use a gradient-text span on **one key phrase** per headline (e.g., the words "AI can fix that" or a savings number), not the whole line.

### Shadows (soft, colored, large-blur)
The site favors big, soft, downward shadows with colored tints — never harsh dark drop shadows.
```css
--sh-card:   0 28px 60px -30px rgba(0,0,0,.8);
--sh-float:  0 50px 120px -40px rgba(0,0,0,.85), 0 0 0 1px rgba(255,255,255,.03), 0 0 90px -30px rgba(79,141,249,.45); /* hero visual / featured card */
--sh-btn-blue:  0 8px 28px -8px rgba(79,141,249,.7), inset 0 1px 0 rgba(255,255,255,.35);
--sh-btn-green: 0 8px 28px -8px rgba(16,185,129,.7), inset 0 1px 0 rgba(255,255,255,.35);
--glow-green: 0 0 0 1px rgba(52,211,153,.2), 0 30px 70px -34px rgba(16,185,129,.45); /* "popular"/highlighted tier */
```
- Buttons get a **colored glow + inset top highlight** (the `inset 0 1px 0 rgba(255,255,255,.35)` gives a glassy top edge).
- Featured / floating panels get the large `--sh-float` plus a faint blue ambient glow.

### Backdrop blur (sticky header & overlays)
```css
backdrop-filter:blur(16px) saturate(140%);  /* sticky header */
```
Use a translucent background behind blur, e.g. `background:linear-gradient(180deg,rgba(13,30,63,.7),rgba(13,30,63,.45))`.

### Radii
| Token / value | Use |
|---|---|
| `--r` (18px) | default cards/panels |
| 26px–36px | large hero/feature panels |
| 100px | pills, badges, buttons (fully rounded) |
| 8px–14px | small chips, inputs, mock UI elements |
| 50% | avatars, icon circles |

---

## 5. Components

### 5.1 Buttons
Two primary styles + a ghost. Always rounded-pill, bold label, generous padding.

```css
.btn{
  display:inline-flex; align-items:center; gap:8px;
  padding:14px 28px; border-radius:100px;
  font-family:'Inter',sans-serif; font-weight:600; font-size:16px;
  border:1px solid transparent; cursor:pointer; text-decoration:none;
  transition:transform .2s var(--ease), box-shadow .2s var(--ease), filter .2s var(--ease);
}
.btn:hover{ transform:translateY(-2px); filter:brightness(1.05); }

/* Primary (blue) — main CTAs */
.btn-blue{ background:var(--grad-btn-blue); color:#04122e; box-shadow:var(--sh-btn-blue); }

/* Success (green) — "results"/booking emphasis (optional) */
.btn-green{ background:var(--grad-btn-green); color:#04221a; box-shadow:var(--sh-btn-green); }

/* Ghost / secondary */
.btn-ghost{ background:rgba(255,255,255,.04); border-color:var(--border-2); color:var(--text); }
.btn-ghost:hover{ background:rgba(255,255,255,.08); }
```
- Note the **dark text** (`#04122e` / `#04221a`) on the bright gradient fills — this is intentional for contrast and the "premium" feel.
- Primary CTA copy is consistently **"Book Your Free AI Discovery Call"** / **"Book a free call →"**. Secondary/ghost is **"See how it works ↓"**.
- On mobile, the primary `.btn` often goes `width:100%`.

### 5.2 Badges / chips / pills
Small rounded-pill labels for credentials and tags ("25+ years experience", "Any industry").
```css
.chip{
  display:inline-flex; align-items:center; gap:6px;
  padding:8px 14px; border-radius:100px;
  background:var(--accent-soft); border:1px solid var(--border-2);
  color:var(--text); font-size:13px; font-weight:500;
}
.chip.green{ background:var(--green-soft); }
.chip .dot{ width:7px; height:7px; border-radius:50%; background:var(--green); box-shadow:0 0 10px currentColor; } /* glowing status dot */
```

### 5.3 Cards (services / features / pricing)
```css
.card{
  background:var(--grad-card);
  border:1px solid var(--border);
  border-radius:var(--r);
  padding:26px;
  box-shadow:var(--sh-card);
  transition:transform .25s var(--ease), border-color .25s var(--ease), box-shadow .25s var(--ease);
}
.card:hover{ transform:translateY(-4px); border-color:var(--border-2); }
.card .icon{               /* gradient square icon */
  width:46px; height:46px; border-radius:12px;
  background:var(--grad-duo); display:grid; place-items:center;
  box-shadow:0 8px 28px -8px rgba(79,141,249,.7);
}
.card h3{ margin:16px 0 8px; }
.card p{ color:var(--muted); }
```
- **Featured pricing tier** gets `--glow-green`, a brighter border, and a small "popular" chip.

### 5.4 Stat block
Large gradient number + small uppercase label. Used in clusters of four (e.g., `25+ YEARS`, `500+ PROJECTS`, `100+ CLIENTS`, `99.9% UPTIME`).
```css
.stat .num{ font-family:'Space Grotesk',sans-serif; font-weight:700; font-size:clamp(34px,4.6vw,52px); }
.stat .num.grad{ background:var(--grad-blue-text); -webkit-background-clip:text; background-clip:text; color:transparent; }
.stat .label{ font-size:12px; letter-spacing:.12em; text-transform:uppercase; color:var(--muted-2); font-family:'JetBrains Mono',monospace; }
```

### 5.5 Header / navigation (sticky)
```css
header{
  position:sticky; top:0; z-index:50;
  background:linear-gradient(180deg,rgba(13,30,63,.7),rgba(13,30,63,.45));
  backdrop-filter:blur(16px) saturate(140%);
  border-bottom:1px solid var(--border);
}
header .wrap{ display:flex; align-items:center; justify-content:space-between; height:68px; }
header nav a{ color:var(--muted); font-size:14.5px; font-weight:500; text-decoration:none; }
header nav a:hover{ color:var(--text); }
```
- **Logo:** light/transparent PNG wordmark (`b4Help`), left-aligned.
- **Nav items (in order):** Services · How it Works · Results · About · FAQ · **Book Free Call** (primary button, right-aligned).
- On mobile, nav collapses; key links + logo remain.

### 5.6 Footer
- Dark band (`--grad-band`), top hairline border.
- Left: logo + tagline — *"From Infrastructure to Intelligence. Practical, secure AI consulting for small & mid-sized businesses. Save hours every week without risking your data."* — plus name/location/email.
- Three link columns:
  - **Services:** AI Readiness Audit · Managed Automation · Training & Policy · Pricing
  - **Explore:** How it works · Results · About · FAQ
  - **Connect:** Facebook · YouTube @b4help · Google Business
- Copyright line: `© 2026 b4Help · AI Consulting · Massachusetts & Remote · 25+ Years of IT & Security.`

### 5.7 Sticky mobile CTA bar (≤600px)
A fixed bottom bar with one full-width primary button: **"📞 Book Your Free AI Call"**. Respect safe area:
```css
.mobile-cta{ position:fixed; left:0; right:0; bottom:0; z-index:60;
  padding:12px 16px calc(12px + env(safe-area-inset-bottom));
  background:rgba(6,13,31,.9); backdrop-filter:blur(10px); border-top:1px solid var(--border); }
@media (min-width:601px){ .mobile-cta{ display:none; } }
```

### 5.8 Forms / inputs (newsletter, email opt-in)
```css
input, textarea{
  background:var(--surface); border:1px solid var(--border-2);
  color:var(--text); border-radius:12px; padding:12px 15px; font-size:15px;
}
input::placeholder{ color:var(--muted-2); }
input:focus{ outline:none; border-color:var(--accent); box-shadow:0 0 0 3px var(--accent-soft); }
```

---

## 6. Motion

- **Standard easing:** `cubic-bezier(.22,.61,.36,1)` (the `--ease` token).
- **Hover lifts:** cards `translateY(-4px)`, buttons `translateY(-2px)` + slight brightness.
- **Durations:** 0.2s–0.25s for hovers; 0.4s–0.6s for scroll-reveal entrances.
- **Scroll reveal (recommended):** fade + 16px upward translate as sections enter the viewport (IntersectionObserver). Keep subtle.
- **Glowing status dots** pulse gently (optional).
- Honor `@media (prefers-reduced-motion:reduce)` — disable transforms/animations.

```css
@media (prefers-reduced-motion:reduce){
  *{ animation:none !important; transition:none !important; }
}
```

---

## 7. Page Structure (homepage section order)

Reproduce sections in this order for a faithful single-page layout. Each is a full-width `<section>` on the dark background, alternating subtle band tints for rhythm.

1. **Sticky header / nav** (§5.5)
2. **Hero** — eyebrow, big headline with one gradient-highlight phrase, lead paragraph, two CTAs (blue + ghost), row of 4 credential chips. Optional split visual on the right.
   - H1: *"Your team is drowning in busywork. AI can fix that, safely."*
   - Lead: *"I help businesses in any industry use AI to save hours every week and cut costs, without risking your data. On-site in Massachusetts or remotely anywhere. 25+ years in IT & security."*
3. **AI Workflow Assistant demo** — a "floating" card (`--sh-float`) showing a chat/automation mock with mono timers ("Done in 4 seconds") and a "11.5 hours saved this week" tally; adjacent stat cluster (25+ / 500+ / 100+ / 99.9%).
4. **Pain points** — *"The hidden cost of doing it by hand"* with a list of manual tasks; closing line *"It adds up to days of lost productivity a month."*
5. **Industry solutions** — *"Works in every industry"*; grid of service cards (lead follow-up, intake/onboarding, weekly reports, document summarization, inbox sorting, customer-service automation, data entry, proposal follow-up).
6. **Three services** — *"Three ways I put AI to work for you"*: AI Readiness Audit · Managed Automation · Training & Policy (3-column cards).
7. **About / Why me** — *"Not another 'AI expert' who learned ChatGPT last week."* 25+ yrs IT/security; secure & local AI; certification logos (Anthropic, Google, Microsoft, IBM, HubSpot); stat cluster repeated.
8. **How it works** — 4-step process with mono step labels: `30 MIN · FREE` Discovery Call → `~1 HOUR` Workflow Assessment → `PROVEN ON YOUR DATA` Prototype → `ONGOING` Deploy & Support. CTA.
9. **Results / social proof** — green-accented: *"11 hrs / week saved for clients and counting."* Before/after testimonial cards.
10. **Pricing** — *"Know what it costs before you call"*: Discovery Call (Free) · Game Plan Session ($500, credited) · Roadmap ($1,950) · Launchpad ($5,500) · Transformation ($12,500) · Advisory Retainer (from $500/mo). One tier highlighted with green glow.
11. **Data-safety objection** — *"But I can't put my data into ChatGPT…"* with reassurance about secure/local AI.
12. **FAQ** — *"Frequently asked questions"*, six expandable Q&As (pricing, data safety, capabilities, industries, remote/on-site, requirements).
13. **Booking CTA** — *"The free Discovery Call"* with embedded Cal.com widget + email option; newsletter signup *"One practical AI tip a week."*
14. **Footer** (§5.6) + **sticky mobile CTA** (§5.7).

---

## 8. Brand Voice (for any generated copy)

- **Plain, confident, jargon-free.** Speaks to busy SMB owners, not engineers.
- First-person singular ("I help…", "I can deploy…") — it's one consultant, Brian Franzen.
- Leads with **outcomes** (hours saved, costs cut) and **safety** (data never leaves the office).
- Reassuring about AI fears; never hype-y. Recurring proof points: **25+ years IT/security, 500+ projects, 100+ clients, 99.9% uptime.**
- Recurring CTA: **"Book Your Free AI Discovery Call."**

---

## 9. Brand Facts (reference)

| Field | Value |
|---|---|
| Business | b4Help — AI Consulting |
| Person | Brian Franzen |
| Email | contact@b4help.com |
| Location | Massachusetts (on-site) + remote nationwide |
| Tagline | From Infrastructure to Intelligence |
| Social | Facebook · YouTube @b4help · Google Business |
| Booking | Cal.com embed |

---

## 10. Quick-start boilerplate

A minimal page skeleton wired with the tokens above:

```html
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>b4Help — Practical, secure AI consulting</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Space+Grotesk:wght@500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{ /* paste §1 tokens here */ }
  *{ box-sizing:border-box; margin:0; padding:0; }
  body{ background:var(--bg); color:var(--text); font:400 16px/1.6 'Inter',-apple-system,BlinkMacSystemFont,'Segoe UI',sans-serif; -webkit-font-smoothing:antialiased; }
  h1,h2,h3{ font-family:'Space Grotesk','Inter',sans-serif; letter-spacing:-.015em; line-height:1.08; }
  a{ color:inherit; }
  .wrap{ max-width:var(--maxw); margin:0 auto; padding:0 24px; }
  /* paste component classes from §2,§4,§5 as needed */
</style>
</head>
<body>
  <!-- header (§5.5) → hero (§7.2) → sections (§7) → footer (§5.6) → mobile CTA (§5.7) -->
</body>
</html>
```

---

### Reproduction checklist
- [ ] Dark navy `--bg`, light `--text`, blue + green accents only.
- [ ] Inter (body) + Space Grotesk (headings) + JetBrains Mono (technical) loaded.
- [ ] Fluid `clamp()` heading sizes; tight heading tracking.
- [ ] One gradient-text highlight phrase per major headline.
- [ ] Pill buttons with colored glow + glassy inset top edge; dark text on bright fills.
- [ ] Cards: surface gradient, hairline border, big soft shadow, hover lift.
- [ ] Sticky blurred header; sticky full-width mobile CTA.
- [ ] Stat clusters (25+/500+/100+/99.9%) with gradient numbers + mono labels.
- [ ] Sections in the order of §7; generous 64–96px vertical rhythm.
- [ ] `prefers-reduced-motion` respected.
