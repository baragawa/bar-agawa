# Bar Agawa — Brand Bible (Summary)

> Pełna wersja stworzona przez CBA (Chief Brand Architect).
> Ten dokument jest skrótem operacyjnym do użytku przy budowaniu strony.

---

## Tożsamość

| Element | Wartość |
|---------|---------|
| Nazwa | Bar Agawa |
| Lokalizacja | Gustawa Morcinka 1, 41-303 Dąbrowa Górnicza |
| Segment | Bar sąsiedzki z tradycjami |
| Archetyp | Zwykły Człowiek 70% + Opiekun 30% |
| Semantic Core | **SĄSIEDZTWO · TRADYCJA · CIEPŁO** |
| Tagline | "Wpadaj jak do siebie." |
| Elevator | Bar sąsiedzki na Morcinka. Kawa rano, piwo wieczorem, imprezy kiedy chcesz. |

---

## Paleta

```css
:root {
  --color-primary: #4A7C59;    /* Ciepła zieleń — liść agawy */
  --color-secondary: #F5E6D3;  /* Kremowy beż — ciepło kawy */
  --color-accent: #C75B39;     /* Terakota — cegła śląska */
  --color-dark: #3D2B1F;       /* Ciemny brąz — drewno baru */
  --color-light: #FFFBF5;      /* Ciepła biel — tło */
}
```

## Typografia

```css
--font-heading: 'Bitter', Georgia, serif;    /* nagłówki */
--font-body: 'Lato', -apple-system, sans-serif; /* body */
```

| Element | Font | Weight | Size (mobile → desktop) |
|---------|------|--------|------------------------|
| H1 | Bitter | 700 | 2rem → 3rem |
| H2 | Bitter | 700 | 1.5rem → 2rem |
| Body | Lato | 400 | 1rem → 1.125rem |
| Price | Bitter | 700 | 1rem | 
| Button | Lato | 600 | 1rem |

## Tone of Voice

- Ciepły, bezpretensjonalny, sąsiedzki
- "Ty" (nie "Państwo")
- Zero anglicyzmów i marketingowego żargonu
- Krótkie zdania. Konkret > ogólnik.
- Przykład: "Piwo od 6 zł" > "Bogata oferta napojów"

## Do / Don't

| ✅ DO | ❌ DON'T |
|-------|---------|
| Autentyczne zdjęcia z telefonu | Stock photos |
| Język potoczny | "Doświadczenie kulinarne" |
| Odręczne napisy (kreda) | Perfekcyjna typografia |
| Ciepłe kolory, naturalne światło | Neon, LED, "insta" look |
| Prawdziwi goście | Modele |
| "Bar Agawa" / "Agawa" | "AGAWA™", "Agawa Experience" |
| Niedoskonałość = charakter | Sterylna perfekcja |

## Imagery

- Naturalne, bez filtrów, ciepła temperatura
- Format: WebP, max 200KB, lazy loading
- Hero: 1920×800, Grid: 800×600
- Styl: "zdjęcie z telefonu sąsiada" nie "sesja zdjęciowa"

## Ikony

Lucide Icons (MIT), stroke-based, 24×24, color: currentColor.

## Animacje

ZERO animacji wejścia. ZERO parallax. Tylko:
- Hover zdjęć: scale(1.02)
- Hover buttonów: darken 10%
- Smooth scroll (CSS native)
