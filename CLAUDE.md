# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the **COSMAL (Computational spintronics and magnetism Lab)** website - a static academic lab website for Prof. Zhifeng Zhu's research group at ShanghaiTech University's School of Information Science and Technology.

**Technology Stack:**
- Pure HTML5, CSS3, and Vanilla JavaScript
- Bootstrap 5 (via CDN in assets/css/)
- FontAwesome icons
- Based on TemplateMo 559 Zay Shop (heavily customized for academic use)
- No build system, framework, or package manager

## File Structure

```
/                           # Root - 13 HTML pages
├── *.html                  # All main pages (index, research, Group, News, etc.)
├── assets/
│   ├── css/               # Bootstrap, FontAwesome, custom styles, templatemo.css
│   ├── js/                # jQuery, Bootstrap JS, templatemo.js, custom.js (empty)
│   ├── img/               # Photos organized by person/event (groupphoto*, lecture/, etc.)
│   └── webfonts/          # FontAwesome font files
```

**Main HTML Pages:**
- `index.html` - Homepage with hero carousel and Prof. Zhu's biography (bilingual: English + 中文)
- `research.html` - Research publications and topics
- `Group.html` - Lab members and alumni
- `News.html` - Lab news and updates
- `Teaching.html` - Course information
- `Openings.html` - Open positions for prospective students
- `Code.html` - Code/software resources
- `Labmanual.html` - Lab manual and protocols
- `Invited Talk.html` - Invited talks and presentations
- `Awards.html` - Awards received by lab members
- `Gallery.html` - Photo gallery
- `Personal.html` - Personal page
- `contact.html` - Contact form (static, no backend)

## Architecture

### Shared Components

Each HTML page follows the same structure (copied, not included):

1. **Top Navigation Bar** (`#templatemo_nav_top`) - Secondary nav with contact info and social links
2. **Main Navigation** - Bootstrap navbar with links to all pages
3. **Search Modal** (`#templatemo_search`) - Search UI (non-functional)
4. **Page-Specific Content** - Main content area unique to each page
5. **Footer** (`#tempaltemo_footer`) - Contact, email, social links, attribution to Zhengde Xu

### Navigation Structure

All pages link to each other via the main navbar. The navigation structure is:
- Home → Research → Group → Openings → Code → Teaching → Labmanual → News → Invited Talk → Awards → Gallery → Personal

### Content Patterns

- **Bilingual Content**: Many pages include both English and Chinese text (especially biography and descriptions)
- **Image References**: Images stored in `assets/img/` with descriptive names (e.g., `groupphoto2025.jpg`, person names)
- **Thesis PDFs**: Located in `assets/img/thesis/` (naming not visible in current files)
- **Lecture Photos**: Located in `assets/img/lecture/` (guest lecture photos)

## Development Workflow

### No Build Process
This is a **static website** with no build system:
- Edit HTML/CSS/JS files directly
- Test by opening files in a browser
- Deploy by pushing to git or uploading files to web server
- No package.json, no npm install, no build step

### Making Changes

1. **Edit pages directly**: Each HTML page is standalone with complete structure
2. **Test locally**: Open HTML file in browser or use a local server
3. **Update navigation**: If adding/removing pages, update the navbar in ALL HTML files
4. **Images**: Place new images in `assets/img/` and reference with relative paths

### Common Updates

- **Adding news**: Edit `News.html`
- **Updating publications**: Edit `research.html`
- **Adding group members**: Edit `Group.html`
- **Updating photos**: Replace/add images in `assets/img/`
- **Changing contact info**: Update footer in all HTML files

## Important Notes

- **Contact form is static**: The form in `contact.html` has no backend - it's purely decorative
- **Manual navigation updates**: Since navigation is duplicated across all pages, changes must be made in every HTML file
- **Template origin**: Site built from TemplateMo 559 (e-commerce template repurposed for academic use)
- **Maintenance**: Site is maintained by Zhengde Xu (2021-present)
- **Multilingual**: Mix of English and Chinese content - maintain both when updating

## Deployment

- Repository: `zhuzibn/zhuzibn.github.io`
- Likely hosted on GitHub Pages (given repository name)
- Simple push-based deployment - no CI/CD configured
