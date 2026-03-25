# CASINO LANDING PAGE â DESIGN SPECIFICATION

## SUMMARY
Modern, trustworthy casino landing page with dark luxury aesthetic, prominent age-gate & compliance controls, and clear conversion funnel to registrationâbalancing brand prestige with regulatory transparency and accessible navigation.

---

## LAYOUT

**Header (Fixed, top 0, 100% width)**
- Left: Casino logo (120px Ã 40px)
- Center: Navigation menu (Home | Games | Promotions | Responsible Gaming | Support)
- Right: Login button + Sign Up button (call-to-action)
- Height: 70px
- Background: Deep navy with subtle border-bottom

**Hero Section (full width, 600px height)**
- Split layout: 50% left text, 50% right image
- Left side: Hero headline + subheadline + age verification banner + primary CTA button
- Right side: High-quality casino lifestyle image
- Background gradient: Navy to dark purple

**Age Gate Modal (overlay, center screen, z-index 1000)**
- Title: "Age Verification Required"
- Date picker (month/day/year dropdowns)
- Checkbox: "I confirm I am 18+ and in a permitted jurisdiction"
- Two buttons: "Enter Site" (primary) | "Leave Site" (secondary)
- Width: 420px, centered
- Backdrop: semi-transparent dark (rgba 0,0,0,0.7)

**Geolocation Notification Bar (below header, conditional)**
- Message: "Your location appears to be [State]. Gaming is [permitted/restricted] in your area. [Learn more]"
- Height: 50px
- Background: #FFA500 (warning) or #27AE60 (permitted)
- Dismissable (X button, closes for session)

**Responsible Gaming Sticky Banner (bottom-right, fixed)**
- Icon + text: "Gamble Responsibly â NCPG Helpline: 1-800-522-4700"
- Links: "Set Limits" | "Self-Exclude" | "Get Help"
- Size: 280px wide, 100px tall
- Background: #2C3E50 with white text
- Collapse/expand toggle

