# Aim High Electrical Services
## Brand Style Guide & Design System

---

## Brand Identity

### Brand Names
- **Primary:** Aim High Electrical Services
- **Short Form:** Aim High Electrical

### Tagline
"Your trusted partner for exceptional electrical solutions"

### Brand Personality

| Trait | Description |
|-------|-------------|
| **Dependable** | Military-grade reliability — shows up on time, follows through on every promise, no excuses |
| **Professional** | Expert craftsmanship backed by 4.9-star satisfaction — quality you can see and trust |
| **Approachable** | Friendly neighbor energy — explains things clearly, never condescending, easy to talk to |
| **Disciplined** | Veteran precision in every detail — clean job sites, organized work, done right the first time |
| **Forward-Thinking** | Modern solutions with traditional values — EV charging, smart home, future-ready expertise |

### Brand Voice
- **Tone:** Confident but not arrogant. Professional but approachable. Warm but authoritative. We know our craft and we respect our customers.
- **Style:** Direct and clear. Jargon-free for homeowners. Benefits before features. Active voice. Short sentences for impact. Longer sentences for explanation.
- **Perspective:** Expert advisor and trusted partner. We're the knowledgeable neighbor who happens to be a licensed electrician. We educate, we don't lecture.

### Voice Examples

| Do Say | Don't Say |
|--------|-----------|
| "We'll upgrade your panel so your home can handle today's power demands." | "We perform 200A residential electrical panel retrofit services." |
| "Your family's safety is our mission." | "We prioritize customer safety metrics." |
| "Glen served our country. Now he serves Aurora homeowners." | "Our CEO has extensive military background." |
| "Call us — we'll explain your options clearly." | "Contact us for a comprehensive consultation." |

---

## Color Palette

### Primary Colors

| Color | Hex | RGB | Usage |
|-------|-----|-----|-------|
| Primary Blue | #046bd2 | 4, 107, 210 | Primary brand color, buttons, links, headings |
| Secondary Blue | #045cb4 | 4, 92, 180 | Hover states, accents, active elements |

### Secondary Colors

| Color | Hex | Usage |
|-------|-----|-------|
| Dark Slate | #1e293b | Dark backgrounds, body text, footer |
| Success Green | #10B981 | Confirmation messages, trust badges, checkmarks |
| Warning Amber | #F59E0B | Urgency callouts, safety warnings, highlights |

### Neutral Colors

| Color | Hex | Usage |
|-------|-----|-------|
| White | #FFFFFF | Backgrounds, text on dark surfaces |
| Light Gray | #F8FAFC | Alternate section backgrounds |
| Medium Gray | #64748B | Secondary text, captions, meta info |
| Dark Slate | #1e293b | Primary text color, dark backgrounds |

---

## Typography

### Font Pairings

- **Headlines:** Inter (Bold/Semibold) — Clean, modern, highly readable
- **Body:** Inter (Regular/Medium) — Consistent family, excellent at small sizes
- **Accent/Fallback:** system-ui, -apple-system, sans-serif

### Type Scale
```
H1: 48-60px    - Hero headlines (bold, tight tracking)
H2: 36-48px    - Section headers (semibold)
H3: 24px       - Subsection titles (semibold)
H4: 20px       - Card titles, feature names (medium)
Body: 16-18px  - Paragraph text (regular, 1.6 line height)
Small: 14px    - Captions, meta text, badges (medium)
```

### Type Rules
- Maximum line length: 65-75 characters for body text
- Paragraph spacing: 1.5em between paragraphs
- Heading spacing: 2em above, 0.5em below
- Never use all caps for more than 3 words

---

## Logo Guidelines

