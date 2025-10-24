# Image Organization Guide

## Directory Structure

```
public/images/
├── hero/           - Hero section backgrounds
├── about/          - Profile photos, credentials
├── services/       - Service illustrations/icons
├── testimonials/   - Client photos (with permission)
└── misc/           - Other images
```

## Image Guidelines

### File Naming
- Use descriptive kebab-case: `alina-profile-headshot.jpg`
- Include size suffix: `hero-desktop.jpg`, `hero-mobile.jpg`
- Avoid: `IMG_1234.jpg`, `image1.jpg`

### Optimization
- **Format**: WebP preferred (fallback to JPG/PNG)
- **Hero images**: Max 1920px width, 80% quality
- **Profile photos**: Max 800px width
- **Thumbnails**: Max 400px width
- **Icons**: Use SVG when possible

### Recommended Sizes
- **Hero**: 1920x1080 (desktop), 768x1024 (mobile)
- **Profile**: 800x800 or 600x900
- **Testimonial avatars**: 200x200
- **Service cards**: 600x400

### Tools
- [TinyPNG](https://tinypng.com/) - Quick compression
- [Squoosh](https://squoosh.app/) - Advanced optimization
- [SVGOMG](https://jakearchibald.github.io/svgomg/) - SVG optimization

## Usage in Astro

### Basic image:
```astro
<img src="/images/hero/main-hero.jpg" alt="Descriptive text" />
```

### Responsive image:
```astro
<picture>
  <source srcset="/images/hero/main-hero-mobile.webp" media="(max-width: 768px)" type="image/webp" />
  <source srcset="/images/hero/main-hero-desktop.webp" media="(min-width: 769px)" type="image/webp" />
  <img src="/images/hero/main-hero-desktop.jpg" alt="Descriptive text" />
</picture>
```

### With Astro Image component (for auto-optimization):
```astro
---
import { Image } from 'astro:assets';
import heroImg from '../../public/images/hero/main-hero.jpg';
---
<Image src={heroImg} alt="Descriptive text" width={1920} height={1080} />
```
