# ATS Developer Resume & Downloadable PDF Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Transform the GitHub profile into an ATS-compliant developer resume with a matching, downloadable PDF (`Ivan_Mharc_Resume.pdf`).

**Architecture:** Create an ATS-standard single-column HTML/CSS resume template, compile it into a vector/text-searchable PDF using headless Chrome, update `README.md` with structured ATS resume sections, link the download badge to the PDF, and preserve `github-stats-extended` analytics at the bottom.

**Tech Stack:** Markdown, HTML5, CSS (Print Stylesheet), Google Chrome Headless (`--print-to-pdf`), `pdftotext`, Git.

## Global Constraints

- ATS single-column hierarchy: No nested table column layouts for body content in either the README or PDF.
- 100% searchable text: The PDF must have selectable, extractable text (verified with `pdftotext`).
- Preserved statistics: Maintain the verified `github-stats-extended` widgets.
- Working download link: The download button must link directly to `./Ivan_Mharc_Resume.pdf` in the repository root.

---

### Task 1: Generate ATS-Compliant PDF Resume

**Files:**
- Create: `resume_template.html`
- Create: `Ivan_Mharc_Resume.pdf`
- Test: `pdftotext` verification command

**Interfaces:**
- Produces: `Ivan_Mharc_Resume.pdf` at repository root with selectable text for Amesco Drug Corporation, Ana's Breeders Farms Inc, ERPNext, Python, JavaScript, and SQL.

- [ ] **Step 1: Create the ATS-friendly HTML template**
Write `resume_template.html` with clean typography, standard 0.5in print margins, semantic headers, and single-column ATS structure.

- [ ] **Step 2: Compile HTML to PDF via Headless Chrome**
Run: `google-chrome --headless --disable-gpu --no-sandbox --print-to-pdf=Ivan_Mharc_Resume.pdf resume_template.html`
Expected: File `Ivan_Mharc_Resume.pdf` created (~20-50 KB).

- [ ] **Step 3: Verify PDF text extraction**
Run: `pdftotext Ivan_Mharc_Resume.pdf - | grep -E "Amesco|Ana's|ERPNext|Junior Web Developer"`
Expected: Prints matched keywords confirming full text parseability.

- [ ] **Step 4: Commit PDF and template**
Run: `git add resume_template.html Ivan_Mharc_Resume.pdf && git commit -m "feat: add ATS resume template and generated PDF"`

---

### Task 2: Redesign Profile README into ATS Resume Layout

**Files:**
- Modify: `README.md`

**Interfaces:**
- Consumes: `./Ivan_Mharc_Resume.pdf` produced by Task 1.
- Produces: Updated `README.md` with ATS sections, contact buttons, and `github-stats-extended` widgets.

- [ ] **Step 1: Draft the ATS-structured README content**
Update `README.md` with:
1. Header: Name, `Junior Web Developer | Davao City, Philippines 🇵🇭`, and Download PDF Badge `[![Download Resume PDF](https://img.shields.io/badge/Download_Resume-PDF-E50914?style=for-the-badge&logo=adobeacrobatreader&logoColor=white)](./Ivan_Mharc_Resume.pdf)`.
2. Professional Summary: ATS-tailored bio.
3. Work Experience: Amesco Drug Corporation (May 2024 – Present) and Ana's Breeders Farms Inc (Jul 2023 – Apr 2024).
4. Technical Skills: Categorized text + Shields badges.
5. Featured Projects: Clear project cards with links.
6. Education: Degree in Computing/IT, Davao City.
7. GitHub Analytics: `github-stats-extended` cards.

- [ ] **Step 2: Verify README structure and links**
Check that markdown formatting is clean, no broken tags exist, and links point to valid targets.

- [ ] **Step 3: Commit README changes**
Run: `git add README.md && git commit -m "feat: redesign README into ATS developer resume format"`

---

### Task 3: Final Verification & Git Push

**Files:**
- Workspace files: `README.md`, `Ivan_Mharc_Resume.pdf`

- [ ] **Step 1: Verify git status and diff**
Run: `git status`
Expected: Working tree clean.

- [ ] **Step 2: Push commits to remote origin**
Run: `git push origin main`
Expected: Remote `origin/main` successfully updated.
