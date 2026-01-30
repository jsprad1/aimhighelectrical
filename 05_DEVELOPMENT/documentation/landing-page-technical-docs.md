# Landing Page Technical Documentation
**Aim High Electrical Services**

---

## Overview

This landing page is a single-file HTML document designed for portability, performance, and ease of deployment. All CSS styles are embedded inline, and JavaScript is minimal for maximum compatibility.

### Key Stats
- **File Size:** ~45KB (uncompressed)
- **Dependencies:** Google Fonts only (Inter, Plus Jakarta Sans)
- **Target Load Time:** < 3 seconds
- **Framework:** None (vanilla HTML/CSS/JS)

---

## Page Structure

### Sections (in order)

1. **Header / Navigation** (`#header`)
   - Fixed position, becomes sticky on scroll
   - Desktop navigation with phone CTA
   - Mobile hamburger menu
   - Links: Services, About, Process, FAQ, Contact

2. **Hero** (`.hero`)
   - Two-column grid layout (content + visual card)
   - Trust badges (veteran-owned, 4.9 stars, licensed)
   - CTAs: Call button, View Services button
   - Floating badges (decorative)

3. **Pain Points** (`.pain-points`)
   - Dark slate background
   - 3-column grid of customer pain points
   - Icons with color-coded backgrounds (red, amber, blue)

4. **Services** (`#services`)
   - 3-column grid of service cards
   - 9 total services with icons
   - Hover effects with top border animation
   - Bottom CTA button

5. **Social Proof** (`#reviews`)
   - 3-column testimonial grid
   - Customer quotes with 5-star ratings
   - Trust badges row (veteran, stars, HomeAdvisor, licensed, years)

6. **About** (`#about`)
   - Two-column layout (image + text)
   - Veteran flag visual
   - Years in business badge
   - Credentials checklist

7. **Process** (`#process`)
   - 4-step horizontal process timeline
   - Numbered circles with connecting line
   - Steps: Call, Assessment, Installation, Walkthrough

8. **FAQ** (`#faq`)
   - Accordion-style FAQ list
   - JavaScript toggle for open/close
   - 6 common questions answered

9. **Contact Form** (`#contact`)
   - Full-featured contact form
   - Fields: Name (req), Phone (req), Email (req), Service dropdown, Message
   - Formspree integration (requires configuration)
   - Accessible with focus states

10. **Final CTA** (`.final-cta`)
    - Gradient blue background
    - Call and email buttons
    - Pattern overlay for visual interest

11. **Footer** (`.footer`)
    - 4-column grid: Brand, Services, Company, Contact
    - Social media links (placeholder)
    - Copyright and legal links

12. **Back to Top Button** (`#backToTop`)
    - Fixed position, bottom-right corner
    - Appears after scrolling 300px
    - Smooth scroll to top on click

---

## CSS Architecture

### Design Tokens (CSS Custom Properties)

```css
:root {
  /* Brand Colors */
  --blue: #046bd2;
  --blue-hover: #045cb4;
  --blue-light: #e8f2fc;
  --blue-glow: rgba(4, 107, 210, 0.15);

  /* Neutral Colors */
  --slate: #1e293b;
  --slate-light: #334155;
  --gray-50: #f8fafc;
  --gray-100: #f1f5f9;
  --gray-200: #e2e8f0;
  --gray-300: #cbd5e1;
  --gray-400: #94a3b8;
  --gray-500: #64748b;
  --white: #ffffff;

  /* Accent Colors */
  --amber: #f59e0b;
  --green: #10b981;
  --red: #ef4444;

  /* Border Radius */
  --radius: 12px;
  --radius-lg: 20px;

  /* Shadows */
  --shadow-sm: 0 1px 3px rgba(0,0,0,0.06), 0 1px 2px rgba(0,0,0,0.04);
  --shadow: 0 4px 6px -1px rgba(0,0,0,0.08), 0 2px 4px -2px rgba(0,0,0,0.05);
  --shadow-lg: 0 10px 25px -3px rgba(0,0,0,0.08), 0 4px 10px -4px rgba(0,0,0,0.04);
  --shadow-xl: 0 20px 40px -4px rgba(0,0,0,0.1);
}
```

