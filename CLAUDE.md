# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a GitHub Pages personal academic website for Shin Dong-Yeon, deployed at `shin-dong-yeon.github.io`. It also hosts individual project pages for papers. There is no build system — everything is pure HTML/CSS/JS deployed directly via git push to `master`.

## Structure

- `index.html` — Personal homepage (Jon Barron style: table-based layout, hover video effects)
- `stylesheet.css` — Shared CSS for the homepage (Lato font, link colors `#1772d0`/`#f09228`)
- `mipnerf/`, `mipnerf360/`, `zipnerf/` — Reference project pages to use as templates
- `HDR-NSFF/` — Project page for the ICLR 2026 paper (main ongoing work)
- `images/` — Profile photos and paper teaser images
- `videos/` — Demo videos for the homepage paper list
- `data/` — CV PDF

## Project Page Pattern

Project pages (e.g., `mipnerf/`, `zipnerf/`, `HDR-NSFF/`) use:
- Bootstrap 3.3.5 (`css/bootstrap.min.css`) + custom `css/app.css`
- jQuery 1.11.3 + CodeMirror 5.8.0 (for BibTeX copy button)
- Standard sections: title → authors → links (paper/code/dataset) → abstract → method figure → results → BibTeX
- CDN links for Bootstrap/jQuery/FontAwesome (no local install needed)

## Homepage Paper Entry Pattern

Each paper in `index.html` follows this structure:
```html
<tr onmouseout="fn_stop()" onmouseover="fn_start()">
  <td><!-- video thumbnail with hover reveal --></td>
  <td>
    <a href="..."><span class="papertitle">Title</span></a>
    <br><strong>Author</strong>, Co-authors<br>
    <em>Venue Year</em><br>
    <a href="...">project page</a> / <a href="...">paper</a> / <a href="...">code</a>
  </td>
</tr>
```
Hover effect: `opacity: 0 → 1` transition on a video overlay above a static thumbnail image.

## HDR-NSFF Paper (ICLR 2026)

- **Full title**: HDR-NSFF: High Dynamic Range Neural Scene Flow Fields
- **Authors**: Shin Dong-Yeon (KAIST), Kim Jun-Seong (POSTECH), Kwon Byung-Ki (POSTECH), Tae-Hyun Oh (KAIST)
- **arXiv**: `https://arxiv.org/abs/2603.08313`
- **Code**: `https://github.com/kaist-ami/HDR-NSFF`
- **Project page URL**: `https://shin-dong-yeon.github.io/HDR-NSFF/`
- Source materials at `/Users/shindy/Duke/github_page/HDR-NSFF/` (paper PDF, poster PDF, presentation PPTX)

## Deployment

Changes go live after `git push origin master`. No CI/CD — GitHub Pages serves the repo root directly.
