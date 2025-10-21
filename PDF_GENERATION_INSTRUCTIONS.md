# PDF Generation Instructions for Campus Events Micro-Site

## Overview
This document provides step-by-step instructions for generating the required PDF submission with screenshots, code samples, and validation results.

---

## Method 1: Using Browser Print to PDF (Recommended)

### Step 1: Open the Documentation Page
1. Navigate to the `prac` directory
2. Open `documentation.html` in your web browser (Chrome, Firefox, or Edge recommended)
3. The page contains all required documentation formatted for PDF export

### Step 2: Generate PDF with Screenshots
1. **Take Screenshots First** (see Section 2 below)
2. Press `Ctrl+P` (Windows/Linux) or `Cmd+P` (Mac) to open Print dialog
3. Select "Save as PDF" as the destination
4. Configure settings:
   - Paper size: A4 or Letter
   - Margins: Default
   - Scale: 100% (or "Fit to page width")
   - Background graphics: **Enabled** (important for colors)
   - Headers and footers: Optional
5. Click "Save" and name the file: `Campus_Events_Microsite_[YourName].pdf`

---

## Method 2: Complete PDF with All Components

### Required PDF Contents:

1. **Cover Page** with:
   - Project title: "Campus Events Micro-Site"
   - Course: APT1040-VA Week 07 Practical
   - Your name and student ID
   - Date of submission

2. **Design Note** (150 words) - from README.md

3. **Screenshots** (minimum 6):
   - Full page view of index.html
   - DevTools Network tab showing successful resource loading
   - DevTools Accessibility tree showing image alt text
   - Skip link demonstration (focused state)
   - HTML validation results
   - Mobile responsive view

4. **Code Samples**:
   - HTML: Semantic structure example
   - CSS: Design tokens and utility classes
   - Evidence of proper alt text implementation

5. **Validation Results**:
   - HTML5 validation output
   - CSS3 validation confirmation
   - Accessibility audit results

6. **Test Plan Results** - from README.md

7. **File Structure** and project organization

8. **Marking Criteria Checklist** with evidence for each requirement

---

## Section 2: Taking Required Screenshots

### Screenshot 1: Full Page View
**Purpose:** Show complete site layout

**Steps:**
1. Open `index.html` in browser
2. Press F12 to open DevTools
3. Press Ctrl+Shift+P (Chrome) or Cmd+Shift+P (Mac)
4. Type "screenshot" and select "Capture full size screenshot"
5. Save as `01_fullpage.png`

**Alternative:**
- Use browser extension like "Full Page Screen Capture"
- Or scroll and take multiple screenshots

---

### Screenshot 2: DevTools Network Tab
**Purpose:** Prove all resources load successfully (no 404 errors)

**Steps:**
1. Open `index.html` in browser
2. Press F12 → Click "Network" tab
3. Press Ctrl+Shift+R to hard reload
4. Wait for all resources to load
5. Take screenshot showing:
   - All files (index.html, styles.css, all images)
   - Status column showing "200" for all
   - No red errors
6. Save as `02_network_tab.png`

---

### Screenshot 3: Accessibility Tree
**Purpose:** Show proper alt text implementation

**Steps (Chrome):**
1. Open `index.html` in browser
2. Press F12 → Click "Elements" tab
3. Click "Accessibility" tab at bottom
4. Expand the tree to show image nodes
5. Click on an image to show its accessibility properties
6. Ensure alt text is visible in properties panel
7. Take screenshot
8. Save as `03_accessibility_tree.png`

**Steps (Firefox):**
1. F12 → "Accessibility" tab
2. Enable accessibility features if prompted
3. Find images in tree
4. Expand to show alt text
5. Screenshot and save

---

### Screenshot 4: Skip Link Demonstration
**Purpose:** Prove skip link functionality

**Steps:**
1. Open `index.html` in browser
2. Reload page (Ctrl+R)
3. Press **Tab** key once
4. The "Skip to main content" link should appear at top
5. Take screenshot showing:
   - Yellow skip link visible
   - Browser focus indicator
6. Save as `04_skip_link.png`

---

### Screenshot 5: HTML Validation
**Purpose:** Prove valid HTML5 code

**Method A - Using HTML Tidy:**
```bash
cd prac
tidy -q index.html > validation_output.txt 2>&1
```
Take screenshot of terminal output showing no errors.

**Method B - W3C Validator:**
1. Go to https://validator.w3.org/#validate_by_upload
2. Click "Choose File" and select `index.html`
3. Click "Check"
4. Take screenshot of results showing "Document checking completed. No errors or warnings to show."
5. Save as `05_html_validation.png`

---

### Screenshot 6: Mobile Responsive View
**Purpose:** Show responsive design works on mobile devices

**Steps:**
1. Open `index.html` in browser
2. Press F12 → Click "Toggle device toolbar" icon (or Ctrl+Shift+M)
3. Select a mobile device from dropdown (e.g., "iPhone 12 Pro")
4. Scroll to show full page layout
5. Take screenshot showing:
   - Header with logo
   - Navigation (stacked vertically)
   - At least one event card