### Current Logo Analysis
- Text-based logo with "Aim High Electrical Services" branding
- Primary Blue (#046bd2) on white background
- Clean, professional appearance

### Logo Usage Rules
- Minimum clear space: 1x logo height on all sides
- Minimum size: 120px width for digital
- Always use on solid backgrounds (white or dark)
- Never stretch, rotate, or alter proportions

### Logo Variations Needed
1. **Primary:** Full color on white
2. **Reversed:** White on dark slate (#1e293b)
3. **Favicon:** Stylized "AH" or lightning bolt icon
4. **Social:** Square format with padding

---

## Visual Elements

### Photography Style
- **Preferred:** Real job site photos showing actual work, not stock photos
- **Lighting:** Clean, well-lit work areas — professionalism evident
- **People:** Glen and team in professional attire/uniforms, friendly expressions
- **Work shots:** Detail shots showing craftsmanship (clean wiring, organized panels)
- **Homes:** Aurora, CO homes and neighborhoods — relatable to local audience
- **Before/after:** Transformation shots for panels, lighting, basements
- **Avoid:** Dark/messy job sites, overly staged stock photos, generic imagery

### Iconography
- **Style:** Line-based icons with 2px stroke weight
- **Corners:** Rounded (4px radius)
- **Color:** Primary Blue (#046bd2) on light backgrounds, White on dark backgrounds
- **Size:** 24px standard, 32-48px for feature icons, 16px for inline
- **Consistency:** All icons must use the same style — no mixing filled and outlined
- **Recommended Set:** Lucide Icons or Heroicons (consistent, open-source)

### Icon Assignments for Services
| Service | Icon Suggestion |
|---------|----------------|
| Generators | Zap / Power |
| Panel Upgrades | Shield / Grid |
| Sub Panels | Layout / Layers |
| Inspections | Search / ClipboardCheck |
| Lighting | Sun / Lightbulb |
| EV Charging | Battery / Car |
| Basement Remodeling | Home / Wrench |
| Home Automation | Smartphone / Wifi |
| Troubleshooting | Tool / AlertCircle |

---

## UI Components

### Buttons

#### Primary Button
```css
background: #046bd2;
color: #FFFFFF;
padding: 14px 28px;
border-radius: 8px;
font-weight: 600;
font-size: 16px;
transition: background 0.2s ease;
/* Hover: background: #045cb4 */
```

#### Secondary Button
```css
background: transparent;
border: 2px solid #046bd2;
color: #046bd2;
padding: 14px 28px;
border-radius: 8px;
font-weight: 600;
/* Hover: background: #046bd2; color: #FFFFFF */
```

#### CTA Button (High Priority)
```css
background: #046bd2;
color: #FFFFFF;
padding: 16px 32px;
border-radius: 8px;
font-weight: 700;
font-size: 18px;
box-shadow: 0 4px 14px rgba(4, 107, 210, 0.3);
/* Hover: transform: translateY(-1px); box-shadow grows */
```

### Cards
```css
background: #FFFFFF;
border-radius: 16px;
box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
padding: 32px;
/* Hover: box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1) */
```

### Trust Badges
```css
display: inline-flex;
align-items: center;
gap: 8px;
background: #F8FAFC;
border: 1px solid #e2e8f0;
border-radius: 24px;
padding: 8px 16px;
font-size: 14px;
font-weight: 600;
color: #1e293b;
```

---

## Content Guidelines

### Headlines
- Lead with benefits, not features
- Use action verbs (Protect, Upgrade, Power, Transform)
- Keep under 10 words
- Include location when relevant (Aurora)
- Address the reader directly ("Your home," "Your family")

### Body Copy
- Short paragraphs (2-3 sentences max)
- Bullet points for features and lists
- Simple language — write at 8th grade level
- Explain technical terms when unavoidable
- Focus on outcomes, not process

### CTAs
- Action-oriented verbs: "Get," "Call," "Schedule," "Request"
- Specific about next step: "Get a Free Estimate" not "Learn More"
- Create value without pressure: "See what's possible" not "Act now!"
- Include phone number in CTA context: "Call (720) 326-8492"

### Tone by Context
| Context | Tone |
|---------|------|
| Emergency/Safety | Urgent, reassuring, action-oriented |
| Service descriptions | Expert, clear, benefit-focused |
| About/Story | Warm, authentic, humble pride |
| Testimonials | Genuine, relatable, specific |
| CTAs | Confident, helpful, low-pressure |

---

## Accessibility

### Color Contrast
- All text must meet WCAG AA standards (4.5:1 minimum)
- Primary Blue (#046bd2) on white: 4.6:1 — passes AA
- White on Dark Slate (#1e293b): 13.5:1 — passes AAA
- Never use light blue text on white backgrounds

### Best Practices
- Alt text for all images (descriptive, not decorative)
- Keyboard navigable (all interactive elements)
- Font size minimum 16px for body text
- Touch targets minimum 44x44px for mobile
- Focus states visible on all interactive elements
- Skip link for keyboard navigation
- Form labels properly connected to inputs
- Error messages clear and specific

---

*Brand Style Guide for Aim High Electrical Services*
*Version 2.0 | 2026-01-30*
*Status: ✅ Complete — Brand personality, voice, visual system, and content guidelines defined*
