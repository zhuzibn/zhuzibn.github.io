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
- Home → Research → Group → News → Awards → Teaching → Labmanual → Gallery

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
- No CI/CD configured

## Source Code Changes

### 2026-05-23 - Talks navigation removal
- Removed the `Talks` navigation item linking to `Invited Talk.html` from the desktop and mobile navbars across all static HTML pages.
- Updated the documented navbar structure in `AGENTS.md` so it no longer lists `Invited Talk`.
- Prevention: when removing a navigation item, search all HTML pages for both the visible label and target filename so desktop, mobile, and accidental content-area copies are removed together.

### 2026-05-23 - Talks Markdown export
- Added `Talks.md` with the visible invited-talk entries from `Invited Talk.html`, organized by year.
- Omitted lecture image attachment links and kept only the talk dates, speakers, affiliations, and lecture titles as plain Markdown text.
- Prevention: when exporting page content to Markdown, strip asset links and navigation fragments unless the request explicitly asks to preserve attachments or page chrome.

### 2026-05-23 - Awards graduate section ordering update
- Moved the `Outstanding Graduate of Shanghai` section before `Outstanding Graduate of ShanghaiTech University` in `Awards.html`.
- Updated the ShanghaiTech University outstanding graduate label to `上海科技大学优秀毕业生Top 10%`.
- Prevention: when adding related award categories, check their display order against the requested hierarchy and verify percentage labels in both English-adjacent and Chinese text before finishing.

### 2026-05-23 - Awards Shanghai outstanding graduate section
- Added a new `Outstanding Graduate of Shanghai` section to `Awards.html` with the Chinese label `上海市优秀毕业生Top3.5%`.
- Added the 2026.05 award entry for Zhengde Xu as a PhD student.
- Prevention: when adding a new award category, place it near related award sections and preserve the existing dated-row layout so awards remain visually consistent.

### 2026-04-28 - Homepage maintainer attribution update
- Replaced the old homepage maintainer sentence with a dated maintainer history for Zhifeng, Jie Ren, and Zhengde Xu.
- Removed the duplicated maintainer attribution from the other static page footers so the maintainer history displays only on `index.html`.
- Prevention: when editing footer-only attribution text, search all HTML pages for the exact visible sentence and verify the retained copy appears only on the intended page.

### 2026-04-28 - ShanghaiTech email addition
- Updated every visible occurrence of `zzfmvp@gmail.com` across the nine static HTML pages to also show `zhuzhf@shanghaitech.edu.cn`.
- Updated matching `mailto:` links so email contact links address both `zzfmvp@gmail.com` and `zhuzhf@shanghaitech.edu.cn`.
- Prevention: when changing site-wide contact information, search all HTML files for both visible email text and `mailto:` attributes so header, footer, and profile-card contact details remain consistent.

### 2026-04-28 - Research page section jump links
- Converted the three section names in the `Research Introduction` helper text in `research.html` into in-page links for `Summary of Research`, `Journal Papers`, and `Conference Papers`.
- Added stable section anchors with scroll offsets so clicking each link jumps to the matching section without hiding the heading under the sticky navigation bar.
- Prevention: when adding in-page navigation, update both the header links and the target section IDs together, then verify each anchor exists exactly once.

### 2026-04-28 - Research page section guide
- Added a short page-header guide under `Research Introduction` in `research.html` stating that the page contains "Summary of Research", "Journal Papers", and "Conference Papers".
- Kept the existing research summary, journal paper list, and conference paper list unchanged.
- Prevention: when adjusting research-page header copy, verify the visible heading and helper text match the requested wording without changing section content below.

### 2026-04-28 - Research page header cleanup
- Removed the page-header sentence and PDF link reading "A brief introduction of our current research can be found here" from `research.html`.
- Kept the `Research Introduction` heading and the main research summary/publication sections unchanged.
- Prevention: when removing header helper text, search for the visible phrase in the target HTML file and verify only the requested paragraph/link is removed.

