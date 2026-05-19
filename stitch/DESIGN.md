---
name: Ticket Loom
colors:
  surface: '#f7f9fb'
  surface-dim: '#d8dadc'
  surface-bright: '#f7f9fb'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f2f4f6'
  surface-container: '#eceef0'
  surface-container-high: '#e6e8ea'
  surface-container-highest: '#e0e3e5'
  on-surface: '#191c1e'
  on-surface-variant: '#434655'
  inverse-surface: '#2d3133'
  inverse-on-surface: '#eff1f3'
  outline: '#737686'
  outline-variant: '#c3c6d7'
  surface-tint: '#0053db'
  primary: '#004ac6'
  on-primary: '#ffffff'
  primary-container: '#2563eb'
  on-primary-container: '#eeefff'
  inverse-primary: '#b4c5ff'
  secondary: '#515f74'
  on-secondary: '#ffffff'
  secondary-container: '#d5e3fc'
  on-secondary-container: '#57657a'
  tertiary: '#943700'
  on-tertiary: '#ffffff'
  tertiary-container: '#bc4800'
  on-tertiary-container: '#ffede6'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#dbe1ff'
  primary-fixed-dim: '#b4c5ff'
  on-primary-fixed: '#00174b'
  on-primary-fixed-variant: '#003ea8'
  secondary-fixed: '#d5e3fc'
  secondary-fixed-dim: '#b9c7df'
  on-secondary-fixed: '#0d1c2e'
  on-secondary-fixed-variant: '#3a485b'
  tertiary-fixed: '#ffdbcd'
  tertiary-fixed-dim: '#ffb596'
  on-tertiary-fixed: '#360f00'
  on-tertiary-fixed-variant: '#7d2d00'
  background: '#f7f9fb'
  on-background: '#191c1e'
  surface-variant: '#e0e3e5'
typography:
  headline-lg:
    fontFamily: Inter
    fontSize: 20px
    fontWeight: '600'
    lineHeight: 28px
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '600'
    lineHeight: 24px
    letterSpacing: -0.01em
  headline-sm:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '600'
    lineHeight: 20px
  body-lg:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  body-md:
    fontFamily: Inter
    fontSize: 13px
    fontWeight: '400'
    lineHeight: 18px
  body-sm:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
  label-md:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '500'
    lineHeight: 16px
    letterSpacing: 0.02em
  label-sm:
    fontFamily: Inter
    fontSize: 11px
    fontWeight: '600'
    lineHeight: 14px
    letterSpacing: 0.03em
  code:
    fontFamily: jetbrainsMono
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
rounded:
  sm: 0.125rem
  DEFAULT: 0.25rem
  md: 0.375rem
  lg: 0.5rem
  xl: 0.75rem
  full: 9999px
spacing:
  base: 4px
  xs: 4px
  sm: 8px
  md: 12px
  lg: 16px
  xl: 24px
  gutter: 16px
  sidebar_width: 240px
  control_height: 32px
---

## Brand & Style

The design system is engineered for high-velocity service environments where information density and clarity are paramount. The brand personality is **precise, reliable, and unobtrusive**, acting as a silent partner to the support professional. 

The aesthetic follows a **Corporate / Modern** movement with a heavy emphasis on **Functional Minimalism**. Every pixel is a utility; decorative elements are stripped away in favor of structural clarity and rapid scannability. The "dense but calm" atmosphere is achieved through a rigorous adherence to a tight mathematical grid, low-contrast UI chrome, and a sophisticated, desaturated color palette that prevents cognitive fatigue during long work sessions.

## Colors

The color system utilizes a sophisticated range of cool grays and deep slates to create a stable, professional environment. 

