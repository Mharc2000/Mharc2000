# Design Specification: ATS-Compliant Developer Resume & Downloadable PDF

**Date**: 2026-10-07  
**Author**: Ivan Mharc Maglangit & Antigravity  
**Target Repository**: `Mharc2000/Mharc2000`  
**Status**: Draft for User Review  

---

## 1. Overview & Objective

Transform the GitHub Profile `README.md` into a modern, ATS-friendly developer resume for **Ivan Mharc Maglangit (Junior Web Developer)**, complete with a prominent "Download Resume (PDF)" badge linking directly to an ATS-compliant PDF resume (`Ivan_Mharc_Resume.pdf`) stored in the repository.

---

## 2. ATS (Applicant Tracking System) Compliance Principles

To ensure 100% ATS parser compatibility:
1. **Single-Column Linear Hierarchy**: Strictly standard hierarchical structure (`#`, `##`, `###`) without nested table column layouts for body text that confuse parsers.
2. **Standard Section Headings**: Exact recognized headings: `Professional Summary`, `Work Experience`, `Technical Skills`, `Projects`, `Education`, and `Contact Information`.
3. **Selectable & Searchable PDF Text**: The generated PDF must contain selectable vector text (never rasterized images of text) so parsing engines can extract keywords.
4. **Keyword Density**: Strategic inclusion of industry-standard keywords: ERPNext, Python, JavaScript, TypeScript, React, SQL, POS, REST APIs, Linux, Database Administration.
5. **Standardized Date Formats**: Unambiguous `Month Year – Present` and `Month Year – Month Year`.

---

## 3. Profile README Architecture

### A. Header & Download Badge
- **Name**: `Ivan Mharc Maglangit`
- **Professional Title**: `Junior Web Developer`
- **Location**: `Davao City, Philippines 🇵🇭`
- **Primary Actions**:
  - `[![Download Resume PDF](https://img.shields.io/badge/Download_Resume-PDF-E50914?style=for-the-badge&logo=adobeacrobatreader&logoColor=white)](./Ivan_Mharc_Resume.pdf)`
  - Direct contact links: Email (`ivanmharcmaglangit@gmail.com`), LinkedIn (`https://www.linkedin.com/in/ivan-mharc-maglangit-86a473205/`), and GitHub.

### B. Professional Summary
- Impact-driven 3-sentence summary highlighting full-stack web development, ERPNext customization, offline-first architectures, and database administration.

### C. Work Experience (Reverse Chronological)
1. **Software Developer** | **Amesco Drug Corporation**  
   *May 2024 – Present | Philippines (On-site)*  
   - Spearheaded customization and maintenance for enterprise Point of Sale (POS) system, aligning workflows with pharmaceutical and retail business operations.
   - Engineered automations utilizing ERPNext Client Scripts (JavaScript) and Server Scripts (Python), reducing manual processes and accelerating store workflows.
   - Designed standardized, audit-ready Print Formats for core DocTypes using HTML/CSS, complying with internal policies and regulatory standards.
   - Built custom SQL queries and reports, delivering real-time visibility into sales performance, stock movement, and inventory tracking.
   - *Key Skills*: ERPNext, Python, JavaScript, SQL, HTML/CSS, Linux.

2. **Assistant Database & System Administrator** | **Ana's Breeders Farms Inc**  
   *Jul 2023 – Apr 2024 (10 mos) | Davao del Sur, Philippines*  
   - Administered on-premise Windows/Linux server infrastructure, ensuring system uptime, reliability, and network stability.
   - Maintained relational enterprise databases and supported internal .NET applications, executing scheduled backups and query diagnostic checks.
   - Managed user permissions, network configurations, and security protocols to protect proprietary operational data.
   - *Key Skills*: Server Administration, .NET Framework, SQL, Database Management, Systems Management.

### D. Technical Skills (ATS Text + Visual Badges)
- **Languages**: JavaScript (ES6+), TypeScript, Python, C#, SQL, HTML5, CSS3, Bash
- **Web & Frameworks**: React, Vue.js, Angular, React Native, Tailwind CSS, FastAPI, Node.js, Express, Django, PHP
- **Databases**: MySQL, MariaDB, MongoDB
- **Enterprise & Tools**: ERPNext, Git, Docker, Linux, .NET Framework

### E. Education
- **Bachelor of Science in Information Technology** (or Degree in Computing)  
  *University / College, Davao City, Philippines*

### F. GitHub Analytics & Activity
- Dedicated section at the bottom preserving the verified `github-stats-extended` widgets:
  - GitHub Stats Card (`theme=radical&rank_icon=github&border_radius=10`)
  - Top Languages Card (`theme=radical&layout=compact&hide_border=true`)

---

## 4. PDF Resume Generation & Delivery

1. **Format**: Single-column clean modern ATS standard, standard margins (0.5–0.75 in), clean web-safe typography, no tables for layout.
2. **Build Method**: A clean automated script (using Python/headless tool) will generate `Ivan_Mharc_Resume.pdf` from the exact resume content.
3. **Verification**: Text extraction verification (`pdftotext` or python parser) to confirm 100% machine readability and keyword extractability.
4. **Repository Asset**: Stored at `./Ivan_Mharc_Resume.pdf` in the root of the repository.

---

## 5. Implementation Phases

1. **Phase 1**: Generate the ATS-compliant `Ivan_Mharc_Resume.pdf` and verify text extraction.
2. **Phase 2**: Restructure `README.md` into the ATS-compliant resume layout with the PDF download badge and `github-stats-extended` analytics.
3. **Phase 3**: Verify links, rendering, and push updates to GitHub.
