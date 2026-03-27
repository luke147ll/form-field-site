# Form and Field — Website

Static site for Form and Field, a SketchUp extension for construction takeoff intelligence. Hosted on Cloudflare Pages, auto-deploys on push to main.

## Stack
- Pure static HTML — no build step, no framework
- All styles are **inline** (WordPress.com stripped `<style>` and `<script>` tags, so everything was built inline and we kept it that way)
- Hosted on Cloudflare Pages
- Media files (images/videos) are currently hosted on WordPress at `form-field.com/wp-content/uploads/` — do NOT change these URLs

## Structure
```
/index.html                           — Homepage (landing page, features, CTA)
/documentation/index.html             — Docs index (links to all guides)
/quick-start-guide/index.html         — Quick Start Guide (full content)
/colors-and-elevation-tags/index.html — Colors & Elevations guide (full content)
/assemblies/index.html                — Coming soon stub
/cad-overlays-and-gridlines/index.html — Coming soon stub
/hyper-parser/index.html              — Coming soon stub
/measurements-and-reports/index.html  — Coming soon stub (note: URL typo "measurements-an-reports" exists on some old links)
/multiverse/index.html                — Coming soon stub
/notes/index.html                     — Coming soon stub
/user-agreements/index.html           — Coming soon stub
/faq/index.html                       — Coming soon stub
```

## Design System
- **Theme:** Catppuccin Mocha dark
- **Background:** `#1e1e2e` (base), `#181825` (mantle), `#11111b` (crust)
- **Surfaces:** `#313244` (surface0), `#45475a` (surface1), `#585b70` (surface2)
- **Text:** `#cdd6f4` (primary), `#a6adc8` (secondary/subtext), `#7f849c` (muted)
- **Accent colors:** `#cba6f7` (mauve/primary), `#89b4fa` (blue), `#a6e3a1` (green), `#f9e2af` (yellow), `#fab387` (peach), `#f38ba8` (red), `#94e2d5` (teal), `#b4befe` (lavender)
- **Fonts:** `'Segoe UI', system-ui, sans-serif` for body, `monospace` for code/labels
- **Monogram blocks:** Two-letter codes in 44x44px rounded squares with tinted backgrounds (e.g., SC for Scanner, HP for Hyper Parse)
- **Borders:** `1px solid #313244`
- **Card style:** `background:#181825; border:1px solid #313244; border-radius:14px; padding:28px`
- **Callout boxes:** Left-colored border with tinted background (mauve for info, yellow for warnings, blue for tips)

## Key URLs
- **LemonSqueezy checkout:** `https://formfield.lemonsqueezy.com/checkout/buy/ae8b9f68-e30c-4edf-b54e-f39a19a73af1`
- **Support email:** `support@form-field.com`
- **Product:** Form and Field v11, SketchUp 2026

## Header Component (used on all guide pages)
Every guide page has this header at the top:
```html
<div style="display:flex;align-items:center;justify-content:space-between;padding:0 0 24px;margin-bottom:8px;">
  <a href="/" style="display:flex;align-items:center;gap:10px;text-decoration:none;">
    <div style="width:36px;height:36px;border-radius:8px;background:linear-gradient(135deg,rgba(203,166,247,0.2),rgba(137,180,250,0.2));border:1.5px solid rgba(203,166,247,0.35);display:flex;align-items:center;justify-content:center;font-family:monospace;font-weight:700;font-size:14px;color:#cba6f7;">FF</div>
    <span style="font-family:monospace;font-weight:600;font-size:15px;color:#cdd6f4;">Form and Field</span>
  </a>
  <a href="/" style="font-size:13px;color:#a6adc8;text-decoration:none;font-family:monospace;">← Home</a>
</div>
```

## Rules
- ALL styles must be inline — no `<style>`, `<script>`, or `<link>` tags (they work on Cloudflare Pages but we keep inline for consistency and portability)
- Exception: the base page wrapper can use a minimal `<style>` for reset and body background since we're on Cloudflare now
- Keep all pages self-contained — each index.html is a complete document
- Max content width: 800px for guides, 1080px for homepage feature grid
- Videos use `<video controls playsinline preload="metadata">` with border-radius:12px and shadow
- Images use `border-radius:8px; border:1px solid #313244`
- Guide pages are numbered steps with colored monogram badges
- "Coming soon" stub pages use the standard template with the header, title, and a centered badge
