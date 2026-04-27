This file provides guidance to agents when working with code in this repository.

## Project Overview

This is the **COSMAL (Computational spintronics and magnetism Lab)** website - a static academic lab website for Prof. Zhifeng Zhu's research group at ShanghaiTech University's School of Information Science and Technology.

**Technology Stack:**
- Pure HTML5, CSS3, and Vanilla JavaScript
- **All pages (9/9)**: Tailwind CSS via CDN with custom design system
- Custom color palette: Green accent (#22c55e) with design tokens
- Typography: Inter (English) + Noto Sans SC (Chinese)
- FontAwesome icons
- No build system, framework, or package manager

**Modernization Status:**
The site modernization is complete. As of Feb 2025:
- ✅ **All pages modernized (Tailwind)**: index, research, Group, Awards, News, Teaching, Labmanual, Invited Talk, Gallery
- See `MODERNIZATION-SUMMARY.md` for details on the modernization project

## File Structure

```
/                           # Root - 9 HTML pages
├── *.html                  # All main pages (index, research, Group, News, etc.)
├── assets/
│   ├── css/               # FontAwesome, custom styles, templatemo.css
│   ├── js/                # jQuery, templatemo.js, custom.js (empty)
│   ├── img/               # Photos organized by person/event (groupphoto*, lecture/, etc.)
│   └── webfonts/          # FontAwesome font files
```

**Main HTML Pages:**
- `index.html` - Homepage with hero carousel and Prof. Zhu's biography (bilingual: English + 中文)
- `research.html` - Research publications and topics
- `Group.html` - Lab members and alumni
- `News.html` - Lab news and updates
- `Teaching.html` - Course information
- `Labmanual.html` - Lab manual and protocols
- `Invited Talk.html` - Invited talks and presentations
- `Awards.html` - Awards received by lab members
- `Gallery.html` - Photo gallery

## Architecture

### Shared Components

All pages use Tailwind CSS with the following shared components:
- Sticky navigation bar with hamburger menu (mobile)
- Clean hero sections with gradient backgrounds
- Footer with organized links and social media
- Responsive grid layouts using Tailwind utilities
- Design tokens for consistent spacing and colors

### Navigation Structure

All pages link to each other via the main navbar. The navigation structure is:
- Home → Research → Group → Teaching → Labmanual → News → Invited Talk → Awards → Gallery

### Content Patterns

- **Bilingual Content**: Many pages include both English and Chinese text (especially biography and descriptions)
- **Image References**: Images stored in `assets/img/` with descriptive names (e.g., `groupphoto2025.jpg`, person names)
- **Thesis PDFs**: Located in `assets/img/thesis/` (naming not visible in current files)
- **Lecture Photos**: Located in `assets/img/lecture/` (guest lecture photos)

## Development Workflow

### Critical Workflow Rules

⚠️ **ALWAYS follow these rules when making website changes:**

**Always setup local server before pushing website changes** - Verify all changes work correctly

```bash
python3 -m http.server 8000
```
Ask the user to test the website in your browser at http://localhost:8000, only the user say yes, then you can push to GitHub.

### No Build Process
This is a **static website** with no build system:
- Edit HTML/CSS/JS files directly
- Test by opening files in a browser
- Deploy by pushing to git or uploading files to web server
- No package.json, no npm install, no build step

### Making Changes

1. **Edit pages directly**: Each HTML page is standalone with complete structure
2. **Update navigation**: If adding/removing pages, update the navbar in ALL HTML files
4. **Images**: Place new images in `assets/img/` and reference with relative paths

**Styling Guidelines:**
- Use Tailwind utility classes for styling
- Follow the design tokens (spacing, colors defined in tailwind.config)
- Maintain the custom green color palette (#22c55e as primary-500)

### Common Updates

- **Adding news**: Edit `News.html`
- **Updating publications**: Edit `research.html`
- **Adding group members**: Edit `Group.html`
- **Updating photos**: Replace/add images in `assets/img/`
- **Changing contact info**: Update footer in all HTML files

### Publication Formatting

- In `research.html`, for both the Journal Papers and Conference Papers sections, use italic styling only on the journal/venue line. Do not italicize paper titles, author lines, numbering, or other publication metadata outside the journal/conference name line.

## Important Notes

- **Manual navigation updates**: Since navigation is duplicated across all pages, changes must be made in every HTML file
- **Maintenance**: Site is maintained by Zhengde Xu (2021-present)

## Deployment

- Repository: `zhuzibn/zhuzibn.github.io`
- Hosted on GitHub Pages
- Deploy using gh CLI: `gh repo sync` (or `git push origin master` if gh CLI auth is configured)
- No CI/CD configured
