# CSS Variables & Utilities Documentation

## Overview
This website now uses a comprehensive CSS variable system that allows for easy color management and consistent styling across the entire site. All colors are centralized using CSS custom properties (variables) to eliminate redundancy and make theme changes simple.

## CSS Variable System

### Dark Mode Color Variables
Located in `assets/css/main.css`, these variables control the dark theme:

```css
/* Primary Colors */
--dark-bg-primary: #000000        /* Main background (pure black) */
--dark-bg-secondary: #111111      /* Secondary background (dark grey) */
--dark-bg-tertiary: #1a1a1a       /* Card/component backgrounds */

/* Text Colors */
--dark-text-primary: #ffffff      /* Main text (white) */
--dark-text-secondary: #e0e0e0    /* Secondary text (light grey) */
--dark-text-muted: #b0b0b0        /* Muted text */

/* Accent Colors */
--dark-accent-primary: #008080    /* Main accent (teal) */
--dark-accent-secondary: #50a3a3  /* Light accent */

/* Borders & Strokes */
--dark-border-primary: #333333    /* Border color */
--dark-border-secondary: #666666  /* Secondary borders */
--dark-stroke-color: #666666      /* Text stroke color */
--dark-stroke-width: 1.5px        /* Text stroke width */

/* Overlays */
--dark-overlay: rgba(0, 0, 0, 0.95)      /* Dark overlay */
--dark-overlay-light: rgba(0, 0, 0, 0.8) /* Light overlay */
```

### Quick Access Variables
Located in `assets/css/utilities.css`, these provide shortcuts:

```css
--color-primary: var(--dark-bg-primary)
--color-accent: var(--dark-accent-primary)
--color-text: var(--dark-text-primary)
/* etc. */
```

## Using CSS Variables

### In CSS Files
```css
.my-element {
  background-color: var(--color-primary);
  color: var(--color-text);
  border: 1px solid var(--color-border);
}
```

### Changing Theme Colors
To change the entire website's color scheme, simply modify the variables in `main.css`:

```css
/* Example: Change from black to dark blue theme */
--dark-bg-primary: #001122;      /* Instead of #000000 */
--dark-accent-primary: #0099cc;  /* Instead of #008080 */
```

## Utility Classes

### Background Colors
- `.bg-primary` - Primary background color
- `.bg-secondary` - Secondary background color
- `.bg-tertiary` - Tertiary background color
- `.bg-accent` - Accent background color
- `.bg-white` - White background
- `.bg-black` - Black background
- `.bg-transparent` - Transparent background

### Text Colors
- `.text-primary` - Primary text color
- `.text-secondary` - Secondary text color
- `.text-accent` - Accent text color
- `.text-white` - White text
- `.text-black` - Black text
- `.text-muted` - Muted text

### Spacing
- `.m-xs`, `.m-sm`, `.m-md`, `.m-lg`, `.m-xl` - Margin utilities
- `.p-xs`, `.p-sm`, `.p-md`, `.p-lg`, `.p-xl` - Padding utilities
- `.mt-md`, `.mb-lg`, `.pt-sm`, `.pb-xl` - Directional spacing

### Layout
- `.flex-center` - Center content with flexbox
- `.flex-between` - Space between with flexbox
- `.text-center` - Center text
- `.w-100`, `.h-100` - Full width/height

### Special Effects
- `.text-stroke` - Outlined text effect (like section titles)
- `.text-stroke-white` - White outlined text
- `.text-stroke-accent` - Accent colored outlined text
- `.hover-scale` - Scale on hover
- `.hover-opacity` - Opacity change on hover

### Custom Components
- `.btn-custom` - Custom styled button
- `.btn-outline` - Outline button
- `.card-dark` - Dark themed card component

## Examples

### Creating a New Section with Consistent Styling
```html
<section class="bg-primary text-primary p-xl">
  <div class="flex-center flex-column">
    <h2 class="text-stroke mb-lg">My Title</h2>
    <p class="text-secondary text-center">Description text</p>
    <a href="#" class="btn-custom mt-md">Call to Action</a>
  </div>
</section>
```

### Custom Card Component
```html
<div class="card-dark">
  <h3 class="text-accent mb-md">Card Title</h3>
  <p class="text-secondary">Card content goes here</p>
  <button class="btn-outline mt-md">Learn More</button>
</div>
```

## Best Practices

### 1. Use Variables Instead of Hard-coded Colors
❌ **Don't do this:**
```css
.my-element {
  background-color: #000000;
  color: #ffffff;
}
```

✅ **Do this:**
```css
.my-element {
  background-color: var(--color-primary);
  color: var(--color-text);
}
```

### 2. Use Utility Classes for Common Styles
❌ **Don't do this:**
```html
<div style="background-color: #000000; padding: 1rem; text-align: center;">
```

✅ **Do this:**
```html
<div class="bg-primary p-md text-center">
```

### 3. Create New Variables for New Colors
When adding new colors, add them to the CSS variables:
```css
:root {
  --my-custom-color: #ff6b6b;
  --my-custom-bg: #2c3e50;
}
```

### 4. Follow Naming Conventions
- Use descriptive names: `--color-success` instead of `--green`
- Follow the existing pattern: `--dark-bg-*`, `--color-*`, etc.
- Use consistent naming: primary, secondary, tertiary, accent

## File Structure
```
assets/css/
├── main.css        # Main styles + dark mode variables & styles
├── utilities.css   # Utility classes + quick access variables
└── spacing.css     # Original spacing utilities
```

## Making Global Changes

### Changing the Accent Color
1. Open `assets/css/main.css`
2. Find `--dark-accent-primary: #008080;`
3. Change to your desired color: `--dark-accent-primary: #ff6b6b;`
4. The entire site will update automatically

### Adding a New Color Scheme
1. Add new variables in `main.css`:
```css
--my-theme-primary: #your-color;
--my-theme-secondary: #your-color;
```
2. Add utility classes in `utilities.css`:
```css
.bg-my-theme { background-color: var(--my-theme-primary) !important; }
.text-my-theme { color: var(--my-theme-primary) !important; }
```

This system ensures consistency, maintainability, and easy customization across your entire website.
