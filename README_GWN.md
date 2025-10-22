# Government Workforce Network LLC – Website

Together, protecting and promoting employee well-being.

This repo contains the static site (single `index.html` + images).  
Deployed on **Netlify** via GitHub, with **auto-publish locked** so changes are safe to preview first.

---

## Quick Start

**Preview locally**
1. Download / clone this repo.
2. Open `index.html` in your browser (double-click it).

**Deploy (safe mode)**
1. Connect the repo to Netlify (if not already).
2. In Netlify go to **Site settings → Build & deploy → Continuous Deployment**  
   - **Stop auto publishing** (keeps production unchanged).  
   - **Deploy Previews**: ON (default).
3. Push changes to GitHub. Netlify creates a **Preview Deploy URL**.
4. Review the preview on desktop & mobile.
5. When ready, click **Publish deploy** in Netlify.

---

## Repo Structure

```
/
├─ index.html
├─ hero.png
├─ logo.jpg              ← (or logo.png; match the extension used in index.html)
├─ free-logodesign.png
├─ free-jobposting.png
├─ join-us.png
├─ professional-growth.png
├─ recognition-galas.png
├─ recruiting-directors.png
├─ service-grant-writing.png
├─ service-job-postings.jpg
├─ service-website-dev.png
├─ sip-and-serve.png
├─ sponsors-partners.png
└─ README.md
```

> **Note:** Netlify is **case-sensitive** (`Hero.png` ≠ `hero.png`).  
> Keep filenames exactly as referenced in `index.html`.

---

## Images & Hero

- Card and banner images use `object-fit: contain` to avoid “zoomed-in” cropping.
- Replace the hero photo by updating **either** the file **or** the HTML.

**Option A – Keep HTML, replace the file**  
Overwrite `hero.png` with your new image (same name).

**Option B – Keep file, change HTML**  
Update the hero `<img>` in `index.html`:
```html
<section class="hero" id="top">
  <img src="hero.png" alt="Government Workforce Team">
  <div class="hero-content container">
    <span class="eyebrow">Government Workforce Network LLC</span>
    <h1>Together, Protecting and Promoting Employee Well-Being</h1>
    <p class="lede">A global, rank-free community for public servants and veterans — where well-being, mentorship, and career growth come first.</p>
  </div>
</section>
```

**Logo**  
If your logo file is `logo.png`, update the header tag:
```html
<img src="logo.png" alt="GWN Logo">
```

---

## Netlify Settings (recommended)

- **Stop auto publishing**: ON  
  _Site settings → Build & deploy → Continuous Deployment → Stop auto publishing_
- **Production branch**: `main`
- **Deploy Previews**: ON (default)
- **Branch deploys**: ON (optional)
- **Atomic deploys**: ON (default)
- **Forms**: No extra setup. Forms use `data-netlify="true"` and a honeypot field.

---

## Pre-Publish Checklist

- [ ] All images load (no broken links; correct **case**).
- [ ] Section anchors land below the sticky header (`scroll-margin-top` is set).
- [ ] All “Click Here” buttons open the correct email, link, or modal.
- [ ] Netlify Forms show a quick inline “Thank you” after submit.
- [ ] Mobile spacing looks good (test 360–414px widths).

---

## Common Fixes

**Image doesn’t show on Netlify**  
- Check the exact filename **and case** in `index.html`.  
- Use relative paths like `src="hero.png"` (no leading `/`).

**Hero looks too boxed**  
- By design we use `contain` so the entire photo is visible.  
  For a single image you want full-bleed, change that image to:
```css
object-fit: cover; object-position: center;
```

**Forms not sending**  
- Ensure `<form ... data-netlify="true" netlify-honeypot="bot-field">` is present.  
- After a test submit, the form should appear under Netlify → **Forms**.

---

## Commit Message Template

```
feat(site): replace hero and update image paths
fix(img): correct case-sensitive filename for sponsors-partners.png
chore: update README with deploy steps
```

---

## Support

Questions or updates?  
Email: **governmentworkforcenetwork@protonmail.com**