### Typography

- **Headings:** Plus Jakarta Sans (700, 800 weight)
- **Body:** Inter (400, 500, 600, 700 weight)
- **Line Height:** 1.6 (body), 1.15 (headings)
- **Letter Spacing:** -0.02em (headings)

### Breakpoints

```css
/* Desktop-first approach */
@media (max-width: 1024px) { /* Tablet */ }
@media (max-width: 768px)  { /* Mobile */ }
```

### Key Responsive Behaviors

| Element | Desktop | Tablet | Mobile |
|---------|---------|--------|--------|
| Hero Grid | 2 columns | 1 column | 1 column |
| Services Grid | 3 columns | 2 columns | 1 column |
| Testimonials | 3 columns | 2 columns | 1 column |
| Process Grid | 4 columns | 2 columns | 1 column |
| Footer Grid | 4 columns | 2 columns | 1 column |
| Nav Links | Visible | Hidden | Hidden |
| Mobile Menu | Hidden | Toggle | Toggle |

---

## JavaScript Functionality

### 1. Header Scroll Effect
```javascript
window.addEventListener('scroll', function() {
  document.getElementById('header').classList.toggle('scrolled', window.scrollY > 20);
});
```
Adds `.scrolled` class to header after scrolling 20px, adding shadow.

### 2. Back to Top Button
```javascript
// Show/hide based on scroll position
if (window.scrollY > 300) {
  backToTop.classList.add('visible');
}

// Smooth scroll to top
function scrollToTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' });
}
```

### 3. Mobile Menu Toggle
```javascript
function toggleMenu() {
  document.getElementById('mobileMenu').classList.toggle('open');
}
```

### 4. FAQ Accordion
```javascript
function toggleFaq(btn) {
  // Close all FAQs
  // Open clicked FAQ if it was closed
  // Animate max-height for smooth transition
}
```

---

## Form Setup Instructions

### Using Formspree (Recommended - Free Tier Available)

