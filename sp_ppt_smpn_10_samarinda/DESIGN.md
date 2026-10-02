---
name: SP-PPT SMPN 10 Samarinda
colors:
  surface: '#101415'
  surface-dim: '#101415'
  surface-bright: '#363a3b'
  surface-container-lowest: '#0b0f10'
  surface-container-low: '#191c1e'
  surface-container: '#1d2022'
  surface-container-high: '#272a2c'
  surface-container-highest: '#323537'
  on-surface: '#e0e3e5'
  on-surface-variant: '#c8c5d0'
  inverse-surface: '#e0e3e5'
  inverse-on-surface: '#2d3133'
  outline: '#928f9a'
  outline-variant: '#47464f'
  surface-tint: '#c4c1fb'
  primary: '#c4c1fb'
  on-primary: '#2d2a5b'
  primary-container: '#1e1b4b'
  on-primary-container: '#8683ba'
  inverse-primary: '#5b598c'
  secondary: '#ffb77d'
  on-secondary: '#4d2600'
  secondary-container: '#d97707'
  on-secondary-container: '#432100'
  tertiary: '#b4c5ff'
  on-tertiary: '#002a78'
  tertiary-container: '#001d58'
  on-tertiary-container: '#5382ff'
  error: '#ffb4ab'
  on-error: '#690005'
  error-container: '#93000a'
  on-error-container: '#ffdad6'
  primary-fixed: '#e3dfff'
  primary-fixed-dim: '#c4c1fb'
  on-primary-fixed: '#181445'
  on-primary-fixed-variant: '#444173'
  secondary-fixed: '#ffdcc3'
  secondary-fixed-dim: '#ffb77d'
  on-secondary-fixed: '#2f1500'
  on-secondary-fixed-variant: '#6e3900'
  tertiary-fixed: '#dbe1ff'
  tertiary-fixed-dim: '#b4c5ff'
  on-tertiary-fixed: '#00174b'
  on-tertiary-fixed-variant: '#003ea8'
  background: '#101415'
  on-background: '#e0e3e5'
  surface-variant: '#323537'
typography:
  headline-xl:
    fontFamily: Plus Jakarta Sans
    fontSize: 36px
    fontWeight: '700'
    lineHeight: 44px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 28px
    fontWeight: '600'
    lineHeight: 36px
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 22px
    fontWeight: '600'
    lineHeight: 28px
  headline-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 18px
    fontWeight: '600'
    lineHeight: 24px
  body-lg:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  body-md:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  body-sm:
    fontFamily: Inter
    fontSize: 13px
    fontWeight: '400'
    lineHeight: 18px
  label-md:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '500'
    lineHeight: 16px
    letterSpacing: 0.05em
  label-sm:
    fontFamily: Inter
    fontSize: 11px
    fontWeight: '500'
    lineHeight: 14px
    letterSpacing: 0.05em
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  gutter: 1.5rem
  margin: 2rem
  space-xs: 0.25rem
  space-sm: 0.5rem
  space-md: 1rem
  space-lg: 1.5rem
  space-xl: 2.5rem
---

## Brand & Style

This design system establishes a sophisticated, authoritative, yet deeply artistic visual identity tailored for a theatrical production assessment platform. The emotional response bridges academic precision with dramatic elegance—evoking the solemnity of a classical stage, the focus of a director's rehearsal, and the prestige of a live performance.

We adopt a **Corporate / Modern** framework infused with subtle **Glassmorphism** accents for floating navigational elements. The aesthetic relies on high-contrast clarity, rich jewel tones, and structured layout grids to ensure high-stakes evaluations remain objective, legible, and visually striking.

## Colors

The color palette is anchored by Deep Indigo (`#1E1B4B`) as the primary foundational canvas, establishing a moody, theatrical atmosphere. Rich Gold (`#D97706` / `#F59E0B`) serves as the distinguished accent for leadership, directors, and critical performance highlights. Royal Blue (`#2563EB`) acts as the functional secondary tone for coordinators and active operational states. Slate and Cream provide high-contrast, glare-free readability across cards and data-dense evaluation tables.

## Typography

Typography balances geometric artistic presence in headings with utilitarian legibility in dense scoring tables. Plus Jakarta Sans drives all structural headlines with a welcoming yet authoritative stance, while Inter maintains crisp data rendering across mobile and desktop viewports. Ensure all large text blocks scale down cleanly on viewports below 768px.

## Layout & Spacing

A **fluid 12-column grid** underpins the interface, allowing complex assessment matrices and performance logs to scale gracefully from mobile viewports to ultra-wide desktop monitors. Spacing adheres to an 8px base rhythm. Outer margins collapse gracefully on small screens, preserving safe boundaries for touch targets.

## Elevation & Depth

Depth is articulated through **tonal layers** paired with low-opacity ambient shadows tinted in Deep Indigo. Floating action panels and evaluation cards leverage soft, multi-layered elevation to lift critical interactive components above the deep background canvas, creating an immersive, stage-like perspective.

## Shapes

We implement a balanced **Rounded** shape language (`0.5rem` base, `1rem` for cards, `1.5rem` for prominent containers). This softens the stark industrial feel of traditional database UI, lending an approachable, contemporary finish suitable for an educational yet creative environment.

## Components

- **Buttons:** Solid primary triggers utilize Rich Gold for leadership actions and Royal Blue for coordinator workflows. Ghost and outlined variants maintain crisp borders and clear focus rings.
- **Chips & Badges:** Color-coded hierarchy (Gold for Directors/Sutradara, Blue for Coordinators, Slate for general crew/observers) to instantly communicate user roles and assessment status.
- **Cards:** Modern, elevated containers featuring subtle borders, high-contrast typography, and clear grid alignment for individual performance evaluations.
- **Input Fields:** Generous touch targets with clear floating labels, focused glowing borders, and immediate validation feedback.
- **Lists & Tables:** Dense, alternating-row data grids optimized for real-time scoring input during live theatrical rehearsals.
- **Checkboxes & Radios:** Custom-styled indicators with clear checked states matching the active role color scheme.