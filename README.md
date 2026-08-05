# Bar Agawa — Project Structure

```
bar-agawa/
├── docs/                          # Dokumentacja projektu
│   ├── BRIEF.md                   # Brief projektowy (cel, persony, wymagania)
│   ├── SITEMAP.md                 # Mapa strony + architektura URL
│   ├── TECH-SPEC.md               # Specyfikacja techniczna (stack, hosting, SEO)
│   ├── DESIGN-SPEC.md             # System wizualny (kolory, typo, komponenty)
│   ├── CONTENT-SPEC.md            # Treści + tone of voice + co potrzebne od klienta
│   └── RESEARCH.md                # Wyniki discovery (inspiracje, legal, tech)
│
├── design/                        # Pliki designu
│   ├── brand-bible.md             # Pełna Brand Bible (z CBA)
│   ├── wireframe.html             # Lo-fi wireframe (HTML preview)
│   └── mockup.html                # Hi-fi mockup (final design preview)
│
├── assets/                        # Pliki źródłowe
│   ├── photos/                    # Zdjęcia od właściciela (oryginały)
│   ├── photos-optimized/          # WebP po optymalizacji
│   ├── fonts/                     # Lokalne kopie fontów (backup)
│   └── icons/                     # SVG ikony (Lucide)
│
├── src/                           # Kod źródłowy strony
│   ├── index.html                 # Główna strona
│   ├── polityka-prywatnosci.html  # RODO
│   ├── styles/
│   │   └── main.css               # Jedyny plik CSS
│   ├── scripts/
│   │   └── main.js                # Minimalny JS (menu, scroll, status)
│   └── assets/                    # Produkcyjne assety (do deployu)
│       ├── photos/                # Zoptymalizowane zdjęcia
│       ├── og-image.jpg           # Open Graph image
│       └── favicon.ico            # Favicon
│
├── public/                        # Pliki root (kopiowane 1:1 do deploy)
│   ├── robots.txt
│   ├── sitemap.xml
│   └── manifest.json              # PWA-lite manifest
│
└── README.md                      # Jak zdeployować / zaktualizować
```

## Workflow

```
1. DISCOVERY (ten etap)
   docs/ → brief, spec, research
   
2. DESIGN
   design/ → wireframe → mockup → akceptacja
   
3. BUILD
   src/ → index.html + CSS + JS
   assets/ → optymalizacja zdjęć
   
4. DEPLOY
   src/ + public/ → push to GitHub → Cloudflare Pages auto-deploy
   
5. MAINTENANCE
   Edycja src/index.html (menu/ceny) → push → live w 30s
```
