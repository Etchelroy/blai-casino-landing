# CASINO LANDING PAGE â RESEARCH BRIEF

## SUMMARY
Building a compliant, high-conversion casino landing page requires regulatory gatekeeping, responsible gaming messaging, trust signals, and mobile-first design with strict age verification and jurisdictional checks.

---

## APPROACH

**Tech Stack:**
- **Frontend:** React or Next.js (SSR for SEO, fast core web vitals)
- **Styling:** Tailwind CSS + CSS custom properties (theming, dark mode)
- **State:** React Context or Zustand (geolocation, age gate, form state)
- **Verification:** Age/location API (GeoIP + form submission)
- **Backend:** Node.js/Express or Python FastAPI (compliant logging, no client-side secrets)
- **Hosting:** Vercel or AWS CloudFront (CDN, GDPR compliance, DDoS protection)
- **Analytics:** Compliance-safe tracking (Plausible or Matomo, not Google Analytics alone in some jurisdictions)

**Why:** Next.js provides server-side rendering for SEO (critical for legal discoverability), built-in image optimization, and environment variable isolation. Tailwind enables fast responsive iteration. Backend API prevents exposing sensitive configs.

---

## REQUIREMENTS

### Phase 1: Gatekeeping & Compliance
- **Age Gate Modal** (dismissable only after confirmation, triggered on page load)
  - Date picker input (format: DD/MM/YYYY or locale-aware)
  - Legal text: "You must be [jurisdiction age limit] or older"
  - Submit button disables until valid date entered
  - Stores age-verified flag in sessionStorage (not localStorageâexpires on tab close)
  
- **Geolocation Check**
  - Silent GeoIP API call on load (MaxMind, CloudFlare, or IP2Location)
  - Block or restrict access if user in prohibited jurisdiction (UK, US states where unlicensed, etc.)
  - Show compliant message: "Services not available in your region"
  - Backend logs all blocked attempts (audit trail required)

- **Responsible Gaming Banner** (sticky footer or header)
  - Text: "If you think you have a gambling problem, visit [official helpline URL]"
  - Link to Gamblers Anonymous / national helpline (e.g., NCPG 1-800-GAMBLER in US)
  - Collapsible but always accessible

### Phase 2: Hero Section
- **Full-width hero image/video** (16:9 aspect ratio, max 2MB optimized)
  - High-contrast text overlay: brand name, tagline, CTA
  - Gradient overlay (dark semi-transparent, WCAG AA contrast â¥4.5:1 on white text)
  - Mobile: stack text vertically, reduce image to 60% viewport height
  
- **Primary CTA Button** (above fold)
  - Text: "Join Now" or "Play Now"
  - Color: brand primary (test 3+ variants for conversion)
  - Disabled until age-gate passed
  - Links to sign-up form (see Phase 3)

### Phase 3: Sign-Up Form Section
- **Email + Password Input**
  - Email: validate format, check DNS blacklist (optional: real-time availability)
  - Password: minimum 8 chars, 1 uppercase, 1 number, 1 special char (show strength meter)
  - Client-side validation, server-side confirmation
  
- **Phone Number Input** (optional but recommended for SMS verification)
  - International dial code selector
  - Format mask (auto-detect country, apply format)
  
- **Address Verification** (KYC requirement in regulated markets)
  - Full name, street address, city, postal code, country
  - Server-side lookup against address databases (fraud prevention)
  
- **Opt-In Checkbox for Marketing**
  - Separate from T&Cs (GDPR/CASL compliance)
  - Text: "Send me promotions and updates" (must be unchecked by default)
  
- **Terms & Conditions + Privacy Policy Links**
  - Inline legal text (small, gray, 12px min, WCAG AA compliant)
  - Checkbox: "I agree to Terms & Conditions" (required before submit)
  - Checkbox: "I've read the Privacy Policy" (required before submit)
  - Links open in new tabs (no user context loss)
  
- **Submit Button**
  - Disabled until: age verified, email valid, password strong, both checkboxes checked
  - Show spinner on submit (disable during request)
  - Success: redirect to welcome email or dashboard
  - Error: display server message (e.g., "Email already registered")

### Phase 4: Trust & Social Proof Section
- **License/Certification Badges** (must be real, verified)
  - MGA (Malta Gaming Authority), UKGC, eCOGRA, GLI certification logos
  - Only display if legitimately licensed
  - Each badge links to verification page (opens new tab)
  
