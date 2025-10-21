# Typst Document Compilation Guide

## What is Typst?

Typst is a modern markup language for creating PDFs, similar to LaTeX but simpler and faster. The file `submission.typ` is a complete, professionally formatted submission document with placeholders for your screenshots.

---

## Method 1: Online Typst Editor (Easiest)

### Steps:
1. Go to https://typst.app/
2. Create a free account
3. Click "New Document"
4. Delete the example content
5. Copy the entire content of `submission.typ`
6. Paste into the editor
7. The PDF will generate automatically in the preview pane
8. Click "Download PDF" when ready

### Adding Screenshots:
1. In the editor, click the folder icon (Files)
2. Upload your screenshot images
3. Replace the placeholder rectangles with actual images:

```typst
// Replace this:
#figure(
  rect(width: 100%, height: 15cm, stroke: 2pt + gray)[...],
  caption: "..."
)

// With this:
#figure(
  image("screenshot1.png", width: 100%),
  caption: "Complete page view showing semantic HTML structure"
)
```

---

## Method 2: Typst CLI (Local Compilation)

### Install Typst:

**Linux:**
```bash
curl -fsSL https://typst.app/install.sh | sh
```

**macOS:**
```bash
brew install typst
```

**Windows:**
- Download from: https://github.com/typst/typst/releases
- Extract and add to PATH

### Compile PDF:

```bash
cd prac
typst compile submission.typ
```

This creates `submission.pdf` in the same directory.

### Watch Mode (Auto-compile on save):

```bash
typst watch submission.typ
```

---

## Method 3: VS Code Extension

### Steps:
1. Install VS Code
2. Install "Typst LSP" extension
3. Install "Typst Preview" extension
4. Open `submission.typ` in VS Code
5. Press Ctrl+K V (or Cmd+K V on Mac) for live preview
6. Save to compile PDF

---

## Adding Your Screenshots

### Screenshot Files Needed:

1. **screenshot1-fullpage.png** - Full page view
2. **screenshot2-network.png** - DevTools Network tab
3. **screenshot3-accessibility.png** - Accessibility tree
4. **screenshot4-skiplink.png** - Skip link focused
5. **screenshot5-validation.png** - HTML validation
6. **screenshot6-mobile.png** - Mobile responsive view

### Replace Placeholders:

In `submission.typ`, find sections like:

```typst
#figure(
  rect(width: 100%, height: 15cm, stroke: 2pt + gray)[
    #align(center + horizon)[
      #text(size: 14pt, fill: gray)[
        *[PLACEHOLDER - Full Page Screenshot]*
      ]
    ]
  ],
  caption: "..."
)
```

Replace with:

```typst
#figure(
  image("screenshot1-fullpage.png", width: 100%),
  caption: "Complete page view showing semantic HTML structure and responsive layout"
)
```

---

## Customization

### Update Student Information:

Find this section near the top:

```typst
*Student Name:* [Your Full Name Here]\
*Student ID:* [Your Student ID Here]\
*Course:* APT1040-VA\
*Date:* #datetime.today().display()
```

Replace with your actual information:

```typst
*Student Name:* John Doe\
*Student ID:* 12345678\
*Course:* APT1040-VA\
*Date:* #datetime.today().display()
```

### Adjust Page Margins:

```typst
#set page(
  paper: "a4",
  margin: (x: 2cm, y: 2.5cm),  // Change these values
  numbering: "1",
)
```

### Change Font:

```typst
#set text(
  font: "Liberation Sans",  // Change to "Arial", "Times New Roman", etc.
  size: 11pt,
)
```

---

## What's Included in the Document

### Table of Contents:
- Automatically generated
- All sections numbered
- Page numbers included

### Sections:
1. Executive Summary
2. Design Note (150 words)
3. Screenshots (6 placeholders)
4. Code Samples (HTML, CSS)
5. Marking Criteria Compliance (all B1-B5)
6. Validation Results
7. Test Plan Execution
8. File Structure
9. Improvements Made
10. Accessibility Features
11. Technical Excellence
12. Learning Outcomes
13. Conclusion
14. Appendices
15. Declaration of Authenticity

### Features:
- Professional layout
- Syntax highlighting for code
- Tables for data presentation
- Numbered headings
- Page numbers
- Proper spacing and typography
- Cover page
- Table of contents

---

## Tips for Best Results

### 1. Screenshot Quality:
- Take screenshots at 100% zoom
- Use PNG format for clarity
- Crop to relevant content
- Ensure text is readable

### 2. Image Placement:
- Keep images within page margins
- Use appropriate captions
- Maintain aspect ratio

### 3. File Size:
- Compress images if PDF is too large
- Target: < 10 MB total
- Use JPEG for photos, PNG for screenshots

### 4. Review Before Submission:
- Check all placeholders replaced
- Verify student information correct
- Ensure all screenshots visible
- Check page numbers sequential
- Verify table of contents accurate

---

## Troubleshooting

### Error: "Font not found"
**Solution:** Change to a common font like "Arial" or "Times New Roman"

### Error: "Image not found"
**Solution:** Make sure screenshot files are in the same directory as submission.typ

### PDF too large
**Solution:** Compress images using online tools (TinyPNG, etc.)

### Text overflows page
**Solution:** Adjust margins or font size in page settings

---

## Alternative: Use Documentation.html

If you prefer not to use Typst, you can still use the alternative method:

1. Open `documentation.html` in browser
2. Press Ctrl+P (Print)
3. Select "Save as PDF"
4. Enable "Background graphics"
5. Save PDF

Then use a PDF editor to add screenshots.

---

## Quick Start Checklist

- [ ] Install Typst (or use online editor)
- [ ] Open submission.typ
- [ ] Update student name and ID
- [ ] Take 6 required screenshots
- [ ] Replace placeholder rectangles with images
- [ ] Compile to PDF
- [ ] Review generated PDF
- [ ] Check file size (< 10 MB)
- [ ] Verify all content present
- [ ] Submit!

---

## Support

**Typst Documentation:** https://typst.app/docs/
**Typst Community:** https://discord.gg/2uDybryKPe
**Typst Examples:** https://typst.app/docs/tutorial/

---

## Summary

The `submission.typ` file provides a complete, professional PDF submission document with:
- All required sections from marking criteria
- Proper formatting and layout
- Placeholders for screenshots
- Code samples with syntax highlighting
- Professional appearance

Simply add your screenshots and student information, compile, and submit!

**Estimated time:** 30 minutes (including screenshot capture)

---

**Good luck with your submission!** 🎉
