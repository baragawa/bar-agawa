# Bar Agawa — Design Spec (Visual Language)

## Filozofia wizualna

> "Strona powinna wyglądać jak bar się czuje — ciepło, prosto, bez udawania."

Nie budujemy strony "dla baru". Budujemy cyfrowe przedłużenie doświadczenia bycia w Agawie.
Kremowe tło jak ściana lokalu. Zieleń jak liście nad ogródkiem. Terakota jak cegła na fasadzie.

## Color System

### Zastosowanie kontekstowe
```
TYNK ŚCIANY (tło strony)     → #FFFBF5 (ciepła biel)
DREWNO BARU (nagłówki, nav)  → #3D2B1F (ciemny brąz)
LIŚĆ AGAWY (akcenty, buttony)→ #4A7C59 (ciepła zieleń)
KAWA Z MLEKIEM (karty, bloki)→ #F5E6D3 (kremowy beż)
CEGŁA FASADY (hover, CTA)    → #C75B39 (terakota)
```

### Gradienty: BRAK
Żadnych gradientów. To bar sąsiedzki, nie SaaS. Płaskie kolory, naturalne przejścia.

### Cienie
Minimalne, ciepłe:
```css
--shadow-card: 0 2px 8px rgba(61, 43, 31, 0.08);
--shadow-hover: 0 4px 16px rgba(61, 43, 31, 0.12);
```

## Typography

### Hierarchia

| Element | Font | Size (mobile) | Size (desktop) | Weight | Color |
|---------|------|---------------|----------------|--------|-------|
| H1 (hero) | Bitter | 2rem | 3rem | 700 | #3D2B1F |
| H2 (sekcje) | Bitter | 1.5rem | 2rem | 700 | #3D2B1F |
| H3 (karty) | Bitter | 1.25rem | 1.5rem | 600 | #3D2B1F |
| Body | Lato | 1rem | 1.125rem | 400 | #3D2B1F |
| Small / caption | Lato | 0.875rem | 0.875rem | 400 | #3D2B1Fcc |
| Button | Lato | 1rem | 1rem | 600 | depends |
| Menu item | Lato | 1rem | 1.125rem | 400 | #3D2B1F |
| Menu price | Bitter | 1rem | 1.125rem | 700 | #4A7C59 |

### Interlinia
- Body: 1.6
- Nagłówki: 1.2
- Menu items: 1.8 (czytelność listy)

## Spacing System

```
XS:  8px  (0.5rem)  — wewnątrz elementów
SM:  16px (1rem)    — między elementami w grupie
MD:  32px (2rem)    — między grupami
LG:  64px (4rem)    — między sekcjami (mobile)
XL:  96px (6rem)    — między sekcjami (desktop)
```

## Component Library

### 1. Hero Section
- Full-width zdjęcie ogródka (overlay 30% dark na dole dla tekstu)
- Napis: "Wpadaj jak do siebie" (Bitter, biały, text-shadow)
- Status badge: "● Otwarte do 22:00" (zielona kropka + tekst)
- 2 buttony: [📞 Zadzwoń] [📍 Jak dojechać]

### 2. Section Header
- Bitter 700, ciemny brąz
- Dekoracja pod tekstem: krótka linia w kolorze accent (#C75B39), 40px szeroka, 3px gruba
- Opcjonalnie: mały ikon SVG obok

### 3. Menu Card
```
┌─────────────────────────────┐
│  ☕ KAWA I NAPOJE           │  ← H3, Bitter
│                             │
│  Espresso ............. 6 zł│  ← Lato + dots + Bitter price
│  Americano ............ 7 zł│
│  Cappuccino ........... 9 zł│
│  Herbata .............. 5 zł│
│                             │
└─────────────────────────────┘
```
- Background: #F5E6D3 (kremowy)
- Border-radius: 12px
- Padding: 24px
- Kropki-separator: border-bottom dotted 1px

### 4. Photo Grid
- Mobile: 1 kolumna, aspect-ratio 4/3
- Desktop: 2 kolumny (masonry-lite z gap 16px)
- Border-radius: 8px
- Hover: scale(1.02) + shadow

### 5. Review Quote
```
┌─────────────────────────────────────────────┐
│  ★★★★★                                      │
│  "Kawiarnia Agawa to lokal z tradycjami     │
│   w którym można wypić wyborną kawę..."     │
│                                             │
│   — Jakub K.                      Google    │
└─────────────────────────────────────────────┘
```
- Tło: białe (#FFFBF5)
- Border-left: 4px solid #4A7C59
- Cudzysłów: font-size 2rem, #C75B39, opacity 0.5

### 6. CTA Block (Imprezy)
- Tło: #4A7C59 (zieleń)
- Tekst: biały
- Nagłówek: "Zorganizuj imprezę u nas"
- Opis: 2 zdania
- Button: biały tekst na #C75B39 (terakota), hover → darken 10%

### 7. Contact / Map Section
- Google Maps embed (16:9 aspect ratio)
- Obok lub pod: adres, telefon, godziny
- Telefon: duży, click-to-call, ikona 📞
- Godziny: prosta tabela (Pon-Pt / Sob / Nd)

### 8. Footer
- Background: #3D2B1F (ciemny brąz)
- Tekst: #F5E6D3 (kremowy)
- Treść: © 2025 Bar Agawa | Polityka prywatności
- Minimalistyczny — 1 linia

## Imagery Guidelines

### Styl zdjęć
- Naturalne, nieprzetworzone (zero HDR, zero filtrów)
- Ciepła temperatura barwowa
- Preferowane: telefon z ręki, nie profesjonalna sesja
- Obowiązkowe: ogródek (latem), wnętrze (klimat), ludzie (za zgodą)

### Przetwarzanie techniczne
- Format: WebP (fallback JPG)
- Max size: 200KB per photo
- Dimensions: 800×600 (grid), 1920×800 (hero)
- Lazy loading: loading="lazy" + decoding="async"

## Ikony

SVG inline, stroke-based, 24×24, color: currentColor.
Źródło: Lucide Icons (MIT license) — pasują do ciepłego, prostego stylu.

Potrzebne:
- ☕ Coffee (menu)
- 🍺 Beer (menu)  
- 📞 Phone (kontakt)
- 📍 MapPin (adres)
- 🕐 Clock (godziny)
- 🌿 Leaf (ogródek)
- 🎉 PartyPopper (imprezy)
- ⭐ Star (opinie)
- ☰ Menu (hamburger)

## Animacje

### Zasada: ZERO animacji wejścia (no fade-in, no slide-up)
To bar, nie landing page SaaS-a. Treść jest od razu widoczna. Jedyne mikro-interakcje:

- **Hover na zdjęciach:** scale(1.02), transition 0.3s ease
- **Hover na button:** darken background 10%, transition 0.2s
- **Smooth scroll:** behavior: smooth (CSS native)
- **Mobile menu:** transform translateX, transition 0.3s

### Zasada: ZERO parallax, ZERO scroll-triggered
Content appears immediately. User scrolls, reads, acts. No waiting.

## Dark Mode: NIE

Nie implementujemy dark mode. Bar jest ciepły i jasny. Ciemna biel (#FFFBF5) i tak jest łagodna dla oczu wieczorem.
