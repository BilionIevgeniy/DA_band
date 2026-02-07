# Copilot Instructions - DA_band

## Project Overview

**DA_band** is a band website landing page showcasing "Rock Mountain" band. The site features a hero section, navigation menu, and category cards for News, Album, and Store.

## Architecture & Structure

### File Organization

- `index.html` - Single-page layout with semantic sections
- `styles/reset.css` - Base reset and form element defaults
- `styles/index.css` - Main styles using CSS nesting (imports reset.css)
- `assets/img/` - All image assets (logo, header background, category images, social icons)

### Layout Pattern

- **Container system**: Max-width 1440px, centered with horizontal padding (100px each side)
- **Sections**: `.header`, `.categories` (main structural containers)
- **Flexbox-first**: All major layout uses `display: flex` for alignment

## Styling Conventions

### CSS Architecture

1. **Reset First**: reset.css removes default margins/padding, sets smooth scrolling, normalizes inputs
2. **Nested Selectors**: Uses CSS nesting (modern syntax) - no preprocessor required
3. **No responsive breakpoints yet**: Current design is desktop-optimized; mobile styles should use media queries

### Design System

- **Primary Color**: `#AF8548` (gold/bronze accent)
- **Background**: `#000` (black for sections, image backgrounds for header)
- **Text**: `#fff` (white on dark backgrounds)
- **Fonts**:
  - Body: 'PT Sans' (400/700 weights, regular/italic)
  - Headlines: 'Viga' (imported from Google Fonts)

### Component Patterns

```scss
// Hover states use color shift or transform
&:hover {
  background-color: #e2b46f; // Lighter gold
  transform: scale(1.01); // Subtle zoom
  filter: drop-shadow(0px 0px 4px #fff); // Glow effect on icons
}
```

## Key Implementation Rules

### When Adding Sections

1. Wrap in a `<section class="section-name">` with a `.container` div
2. Use consistent padding (80px shown in .categories)
3. Import/reference assets from `./assets/img/`

### Images

- Store all in `assets/img/` directory
- Use relative paths: `./assets/img/filename.png`
- Add descriptive alt text for accessibility
- Use background-image for full-width hero sections

### Typography

- Headings use Viga font (imported in index.css)
- Body text: PT Sans, 20px default for navigation
- Text sizing: Absolute px values (no rem/em for now)
- Uppercase transforms: Use `text-transform: uppercase;` on links/buttons

## Common Workflows

### Adding a New Section

1. Add `<section class="new-section">` before closing body tag
2. Create corresponding CSS under `.new-section` in index.css
3. Use `.container` wrapper for content alignment
4. Follow existing hover/interaction patterns

### Updating Colors

- All gold references: `#AF8548` (primary) or `#e2b46f` (hover)
- Maintain contrast for white text on backgrounds
- Social icons maintain original white; add filter glow on hover

## Browser Compatibility Notes

- **CSS Nesting**: Modern browsers only (Chrome 112+, Safari 16.5+, Firefox 117+)
- **100dvh**: Dynamic viewport height; consider `100vh` for older browsers
- **Google Fonts**: Requires internet connection; hosted via CDN

## External Dependencies

- Google Fonts (PT Sans, Viga) - loaded synchronously in head
- No external JS frameworks
- Images are critical assets for visual design

## Accessibility Considerations

- Navigation links are semantic `<nav>` element
- Image alt text present for content images
- Background images should have fallback color
- Text contrast: White on dark backgrounds meets WCAG AA