6. Save as `06_mobile_view.png`

---

### Screenshot 7: CSS Variables in DevTools
**Purpose:** Show design tokens being used

**Steps:**
1. Open `index.html` in browser
2. F12 → Elements tab
3. Click on any colored element (like h1)
4. In Styles panel on right, find computed color
5. Expand to show it uses `var(--color-primary)`
6. Screenshot showing CSS variable usage
7. Save as `07_css_variables.png`

---

### Screenshot 8: Lighthouse Accessibility Score
**Purpose:** Prove WCAG compliance

**Steps:**
1. Open `index.html` in Chrome browser
2. F12 → "Lighthouse" tab
3. Select "Accessibility" category only
4. Click "Analyze page load"
5. Wait for audit to complete
6. Take screenshot showing score (should be 95+)
7. Save as `08_lighthouse_score.png`

---

## Section 3: Assembling the PDF

### Option A: Using Word Processor (Microsoft Word, Google Docs, LibreOffice)

1. **Create Document Structure:**
   - Title page
   - Table of contents
   - Each section as a heading

2. **Insert Screenshots:**
   - Insert → Picture → From File
   - Add captions below each screenshot
   - Format: "Figure 1: Full Page View"

3. **Add Code Blocks:**
   - Copy from HTML/CSS files
   - Format as "Code" style (monospace font)
   - Use gray background for readability

4. **Insert Tables:**
   - Create marking criteria table
   - File structure table
   - Test results table

5. **Export as PDF:**
   - File → Save As → PDF
   - Ensure all images are embedded

---

### Option B: Using Markdown → PDF Converter

1. **Edit README.md** to include screenshot references:
```markdown
## Screenshots

### Full Page View
![Full page](screenshots/01_fullpage.png)
```

2. **Use Pandoc** (if installed):
```bash
pandoc README.md -o submission.pdf --pdf-engine=xelatex
```

3. **Use Online Converter:**
- https://www.markdowntopdf.com/
- Upload README.md
- Add images directory
- Download PDF

---

### Option C: Print Multiple Documents to Single PDF

1. Open `documentation.html` in browser
2. Print to PDF (first document)
3. Open each screenshot image
4. Print each to PDF
5. Use PDF merger tool:
   - Online: https://www.ilovepdf.com/merge_pdf
   - Offline: Adobe Acrobat, PDFtk, etc.
6. Merge all PDFs in order

---

## Section 4: PDF Content Checklist

Before submission, verify your PDF includes:

### ✅ Cover Page
- [ ] Project title
- [ ] Your name and student ID
- [ ] Course code (APT1040-VA)
- [ ] Submission date

### ✅ Design Note (150-180 words)
- [ ] Semantic structure justification
- [ ] Color system rationale
- [ ] Image format choices explained
- [ ] Typography decisions with line-height rationale

### ✅ Screenshots (minimum 6)
- [ ] 1. Full page view
- [ ] 2. DevTools Network tab (all resources 200 OK)
- [ ] 3. Accessibility tree (alt text visible)
- [ ] 4. Skip link focused and visible
- [ ] 5. HTML validation results (no errors)
- [ ] 6. Mobile responsive view
- [ ] 7. (Optional) CSS variables in DevTools
- [ ] 8. (Optional) Lighthouse accessibility score

### ✅ Code Samples
- [ ] HTML: Article element with semantic markup
- [ ] HTML: Skip link implementation
- [ ] HTML: Image with alt text and dimensions
- [ ] CSS: Design tokens (custom properties)
- [ ] CSS: Typography scale with line-heights
- [ ] CSS: Utility classes

### ✅ Validation Results
- [ ] HTML5 validation output (tidy or W3C)
- [ ] CSS3 validation confirmation
- [ ] No inline styles (except if demonstrating in theory)

### ✅ File Structure
- [ ] Directory tree showing all files
- [ ] index.html confirmed
- [ ] styles.css confirmed
- [ ] assets/ directory with 3 images
- [ ] README.md confirmed

### ✅ Marking Criteria Evidence
- [ ] B1: Semantic structure (8 marks)
  - [ ] Header, nav, main, footer present
  - [ ] 3 article elements with metadata
  - [ ] Skip link working
- [ ] B2: Typography & color (8 marks)
  - [ ] CSS variables screenshot
  - [ ] Type scale documented with comments
  - [ ] Utility classes shown
- [ ] B3: Images (10 marks)
  - [ ] SVG logo in code
  - [ ] 3 bitmap images in assets/
  - [ ] Alt text screenshot from accessibility tree
  - [ ] width/height attributes shown
  - [ ] loading="lazy" shown
- [ ] B4: Links & navigation (2 marks)
  - [ ] 3+ navigation links
  - [ ] External link shown
  - [ ] Anchor links working