- **Testimonial Carousel** (3â5 cards, auto-rotate every 5s, pausable on hover)
  - Avatar image (placeholder if real photos unavailable)
  - Name, location (generic: "John, UK" not full address)
  - Quote: max 100 chars, avoid fake testimonials
  - Star rating (1â5 stars, numeric display)
  - Attribution: "Verified player" or similar trust marker
  
- **Stats Section** (numbers build credibility)
  - "1M+ Active Players" / "â¬X Paid Out" / "15+ Years Operating"
  - Use conservative, defensible numbers only
  - Display in 2-column grid (mobile) â 3-column (desktop)

### Phase 5: Game Preview Section
- **Game Grid** (3 columns on desktop, 1 on mobile)
  - 6â12 game cards (slots, table games, live dealer)
  - Each card: thumbnail image, game title, RTP/volatility badge (if allowed)
  - Hover state: slightly lift, show "Play Demo" button (no real play on landing page)
  - No actual gameplay on landing page (legal/compliance issue)
  
- **"View All Games" CTA**
  - Directs to full game library (after user logs in)

### Phase 6: Promotions Section
- **Welcome Bonus Card**
  - Headline: "100% Up to â¬500 Welcome Bonus"
  - Terms in small text: "35x wagering requirement, valid on slots only, 7-day expiry"
  - Must clearly state all conditions (legal requirement)
  - CTA: "Claim Bonus" (redirects to sign-up if not registered)
  
- **Sticky Promo Bar** (optional, above footer)
  - Rotating text: "New players get 50 Free Spins" (cycle every 4 seconds)

### Phase 7: Footer
- **Links Grid** (4 columns on desktop, 1 on mobile)
  - About, Responsible Gaming, Support, Careers
  - Terms, Privacy Policy, Complaints, Cookies
  - Contact: phone, email, support chat CTA
  
- **Social Links** (icons only, no tracking pixels)
  - Facebook, Twitter, Instagram (only if brand actually uses them)
  
- **Payment Methods Icons** (Visa, Mastercard, PayPal, Apple Pay, etc.)
  - Display only methods actually supported
  
- **Copyright & License Info**
  - "Licensed & Regulated by [Authority]"
  - Contact address of operator (legal requirement)
  - License number (clickable, verifiable)

### Phase 8: Responsive Design
- **Breakpoints:**
  - Mobile: 320pxâ640px (1 column layouts, touch-friendly buttons â¥48px)
  - Tablet: 641pxâ1024px (2 columns)
  - Desktop: 1025px+ (3+ columns, max-width container 1280px)
  
- **Touch Optimization:**
  - Buttons: minimum 44Ã44px (Apple) or 48Ã48px (Android)
  - Form inputs: auto-zoom on iOS (don't lock viewport scale)
  - Modals: full-screen on mobile, centered overlay on desktop

---

## CONSTRAINTS

### Legal/Regulatory
- **Jurisdiction-dependent:** Rules differ wildly between UK (UKGC), Malta (MGA), US (state-by-state), Canada, Australia
  - Age limits: 18 in most places, 19 in some Canadian provinces
  - Advertising: UK requires prominent "BeGambleAware.org" link
  - Data residency: GDPR requires EU user data stored in EU
  
- **No affiliate links or revenue-share disclosures** in UI (hide via backend)
- **No false scarcity language** ("Limited time!" without end date is illegal in some regions)
- **Cannot auto-play video sound** (WCAG, user consent)

### Technical Constraints
- **Load time:** Core Web Vitals target LCP <2.5s, FID <100ms, CLS <0.1
  - Image optimization critical (WebP with JPEG fallback, lazy loading)
  - Minify CSS/JS, remove unused Tailwind classes
  
- **API Rate Limiting:**
  - Age/location verification: 1 request per session (cache result)
  - Sign-up email check: 1 request per keystop (300ms debounce)
  - Implement exponential backoff (429 Retry-After header)
  
- **No third-party tracking on sign-up form** (privacy/data protection law)
  - Cookie consent banner required before GA/Mixpanel scripts load
  
- **HTTPS only**, no mixed content

### Performance Budget
- **Page load:** â¤3s on 4G (include all assets)
- **JavaScript:** â¤100KB gzipped (React + Tailwind bundle)
- **Images:** â¤500KB total (hero, testimonials, logos)

---

## NOTES

### Best Practices
1. **Age Gate UX:**
   - Don't let users dismiss without entering DOB (they'll click through carelessly)
   - Use a date picker widget (easier than text input, prevents invalid dates)
   - Store verification server-side, not just client-side (user can edit localStorage)
   - Log all age-gate attempts + results (audit trail)

