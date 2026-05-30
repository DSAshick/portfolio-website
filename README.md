# Ashick Sanjey — 3D Interactive Portfolio

A premium, Apple-inspired personal portfolio with an immersive Three.js 3D background, smooth scroll interactions, and minimalist luxury design aesthetic.

---

## 🚀 Quick Start

This is a **single-file HTML portfolio** — zero dependencies to install, no build tools required.

1. Download `index.html`
2. Open it in any modern browser, or host it anywhere

That's it. No npm, no build step.

---

## ✨ Features

| Feature | Details |
|---|---|
| **3D Scene** | Three.js particle field + floating wireframe geometries |
| **Mouse Tracking** | 3D objects rotate and parallax with cursor movement |
| **Scroll Parallax** | Camera and scene drift on scroll |
| **Custom Cursor** | Smooth lagging cursor with hover state expansion |
| **Project Filtering** | Filter by ML / Analytics / Web categories |
| **Timeline Experience** | Interactive experience switcher with animated detail panel |
| **Reveal Animations** | Intersection Observer scroll-reveal on all sections |
| **Scroll Progress** | Top progress bar |
| **Responsive** | Fully mobile/tablet responsive, 3D degrades gracefully |
| **Performance** | Additive blending particles, capped pixel ratio, lazy geometry |

---

## 🎨 Design System

```
Colors:
  --bg:          #060810   (near-black base)
  --accent:      #5b8ef0   (electric blue)
  --accent2:     #a78bfa   (soft violet)
  --accent3:     #34d399   (mint green)

Fonts:
  Display:   Cormorant Garamond (serif, italic, elegant)
  Body:      DM Sans (clean, geometric)
  Mono:      DM Mono (labels, badges, numbers)
```

---

## 📁 Sections

1. **Hero** — Name, tagline, CTA buttons
2. **About** — Bio, stat cards (projects / internships / certs / years)
3. **Skills** — SVG icon grid (Programming / ML+AI / Data Viz)
4. **Projects** — Filterable card grid (12 featured projects)
5. **Experience** — Interactive timeline with detail panel
6. **Certifications** — Card grid with issuer badges
7. **Contact** — Email, socials, contact form
8. **Footer** — Copyright and social links

---

## ✏️ How to Customize

### Name & Tagline (Hero)
```html
<!-- Line ~200 in index.html -->
<h1 class="hero-name">Your <em>Name</em></h1>
<h1 class="hero-name">Your Title & Role</h1>
<p class="hero-tagline">Your one-line value proposition.</p>
```

### Contact Info
```html
<!-- Search for "ashicksanjey@outlook.com" and replace with your email -->
<!-- Search for "ashick-sanjey" and replace with your LinkedIn handle -->
<!-- Search for "DSAshick" and replace with your GitHub username -->
<!-- Search for "+971 0543461832" and replace with your phone -->
```

### About Stats
```html
<!-- Find the .about-stats div and update numbers -->
<div class="stat-number">23<span>+</span></div>   <!-- Projects -->
<div class="stat-number">3<span>+</span></div>    <!-- Internships -->
```

### Projects
Each project card follows this pattern:
```html
<div class="project-card reveal" data-category="ml">
  <div class="project-number">01 / ML</div>
  <div class="project-title">Your Project Name</div>
  <div class="project-desc">Description of what you built and the outcome.</div>
  <div class="project-tags">
    <span class="tag accent">Python</span>
    <span class="tag green">Healthcare AI</span>
  </div>
</div>
```

`data-category` options: `ml` · `analytics` · `web`  
Tag color options: `tag accent` (blue) · `tag green` · `tag purple` · `tag` (default)

### Experience Timeline
Edit the `expData` object in the `<script>` section:
```javascript
const expData = {
  mykey: {
    role: 'Job Title',
    company: 'Company Name · Dates',
    list: [
      'What you did bullet 1',
      'What you did bullet 2',
    ],
    tags: [
      { label: 'Skill', cls: 'accent' },
    ]
  },
  // add more entries...
};
```
Then add a matching `.timeline-item` in the HTML with `data-exp="mykey"`.

### Skills Grid
Each skill icon is an SVG block. Duplicate any `.skill-item` and swap the SVG + name:
```html
<div class="skill-item" data-tip="Tool Name">
  <div class="skill-icon">
    <!-- Your SVG icon here -->
  </div>
  <div class="skill-name">Tool Name</div>
</div>
```

Use any icon set that provides inline SVG — [Lucide](https://lucide.dev/), [Heroicons](https://heroicons.com/), or [Tabler Icons](https://tabler-icons.io/).

### Certifications
```html
<div class="cert-card reveal">
  <div class="cert-icon"><!-- SVG icon --></div>
  <div>
    <div class="cert-issuer">Issuer Name</div>
    <div class="cert-title">Certificate Title</div>
    <div class="cert-desc">Brief description of what you learned.</div>
  </div>
</div>
```

### 3D Scene
The Three.js scene is inside `initThree()` in the `<script>`. Tweak:
- `particleCount` — number of floating particles (default 1800)
- `palette` — particle colors
- `wireMat(0x5b8ef0)` — geometry wireframe color
- Camera position: `camera.position.z = 5`
- Mouse sensitivity: `mouse.x * 0.5` (higher = more reactive)

---

## 🌐 Deployment Options

| Platform | Command / Steps |
|---|---|
| **GitHub Pages** | Push `index.html` to repo root, enable Pages in Settings |
| **Netlify** | Drag & drop `index.html` into netlify.com/drop |
| **Vercel** | `vercel` in folder with the HTML file |
| **Cloudflare Pages** | Push to GitHub → connect in Cloudflare dashboard |
| **Any static host** | Upload `index.html` — no server-side requirements |

---

## 🔧 Browser Support

| Browser | Support |
|---|---|
| Chrome 90+ | ✅ Full |
| Firefox 88+ | ✅ Full |
| Safari 14+ | ✅ Full |
| Edge 90+ | ✅ Full |
| Mobile Chrome/Safari | ✅ (cursor hidden, touch events active) |

---

## 📄 File Structure

```
index.html     ← Everything in one file
README.md      ← This file
```

All fonts load from Google Fonts CDN.  
Three.js and GSAP load from cdnjs.cloudflare.com.  
No local assets required.

---

## License

MIT — use freely, attribution appreciated.