1. **Sign up:** Go to [formspree.io](https://formspree.io)
2. **Create a form:** Create a new form in your dashboard
3. **Get your form ID:** Copy the form endpoint (e.g., `xyzabc123`)
4. **Update the HTML:** Find this line in `index.html`:
   ```html
   <form class="contact-form" action="https://formspree.io/f/placeholder" method="POST">
   ```
   Replace `placeholder` with your actual Formspree form ID:
   ```html
   <form class="contact-form" action="https://formspree.io/f/xyzabc123" method="POST">
   ```
5. **Test it:** Submit a test form submission
6. **Configure notifications:** In Formspree dashboard, set email to `glen@aimhighelectrical.net`

### Alternative: Mailto Fallback (Not Recommended)

If you cannot use Formspree, you can use a mailto fallback:
```html
<form action="mailto:glen@aimhighelectrical.net" method="post" enctype="text/plain">
```
**Note:** This opens the user's email client, which is not ideal UX.

### Form Fields

| Field | Type | Required | Name Attribute |
|-------|------|----------|----------------|
| Name | text | Yes | `name` |
| Phone | tel | Yes | `phone` |
| Email | email | Yes | `email` |
| Service Interest | select | No | `service` |
| Message | textarea | No | `message` |

---

## Schema.org Structured Data

### What's Included

The page includes JSON-LD structured data in the `<head>` section:

- **@type:** Electrician (LocalBusiness subtype)
- **Contact Info:** Phone, email, address
- **Area Served:** Aurora, CO and 40km radius
- **Price Range:** $$
- **Aggregate Rating:** 4.9/5 (25 reviews)
- **Opening Hours:** Mon-Fri 7am-6pm, Sat 9am-3pm
- **Services:** All 9 services listed as OfferCatalog

### Benefits
- Better visibility in Google search results
- Rich snippets (stars, hours, contact)
- Local Pack eligibility
- Voice search optimization

### To Update
If business hours, ratings, or services change, update the JSON-LD block in the `<head>`.

---

## SEO Meta Tags

### Current Configuration

```html
<title>Aim High Electrical Services | Licensed Electrician Aurora CO</title>
<meta name="description" content="Veteran-owned electrician in Aurora, CO. Expert panel upgrades, EV charging, generators & more. 4.9-star rated. Licensed & insured. Call 720-326-8492.">
<link rel="canonical" href="https://aimhighelectricalservices.com">
<meta name="robots" content="index, follow">
```

### Open Graph Tags (Social Sharing)

```html
<meta property="og:title" content="Aim High Electrical Services | Licensed Electrician Aurora CO">
<meta property="og:description" content="Veteran-owned electrician in Aurora, CO...">
<meta property="og:type" content="website">
<meta property="og:url" content="https://aimhighelectricalservices.com">
<meta property="og:image" content="https://aimhighelectricalservices.com/og-image.jpg">
```

### To Add (Client Action Required)
1. **og:image** - Create a 1200x630px social sharing image and upload to server
2. **Favicon** - Add `<link rel="icon" href="/favicon.ico">`
3. **Apple Touch Icon** - Add `<link rel="apple-touch-icon" href="/apple-touch-icon.png">`

---

## Performance Optimization

### Current Optimizations
- Inline CSS (no external stylesheet request)
- Minimal JavaScript (< 1KB)
- SVG icons (no image sprites)
- System font fallbacks
- Smooth scroll behavior in CSS

### Recommendations
1. **Image Optimization**
   - When adding real photos, use WebP format
   - Compress images with TinyPNG or Squoosh
   - Use `loading="lazy"` attribute

2. **Google Fonts**
   - Currently loads 2 font families (Inter, Plus Jakarta Sans)
   - Consider self-hosting fonts for even faster load times
   - Or use system fonts only: `font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;`

3. **Minification**
   - Before deploying, minify HTML with [HTMLMinifier](https://kangax.github.io/html-minifier/)
   - Estimated size reduction: 15-20%

---

## Accessibility Features

### WCAG 2.1 AA Compliance

| Feature | Implementation |
|---------|----------------|
| **Color Contrast** | All text meets 4.5:1 minimum contrast ratio |
| **Keyboard Navigation** | All interactive elements are keyboard accessible |
| **Focus States** | Blue outline and shadow on all form inputs and buttons |
| **ARIA Labels** | Used on icon-only buttons (mobile toggle, back-to-top) |
| **Form Labels** | All inputs have associated `<label>` elements with `for` attribute |
| **Semantic HTML** | Proper use of `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>` |
| **Heading Hierarchy** | Logical h1 > h2 > h3 structure |
| **Link Text** | Descriptive link text (no "click here") |

### Testing Recommendations
- Run [WAVE accessibility checker](https://wave.webaim.org/)
- Test keyboard navigation (Tab, Shift+Tab, Enter, Space)
- Test with screen reader (NVDA for Windows, VoiceOver for Mac)

---

## Deployment Information

### Current Deployment
- **Platform:** Vercel
- **Auto-Deploy:** Yes (GitHub integration)
- **URL:** https://aimhighelectrical.vercel.app
- **Custom Domain:** https://aimhighelectricalservices.com
- **SSL:** Enabled (automatic via Vercel)

### Deployment Configuration
File: `vercel.json` in project root
```json
{
  "outputDirectory": "landing-page"
}
```

### How Auto-Deploy Works
1. Push changes to GitHub repository (`aimhighelectrical`)
2. Vercel detects the push via webhook
3. Vercel builds and deploys automatically
4. Changes go live in ~30 seconds

### Manual Deploy Process
If you need to deploy manually:
1. Ensure you're in the project root directory
2. Run: `vercel --prod` (requires Vercel CLI installed)
3. Or push to GitHub and let auto-deploy handle it

---

## What Needs Client Input

### High Priority
1. **Formspree Configuration**
   - Sign up for Formspree
   - Replace `placeholder` in form action with real form ID
   - Configure email notifications to `glen@aimhighelectrical.net`

2. **Real Photos**
   - Hero section image (electrician at work, van, Glen portrait)
   - About section veteran photo
   - Service photos (optional but recommended)

3. **Real Testimonials**
   - Replace placeholder testimonials with actual customer reviews
   - Get permission from customers to use their names
   - Link to actual review platforms if available

4. **Social Media Links**
   - Update footer social media links (Facebook, Instagram, LinkedIn)
   - Or remove social icons if not using social media

### Medium Priority
5. **Open Graph Image**
   - Create 1200x630px image for social sharing
   - Upload to server and update `og:image` meta tag

6. **Favicon & App Icons**
   - Design favicon (16x16, 32x32, 48x48)
   - Design apple-touch-icon (180x180)
   - Add to `<head>` section

7. **Google Analytics / Tracking**
   - Add Google Analytics 4 tracking code if desired
   - Add Google Tag Manager container if using

8. **Business Hours Confirmation**
   - Verify hours in Schema.org markup (currently Mon-Fri 7am-6pm, Sat 9am-3pm)

### Low Priority
9. **Privacy Policy & Terms**
   - Create actual Privacy Policy page
   - Create Terms of Service page
   - Update footer links

10. **Physical Address**
    - Currently only showing "Aurora, CO 80016"
    - If comfortable, add full street address to footer and Schema.org

---

## Browser Compatibility

### Tested & Supported
- Chrome 90+ (Windows, Mac, Android)
- Firefox 88+ (Windows, Mac)
- Safari 14+ (Mac, iOS)
- Edge 90+ (Windows)

### Known Issues
- **IE11:** Not supported (smooth scroll, CSS Grid not polyfilled)
- **Safari < 13:** May have issues with CSS custom properties

### Fallbacks Included
- System fonts if Google Fonts fail to load
- Basic styles if CSS fails to load
- Form still submits if JavaScript is disabled

---

## Maintenance & Updates

### Common Updates

**1. Change Phone Number**
- Search for `7203268492` or `(720) 326-8492`
- Replace in: header, hero, services CTA, final CTA, footer, Schema.org

**2. Update Services**
- Edit service cards in Services section
- Update Schema.org `hasOfferCatalog` array
- Update form dropdown options

**3. Change Brand Colors**
- Update CSS custom properties in `:root`
- Colors will cascade throughout entire page

**4. Add New Section**
- Copy existing section structure
- Follow naming convention (`.section`, `.section-sm`)
- Update navigation links if needed

---

## File Structure

```
aimhighelectrical/
├── landing-page/
│   └── index.html (THE LANDING PAGE - single file)
├── 05_DEVELOPMENT/
│   └── documentation/
│       └── landing-page-technical-docs.md (THIS FILE)
├── vercel.json (Vercel deployment config)
└── README.md
```

---

## Support & Troubleshooting

### Common Issues

**Form not submitting:**
- Check Formspree form ID is correct (not 'placeholder')
- Verify form method is `POST`
- Check browser console for errors

**Styles look broken:**
- Clear browser cache (Ctrl+Shift+R / Cmd+Shift+R)
- Check if Google Fonts are loading (network tab)

**Back to top button not appearing:**
- Scroll down more than 300px
- Check JavaScript console for errors

**Mobile menu not opening:**
- Check JavaScript is enabled
- Verify `toggleMenu()` function is present

### Getting Help
- Review this documentation
- Check browser console for errors
- Test in different browser
- Contact developer: Check project README for contact info

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-30 | Initial landing page launch |
| 1.1 | 2026-01-30 | Added contact form, Schema.org, back-to-top button, SEO improvements |

---

## Credits

- **Design & Development:** Claude Code (AI Assistant)
- **Client:** Aim High Electrical Services LLC
- **Fonts:** Google Fonts (Inter, Plus Jakarta Sans)
- **Icons:** Inline SVG (Feather Icons style)
- **Hosting:** Vercel

---

**Document Last Updated:** 2026-01-30
**Document Version:** 1.0
**Developer:** @developer agent for Aim High Electrical Services