2. **Responsible Gaming:**
   - Make helpline link *visible and findable*, not hidden in footer
   - Test that link works and points to legitimate, current resource
   - Consider adding "Set Limits" / "Self-Exclude" buttons (even if dormant, shows intent)

3. **Trust Signals:**
   - Only display licenses you actually have (fake ones = serious legal trouble)
   - Verify logos are current (some gaming authorities update them)
   - Get written permission before using testimonials (avoid defamation)
   - Never photoshop or use stock photos of "players"

4. **Accessibility (WCAG AA minimum):**
   - Color contrast: 4.5:1 for normal text, 3:1 for large text
   - Alt text on all images (include game names, not just "slot machine")
   - Form labels associated with inputs (use `<label htmlFor>`), not placeholders alone
   - Keyboard navigation: Tab order matches visual flow, all interactive elements focusable
   - Screen reader testing: test with NVDA (Windows) or VoiceOver (Mac)
   - Modals: trap focus inside modal, restore focus on close
   - Avoid flashing/seizure triggers (no more than 3 flashes/second)

5. **SEO:**
   - Meta title: "Online Casino | Play Slots & Games at [Brand]" (include location if targeting specific market)
   - Meta description: max 160 chars, include CTA
   - H1: one per page, use "Play Now at [Brand]" or similar
   - Schema markup: add "WebSite" schema (brand name, logo, contact) + "LocalBusiness" if location-specific
   - Internal links: link from hero CTA to sign-up form (no broken links)

6. **Edge Cases to Handle:**
   - User blocks geolocation request â fall back to GeoIP API
   - User is in blocked region but uses VPN â document policy ("We don't tolerate abuse")
   - User enters future date in age gate â show error "Invalid date"
   - User submits sign-up twice in <2s â debounce, show "Processing..." state
   - Email already registered â clear error message, offer "Forgot Password" link
   - Session expires during sign-up â preserve form data in sessionStorage, warn user

7. **Mobile-Specific:**
   - Test on actual devices (iOS Safari, Chrome Android)
   - Use viewport meta tag: `<meta name="viewport" content="width=device-width, initial-scale=1">`
   - Avoid fixed headers that eat screen real estate on mobile
   - Touch targets: buttons â¥48px, spacing â¥8px between targets
   - Avoid hover-only interactions (mobile has no hoverâuse active state instead)

8. **Performance Optimizations:**
   - Lazy load images below fold (Intersection Observer, `loading="lazy"`)
   - Code-split sign-up form (load only on page scroll or CTA click)
   - Cache static assets: set Cache-Control headers (images: 1 year, HTML: 1 hour, JS: 1 day)
   - Use WebP images with JPEG fallback: `<picture>` tag, not `srcset` alone
   - Minify legal text sections (they're large, compress well)

9. **Testing Checklist:**
   - â Age gate blocks users under threshold, allows those over
   - â Geolocation blocks users in restricted regions
   - â Form validation works (email, password strength, address)
   - â All external links (T&Cs, helplines, licenses) are live and current
   - â Page works on iOS 14+, Android 8+, desktop (Chrome, Firefox, Safari, Edge)
   - â No console errors or warnings
   - â Lighthouse score â¥80 (performance + accessibility)
   - â WCAG AA compliance (color contrast, focus indicators, alt text)
   - â Sign-up API calls don't expose API keys or sensitive data
   - â Responsible gaming helpline link is functional

10. **Things to Avoid:**
    - â Testimonials that sound fake ("This changed my life!")
    - â Countdown timers that reset or are fake
    - â "Limited time offer" without expiration date
    - â Images of casino floors with real people (privacy issues)
    - â Guarantees of winning ("Guaranteed Payout", "Sure Wins")
    - â Targeting minors in any way (no cartoon characters, bright colors signaling "fun")
    - â Hiding the T&Cs in 8pt font (legal requirement to be readable)
    - â Auto-playing audio/video
    - â Session cookies without explicit consent (GDPR)
    - â Third-party analytics before cookie consent

---

**Ready for Developer handoff.** This brief defines exactly what needs to be built, with no code written. Developer should implement with the constraints and testing checklist in mind.