- **Primary Action Blue:** Used sparingly for primary call-to-actions and active states to guide the eye without overwhelming it.
- **Surface & Chrome:** The UI uses a "layered gray" approach. Backgrounds are kept at the lightest neutral, while sidebars and headers use subtle slate shifts to create boundaries without heavy lines.
- **Semantic Status:** Success, Warning, and Error colors are used for critical feedback. These are paired with 10% opacity background tints (e.g., a desaturated soft red background for error states) to ensure high scannability of ticket statuses while maintaining the "calm" aesthetic.

## Typography

This design system employs a crisp, systematic type scale designed for maximum legibility in data-heavy contexts. By utilizing **Inter**, we benefit from its tall x-height and excellent clarity at small sizes.

Hierarchy is established through **font weight (Medium/SemiBold)** and **color (Slate-900 vs Slate-500)** rather than dramatic size shifts. The scale is compressed, rarely exceeding 20px, to ensure that the maximum amount of "ticket data" is visible above the fold. Monospaced fonts are used for ticket IDs and technical logs to provide a distinct visual break from prose.

## Layout & Spacing

The layout philosophy is based on a **strict 4px/8px grid system**. It utilizes a **fixed sidebar** for primary navigation and a **fluid content area** that adapts to the browser width, optimized for multi-pane "split-screen" workflows.

- **High Density:** Padding within table cells and list items is kept to a minimum (8px horizontal, 4px vertical) to maximize the "row count" per screen.
- **Grid:** Use a 12-column grid for complex forms, but default to flexbox-based layouts for ticket feeds.
- **Breakpoints:**
  - **Desktop (1280px+):** Full multi-pane view (Sidebar + List + Detail).
  - **Tablet (768px - 1279px):** Sidebar collapses to icons; List and Detail panes remain.
  - **Mobile (<767px):** Single pane view with bottom navigation bar.

## Elevation & Depth

To maintain a flat, professional profile, this design system avoids heavy drop shadows. Depth is communicated primarily through **Tonal Layering** and **1px Borders**.

- **Level 0 (Background):** The main canvas, typically the lightest gray (#F8FAFC).
- **Level 1 (Card/Surface):** White (#FFFFFF) surfaces with a 1px border (#E2E8F0).
- **Level 2 (Popovers/Modals):** These use a minimal, crisp shadow (0px 4px 6px -1px rgba(0,0,0,0.1)) to lift the element off the canvas without breaking the clean aesthetic.
- **Active State:** Focus states use a 2px outer glow in the primary blue at 20% opacity.

## Shapes

The shape language is **geometric and disciplined**. A consistent **4px radius (Soft)** is applied to all components—buttons, input fields, and cards. This small radius provides a hint of approachability while maintaining a structured, professional appearance that aligns with the 4px grid. 

- **Interactive Elements:** Buttons and Inputs use the 4px radius.
- **Status Pills:** Use a fully rounded (pill) shape to distinguish them clearly from interactive buttons.
- **Selection Brackets:** Active list items use a 2px vertical "accent bar" on the left edge rather than rounded corners to indicate selection.

## Components

### Buttons & Inputs
- **Height:** Standardized at 32px for high density; 36px for "large" primary actions.
- **Input Fields:** 1px Slate-200 borders, transitioning to Primary Blue on focus. Labels are always "Top-aligned" and use the `label-sm` style for maximum space-saving.

### Status Badges (Chips)
- Compact, non-interactive indicators using `label-sm`. 
- They feature a desaturated background (10% opacity) and high-contrast text (900-weight equivalent color) of the same hue for instant recognition.

### Data Tables & Lists
- **Row Height:** 40px for standard rows.
- **Hover State:** Subtle Slate-50 background shift.
- **Dividers:** 1px solid Slate-100; avoid dividers if tonal shifts provide enough separation.

### Cards
- Minimalist containers with no shadow; defined by a 1px Slate-200 border. 
- Padding inside cards is strictly 12px or 16px.

### Sidebar Navigation
- Dark Slate (#1E293B) or Light Slate (#F1F5F9) background. 
- Icons are 18px, paired with `body-md` (Medium weight) text. Active states are indicated by a subtle background "pill" or a left-hand accent bar.