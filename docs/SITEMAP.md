# Bar Agawa — Mapa Strony

## Architektura: Single Page (scroll sections)

Uzasadnienie: Dla tak prostego biznesu multi-page robi więcej zamieszania niż pożytku.
Użytkownik mobile scrolluje naturalnie. Nawigacja sticky z anchor linkami.

```
┌─────────────────────────────────────────┐
│           HEADER / NAV (sticky)          │
│  Logo · Menu · O nas · Galeria · Kontakt │
├─────────────────────────────────────────┤
│                                         │
│            HERO SECTION                 │
│   "Wpadaj jak do siebie"               │
│   Zdjęcie ogródka / wnętrza            │
│   Status: Otwarte do 22:00             │
│   [Zadzwoń] [Jak dojechać]             │
│                                         │
├─────────────────────────────────────────┤
│                                         │
│            MENU / OFERTA                │
│   Kawa · Piwo · Napoje · Przekąski     │
│   (prosta lista z cenami)              │
│                                         │
├─────────────────────────────────────────┤
│                                         │
│            O NAS                        │
│   "Bar z tradycjami na Morcinka"       │
│   Krótki opis (3-4 zdania)            │
│   Ikony: ogródek / imprezy / TV        │
│                                         │
├─────────────────────────────────────────┤
│                                         │
│            GALERIA                      │
│   4-8 zdjęć (grid responsive)         │
│   Ogródek · Wnętrze · Imprezy         │
│                                         │
├─────────────────────────────────────────┤
│                                         │
│          IMPREZY OKOLICZNOŚCIOWE        │
│   "Zorganizuj u nas"                   │
│   Opis oferty + CTA (zadzwoń)         │
│                                         │
├─────────────────────────────────────────┤
│                                         │
│            OPINIE                       │
│   3 cytaty z Google Reviews            │
│   Link do pełnych opinii              │
│                                         │
├─────────────────────────────────────────┤
│                                         │
│            KONTAKT / DOJAZD            │
│   Mapa (Google Maps embed)            │
│   Adres · Telefon (click-to-call)     │
│   Godziny otwarcia (tabela)           │
│                                         │
├─────────────────────────────────────────┤
│              FOOTER                     │
│   © Bar Agawa · Polityka prywatności   │
└─────────────────────────────────────────┘
```

## Nawigacja

### Mobile (< 768px)
- Hamburger menu → overlay z anchor linkami
- Sticky bar: logo + telefon (click-to-call)

### Desktop (≥ 768px)
- Sticky nav: Logo | Menu | O nas | Galeria | Imprezy | Kontakt
- Smooth scroll do sekcji

## URL Structure
```
/               → Single page (wszystko)
/polityka-prywatnosci  → RODO (osobna podstrona, wymagane prawnie)
```

## SEO
- Title: "Bar Agawa — Dąbrowa Górnicza | Kawa, piwo, imprezy"
- Meta description: "Bar sąsiedzki na Morcinka. Ogródek pod drzewami, 
  imprezy okolicznościowe, poranna kawa i wieczorne piwo. Wpadaj jak do siebie."
- Schema.org: LocalBusiness + Restaurant
- Open Graph: zdjęcie ogródka + nazwa
