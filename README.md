### ***Personal portfolio site***

Live at: [https://andreviaaa.github.io](https://andreviaaa.github.io)

---

## Folder Structure

```
andreviaaa.github.io/
├── index.html               — main landing page
├── 404.html                 — custom not found page
├── robots.txt               — search engine crawler rules
├── sitemap.xml              — page index for search engines
├── README.md                — this file
│
├── assets/
│   ├── css/
│   │   ├── main.css         — styles for index.html and 404.html
│   │   └── inner.css        — styles for all pages/ subpages
│   └── icons/               — local PNG icons (no external CDN)
│       ├── github.png
│       ├── linkedin.png
│       ├── tryhackme.png
│       └── email.png
│
└── pages/
    ├── projects.html        — scripts, tools, and builds
    ├── writeups.html        — TryHackMe and CTF writeups
    ├── blog.html            — blog posts and notes
    └── certs.html           — certifications and badges
```

---

## index.html Section Order

```
Header
Intro
Socials
Profiles
Projects
Writeups
Blog & Notes
Certifications
Footer
```

---

## CSS Architecture

| File | Used by |
|------|---------|
| `assets/css/main.css` | `index.html`, `404.html` |
| `assets/css/inner.css` | `pages/*.html` |

**Path rule:** Pages inside `/pages/` use `../assets/css/inner.css` and link back with `../index.html`. Root pages use `assets/css/main.css` directly.

---

## How To Extend

### Add a social pill (index.html)
Find `<!-- add more pills here -->` and copy:
```html
<a class="social-pill" href="YOUR_URL" target="_blank" rel="noopener noreferrer">platform</a>
```

### Add a profile link (index.html)
Find `<!-- TO ADD: copy any link-item block -->` and copy:
```html
<a class="link-item" href="YOUR_URL" target="_blank" rel="noopener noreferrer">
  <div class="link-left">
    <div class="link-icon"><img src="assets/icons/youricon.png" alt="Name" /></div>
    <div class="link-info">
      <span class="link-name">Name</span>
      <span class="link-handle">@handle</span>
    </div>
  </div>
  <span class="link-arrow">→</span>
</a>
```

### Add a portfolio card (any page)
Find `<!-- TO ADD: copy any port-card block -->` and copy:
```html
<a class="port-card" href="YOUR_URL" target="_blank" rel="noopener noreferrer">
  <div class="port-info">
    <span class="port-title">Title</span>
    <span class="port-desc">Short description</span>
  </div>
  <div class="port-meta"><span class="port-tag">tag</span><span class="port-arrow">→</span></div>
</a>
```

### Add a cert with no link
```html
<div class="cert-card static">
  <div class="cert-info">
    <span class="cert-title">Cert Name</span>
    <span class="cert-issuer">Issuer</span>
  </div>
  <div class="cert-meta"><span class="cert-year">2024</span></div>
</div>
```

### Add a new page
1. Copy any file from `pages/` as a starting point
2. Update `<title>`, meta description, `.page-title`, `.page-sub`, and content
3. Add a `<url>` block to `sitemap.xml`

### Add a new icon
Drop a PNG into `assets/icons/`. Use white or light coloured icons for best results on dark background. 32×32 or 64×64 source PNG recommended.

---

## Theme

| Mode  | Background | Surface   | Text      |
|-------|------------|-----------|-----------|
| Dark  | `#0e0e0f`  | `#161618` | `#e8e8e8` |
| Light | `#f4f4f5`  | `#ffffff`  | `#1a1a1a` |

Toggle is fixed top-right on every page. Preference saved to `localStorage` and shared across all pages. Default is **dark**.

---

## Tech

- Pure **HTML & CSS** — no frameworks, no build tools
- One small **JavaScript** block per page for the theme toggle only
- **Zero external requests** — no Google Fonts, no CDNs, no trackers
- Fully **responsive** — mobile and desktop
- Hosted on **GitHub Pages** — free

---

## Deployment

```bash
git add .
git commit -m "your message"
git push
```

Changes go live within seconds to a few minutes.

---

## License

Personal website — all rights reserved.