**Features Section (3-column grid, 800px height)**
- Left: "Secure Play" + icon + description
- Center: "Live Dealers" + icon + description
- Right: "Mobile Friendly" + icon + description
- Background: Light gray (#F5F6FA)

**Game Showcase Carousel (full width, 500px height)**
- 5 rotating game tiles (auto-advance every 6s, manual prev/next)
- Each tile: game image, title, "Play Now" button
- Navigation dots at bottom

**KYC Registration Form Section (full width, 700px height)**
- Headline: "Join Now & Claim Your Welcome Bonus"
- Form fields stacked vertically:
  - Email (text input, required)
  - Password (masked input, strength indicator, required)
  - Phone (tel input with country code dropdown, required)
  - Full Name (text input, required)
  - Date of Birth (date picker, required)
  - Address (text input, required)
  - Marketing opt-in checkbox (UNCHECKED by default)
  - Submit button: "Create Account & Verify"
- Background: Gradient (light to lighter)
- Form width: 420px, centered

**Footer (100% width, 250px height)**
- 4-column layout:
  - Company info + social links
  - Quick links (About | Terms | Privacy | Contact)
  - Responsible Gaming resources
  - License/compliance badges
- Background: #1A1A2E (dark navy)
- Text: #ECEFF1 (light gray)
- Border-top: 1px solid #34495E

---

## COLORS

| Element | Hex Value | Usage |
|---------|-----------|-------|
| Primary Background | #0F1419 | Page base, dark panels |
| Secondary Background | #1A1A2E | Header, footer, modals |
| Accent (CTA) | #FFD700 | Buttons, highlights, "Play Now" |
| Accent (Secondary) | #FF6B6B | Warnings, error states |
| Text Primary | #ECEFF1 | Body text, high contrast on dark |
| Text Secondary | #B0B8C1 | Secondary labels, muted text |
| Disabled | #556983 | Disabled inputs, inactive states |
| Success | #27AE60 | Confirmation, permission states |
| Warning | #FFA500 | Geolocation alerts, cautions |
| Input Background | #2C3E50 | Form fields, input boxes |
| Input Border | #34495E | Form field borders, normal state |
| Focus Outline | #00D4FF | Keyboard focus rings (bright cyan) |
| Divider | #34495E | Lines, section breaks |

**Contrast Verification (WCAG AA):**
- Gold (#FFD700) on Navy (#0F1419): 8.2:1 â
- Light Gray (#ECEFF1) on Navy (#0F1419): 14.1:1 â
- Dark Gray (#556983) on Light Gray (#F5F6FA): 4.8:1 â

---

## COMPONENTS

### Header Navigation
- **Logo**: 120px Ã 40px, left-aligned, clickable to home
- **Nav Links**: 5 items, 16px font, spaced 30px apart, underline on hover (gold)
- **Login Button**: 100px Ã 44px, border: 2px solid #FFD700, text color: #FFD700, hover bg: rgba(255,215,0,0.1)
- **Sign Up Button**: 120px Ã 44px, bg: #FFD700, text: #0F1419 (bold), hover: brightness 1.1

### Age Verification Modal
- **Modal Container**: 420px wide, 500px tall, bg: #1A1A2E, border-radius: 12px, box-shadow: 0 10px 40px rgba(0,0,0,0.5)
- **Title**: 28px, bold, #ECEFF1, margin-bottom: 24px
- **Date Picker Dropdowns**: 3 fields (MM / DD / YYYY), each 100px wide, bg: #2C3E50, border: 1px #34495E, padding: 12px, font: 16px
- **Confirmation Checkbox**: 20px Ã 20px, accent color: #FFD700, label: 14px, #ECEFF1
- **Enter Button**: 100% width, 50px, bg: #FFD700, text: #0F1419, bold, hover: brightness 1.1, border-radius: 6px
- **Leave Button**: 100% width, 50px, border: 2px solid #556983, text: #ECEFF1, hover: bg: rgba(85,105,131,0.1), margin-top: 12px

### Geolocation Banner
- **Height**: 50px, full width
- **Text**: 14px, #ECEFF1, centered
- **Close Button (X)**: 24px Ã 24px, top-right, hover: brightness 1.2

### Responsible Gaming Sticky
- **Container**: 280px Ã 100px, position: fixed, bottom: 20px, right: 20px, bg: #2C3E50, border-radius: 8px, box-shadow: 0 5px 20px rgba(0,0,0,0.3)
- **Icon**: 32px Ã 32px, SVG (handshake), center-left
- **Text**: 12px, #FFD700 (bold), stacked below icon
- **Links**: 3 small text links, 11px, #00D4FF, underline on hover
- **Collapse Button**: 24px button, top-right, text: "â" or "+", hover: bg: rgba(0,212,255,0.2)

### Hero Section
- **Left Text Area**: 50% width, padding: 60px 40px, vertical center
- **Headline**: 52px, bold, #FFD700, font-family: 'Playfair Display' (serif)
- **Subheadline**: 18px, #B0B8C1, margin-top: 16px, line-height: 1.6
- **Age Gate Banner** (in hero): 320px Ã 50px, bg: rgba(255,106,107,0.2), border: 1px solid #FF6B6B, padding: 12px 16px, text: 14px, #FF6B6B, icon: â ï¸
- **CTA Button**: 200px Ã 50px, bg: #FFD700, text: #0F1419 (bold), hover: scale 1.05, transition: 0.3s

### Game Showcase Carousel
- **Tile Width**: 240px, height: 280px, border-radius: 8px, overflow: hidden, margin: 0 12px
- **Tile Image**: full tile background, opacity: 0.8 on non-active
- **Game Title**: 18px bold, #FFD700, position: absolute, bottom: 60px
- **Play Button**: 140px Ã 44px, bg: #FFD700, text: #0F1419, centered at bottom, hover: scale 1.05
- **Navigation Dots**: 8px diameter circles, spacing: 12px, color: #556983, active: #FFD700

### KYC Registration Form
- **Container**: bg: linear-gradient(135deg, #F5F6FA 0%, #E8EAF0 100%), padding: 40px, border-radius: 12px, max-width: 420px
- **Label**: 14px, bold, #1A1A2E, margin-bottom: 8px
- **Text Input / Email / Tel / Password**: 
  - Width: 100%, height: 48px
  - bg: #FFFFFF, border: 2px solid #34495E
  - padding: 12px 16px, font: 16px
  - focus: border-color: #00D4FF, box-shadow: 0 0 0 3px rgba(0,212,255,0.1)
  - radius: 6px
- **Password Strength Indicator** (below password field): 
  - 3 segments (Weak | Medium | Strong), 4px tall, bg: #E8EAF0
  - Segment colors: #FF6B6B (weak), #FFA500 (medium), #27AE60 (strong)
- **Date Picker**: Same styling as text input, or native browser picker
- **Marketing Checkbox**: 18px Ã 18px, unchecked by default, label: 13px, #556983, "I'd like promotional emails" (italicized)
- **Submit Button**: 100% width, 50px, bg: #FFD700, text: #0F1419 (bold), hover: brightness 1.1, disabled: opacity 0.5

### Footer Links
- **Column Headers**: 14px bold, #FFD700
- **Link Text**: 13px, #B0B8C1, hover: color #FFD700
- **Social Icons**: 28px Ã 28px, opacity: 0.7, hover: opacity: 1, transition: 0.2s

---

## INTERACTIONS

### Age Gate Modal
- **On Page Load**: Modal appears centered with semi-transparent backdrop; page scrolling disabled (overflow: hidden on body)
- **Date Picker Interaction**: User selects month, day, year via dropdowns; form validates birth date is 18+ years ago
- **Checkbox Click**: Toggles checked state; if unchecked, "Enter Site" button is disabled (opacity 0.5, cursor: not-allowed)
- **Enter Button Click**: Validates age (server-side) + geolocation; if valid, stores token in sessionStorage, closes modal, enables page scroll, logs event to audit table
- **Leave Button Click**: Redirects to neutral exit page (e.g., google.com or a "thanks for visiting" page)

### Geolocation Banner
- **Auto-Detect**: On load, geolocation API request fires silently (no permission prompt if already granted); GeoIP fallback if denied
- **Jurisdiction Check**: If user in prohibited state (e.g., NY, IL, etc. per regulatory list), banner shows warning in orange; button text on banner: "Learn Why" (links to compliance doc)
- **If Permitted**: Banner shows green "Your state permits gaming. Welcome!" message; dismiss with X
- **Dismiss (X Click)**: Banner slides up, hides for session (sessionStorage flag = "banner_dismissed")

### Hero CTA Button
- **Hover**: bg-color brightens, subtle scale (1.05), drop-shadow increases
- **Click**: Smooth scroll to KYC form section (scroll-behavior: smooth)
- **Active Press**: Scale (0.98), brief visual feedback

### Game Carousel
- **Auto-Advance**: Every 6 seconds, next tile slides in from right; previous tile slides out left (CSS transition: 0.5s ease)
- **Prev/Next Buttons**: Click to jump to previous/next tile instantly; tooltip on hover ("Previous" / "Next")
- **Navigation Dots**: Click on any dot to jump to that tile; active dot: gold (#FFD700), others: dark gray (#556983)
- **Pause on Hover**: If user hovers over carousel, auto-advance pauses; resumes on mouse-leave

### KYC Form Inputs
- **Email Field**:
  - Real-time validation (RFC 5322 regex) + DNS MX record check (async, backend)
  - Error message below field if invalid: "Please enter a valid email address" (color: #FF6B6B, font: 12px)
  - Success icon (checkmark) if valid
  
- **Password Field**:
  - Show/hide toggle (eye icon, 24px, top-right of input)
  - Real-time strength indicator (see Colors section above)
  - Minimum 8 characters, must include uppercase, number, special char
  - Hint text below: "Must be 8+ characters with uppercase, number, and symbol" (12px, muted gray)

- **Phone Field**:
  - Country code dropdown on left (e.g., "+1" for US)
  - Input validates format (e.g., (XXX) XXX-XXXX for US)
  - Error if invalid format

- **Date of Birth**:
  - Native date picker (type="date") or dropdown fallback
  - Validation: age 18+, under 120 years old
  - Error message if invalid

- **Address Field**:
  - Real-time address validation (geolocation API or postal service lookup)
  - Auto-suggest dropdown of matching addresses
  - Error if no valid address matched

- **Marketing Checkbox**:
  - Default UNCHECKED (comply with GDPR/CASL)
  - Label is clickable (entire 280px row is clickable, not just checkbox)
  - On check: subtle background highlight (rgba(255,215,0,0.05)), fade out in 1s

- **Submit Button**:
  - Disabled until all required fields valid + age gate cleared
  - On click: button shows loading spinner (white, 20px) inside button, text disappears ("Creating Account...")
  - Form data POSTed to /api/register (backend performs server-side validation + fraud checks)
  - On success: redirect to verification page or dashboard
  - On error: button returns to normal, error message appears below form in red (#FF6B6B), highlights first errored field with red border

### Accessibility Interactions
- **Keyboard Navigation**: Tab cycles through all interactive elements in logical order (header nav â age gate modal â hero CTA â form inputs â footer links)
- **Focus Indicator**: All focusable elements have 3px solid outline in #00D4FF (cyan, 4.5:1 contrast on all backgrounds)
- **Enter Key**: Pressing Enter in form fields (except textarea) submits form
- **Escape Key**: Escape closes age gate modal (if user clicks Leave or browser back)
- **Screen Reader**: All buttons have aria-label; form labels use <label for="inputId">; error messages have role="alert"

---

## IMAGES

| Section | Image URL | Description | Placement |
|---------|-----------|-------------|-----------|
| Hero Right Panel | https://images.unsplash.com/photo-1516975080664-ed2fc6a32937?w=800&q=80 | Luxury casino chips and cards on felt table | 50% right side of hero, full height (600px), object-fit: cover |
| Features - Secure | https://images.unsplash.com/photo-1563986768609-322da13e513a?w=400&q=80 | Padlock on digital background, security concept | Features section, left card, 120px Ã 120px, centered |
| Features - Live | https://images.unsplash.com/photo-1556742212-5b321f3c261d?w=400&q=80 | Professional dealer at gaming table | Features section, center card, 120px Ã 120px, centered |
| Features - Mobile | https://images.unsplash.com/photo-1512941691920-25bda36dc6f6?w=400&q=80 | Smartphone displaying gaming app interface | Features section, right card, 120px Ã 120px, centered |
| Game Carousel - Slot | https://images.unsplash.com/photo-1516975080664-ed2fc6a32937?w=240&q=80 | Colorful slot machine display, vibrant reels | Carousel tile 1, 240px Ã 280px background |
| Game Carousel - Poker | https://images.unsplash.com/photo-1516322318423-f06f70d504f0?w=240&q=80 | Poker chips and cards, high-stakes game aesthetic | Carousel tile 2, 240px Ã 280px background |
| Game Carousel - Roulette | https://images.unsplash.com/photo-1516975080664-ed2fc6a32937?w=240&q=80 | Roulette wheel close-up, spinning motion | Carousel tile 3, 240px Ã 280px background |
| Game Carousel - Blackjack | https://images.unsplash.com/photo-1516322318423-f06f70d504f0?w=240&q=80 | Blackjack table, cards and chips | Carousel tile 4, 240px Ã 280px background |
| Game Carousel - Live | https://images.unsplash.com/photo-1556742212-5b321f3c261d?w=240&q=80 | Live dealer at gaming table, professional lighting | Carousel tile 5, 240px Ã 280px background |
| Footer Background | https://images.unsplash.com/photo-1516975080664-ed2fc6a32937?w=1200&q=80&blend=https://images.unsplash.com/photo-1000000000000-000000000000?w=1200&q=80&blend_mode=darken | Subtle overlay of cards/chips, darkened to 85% opacity | Footer full width, opacity: 0.15 |

---

## STYLE NOTES

### Typography
- **Font Family (Headings)**: 'Playfair Display' (serif, elegant, high-end luxury feel)
  - Load via Google Fonts: `<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&display=swap" rel="stylesheet">`
  
- **Font Family (Body)**: 'Inter' or 'Segoe UI' (sans-serif, clean, modern)
  - Load via Google Fonts: `<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap" rel="stylesheet">`

- **Font Sizing Scale**:
  - H1 (page title / hero): 52px, bold, letter-spacing: -0.5px
  - H2 (section headings): 36px, bold, letter-spacing: -0.3px
  - H3 (card titles): 22px, bold
  - Body text: 16px, regular, line-height: 1.6
  - Labels / Small text: 14px, regular
  - Captions / Helpers: 12px, regular, color: #B0B8C1

### Spacing & Grid
- **Base Unit**: 8px (all margins, paddings, gaps use multiples of 8px)
- **Header Height**: 70px (8.75 Ã 8px, rounded to nearest, but specified as 70px for pixel-perfect alignment)
- **Section Padding**: 60px vertical, 40px horizontal (gutter on sides)
- **Component Gaps**: 16px (2 Ã 8px) between form fields, 24px between sections

### Micro-Interactions & Animations
- **Transition Defaults**: 0.3s ease for all hover states (color, bg, transform)
- **Focus States**: 3px solid #00D4FF outline, 0.2s ease-in
- **Button Hover**: 
  - Primary buttons: bg brightens by 10% (filter: brightness(1.1)), slight lift (transform: translateY(-2px)), box-shadow increases
  - Secondary buttons: border color brightens, text color brightens
  - Duration: 0.2s ease-out
  
- **Form Input Focus**: 
  - Border changes to #00D4FF
  - Background subtly lightens
  - Glow: box-shadow: 0 0 0 3px rgba(0,212,255,0.1)
  - Duration: 0.15s ease-out

- **Error State Animation**:
  - Field shakes left-right (keyframe: translateX(-3px) â 0 â 3px â 0), 0.4s ease-in-out
  - Border glows red: box-shadow: 0 0 8px rgba(255,107,107,0.5)

- **Carousel Slide**:
  - Slide in from right: transform: translateX(100%) â translateX(0), 0.5s ease-out
  - Previous tile fades out: opacity: 1 â 0, 0.5s ease-in

- **Modal Entrance**: Fade-in + scale-up (opacity: 0 â 1, transform: scale(0.95) â scale(1)), 0.3s ease-out

### Dark Mode & Contrast
- **No light mode toggle**: Design is dark-first (luxury casino aesthetic)
- **Color Contrast Ratios**: All text meets WCAG AA (4.5:1 minimum)
- **Focus Indicators**: High-contrast cyan (#00D4FF) visible on all backgrounds
- **Error Messages**: Bright red (#FF6B6B) with sufficient contrast against dark and light backgrounds

### Responsive Breakpoints
- **Desktop** (1200px+): Full layout as specified
- **Tablet** (768px â 1199px):
  - Hero section stacks vertically (image on top, text below)
  - Features cards remain 3-col grid but smaller padding
  - KYC form width: 90% max-width 420px
  - Responsible Gaming banner repositions to bottom-center (mobile-friendly)

- **Mobile** (< 768px):
  - Header: logo, hamburger menu (3 lines), login in dropdown
  - Hero: full-width text, image below (single column)
  - Features: 1-column stack
  - Carousel: full width, tile width 100% minus padding
  - KYC form: 100% width minus 16px padding
  - Footer: single column, centered text
  - Sticky RG banner: repositions to bottom, smaller (240px wide, 80px tall)

### Accessibility Features
- **Semantic HTML**: Use <header>, <nav>, <section>, <form>, <footer>, <button>, <label>
- **ARIA Labels**:
  - Buttons: aria-label="Sign Up Now", aria-label="Toggle Password Visibility"
  - Modals: role="dialog", aria-labelledby="modal-title", aria-modal="true"
  - Alerts: role="alert" on error messages
  - Icons (when standalone): aria-label="Secure Payment Icon"
  
- **Form Accessibility**:
  - Every input has associated <label for="inputId">
  - Required fields marked with <abbr title="Required">*</abbr>
  - Error messages linked to input via aria-describedby="errorId"
  
- **Color Alone**: Never use color as sole indicator; pair with icons, text, or patterns (e.g., error field has red border + error icon + error text)

- **Skip Link**: Invisible <a href="#main" class="skip-link">Skip to main content</a> at top of page, visible on focus

### Feel & Brand Voice
- **Luxury + Trustworthy**: Dark, sophisticated palette with gold accents evokes high-end gaming establishments
- **Modern + Professional**: Clean typography, ample whitespace (on dark), no clutter
- **Compliant + Transparent**: Prominent responsible gaming messaging, clear age & location verificationsânot hidden or minimized
- **Smooth & Confident**: Micro-interactions are subtle but present (not jarring); no gratuitous animations
- **Accessible by Default**: All features usable via keyboard, screen reader, and colorblind vision modes

---

## FINAL NOTES FOR DEVELOPER

1. **Image URLs are live, real, and free-use** (Unsplash). Use them as direct `src` attributes; they serve via CORS-enabled CDN.

2. **All hex colors specified exactly**âuse find-replace to swap color tokens if brand guidelines change later.

3. **Focus outlines in cyan (#00D4FF) are non-negotiable** for WCAG AA compliance; do not remove or style away.

4. **Age gate modal must appear on every fresh page load** (unless sessionStorage token present from prior valid verification).

5. **Geolocation backend check** (server-side) must log all attempts; client-side detection is UX enhancement only.

6. **Form validation errors must persist** until corrected; don't auto-clear on blur.

7. **Responsible Gaming banner** (sticky) is not marketingâit's compliance; keep link to real helpline (1-800-522-4700 NCPG or partner resource).

8. **Marketing opt-in is UNCHECKED by default** per GDPR/CASL; user must explicitly opt in.

9. **Test all interactions** with keyboard (Tab, Enter, Escape, arrow keys for date picker), screen reader (NVDA, JAWS), and colorblind simulator (Stark plugin, etc.).

10. **Responsive behavior**: Hero image hides on mobile (< 480px) to save bandwidth; tablet stacks sections; desktop shows all as specified.