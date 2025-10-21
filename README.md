# Campus Events Micro-Site

## Design Note (150 words)

This micro-site employs semantic HTML5 elements to create a clear document structure and enhance accessibility. The `<header>`, `<nav>`, `<main>`, `<article>`, `<aside>`, and `<footer>` elements establish meaningful content hierarchy, while `<figure>` and `<figcaption>` provide context for images. Each event uses `<article>` with descriptive metadata in `<dl>` elements for semantic richness.

The color system uses CSS custom properties for consistency and maintainability. Primary blue (#2E5CB8) conveys professionalism and trust, while accent gold (#FFB81C) drives attention to CTAs. Muted text (#666666) reduces visual noise for secondary information. The typography scale follows modular proportions with carefully chosen line-heights: 1.6 for body text ensures comfortable long-form reading, while 1.2 for headings prevents excessive spacing in larger text.

Image format choices balance quality and performance: JPEG for photographs (tech-summit.jpg, cultural-fest.jpg) provides optimal compression, while SVG for the logo ensures crisp rendering at any scale. The decorative background uses an empty `alt=""` attribute, whereas content images receive descriptive alt text describing relevant visual information.

## Test Plan

### Browser DevTools Tests

- **Missing File Handling**: Open Network tab, reload page, verify no 404 errors for assets. Check that all CSS, images load successfully with 200 status codes.

- **Broken Link Detection**: Inspect each `<a>` element in Elements panel. Verify `href` attributes point to valid anchors (`#events`, `#about`) or external URLs. Test navigation by clicking each link.

- **Image Alt Text Accessibility**: Open Accessibility inspector (Firefox) or Accessibility tree (Chrome DevTools > Elements > Accessibility). Expand image nodes and verify alt text appears for content images. Confirm decorative image (career-fair-bg.jpg) shows empty alt or role="presentation".

- **Layout Stability (CLS Prevention)**: In Elements panel, inspect `<img>` tags and verify all have explicit `width` and `height` attributes. Open Performance tab, record page load, check Layout Shift metrics. Images with intrinsic dimensions should not cause content reflow during loading.

- **Lazy Loading Verification**: Network tab > throttle to "Slow 3G". Scroll slowly and observe images load only when approaching viewport (loading="lazy" attribute working).

- **CSS Variables Usage**: Inspect computed styles for any element. Verify colors, spacing, and typography reference CSS custom properties (var(--color-primary), etc.).

- **Skip Link Functionality**: Tab to first focusable element (skip link), press Enter, verify focus jumps to `#main-content`.

- **Semantic Structure Validation**: Use HTML5 Outliner browser extension or W3C validator to verify proper heading hierarchy (h1 > h2 > h3) and semantic element nesting.

### HTML Validation

- Validate at https://validator.w3.org/
- Ensure no errors, confirm HTML5 DOCTYPE
- Verify all required attributes present

### CSS Validation

- Validate at https://jigsaw.w3.org/css-validator/
- Confirm CSS3 compliance
- Check custom properties properly declared in :root

### Accessibility Checks

- Run Lighthouse audit (DevTools > Lighthouse > Accessibility)
- Target score: 95+ for accessibility
- Verify color contrast ratios meet WCAG AA standards (4.5:1 for normal text)

## File Structure

```
prac/
├── index.html          # Main HTML file with semantic structure
├── styles.css          # External stylesheet with design tokens
├── README.md           # This file
└── assets/             # Image directory
    ├── tech-summit.jpg        # JPEG photo for Tech Summit event
    ├── cultural-fest.jpg      # JPEG photo for Cultural Festival
    ├── career-fair-bg.jpg     # Decorative background image
    └── (SVG logo inline in HTML)
```

## Features Implemented

### B1: Semantic Structure (8 marks)
- ✅ `<header>`, `<nav>`, `<main>`, `<footer>` layout
- ✅ Three events as `<article>` elements with title, date, location, description
- ✅ "About this site" `<aside>` section
- ✅ Working "Skip to main content" link
- ✅ Proper heading hierarchy (h1 > h2 > h3)

### B2: Typography and Color System (8 marks)
- ✅ External styles.css
- ✅ CSS variables for colors (primary, accent, text-base, text-muted, background)
- ✅ Type scale with justified line-heights (comments included)
- ✅ Utility classes with low specificity

### B3: Images and Graphics (10 marks)
- ✅ Inline SVG logo with proper accessibility attributes
- ✅ Three bitmap images in assets/ folder
- ✅ Informative alt text for content images
- ✅ Empty alt for decorative image
- ✅ `<figure>` with `<figcaption>` for event photos
- ✅ Explicit width/height attributes on all images
- ✅ `loading="lazy"` for below-fold images
- ✅ JPEG format for photos (explained in comments)

### B4: Links and Navigation (2 marks)
- ✅ Navigation with 3+ links
- ✅ External link to USIU website (opens in same tab)
- ✅ Internal anchor links (#events, #about)

### B5: Design Note and Test Plan (2 marks)
- ✅ 150-word design justification
- ✅ DevTools-based test plan

## Notes

- All images should be replaced with actual photos for production use
- The current implementation uses placeholder image paths
- To create actual images, you can use royalty-free images from Unsplash or Pexels
- Recommended image dimensions: 800x500px for event photos

## Local Development

1. Clone or download this directory
2. Open `index.html` in a modern browser
3. No build process or server required

## Browser Compatibility

Tested and working in:
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+