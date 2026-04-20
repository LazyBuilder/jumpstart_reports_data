# Jumpstart-Reports Technical Documentation

## Overview

This is a publication website where AI-generated business reports are hosted for public consumption. The site is hosted on **Cloudflare Pages** and uses a **GitHub Pages** repo for report data storage.

---

## Architecture

```
Jumpstart-Reports (Core Website)
├── Cloudflare Pages (production hosting)
├── index.html (main landing page)
├── template-page.html (page template)
├── content/
│   ├── asthetics.css (custom styling)
│   ├── asthetics.js (carousel, animations)
│   ├── business_reports.js (report rendering logic)
│   └── report-list.json (data source)
└── reports/ (individual report HTML files)

Jumpstart-Reports-Data (Data Repo - NEW)
├── GitHub Pages (hosted separately)
├── report-list.json (central data source)
├── reports/
│   ├── business-workbooks/
│   ├── fifty-questions/
│   └── special-reports/
└── assets/ (optional thumbnails)
```

---

## Report Categories

1. **Business Discovery Workbooks** - Market research reports for specific business concepts
2. **50 First Questions** - Guides with probing questions to validate business ideas
3. **Special Reports** - Additional specialized reports

---

## Tech Stack

### Core Website
- **Framework**: Vanilla HTML/CSS/JavaScript (no build system)
- **Styling**: Bootstrap 5.3.3
- **Hosting**: Cloudflare Pages
- **External Services**:
  - Typeform (custom report requests)
  - Google Gemini AI (report generation)
  - Airtable (data storage)
  - Google Analytics (G-V318Q5MBSW)

### Data Repo
- **Hosting**: GitHub Pages
- **License**: CC0 1.0 Universal (content) or MIT (code)
- **Data Format**: JSON + HTML/PDF report files

---

## Data Structure (report-list.json)

```json
{
  "business_workbooks": [
    {
      "id": "aller-scan",
      "title": "AllerScan Business Workbook",
      "description": "Market research for allergy testing businesses",
      "url": "https://yourusername.github.io/Jumpstart-Reports-Data/reports/business-workbooks/aller-scan.html",
      "published": "2026-04-15",
      "tags": ["market-research", "healthcare"],
      "thumbnail": "https://yourusername.github.io/Jumpstart-Reports-Data/assets/thumbnails/aller-scan.png"
    }
  ],
  "fifty_questions": [
    {
      "id": "fitness-trainer",
      "title": "50 First Questions for Fitness Trainers",
      "description": "Questions to validate your fitness coaching business idea",
      "url": "https://yourusername.github.io/Jumpstart-Reports-Data/reports/fifty-questions/fitness-trainer.html",
      "published": "2026-04-10",
      "tags": ["validation", "questions"]
    }
  ],
  "special_reports": []
}
```

---

## Report File Formats

- **Option A**: HTML files (display inline)
- **Option B**: PDF files (download or embed)
- **Option C**: Google Docs exports (export as HTML, upload)

---

## Publishing Workflow

1. Create report (HTML or PDF)
2. Add to `Jumpstart-Reports-Data/reports/` directory
3. Update `report-list.json` with new entry
4. Commit and push to GitHub
5. GitHub Pages auto-deploys
6. Core website fetches updated JSON on next page load

---

## Integration Points

The core website (`index.html`) has three containers:
- `#container_business_workbooks`
- `#container_fifty_questions`
- `#container_default` (other reports)

JavaScript (`content/business_reports.js`) fetches `report-list.json` and creates Bootstrap cards dynamically.

---

## Current Status

- Core website: **Do not modify** (for now)
- Data repo: **Under construction**
- Integration: To be implemented after data repo is ready
