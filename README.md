# Universal Scalable Design Tokens

An enterprise-wide, scalable, description-agnostic master design token system for CSS. This system is based on Material Design 3 principles and provides a comprehensive set of CSS custom properties (variables) that can be customized to match any brand identity.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Getting Started](#getting-started)
- [File Structure](#file-structure)
- [Customization Guide](#customization-guide)
- [Usage Examples](#usage-examples)
- [Token Categories](#token-categories)
- [Best Practices](#best-practices)
- [Contributing](#contributing)

## 🎯 Overview

This design token system provides a complete foundation for building consistent, accessible, and themeable user interfaces. It includes:

- **Color System**: Full palette with light/dark mode support
- **Typography Scale**: Comprehensive type system from display to label sizes
- **Elevation**: Material Design elevation levels
- **Motion**: Animation durations and easing functions
- **Shape**: Border radius tokens for consistent shapes
- **State**: Interaction state layer opacities

## ✨ Features

- 🎨 **Theme Flexibility**: Easy switching between light and dark modes
- 📐 **Scalable System**: Built on CSS custom properties for easy customization
- 🔄 **Description Agnostic**: Token names follow semantic conventions, not specific implementations
- 🎯 **Material Design 3**: Based on Google's latest design system
- 🌐 **Enterprise Ready**: Structured for large-scale applications
- 🧩 **Component Library**: Drop-in UI primitives, patterns, and layouts built from the token system
- ♿ **Accessible**: Built with accessibility best practices
- 🎯 **WCAG 2 Palette**: Ships with high-contrast blues and a vivid accent tuned for readability
- 🧱 **Responsive Grid**: Auto-fit layout utilities that shrink and expand with the viewport

### Default Theme at a Glance

- **GitHub-inspired blue** `#0969da` for primary actions with subtle, accessible styling.
- **Neutral grays** `#24292f`, `#6e7781`, and `#d0d7de` create clean, professional surfaces and borders.
- **Success green** `#1a7f37` for positive feedback and completed states.
- **Semantic feedback** colors: warning `#bf8700` and error `#cf222e`.
- **Responsive layout primitives** (`.ust-container--grid`, `.ust-grid`, `.ust-sidebar-layout`) auto-fit cards, tables, and panels.
- **Clean UI components**—buttons, forms, tables, badges, alerts—pre-styled for GitHub-like admin experiences.
- **Subtle design** with 6px border radius, minimal shadows, and 1px borders for a modern, clean look.

## 🚀 Getting Started

### Basic Setup

1. **Include the master stylesheet** in your HTML:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Application</title>
    
    <!-- Import all design tokens -->
    <link rel="stylesheet" href="path/to/master.css">
    
    <!-- OR import individual token files as needed -->
    <link rel="stylesheet" href="path/to/palette.css">
    <link rel="stylesheet" href="path/to/light.css">
    <link rel="stylesheet" href="path/to/colors.css">
    <link rel="stylesheet" href="path/to/typography.css">
    <link rel="stylesheet" href="path/to/elevation.css">
    <link rel="stylesheet" href="path/to/motion.css">
    <link rel="stylesheet" href="path/to/shape.css">
    <link rel="stylesheet" href="path/to/state.css">
</head>
<body>
    <div class="primary body-large">
        Hello, Design Tokens!
    </div>
</body>
</html>
```

### Quick Example

```html
<button class="primary shape-medium elevation-2">
    <span class="label-large">Click Me</span>
</button>
```

### Component Example

```html
<section class="ust-stack">
  <header class="ust-hero">
    <h1 class="ust-heading-3">Welcome back</h1>
    <p class="ust-paragraph">Here is a snapshot of your product health.</p>
    <div class="ust-cluster ust-cluster--spread">
      <button class="ust-btn ust-btn--primary">Create report</button>
      <button class="ust-btn ust-btn--ghost">Dismiss</button>
    </div>
  </header>

  <div class="ust-dashboard-grid">
    <article class="ust-dashboard-widget">
      <h2 class="title-medium">Active users</h2>
      <p class="display-small">12,480</p>
      <span class="ust-badge ust-badge--success">+8% WoW</span>
    </article>

    <article class="ust-dashboard-widget">
      <h2 class="title-medium">Onboarding completion</h2>
      <progress class="ust-progress" value="72" max="100"></progress>
      <span class="ust-inline-status"><span class="ust-status-dot ust-status-dot--success"></span>72% finished</span>
    </article>
  </div>
</section>
```

## 📁 File Structure

```
Universal-Scalable-Tokens/
├── master.css           # Imports all token files
├── palette.css          # Raw color palette definitions
├── light.css           # Light theme color mappings
├── dark.css            # Dark theme color mappings
├── colors.css          # Color utility classes
├── typography.css      # Font families, sizes, and type scale
├── elevation.css       # Box shadow elevation levels
├── motion.css          # Animation durations and easing
├── shape.css           # Border radius values
├── state.css           # Interaction state opacities
├── components.css      # Prebuilt primitives, components, and patterns
├── example.html        # Live demonstration
└── README.md           # This file
```

## 🎨 Customization Guide

### Customizing Colors

The color system is split into three layers:

#### 1. **palette.css** - Base Color Palette
This is where you define your **raw color values**. Replace these with your brand colors:

```css
:root {
    /* Primary palette - GitHub-inspired blue (#0969da) */
    --md-ref-palette-primary40: #0969da;   /* GitHub primary blue */
    --md-ref-palette-primary80: #80b3ff;   /* Lighter variant */

    /* Secondary palette - Neutral grays (#6e7781) */
    --md-ref-palette-secondary40: #30363d; /* GitHub dark gray */
    --md-ref-palette-secondary60: #6e7781; /* GitHub medium gray */

    /* Tertiary palette - Success green (#1a7f37) */
    --md-ref-palette-tertiary40: #1a7f37;  /* GitHub success green */
    --md-ref-palette-tertiary90: #aff5b4;  /* Light green background */

    /* Error color palette */
    --md-ref-palette-error40: #cf222e;     /* GitHub error red */
}
```

#### 2. **light.css / dark.css** - Theme Mappings
These files map palette colors to semantic tokens. Generally, you won't need to change these unless you want to alter the theme behavior:

```css
:root {
    /* These reference your palette colors */
    --md-sys-color-primary: var(--md-ref-palette-primary40);
    --md-sys-color-secondary: var(--md-ref-palette-secondary40);
    /* ... */
}
```

#### 3. **colors.css** - Utility Classes
These provide ready-to-use CSS classes. No customization needed here.

### Customizing Typography

Edit **typography.css** to match your brand's type system:

```css
:root {
    /* Replace with your font families */
    --md-ref-typeface-plain: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;   /* CUSTOMIZE: GitHub system fonts */
    --md-ref-typeface-brand: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;   /* CUSTOMIZE: Your brand font */
    
    /* Font weights - CUSTOMIZE THESE */
    --md-ref-typeface-weight-bold: 600;    /* GitHub uses 600 for semibold */
    --md-ref-typeface-weight-medium: 500;
    --md-ref-typeface-weight-regular: 400;
    
    /* Adjust font sizes if needed */
    --md-sys-typescale-body-large-size: 16px;   /* CUSTOMIZE */
    --md-sys-typescale-headline-small-size: 24px; /* CUSTOMIZE */
    /* ... more size tokens ... */
}
```

### Customizing Shapes

Edit **shape.css** to adjust border radius values:

```css
:root {
    /* Adjust these for your brand's shape language - GitHub style */
    --md-sys-shape-corner-extra-small-default-size: 2px;   /* CUSTOMIZE: Very subtle */
    --md-sys-shape-corner-small-default-size: 3px;         /* CUSTOMIZE: Minimal */
    --md-sys-shape-corner-medium-default-size: 6px;        /* CUSTOMIZE: GitHub standard */
    --md-sys-shape-corner-large-default-size: 12px;        /* CUSTOMIZE: Emphasized */
    --md-sys-shape-corner-extra-large-default-size: 28px;  /* CUSTOMIZE: Kept same */
}
```

### Customizing Elevation

Edit **elevation.css** to adjust shadow depths:

```css
:root {
    /* Adjust elevation levels */
    --md-sys-elevation-level0: 0px;    /* No elevation */
    --md-sys-elevation-level1: 1px;    /* CUSTOMIZE */
    --md-sys-elevation-level2: 3px;    /* CUSTOMIZE */
    --md-sys-elevation-level3: 6px;    /* CUSTOMIZE */
    --md-sys-elevation-level4: 8px;    /* CUSTOMIZE */
    --md-sys-elevation-level5: 12px;   /* CUSTOMIZE */
}
```

### Customizing Motion

Edit **motion.css** to adjust animation timing:

```css
:root {
    /* Adjust durations to match your brand's motion feel */
    --md-sys-motion-duration-50: 50ms;     /* CUSTOMIZE */
    --md-sys-motion-duration-100: 100ms;   /* CUSTOMIZE */
    --md-sys-motion-duration-200: 200ms;   /* CUSTOMIZE */
    /* ... more durations ... */
}
```

## 💡 Usage Examples

### Colors

```html
<!-- Apply primary color with text -->
<div class="primary">Primary Surface</div>

<!-- Apply secondary color -->
<div class="secondary">Secondary Surface</div>

<!-- Error states -->
<div class="error">Error Message</div>

<!-- Background and surface -->
<div class="surface">Content Surface</div>
```

### Typography

```html
<!-- Display styles (largest) -->
<h1 class="display-large">Display Large</h1>
<h2 class="display-medium">Display Medium</h2>
<h3 class="display-small">Display Small</h3>

<!-- Headline styles -->
<h1 class="headline-large">Headline Large</h1>
<h2 class="headline-medium">Headline Medium</h2>
<h3 class="headline-small">Headline Small</h3>

<!-- Title styles -->
<h4 class="title-large">Title Large</h4>
<h5 class="title-medium">Title Medium</h5>
<h6 class="title-small">Title Small</h6>

<!-- Body text -->
<p class="body-large">Body Large text</p>
<p class="body-medium">Body Medium text</p>
<p class="body-small">Body Small text</p>

<!-- Labels -->
<span class="label-large">Label Large</span>
<span class="label-medium">Label Medium</span>
<span class="label-small">Label Small</span>
```

### Elevation

```html
<!-- Apply elevation shadows -->
<div class="elevation-0">No shadow</div>
<div class="elevation-1">Light shadow</div>
<div class="elevation-2">Raised element</div>
<div class="elevation-3">Card shadow</div>
<div class="elevation-4">Elevated card</div>
<div class="elevation-5">Modal overlay</div>
```

### Shapes

```html
<!-- Apply border radius -->
<div class="shape-none">No rounding</div>
<div class="shape-extra-small">4px radius</div>
<div class="shape-small">8px radius</div>
<div class="shape-medium">12px radius</div>
<div class="shape-large">16px radius</div>
<div class="shape-extra-large">28px radius</div>

<!-- Special shapes -->
<div class="extra-small-top">Rounded top only</div>
<div class="large-top">Large rounded top</div>
<div class="large-end">Rounded right side</div>
```

### Motion

```html
<!-- Apply animation durations -->
<div class="duration-200 easing-standard">Quick transition</div>
<div class="duration-400 easing-emphasized">Standard transition</div>
<div class="duration-600 easing-standard">Slower transition</div>

<!-- Different easing functions -->
<div class="duration-300 easing-linear">Linear motion</div>
<div class="duration-300 easing-standard-accelerate">Accelerating</div>
<div class="duration-300 easing-standard-decelerate">Decelerating</div>
```

### State Layers

```html
<!-- Apply interaction state opacities -->
<div class="hover-state-layer">Hover effect</div>
<div class="pressed-state-layer">Pressed effect</div>
<div class="focus-state-layer">Focus effect</div>
<div class="dragged-state-layer">Drag effect</div>
```

### Combining Classes

```html
<!-- Button with multiple token classes -->
<button class="primary shape-medium elevation-2 label-large">
    Primary Button
</button>

<!-- Card component -->
<article class="surface shape-large elevation-1">
    <h2 class="headline-small">Card Title</h2>
    <p class="body-medium">Card content with proper typography.</p>
</article>
```

## 🎯 Token Categories

### Color Tokens

- **Primary**: Main brand color for primary actions
- **Secondary**: Secondary brand color for complementary elements
- **Tertiary**: Accent color for highlights
- **Error**: Error states and destructive actions
- **Background**: Page backgrounds
- **Surface**: Component surfaces
- **Outline**: Borders and dividers

### Typography Tokens

- **Display**: Largest text (display-large, display-medium, display-small)
- **Headline**: Page and section headers (headline-large, headline-medium, headline-small)
- **Title**: Subsection headers (title-large, title-medium, title-small)
- **Body**: Paragraph text (body-large, body-medium, body-small)
- **Label**: UI labels and buttons (label-large, label-medium, label-small)

### Elevation Tokens

- **Level 0**: Flat, no shadow
- **Level 1**: Subtle elevation (1px)
- **Level 2**: Raised elements (3px)
- **Level 3**: Cards and panels (6px)
- **Level 4**: Elevated cards (8px)
- **Level 5**: Modals and overlays (12px)

### Motion Tokens

- **Duration**: 50ms to 1000ms in various increments
- **Easing**: standard, linear, emphasized, accelerate, decelerate

### Shape Tokens

- **None**: 0px (square corners)
- **Extra Small**: 4px
- **Small**: 8px
- **Medium**: 12px
- **Large**: 16px
- **Extra Large**: 28px

## 🧱 Component Library Overview

`components.css` composes the design tokens into ready-to-use patterns that cover entire application flows. The library is grouped into seven families so you can mix and match what you need:

1. **Base elements** – typographic helpers, buttons, inputs, lists, tables, badges, tooltips, avatars, progress indicators, and utilities such as `ust-stack`, `ust-cluster`, and `ust-divider`.
2. **Composite components** – cards, panels, tabs, accordions, menus, alerts/toasts, breadcrumbs, pagination, steppers, search bars, pickers, upload zones, ratings, navigation shells, empty states, and more.
3. **Form patterns** – grid and inline form layouts, reusable `ust-field` wrappers, inline editing, and autosave/confirmation affordances.
4. **Feedback patterns** – popovers, snackbars, banners, status messages, and loading overlays.
5. **Layout primitives** – responsive containers, grids, masonry clusters, split panes, app shells, hero blocks, and content lists.
6. **Complex templates** – search & filter panels, dashboard widgets, rich data tables, authentication cards, settings panels, comment threads, chat bubbles, file viewers, workflow trackers, and onboarding tours.
7. **System-level components** – theme toggles, language switchers, skip links, command palettes, notification centers, user menus, help widgets, and keyboard shortcut legends.

Each component is theme aware, keyboard navigable, and built with token-driven spacing, shape, and color so it snaps to your brand automatically.

## 📚 Best Practices

### 1. Use Semantic Tokens

Always use semantic tokens (e.g., `--md-sys-color-primary`) rather than palette tokens (e.g., `--md-ref-palette-primary40`) in your application code:

```css
/* ✅ Good */
.my-button {
    background-color: var(--md-sys-color-primary);
}

/* ❌ Avoid */
.my-button {
    background-color: var(--md-ref-palette-primary40);
}
```

### 2. Theme Switching

To switch themes, simply swap the light.css and dark.css imports:

```html
<!-- Light theme (default) -->
<link rel="stylesheet" href="light.css">

<!-- Dark theme -->
<link rel="stylesheet" href="dark.css">
```

Or use JavaScript for dynamic switching:

```javascript
const themeLink = document.getElementById('theme');
function toggleTheme() {
    const isDark = themeLink.href.includes('dark.css');
    themeLink.href = isDark ? 'light.css' : 'dark.css';
}
```

### 3. Combine with Custom CSS

Use tokens as the foundation and build custom components:

```css
.custom-card {
    background-color: var(--md-sys-color-surface);
    border-radius: var(--md-sys-shape-corner-large-default-size);
    box-shadow: var(--md-sys-elevation-level2);
    padding: 16px;
    transition-duration: var(--md-sys-motion-duration-200);
}

.custom-card:hover {
    box-shadow: var(--md-sys-elevation-level4);
}
```

### 4. Maintain Consistency

- Use the same token for the same purpose across your application
- Don't create arbitrary values; extend the token system if needed
- Document any custom tokens you create

### 5. Accessibility

The token system provides accessible color contrasts by default. When customizing:
- Ensure sufficient contrast between text and backgrounds (WCAG AA minimum)
- Test both light and dark themes
- Use semantic HTML with utility classes

## 🤝 Contributing

To contribute to this design token system:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly in both light and dark modes
5. Submit a pull request

## 📄 License

See the LICENSE file for details.

---

**Ready to get started?** Check out the `example.html` file for a live demonstration of all tokens in action!