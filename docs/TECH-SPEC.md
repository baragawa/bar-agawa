# Bar Agawa — Specyfikacja Techniczna

## Rekomendacja: Static HTML + CSS (zero dependencies)

### Uzasadnienie
| Kryterium | Decyzja | Dlaczego |
|-----------|---------|----------|
| Utrzymanie | Zero maintenance | Właściciel nie jest techniczny |
| Szybkość | Static = najszybsze | Brak JS framework, brak hydration |
| Hosting | Cloudflare Pages (free) | CDN globalny, SSL auto, custom domain |
| Skala | Nie potrzebna | 50-200 wizyt/miesiąc max |
| CMS | Nie potrzebny | Treść zmienia się 1-2x/rok (edycja HTML ręcznie lub przez nas) |
| Framework | Nie potrzebny | 1 strona + 1 podstrona. Overhead > benefit |

### Alternatywy rozważone i odrzucone
| Opcja | Odrzucenie |
|-------|-----------|
| WordPress | Overkill, wymaga hostingu, aktualizacji, pluginów, podatny na ataki |
| Wix/Squarespace | Płatny (lub reklamy), wolniejszy, mniej kontroli SEO |
| Astro/Hugo/11ty | Wymaga build step, npm, Node.js — overengineering dla 1 strony |
| Google Sites | Ograniczone customizacje, nie da się zrobić brand identity |
| Carrd | Ograniczony do jednej kolumny, brak full custom CSS |

## Stack technologiczny

```
HTML5 + CSS3 + vanilla JS (minimal)
├── index.html          (główna strona, ~300 linii)
├── polityka-prywatnosci.html  (RODO)
├── styles/
│   ├── main.css        (custom properties, layout, components)
│   └── fonts.css       (Google Fonts preload)
├── assets/
│   ├── photos/         (WebP, max 200KB each, lazy loading)
│   ├── icons/          (SVG inline)
│   └── og-image.jpg    (1200x630 Open Graph)
├── robots.txt
├── sitemap.xml
└── manifest.json       (PWA-lite: ikona na home screen)
```

## Performance Budget

| Metric | Target | Jak osiągnąć |
|--------|--------|-------------|
| LCP | < 1.5s | Hero image preload, no render-blocking JS |
| FID | < 50ms | Zero JS w critical path |
| CLS | < 0.05 | Explicit image dimensions, font-display: swap |
| Total weight | < 500KB | WebP photos, system font fallbacks, no frameworks |
| Requests | < 15 | Inline SVGs, CSS in <style>, minimal external |

## SEO Implementation

### Schema.org (JSON-LD)
```json
{
  "@context": "https://schema.org",
  "@type": "Restaurant",
  "name": "Bar Agawa",
  "image": "og-image.jpg",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "Gustawa Morcinka 1",
    "addressLocality": "Dąbrowa Górnicza",
    "postalCode": "41-303",
    "addressCountry": "PL"
  },
  "telephone": "+48506721654",
  "priceRange": "1-20 PLN",
  "servesCuisine": "Bar, Kawiarnia",
  "openingHoursSpecification": [...],
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "5.0",
    "reviewCount": "12"
  }
}
```

### Meta Tags
```html
<title>Bar Agawa — Dąbrowa Górnicza | Kawa, piwo, imprezy</title>
<meta name="description" content="Bar sąsiedzki na Morcinka. Ogródek pod drzewami, imprezy okolicznościowe, poranna kawa i wieczorne piwo. Wpadaj jak do siebie.">
<meta name="keywords" content="bar Dąbrowa Górnicza, bar Morcinka, ogródek, imprezy okolicznościowe, kawiarnia Dąbrowa Górnicza">
<link rel="canonical" href="https://bar-agawa.pl/">

<!-- Open Graph -->
<meta property="og:title" content="Bar Agawa — Wpadaj jak do siebie">
<meta property="og:description" content="Bar sąsiedzki na Morcinka. Ogródek, piwo, kawa, imprezy.">
<meta property="og:image" content="https://bar-agawa.pl/assets/og-image.jpg">
<meta property="og:type" content="restaurant">
<meta property="og:locale" content="pl_PL">
```

## CSS Architecture

### Design Tokens (Custom Properties)
```css
:root {
  /* Colors */
  --color-primary: #4A7C59;
  --color-secondary: #F5E6D3;
  --color-accent: #C75B39;
  --color-dark: #3D2B1F;
  --color-light: #FFFBF5;
  
  /* Typography */
  --font-heading: 'Bitter', Georgia, serif;
  --font-body: 'Lato', -apple-system, sans-serif;
  
  /* Spacing */
  --space-xs: 0.5rem;
  --space-sm: 1rem;
  --space-md: 2rem;
  --space-lg: 4rem;
  --space-xl: 6rem;
  
  /* Breakpoints (for reference) */
  /* mobile: < 768px */
  /* desktop: ≥ 768px */
}
```

### Responsive Strategy
- **Mobile-first** — base styles for 320px+
- **Single breakpoint** at 768px (phone → everything else)
- No complex grid — flexbox only
- Photos: CSS aspect-ratio + object-fit: cover

## Hosting & Deploy

### Primary: Cloudflare Pages
```bash
# Setup (one-time)
1. Repo na GitHub: bar-agawa/bar-agawa-site
2. Cloudflare Pages → Connect to GitHub
3. Build command: (none — static files)
4. Output directory: /
5. Custom domain: bar-agawa.pl

# Update flow (gdy potrzeba zmian)
1. Edytuj HTML/CSS lokalnie lub na GitHub
2. Push to main → auto-deploy w 30 sekund
```

### Fallback: GitHub Pages
- Jeśli Cloudflare z jakiegoś powodu nie wchodzi w grę
- `username.github.io/bar-agawa` lub custom domain

## Accessibility

- Semantic HTML5 (header, nav, main, section, footer)
- Alt text na wszystkich zdjęciach (po polsku)
- Color contrast ratio ≥ 4.5:1 (verified)
- Focus styles visible
- Skip-to-content link
- Lang="pl" na <html>

## JavaScript (minimal)

Jedyny JS na stronie:
1. **Hamburger menu toggle** (~10 linii)
2. **Smooth scroll** do anchor sekcji (~5 linii)
3. **Lazy loading photos** (native: loading="lazy")
4. **Opcjonalnie:** status otwarte/zamknięte na podstawie aktualnej godziny (~15 linii)

Total: < 50 linii vanilla JS. Zero dependencies. Zero build step.

## Domena

### Rekomendacja: `bar-agawa.pl`
- Alternatywy: `agawa-dg.pl`, `baragawa.pl`
- Rejestracja: ~50-80 PLN/rok
- DNS: Cloudflare (free)

## Timeline

| Faza | Czas | Output |
|------|------|--------|
| Research & Spec | ✅ | Ten dokument |
| Design mockup | 2h | HTML/CSS prototype |
| Content gathering | 1-2 dni | Zdjęcia od właściciela, dokładne godziny, menu |
| Build | 3-4h | Gotowa strona |
| Deploy + domain | 1h | Live na custom domain |
| SEO verification | 30min | Google Search Console + schema test |

**Total: 1-2 dni roboczych** (zależnie od dostarczenia zdjęć/treści)
