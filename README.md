# Fitness Arena Gym — Website (G-6, Islamabad)

A premium, animated, multi-page demo website built for **Fitness Arena Gym**, G-6, Islamabad — created as a sales/portfolio concept to show the gym owner what a professional online presence could look like.

**Live site:** _add your GitHub Pages link here once deployed_

---

## What this is

A fully static (no build tools, no backend) multi-page website:

| File | Page |
|---|---|
| `index.html` | Home |
| `about.html` | About the gym |
| `trainers.html` | Full coaching roster (9 named staff) |
| `facilities.html` | Facilities, immersive full-image layout |
| `gallery.html` | Photo gallery (real-photo-ready, no stock) |
| `membership.html` | Membership info |
| `appointment.html` | Booking form |
| `location.html` | Map & address |
| `contact.html` | Contact form |
| `media-test.html` | Diagnostic page — confirms external images/video load correctly in a browser |

Every page shares the same design system, animation engine, navigation and footer.

## Content policy — what's real vs. placeholder

This project was built with one hard rule throughout: **never invent facts about the business.**

- ✅ **Real & verified:** all 9 coach/staff names, roles, and every review quote are sourced directly from Fitness Arena's public Google reviews (63 reviews reviewed).
- ✅ **Real address:** G-6, Abpara Market, Islamabad — as referenced by reviewers (not independently confirmed against an official listing).
- 🟠 **Stock media:** photos and video are tasteful, free-license stock (Unsplash / Pexels / Mixkit), clearly tagged "Sample" on the page. **None of it is real Fitness Arena photography.**
- ❌ **Deliberately left blank:** phone number, opening hours, social media links, and membership pricing — none of this information was supplied, so nothing was invented. Replace these placeholders with real details as soon as they're available.
- **Gallery page is the one exception** — it intentionally contains *no* stock images, only empty placeholder tiles with category filters, ready to receive real gym photography.

## Replacing the stock media with real assets

Every image is a plain `<img src="...">` tag and every video is a `<video><source src="..."></video>` tag — no build step, no image pipeline. To swap in real photos/video:

1. Add your image/video files to the repo (e.g. an `/assets` folder).
2. Find the relevant `src="https://images.unsplash.com/..."` or `src="https://assets.mixkit.co/..."` in the HTML.
3. Replace it with your local path, e.g. `src="assets/gym-floor.jpg"`.
4. Remove the neighboring `<span class="stock-tag">Sample photo</span>` element.

## Running locally

Because the site loads external images/video, **open it through a local server rather than double-clicking the HTML file** — some browsers restrict external requests from `file://` pages.

```bash
# from inside the project folder
python3 -m http.server 8000
# then open:
http://localhost:8000/index.html
```

If images/video still don't appear, open `media-test.html` first — it isolates the problem to either your network/browser or the site itself.

## Deploying (GitHub Pages)

1. Push all files to a public GitHub repository.
2. Repo → **Settings → Pages** → set Branch to `main`, folder `/ (root)` → Save.
3. Your site goes live at `https://<username>.github.io/<repo-name>/` within a minute or two.

## Tech notes

- Pure HTML/CSS/JS — no framework, no npm install, no build step.
- Fonts: Anton, Bebas Neue, Inter, JetBrains Mono (Google Fonts, loaded via CDN).
- Respects `prefers-reduced-motion` throughout.
- Custom cursor, particle-field canvas backgrounds, 3D tilt cards, and page-transition wipes are all vanilla JS (no GSAP/Framer Motion dependency).
- Forms (`appointment.html`, `contact.html`) currently submit via `mailto:` — no backend is connected. Wire up a real form endpoint before relying on them to capture leads.

## Credits

- Review data & staff names: Fitness Arena Gym's public Google Business listing.
- Stock photography: [Unsplash](https://unsplash.com) and [Pexels](https://pexels.com) (free license).
- Stock video: [Mixkit](https://mixkit.co) (free license).