### 2026-04-28 - Research page Bio_Research_teaching refresh
- Updated the `Summary of Research` section in `research.html` to follow the research section from `Bio_Research_teaching.docx`, including the open-source GitHub sentence and collaborative "our/we" voice.
- Preserved the existing Tailwind card layout, publication list, typography conventions, underline emphasis, italics, bold journal metadata, subscripts, and external-link behavior.
- Prevention: when refreshing page text from a Word source, extract the `.docx` content first and compare it against the existing HTML summary so wording, emphasis, and source links are not accidentally dropped.

### 2026-04-28 - Candidate statement research and teaching sections
- Added a `Summary of Research` section near the top of `research.html`, preserving the wording and structure from `6-Candidate's Statement.docx` while converting Word formatting such as underline, italics, bold, and subscripts into HTML.
- Added a `Summary of Teaching` section near the top of `Teaching.html`, preserving the wording from `6-Candidate's Statement.docx` and rendering Table I as a responsive HTML table.
- Kept existing publication entries, thesis links, and course-material cards intact so the new statement-derived content supplements the current pages without changing established navigation or resource links.
- Prevention: when incorporating statement or CV content into public pages, confirm whether the request calls for exact wording or a page-level summary before editing, then verify that existing publication formatting and course-resource links remain unchanged.

### 2026-04-28 - Gallery group photo additions
- Updated `Gallery.html` to show the 2025, 2024, and 2020 group photos in the gallery grid, keeping the newest photos first and preserving the existing card layout.
- Added `assets/img/groupphoto2020.jpg` and `assets/img/groupphoto2024.jpg` from the OneDrive website photo folder; reused the existing `assets/img/groupphoto2025.jpg` because it matched the provided `2025.jpg` exactly.
- Removed a stray `Labmanual.html` navigation link that had been accidentally rendered inside the gallery content area.
- Prevention: when adding gallery photos, compare provided source images against existing `assets/img/groupphotoYYYY.*` files first, then verify the gallery grid contains only photo cards and no copied navigation fragments before finishing.

### 2026-04-27 - Homepage biography refresh
- Updated `index.html` to replace the English and Chinese biography text for Prof. Zhifeng Zhu with the April 2026 version covering education, ShanghaiTech appointment, research focus, grants, honors, publications, reviewing service, and student outcomes.
- Updated `.gitignore` to include the required local tool/cache exclusions: `.sisyphus/`, `.ruff_cache/`, and `**/__pycache__/`.
- Prevention: when updating homepage profile content, search for both `Biography` and `简介` in `index.html`, then verify the bilingual sections remain aligned before considering the content update complete.

## Error Logs

### 2026-05-23 - local server not running during navbar verification
- Error: `curl --noproxy '*' -I http://127.0.0.1:8000/index.html` failed with connection refused because the previous local static server was no longer running.
- Resolution: restarted the static server with `python3 -m http.server 8000` from the repository root and verified `index.html` returned `200 OK`.
- Prevention: before verifying static pages through `127.0.0.1:8000`, check whether the local server is still running or restart it from the repository root.

### 2026-04-28 - Git metadata writes blocked by sandbox
- Error: `git update-index --chmod=-x research.html AGENTS.md`, `git config core.filemode false`, and `git restore --staged research.html AGENTS.md` initially failed when the sandbox could not create temporary files or lock files under `.git`, reporting a read-only filesystem.
- Resolution: reran the required Git metadata operations with approved escalation, disabled local file-mode tracking for the WSL/OneDrive workspace, and unstaged the files so only working-tree content changes remain.
- Prevention: when Git reports mode-only changes on this Windows-mounted repository, confirm `core.filemode=false` before editing index metadata, and use approved escalation for `.git` metadata writes if the sandbox blocks lock-file creation.

### 2026-04-27 - local browser launch unavailable
- Error: `xdg-open http://localhost:8000` failed because no supported desktop or terminal browser was installed in the execution environment.
- Resolution: kept the local `python3 -m http.server 8000` server running and verified the homepage endpoint directly with `curl --noproxy '*' -I http://127.0.0.1:8000`, which returned `200 OK`.
- Prevention: when browser launch is unavailable in a headless environment, verify the static site through `127.0.0.1` with proxy bypass and provide the local URL for manual browser testing.
