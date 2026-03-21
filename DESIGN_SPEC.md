# Dote — Design Specification

## Brand

- **Name:** Dote ("to lavish affection")
- **Tagline:** "Because they deserve it."
- **Product:** Premium pet expense tracker, mobile-first

## Design Tokens

### Colors
| Role | Hex | Usage |
|------|-----|-------|
| Background | `#FAF8F5` | Page background, warm paper white |
| Text Primary | `#1A1815` | Headlines, body text, buttons |
| Accent | `#C4632A` | Terracotta — "Penny" label, feature numbers, category dots |
| Text Secondary | `#8C867D` | Warm stone gray — sublabels, body copy, nav links |
| Surface | `#F0ECE6` | Card backgrounds (month card, CTA section) |
| Border | `#E5E0D8` | Dividers, card internal borders |
| Border Light | `#EDEAE5` | Activity row separators |
| Button Text | `#FAF8F5` | White text on dark buttons |

### Typography
| Role | Font | Weight | Size | Line Height | Letter Spacing |
|------|------|--------|------|-------------|----------------|
| Wordmark | DM Serif Display | 400 | 22px | 28px | -0.01em |
| Hero Headline | DM Serif Display | 400 | 44px | 48px | -0.02em |
| Section Headline | DM Serif Display | 400 | 28-32px | 36-38px | -0.01em |
| Big Number | Inter Tight | 800 | 48px | 48px | -0.03em |
| Body | Inter | 400 | 15-16px | 18-24px | — |
| Body Medium | Inter | 500 | 15px | 18px | — |
| Label Uppercase | Inter | 500 | 12px | 16px | 0.08em, uppercase |
| Feature Number | Inter | 500 | 11px | 14px | 0.06em |
| Small | Inter | 400 | 12-13px | 16-19px | — |
| Button | Inter | 500 | 15px | 18px | 0.01em |

### Spacing
- Page side padding: `24px`
- Section gap: `48-64px` (top padding between major sections)
- Group gap: `24px` (within cards, between related elements)
- Element gap: `3-4px` (label to sublabel)
- Card padding: `28px`
- Card border radius: `16px`
- Image border radius: `12px`
- Button padding: `14px 28px`
- Button border radius: `8px`

### Fonts to Load (Google Fonts)
- DM Serif Display (400)
- Inter (400, 500)
- Inter Tight (800)

## Layout

- **Mobile-first:** 390px viewport
- **Flex column** layout, no grid
- **No gradients, no card grids, no icon cards** — editorial, typographic approach

## Page Sections (top to bottom)

### 1. Nav
- Left: "dote" wordmark (DM Serif Display 22px)
- Right: "Sign in" (Inter 500 13px, stone gray)

### 2. Hero
- Headline: "Know what love costs." (DM Serif Display 44px)
- Body: "Track every treat, every grooming session, every vet visit. Spoil them without the surprises." (Inter 16px, stone gray)
- CTA: "Start tracking" button (dark bg, white text, 8px radius)

### 3. Hero Image
- Full-width image of Penny (brown Doberman, cropped ears, pink collar)
- `heroes/penny-v2a.jpg` — 380px height, object-fit: cover, 12px radius

