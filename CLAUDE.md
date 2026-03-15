# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **static HTML/CSS portfolio website** for Pravin Mishra, used as a Week 1 deployment exercise in the **DevOps Micro Internship (DMI)** program. Students clone this repo, add ownership proof to the footer, and deploy it on Ubuntu + Nginx.

## No Build System

There is no build step, package manager, test suite, or linter. To preview the site, open `index.html` directly in a browser or serve it with any static file server:

```bash
# Quick local preview (Python)
python -m http.server 8080

# Or with Nginx on Ubuntu (DMI deployment target)
sudo cp -r . /var/www/html/
sudo systemctl start nginx
```

## File Structure

- `index.html` — single-page site with all sections: navbar, hero, about, services, courses, books, community, contact, footer
- `style.css` — all styles for `index.html` (privacy.html and terms.html use inline styles)
- `privacy.html` / `terms.html` — standalone pages with self-contained inline CSS
- `images/` — local assets (logo, profile, book covers, hero banner, signature)

## DMI Student Customization Rule

Students must edit the footer in `index.html` before deployment. The ownership proof line goes inside `.footer-bottom`, directly after the copyright line:

```html
<p><strong>Deployed by:</strong> DMI Cohort X | Your Name | Group X | Week 1 | DD-MM-YYYY</p>
```

This proof must be visible in the browser screenshot submission.

## Key Design Details

- Dark navbar (`rgba(0,0,0,0.95)`) with fixed positioning; `max-width: 1200px` container throughout
- Responsive via a hamburger menu (`#mobileMenu`) toggled by `toggleMenu()` inline JS in the navbar
- Font Awesome 6.5.0 loaded from cdnjs CDN — no local icon assets
- `privacy.html` and `terms.html` have dark backgrounds (`#111827`) with their own animation/styles; `index.html` has a white background
