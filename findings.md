# Findings & Decisions

## Requirements
- Modernize UI/UX of COSMAL lab website
- Use Tailwind CSS + Shadcn/UI aesthetic (clean, modern, professional)
- Improve responsiveness (mobile-first)
- Enhance accessibility (WCAG AA compliance)
- **CRITICAL**: Preserve ALL existing content (publications, awards, bio, news, teaching materials)
- Maintain bilingual content (English/Chinese)
- Clean, professional academic aesthetic
- Optional: Dark mode support

## Research Findings
- **Current Stack**: Pure HTML5, CSS3, Vanilla JavaScript + Bootstrap 5 (CDN)
- **Template Origin**: TemplateMo 559 Zay Shop (e-commerce template repurposed)
- **Build System**: None - pure static site
- **Total Pages**: 13 HTML files in root directory
- **Shared Components**: Navigation, footer, and search modal duplicated across all pages
- **Images**: Stored in assets/img/ with organized subdirectories (lecture/, thesis/)
- **Custom Files**: assets/css/custom.css and assets/js/custom.js are mostly empty
- **Maintenance**: Hand-maintained by Zhengde Xu (2021-present)

### File Structure Discovery
```
/home/zhuzibn/zhuzibn.github.io/
├── index.html (homepage + Prof. Zhu's bilingual bio)
├── research.html (publications and research topics)
├── Group.html (lab members and alumni)
├── News.html (lab news and updates)
├── Teaching.html (course information)
├── Openings.html (open positions)
├── Code.html (code/software resources)
├── Labmanual.html (lab manual)
├── Invited Talk.html (invited talks)
├── Awards.html (awards received)
├── Gallery.html (photo gallery)
├── Personal.html (personal page)
├── contact.html (static form, no backend)
└── assets/
    ├── css/ (Bootstrap, FontAwesome, templatemo.css, custom.css)
    ├── js/ (jQuery, Bootstrap JS, custom.js)
    ├── img/ (photos, lecture/, thesis/)
    └── webfonts/ (FontAwesome fonts)
```

### Navigation Structure
All pages link via main navbar in this order:
1. Home
2. Research
3. Group
4. Openings
5. Code
6. Teaching
7. Labmanual
8. News
9. Invited Talk
10. Awards
11. Gallery
12. Personal

### Content Types Identified (Detailed Inventory)

### **Publications** (research.html) - MUST PRESERVE ALL
- **Journal Papers**: 39 publications numbered 39-1 (2025-2017)
  - Recent 2025 papers: Fe3GaTe2 modulation, Mn3Neel vector switching, Vertical Soliton, etc.
  - All papers include: title, full author list, journal name, volume, page numbers, year
  - Some have "News Coverage" links (WeChat articles)
  - Corresponding authors marked with asterisk (*)
  - Links to Nature Communications, Physical Review Letters, Applied Physics Letters, etc.

- **Conference Papers**: 31 publications numbered 31-1 (2025-2016)
  - Include conference names, locations, dates
  - Some in Chinese (磁学会议)
  - Poster presentations noted
  - Co-authors marked with #, corresponding authors with *

- **Theses**: 3 theses
  - Zhifeng Zhu PhD thesis (NUS)
  - 2 Master's theses in Chinese with PDF downloads
  - Files in assets/img/thesis/

### **Awards** (Awards.html) - MUST PRESERVE ALL
- **Outstanding Graduate Awards**: 2025.04, 2024.05 (names listed)
- **National Scholarship (Top 2%)**: 2025.10, 2024.10 (names listed)
- **Merit Student (Top 5%)**: 2025.12, 2024.12, 2023.12, 2022.12 (names listed)
- **Outstanding Student (Top 10%)**: 2025.12, 2024.12, 2023.12, 2022.12 (names listed)
- **Alumni**: 2025.05, 2024.05, 2023.05, 2021.06 (names and destinations)
- **Others**: Awards & Visiting (2025.09 Si-Nan Award, CSC funding 2025.05, 2024.07)

