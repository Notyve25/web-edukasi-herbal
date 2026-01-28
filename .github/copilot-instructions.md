# Nutri Herbal Web Project - AI Coding Guidelines

## Project Overview
**web-edukasi-herbal** is an educational web platform about herbal nutrition (Nutri Herbal). It provides information, videos, and interactive features about herbal medicines and their health benefits. The site is primarily in Indonesian.

## Architecture

### Multi-Page Structure
- **awal.html**: Landing/home page with hero section, features, and call-to-action
- **index.html**: Information page with detailed content about herbal products
- **form.html**: Registration form for participants with image upload capability
- **Videoedukasi.html / vid.html**: Video education pages
- **grafik.html**: Charts/graphics page (referenced in navigation)
- **style.css**: Global styles (external stylesheet)

### Technology Stack
- **Frontend Framework**: Bootstrap 5.3.6 (CDN-based)
- **Icons**: Font Awesome 6.7.2 (CDN)
- **Animations**: Animate.css 4.1.1 (CDN)
- **Styling**: Custom CSS with CSS variables for theming
- **No Build Tool**: Plain HTML/CSS/JS - files served directly

## Design Patterns & Color Scheme

### Color System (CSS Variables)
- **Primary**: `#28a745` (green) - main brand color
- **Secondary**: `#1ec3ff` (cyan/blue) - accent color
- **Gradient**: Linear gradient from secondary to primary (120deg)
- **Background**: `#f0f4f8` / `#f8f9f9` (light gray)

### Consistent Elements Across Pages
1. **Navbar Pattern**: Dark green (`bg-success`) with Font Awesome icons and dropdown menus
2. **Navigation Links**: Icon + text format (e.g., `<i class="fa-solid fa-home"></i> Beranda`)
3. **Dropdown Structure**: Always uses `dropdown-menu-end` for right alignment
4. **Card Components**: `border: none`, `border-radius: 16px`, box shadows for depth
5. **Buttons**: Gradient backgrounds, hover scale/transform effects, smooth transitions

### Interactive Patterns
- **CTA Buttons**: Use gradient background with pulse animation on load, scale on hover
- **Image Hover Effects**: Transform (scale/rotate), box-shadow changes
- **Form Elements**: Gradient headers, custom focus states with color from `--primary-color`
- **Fixed Elements**: WhatsApp floating button positioned `fixed bottom-24px right-24px`

## Key Developer Workflows

### File Organization
- All HTML files in root directory
- Single external stylesheet `style.css` for shared styles
- Inline `<style>` blocks for page-specific overrides
- Assets (images) stored in root with descriptive names (e.g., `air-jahe.jpeg`, `herbal.jpg`)

### Common Patterns When Adding Pages
1. Copy navbar structure from existing pages (awal.html or form.html show pattern)
2. Link Bootstrap and Font Awesome CDN in `<head>`
3. Define page-specific styles in inline `<style>` block
4. Use CSS variables from form.html pattern if consistent theming needed
5. Update navigation dropdowns in all pages to reflect new pages

### Image Handling
- Hero sections use background images (e.g., `herbal.jpg`, `penyakit-hipertensi.jpg`)
- Product/feature images use `<img>` tags with border-radius and shadows
- Responsive images use `max-width: 100%` and `height: auto`

### Responsive Design
- Mobile breakpoints at `768px` and `576px` (Bootstrap conventions)
- Hero sections: `min-height: 300px` on mobile, full viewport on desktop
- Gap/padding adjustments for smaller screens (see awal.html institusi-logos)
- Navbar uses Bootstrap's `navbar-toggler` for mobile menu collapse

## Naming & Conventions

### CSS Class Naming
- Uses descriptive kebab-case (e.g., `cta-button`, `hero-overlay`, `institusi-section`)
- Pattern: `[component]-[element]` (e.g., `.whatsapp-float a`, `.institusi-logo`)
- Reusable classes defined once in `style.css` or inline style blocks

### HTML Conventions
- Indonesian language labels (`lang="id"`)
- Semantic structure with `<header>`, `<main>`, `<nav>`, `<section>` when applicable
- Font Awesome icons always wrapped in `<i>` tags with full class path

### Content Language
- Primary language is Indonesian (ID)
- Use existing terminology from pages: "Beranda" (home), "Informasi" (info), "Video Edukasi" (educational videos), "Pilihan" (options)

## Critical Integration Points

### Navigation System
All pages include standardized navbar with these links:
- Beranda (awal.html)
- Informasi (index.html)
- Video Edukasi (vid.html or Videoedukasi.html)
- Pilihan dropdown → grafik.html, form.html

**When updating navigation**: Update the navbar in ALL HTML files to maintain consistency.

### Form Implementation (form.html reference)
- Card-based layout with gradient header
- Input groups with Font Awesome icons for visual context
- Image preview functionality with `display: none` toggle
- Submit button with spinner feedback state
- Uses Bootstrap form classes with custom focus styling

### External Dependencies
- All scripts loaded from CDN (no local node_modules)
- Bootstrap JS included via CDN for navbar toggler functionality
- No build compilation needed - direct browser execution

## Notes for AI Agents

1. **Consistency is Critical**: The site uses uniform navbar, button styling, and card patterns. Changes to one page should cascade to all pages.
2. **No JavaScript Logic Found Yet**: Pages appear to be static/presentation. Verify before adding interactivity.
3. **Mobile-First Approach**: Always test responsive breakpoints when adding new elements.
4. **Keep It Simple**: No build tools or package management. Avoid introducing complexity.
5. **CDN Dependencies**: All external resources use CDN URLs. Ensure integrity hashes are consistent when updating libraries.