### 4. Monthly Spend Card
- Surface background (#F0ECE6), 16px radius
- Header: "MARCH 2026" (uppercase label) + "Penny" (accent color)
- Big number: "$847" (Inter Tight 800, 48px)
- Category rows with colored dots:
  - Food & treats: $340 (terracotta dot)
  - Grooming: $285 (dark dot)
  - Toys & accessories: $142 (gray dot)

### 5. Recent Activity
- "RECENT" uppercase label + divider
- Transaction rows with merchant name, category + date, and amount:
  - The Good Dog Bakery — Food & treats · Today — $28
  - Paws & Claws Spa — Grooming · Yesterday — $85
  - Dr. Williams — annual visit — Vet · Mar 14 — $180
  - BarkShop — Super Chewer box — Toys · Mar 10 — $35

### 6. Value Proposition
- Headline: "They give you everything. The least you can do is keep track." (DM Serif Display 28px)
- Lifestyle image: `heroes/penny-accessories-pink.jpg` — pink unicorn collar flatlay, 240px height

### 7. Features (numbered list, not cards)
- 01: "Snap a receipt, done" — "Photo it at the pet store. Dote reads the total and sorts it."
- 02: "Categories that make sense" — "Food, vet, grooming, toys — not 'miscellaneous.'"
- 03: "Monthly totals, no spreadsheet" — "See what you spent and where. Trends over time without the effort."

### 8. Bottom CTA
- Surface background (#F0ECE6), 16px radius, inset 12px from edges
- Headline: "She's not going to track it herself." (DM Serif Display 32px, centered)
- CTA: "Start tracking" button
- Image: `heroes/penny-intimate-v2.jpg` — Penny resting on couch, 200px height

### 9. Footer
- Left: "dote" (DM Serif Display 16px, stone gray)
- Right: "Because they deserve it." (Inter 12px, stone gray)

## Image Assets

All in `heroes/` directory:

| File | Description | Usage |
|------|-------------|-------|
| `penny.jpeg` | Reference photo of Penny (the real dog) | Source reference |
| `penny-v2a.jpg` | Editorial portrait, standing in warm interior | Hero image |
| `penny-accessories-pink.jpg` | Flatlay with pink unicorn collar, treats, bowl | Mid-section lifestyle |
| `penny-intimate-v2.jpg` | Close-up resting on cream sofa | Bottom CTA |

## JSX Export (inline styles)

The complete JSX with exact computed styles from Paper is below. Note: image URLs reference Paper's CDN — replace with local paths from `heroes/` directory.

```jsx
<div style={{ backgroundColor: '#FAF8F5', boxSizing: 'border-box', display: 'flex', flexDirection: 'column', fontSynthesis: 'none', height: 'fit-content', overflow: 'clip', WebkitFontSmoothing: 'antialiased', width: '390px' }}>
  {/* Nav */}
  <div style={{ alignItems: 'center', boxSizing: 'border-box', display: 'flex', justifyContent: 'space-between', paddingBlock: '20px', paddingInline: '24px', width: '100%' }}>
    <div style={{ color: '#1A1815', fontFamily: '"DM Serif Display", system-ui, sans-serif', fontSize: '22px', letterSpacing: '-0.01em', lineHeight: '28px' }}>dote</div>
    <div style={{ color: '#8C867D', fontFamily: '"Inter", system-ui, sans-serif', fontSize: '13px', fontWeight: 500, lineHeight: '16px' }}>Sign in</div>
  </div>

  {/* Hero */}
  <div style={{ display: 'flex', flexDirection: 'column', gap: '24px', paddingLeft: '24px', paddingRight: '24px', paddingTop: '48px', width: '100%' }}>
    <div style={{ color: '#1A1815', fontFamily: '"DM Serif Display", system-ui, sans-serif', fontSize: '44px', letterSpacing: '-0.02em', lineHeight: '48px' }}>Know what love costs.</div>
    <div style={{ color: '#8C867D', fontFamily: '"Inter", system-ui, sans-serif', fontSize: '16px', lineHeight: '24px' }}>Track every treat, every grooming session, every vet visit. Spoil them without the surprises.</div>
    <div style={{ alignItems: 'center', alignSelf: 'flex-start', backgroundColor: '#1A1815', borderRadius: '8px', display: 'flex', justifyContent: 'center', paddingBlock: '14px', paddingInline: '28px' }}>
      <div style={{ color: '#FAF8F5', fontFamily: '"Inter", system-ui, sans-serif', fontSize: '15px', fontWeight: 500, letterSpacing: '0.01em', lineHeight: '18px' }}>Start tracking</div>
    </div>
  </div>

  {/* Hero Image — replace URL with heroes/penny-v2a.jpg */}
  <div style={{ display: 'flex', paddingLeft: '24px', paddingRight: '24px', paddingTop: '32px', width: '100%' }}>
    <div style={{ backgroundImage: 'url(heroes/penny-v2a.jpg)', backgroundPosition: 'center', backgroundSize: 'cover', borderRadius: '12px', height: '380px', width: '100%' }} />
  </div>

  {/* Monthly Spend Card */}
  <div style={{ display: 'flex', flexDirection: 'column', paddingLeft: '24px', paddingRight: '24px', paddingTop: '32px', width: '100%' }}>
    <div style={{ backgroundColor: '#F0ECE6', borderRadius: '16px', display: 'flex', flexDirection: 'column', gap: '24px', paddingBlock: '28px', paddingInline: '28px', width: '100%' }}>
      <div style={{ alignItems: 'baseline', display: 'flex', justifyContent: 'space-between' }}>
        <div style={{ color: '#8C867D', fontFamily: '"Inter", system-ui, sans-serif', fontSize: '12px', fontWeight: 500, letterSpacing: '0.08em', lineHeight: '16px', textTransform: 'uppercase' }}>March 2026</div>
        <div style={{ color: '#C4632A', fontFamily: '"Inter", system-ui, sans-serif', fontSize: '12px', fontWeight: 500, lineHeight: '16px' }}>Penny</div>
      </div>
      <div style={{ color: '#1A1815', fontFamily: '"Inter Tight", system-ui, sans-serif', fontSize: '48px', fontWeight: 800, letterSpacing: '-0.03em', lineHeight: '48px' }}>$847</div>
      {/* Category rows with top borders and colored dots */}
    </div>
  </div>

  {/* Recent Activity — "RECENT" label + divider + transaction rows */}
  {/* Value Prop — DM Serif headline + flatlay image (heroes/penny-accessories-pink.jpg) */}
  {/* Features — numbered 01/02/03 list */}
  {/* Bottom CTA — surface bg, headline, button, intimate image (heroes/penny-intimate-v2.jpg) */}
  {/* Footer — "dote" + "Because they deserve it." */}
</div>
```

See full unabridged JSX export by running `get_jsx` on node `A3-0` in Paper.