### **Biography** (index.html) - MUST PRESERVE ALL
- **Prof. Zhifeng Zhu**: Complete bilingual bio (English + 中文简介)
  - Education: NUS PhD (2019), UESTC Bachelor (2014)
  - Research focus: Antiferromagnets, ferrimagnets spintronic devices
  - Current positions: Shanghai Sailing Project, NSFC Youth Project
  - Reviewer roles for multiple journals
  - Links to "More Information" (WeChat article)

### **Group Members** (Group.html) - MUST PRESERVE ALL
- **Principal Investigator**: Zhifeng Zhu with photo, email, position
- **Graduate Students** (8 current members):
  - Xue Zhang (PhD, since 2021): B.Sc. Xidian, research interests
  - Zhengde Xu (PhD, since 2021): B.Sc. Hebei, research interests
  - Zhenhang Kong (PhD, since 2023): B.Sc. Xidian, research interests
  - Boyu Zhao (Master, since 2023): B.Sc. Beihang, research interests
  - Dongyang Chen (Master, since 2024): B.Sc. Southwest Petroleum, research interests
  - Xuezhong Li (Master, since 2025): B.Sc. ShanghaiTech, research interests
  - Chenhao Xu (Master, since 2025): B.Sc. ShanghaiTech, research interests
  - Guo Chen (Master, since 2025): B.Sc. ShanghaiTech, research interests
  - Each has photo, role, start date, B.Sc. university, research interests

- **Former Members**:
  - **Alumni**: 7 names with graduation years and B.Sc. universities
  - **Professional Master's (专硕)**: 2020, 2022, 2024 cohorts with names and companies
  - **FYP Students**: 2020-2025 with names and current positions

### **News** (News.html) - PARTIALLY READ
- **2025 News** (multiple entries November-October):
  - Guest lectures with speakers, topics, and photo links
  - Paper acceptances with journal names
  - Need to read full file for complete inventory

### **Teaching** (Teaching.html) - MUST PRESERVE ALL
- **3 Courses** with Baidu Pan links and passwords:
  - Spintronics @ SIST ShanghaiTech (password: b3bg)
  - Digital Circuits @ SIST ShanghaiTech (password: xdy6)
  - Digital Integrated Circuits II @ SIST ShanghaiTech (password: b4fq)

### **Openings** (Openings.html) - MUST PRESERVE ALL
- **Master Students**: Position available with link to recruitment PDF
- **Research Assistant Professor/Postdoctoral Fellow**: Link to job posting
- **Research Engineer**: Link to job posting
- All positions have Chinese descriptions and application links

### **Other Pages** (to be audited):
- **Code.html**: Code/software resources
- **Labmanual.html**: Lab manual and protocols
- **Invited Talk.html**: Invited talks and presentations
- **Gallery.html**: Photo gallery
- **Personal.html**: Personal page
- **contact.html**: Static contact form

## Technical Decisions
| Decision | Rationale |
|----------|-----------|
| **TBD: Tailwind CDN vs Build** | Will determine during Phase 2 based on user preference |
| **Component extraction** | Nav, footer, cards duplicated - extract for maintainability |
| **Keep static HTML** | No build system currently, simplest path is minimal changes to architecture |
| **Preserve page structure** | Reduce risk of content loss during migration |
| **Mobile-first breakpoints** | Standard Tailwind: sm (640px), md (768px), lg (1024px), xl (1280px) |

## Issues Encountered
| Issue | Resolution |
|-------|------------|
| None yet | - |

## Resources
- Tailwind CSS: https://tailwindcss.com/docs
- Tailwind via CDN: https://tailwindcss.com/docs/installation/play-cdn
- Shadcn/UI design inspiration: https://ui.shadcn.com/
- Web Content Accessibility Guidelines (WCAG): https://www.w3.org/WAI/WCAG21/quickref/
- Current site: /home/zhuzibn/zhuzibn.github.io/

## Visual/Browser Findings
- **Not yet viewed in browser** - will add findings during Phase 5 testing
- Will document current rendering, spacing, colors, and responsive behavior
- Will screenshot before/after for comparison

---
REMINDER: The 2-Action Rule
After every 2 view/browser/search operations, you MUST update this file.
This prevents visual information from being lost.