- [ ] B5: Design note & test plan (2 marks)
  - [ ] 150-word note included
  - [ ] DevTools test plan included

### ✅ Test Plan Results
- [ ] Missing file handling test
- [ ] Broken link detection test
- [ ] Alt text accessibility test
- [ ] Layout stability test (CLS)
- [ ] Lazy loading verification
- [ ] Skip link functionality test

### ✅ Additional Information
- [ ] Browser compatibility notes
- [ ] Accessibility audit results
- [ ] Performance metrics (optional)
- [ ] Future enhancements (optional)

---

## Section 5: Quick PDF Generation (Fast Method)

If you need to generate PDF quickly:

1. **Open `documentation.html` in browser**
2. **Print to PDF** (Ctrl+P → Save as PDF)
3. **Take 6 screenshots** as described above
4. **Edit the PDF** to add screenshots:
   - Use online PDF editor: https://www.sejda.com/pdf-editor
   - Or Adobe Acrobat
   - Insert screenshot images into appropriate sections

---

## Section 6: Command-Line PDF Generation (Advanced)

If you have command-line tools installed:

```bash
# Using wkhtmltopdf
wkhtmltopdf documentation.html Campus_Events_Documentation.pdf

# Using Chromium headless
chromium --headless --print-to-pdf=submission.pdf documentation.html

# Using Chrome headless
google-chrome --headless --print-to-pdf=submission.pdf documentation.html
```

---

## Section 7: Final Submission Checklist

Before uploading:

1. **File Size:** Check PDF is under 10MB (compress if needed)
2. **Readability:** Open PDF and verify:
   - All text is readable
   - All images are clear
   - Code blocks are properly formatted
   - Colors are visible (if background graphics enabled)
3. **Completeness:** All sections from marking criteria included
4. **File Name:** Use descriptive name (e.g., `YourName_APT1040_Week07_Campus_Events.pdf`)
5. **Page Numbers:** Add page numbers if creating multi-page PDF

---

## Section 8: Alternative: Include Source Code in PDF

If instructor wants actual code files in PDF:

### Include index.html:
```html
<!-- Full contents of index.html -->
<!-- Copy entire file here -->
```

### Include styles.css:
```css
/* Full contents of styles.css */
/* Copy entire file here */
```

Or attach as appendices at end of PDF.

---

## Section 9: Troubleshooting

### Problem: Screenshots not clear
**Solution:** Take screenshots at 100% zoom, use PNG format, ensure high DPI

### Problem: PDF too large
**Solution:** 
- Compress images before inserting (use TinyPNG.com)
- Use JPEG instead of PNG for screenshots
- Use PDF compression tool

### Problem: Code formatting lost in PDF
**Solution:**
- Use monospace font (Courier New, Consolas)
- Add light gray background
- Preserve indentation with spaces not tabs

### Problem: Colors not showing in PDF
**Solution:** Enable "Background graphics" in print dialog

---

## Section 10: Example PDF Structure

```
PAGE 1: Cover Page
  - Title
  - Name, Course, Date

PAGE 2: Table of Contents

PAGE 3-4: Design Note & Project Overview

PAGE 5-7: Screenshots with Captions
  - Figure 1: Full Page View
  - Figure 2: Network Tab
  - Figure 3: Accessibility Tree
  - Figure 4: Skip Link
  - Figure 5: HTML Validation
  - Figure 6: Mobile View

PAGE 8-10: Code Samples
  - HTML semantic structure
  - CSS design tokens
  - CSS utility classes

PAGE 11-12: Validation Results
  - HTML5 validation
  - CSS3 validation
  - Accessibility audit

PAGE 13-14: Marking Criteria Compliance
  - B1: Semantic structure (with evidence)
  - B2: Typography & color (with evidence)
  - B3: Images (with evidence)
  - B4: Links (with evidence)
  - B5: Design note & tests (with evidence)

PAGE 15-16: Test Plan Results
  - Each test with procedure and results

PAGE 17: File Structure & Submission Info

PAGE 18: Conclusion
```

---

## Links and Resources

- **W3C HTML Validator:** https://validator.w3.org/
- **W3C CSS Validator:** https://jigsaw.w3.org/css-validator/
- **Image Compression:** https://tinypng.com/
- **PDF Merger:** https://www.ilovepdf.com/merge_pdf
- **Markdown to PDF:** https://www.markdowntopdf.com/
- **Screenshot Tools:** 
  - Windows: Snipping Tool, Win+Shift+S
  - Mac: Cmd+Shift+4
  - Linux: Screenshot/Flameshot

---

## Final Note

The `documentation.html` file in this project is specifically designed to be printed as a comprehensive PDF. It includes all required sections, formatted for print, with placeholders for screenshots.

**Recommended approach:** 
1. Print `documentation.html` to PDF
2. Take the 6-8 screenshots
3. Use a PDF editor to insert screenshots into the appropriate placeholder sections
4. Add your name to the cover page
5. Submit!

Good luck with your submission! 🎓