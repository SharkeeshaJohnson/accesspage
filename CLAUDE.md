# ANUMA Design System

This document captures the typography, styling, and design conventions for the ANUMA landing page.

---

## Color System

```css
--color-bg: #ECECEC;           /* Primary background */
--color-bg-alt: #E5E5E5;       /* Alternate background */
--color-text: #1A1A1A;         /* Primary text */
--color-text-muted: #6B6560;   /* Muted/secondary text */
--color-accent: #8B7355;       /* Accent color (warm brown) */
--color-border: #E8E4DF;       /* Borders */
--color-white: #FFFFFF;        /* White */
```

### Brand Colors
- **Logo Orange**: `#C57741` - Used for ANUMA wordmark
- **Footer Background**: `#595552` - Dark warm gray

---

## Typography

### Font Family
```css
--font-family: 'Manrope', sans-serif;
```

**Google Fonts Import:**
```html
<link href="https://fonts.googleapis.com/css2?family=Manrope:wght@200;300;400;500;600;700;800&display=swap" rel="stylesheet">
```

### Font Weights Used
- `200` - Extra Light (display text)
- `300` - Light (headings, mobile menu)
- `400` - Regular (body, descriptions)
- `500` - Medium (eyebrows, nav, labels)
- `600` - Semi-bold (titles, column headers)
- `700` - Bold
- `800` - Extra Bold (logo only)

### Typography Scale

#### Display Text (Hero)
```css
.hero-line {
    font-size: clamp(3.5rem, 10vw, 7.5rem);  /* 56px to 120px */
    font-weight: 400;
    letter-spacing: -0.02em;
    text-transform: uppercase;
    line-height: 1.05;
}
```

#### Text Display (Utility)
```css
.text-display {
    font-size: clamp(2.5rem, 5vw, 4rem);     /* 40px to 64px */
    font-weight: 200;
    letter-spacing: -0.02em;
    line-height: 1.1;
}
```

#### Headings
```css
.text-heading {
    font-size: clamp(1.75rem, 3vw, 2.25rem); /* 28px to 36px */
    font-weight: 300;
    letter-spacing: -0.01em;
    line-height: 1.2;
}
```

#### Section Titles (Intro, Features)
```css
.intro__title,
.feature-slide__title {
    font-size: clamp(1.8rem, 3.6vw, 2.4rem); /* ~29px to 38px */
    font-weight: 600;
    letter-spacing: -0.02em;
    line-height: 1.4;
    text-transform: uppercase;
}
```

#### Section Subtitles/Descriptions
```css
.intro__subtitle,
.feature-slide__description {
    font-size: clamp(1.05rem, 1.8vw, 1.35rem); /* ~17px to 22px */
    font-weight: 400;
    letter-spacing: -0.01em;
    line-height: 1.6;
    text-transform: uppercase;
}
```

#### Body Text
```css
.text-body {
    font-size: 1rem;              /* 16px */
    font-weight: 400;
    line-height: 1.7;
    color: var(--color-text-muted);
}
```

#### Small Text
```css
.text-small {
    font-size: 0.875rem;          /* 14px */
    font-weight: 400;
    line-height: 1.6;
}
```

#### Eyebrow Text
```css
.text-eyebrow {
    font-size: 0.75rem;           /* 12px */
    font-weight: 500;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--color-text-muted);
}
```

### Logo Typography
```css
/* Header Logo */
.header__logo-text {
    font-size: 2.475rem;          /* ~39.6px */
    font-weight: 800;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: #C57741;
}

/* Footer Logo */
.footer__logo-text {
    font-size: 2.475rem;
    font-weight: 800;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--color-bg);
}
```

---

## Spacing System

```css
--container-width: 1280px;
--container-padding: 48px;
--section-spacing: 160px;
```

### Responsive Spacing

| Breakpoint | Container Padding | Section Spacing |
|------------|-------------------|-----------------|
| > 1024px   | 48px              | 160px           |
| 768-1024px | 32px              | 120px           |
| 480-768px  | 24px              | 80px            |
| 360-480px  | 20px              | 64px            |
| < 360px    | 16px              | 64px            |

---

## Transitions & Animations

### Easing Function
```css
--transition-smooth: cubic-bezier(0.4, 0, 0.2, 1);
```

### Standard Transitions
```css
/* General hover */
transition: opacity 0.2s ease;

/* Button/interactive */
transition: all 0.3s var(--transition-smooth);

/* Header background */
transition: background 0.4s var(--transition-smooth),
            box-shadow 0.4s var(--transition-smooth);
```

### Fade In Up Animation
```css
@keyframes fadeInUp {
    from {
        opacity: 0;
        transform: translateY(24px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

---

## Buttons

### Primary CTA (Hero)
```css
.hero__cta-btn {
    padding: 20px 48px;
    font-size: 1.25rem;           /* 20px */
    font-weight: 400;
    letter-spacing: -0.01em;
    text-transform: uppercase;
    color: var(--color-text);
    background: transparent;
    border: 1px solid var(--color-text);
    border-radius: 160px;         /* Full pill shape */
}

/* Hover */
.hero__cta-btn:hover {
    background: var(--color-text);
    color: var(--color-white);
}
```

### Header CTA
```css
.header__cta {
    padding: 13px 29px;
    font-size: 0.9rem;            /* 14.4px */
    font-weight: 400;
    letter-spacing: -0.01em;
    text-transform: uppercase;
    border: 1px solid var(--color-text);
    border-radius: 160px;
}
```

### Standard Button
```css
.btn {
    padding: 14px 24px;
    font-size: 0.6875rem;         /* 11px */
    font-weight: 500;
    letter-spacing: 0.1em;
    text-transform: uppercase;
}
```

---

## Component Patterns

### Container
```css
.container {
    max-width: var(--container-width);  /* 1280px */
    margin: 0 auto;
    padding: 0 var(--container-padding);
}
```

### Header
- Fixed position, transparent initially
- Height: 72px (desktop), 52px (tablet), 56px (mobile)
- Scrolled state: `rgba(236, 236, 236, 0.98)` with `backdrop-filter: blur(20px)`

### Feature Cards (Slide Layout)
- Full viewport height (`100vh`)
- 57%/43% grid split (alternates)
- Image spans full height with `object-fit: cover`
- Content padding: `60px 80px` (desktop), `48px` (tablet), `40px` (mobile)

### Footer
- Background: `#595552`
- Padding: `64px 0 38px` (desktop)
- Text color: `var(--color-bg)` (light on dark)
- Links and borders at 20% opacity white

---

## Responsive Breakpoints

```css
/* Tablet Landscape */
@media (max-width: 1024px) { }

/* Tablet Portrait */
@media (max-width: 768px) { }

/* Mobile */
@media (max-width: 480px) { }

/* Small Mobile */
@media (max-width: 360px) { }
```

---

## Text Rendering

```css
html {
    font-size: 16px;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}

body {
    line-height: 1.6;
}
```

---

## Key Design Principles

1. **All caps aesthetic** - Most text is `text-transform: uppercase`
2. **Negative letter-spacing** - Display and heading text uses `-0.01em` to `-0.02em`
3. **Positive letter-spacing** - Small/eyebrow text uses `0.05em` to `0.15em`
4. **Pill-shaped buttons** - Extreme border-radius (`160px`) for rounded buttons
5. **Alternating layouts** - Feature sections alternate image left/right
6. **Full-bleed images** - Images span container edges, full viewport height
7. **Warm neutral palette** - Grays with brown undertones, orange accent
8. **Light weight display** - Hero uses weight 400, headings often 300 or 200
9. **Strong weight for emphasis** - Logo uses 800, titles use 600
