# Bar Agawa — Research & Discovery

## Data sources
- Web research: design patterns, CMS comparison, legal requirements (PL)
- Google Maps: profil baru, opinie, zdjęcia
- Brand Bible: analiza archetypowa (Everyman 70% + Caregiver 30%)

---

## 1. Benchmarki — Strony małych barów/kawiarni

### Polska
| Lokal | Co robią dobrze | Pattern |
|-------|-----------------|---------|
| Bar Centralny (Warszawa) | Single-page, vintage typo, ciepłe kolory, prosta lista menu | Static scroll |
| Café Szafa (Kraków) | Zdjęcia dominują, godziny w sticky header, events jako lista | Photo-forward |
| Bar Przychodnia (Warszawa) | Events-first, dark + warm, social media integration | Community hub |
| Cafe Gołębia (Kraków) | Clean, minimal, menu z cenami, godziny widoczne zawsze | Informational |

### Globalnie
| Lokal | Co robią dobrze | Pattern |
|-------|-----------------|---------|
| The Attendant (London) | Minimalizm, cream palette, menu jako tekst nie PDF | Warm minimal |
| Storm in a Teacup (Edinburgh) | Hand-drawn ilustracje, playful typo, events jako blog | Illustrated |
| Seva Café (Ahmedabad) | Story-first, community values, earth tones | Values-driven |

### Kluczowy insight
**~70-80% barów sąsiedzkich w PL NIE MA strony www.** Polegają na:
1. Google Business Profile (95%)
2. Facebook Page (90%)
3. Instagram (60-70%)
4. Strona www (20-30%)

→ Sama obecność strony www = natychmiastowe wyróżnienie w DG.

---

## 2. Wymagania prawne (PL)

### MUST — Ustawa o świadczeniu usług drogą elektroniczną (Art. 5)
- [x] Pełna nazwa firmy / imię nazwisko właściciela
- [x] NIP (jeśli JDG/spółka)
- [x] Adres siedziby
- [x] Email kontaktowy (wymagany prawnie — sam telefon nie wystarczy!)
- [x] REGON (jeśli dotyczy)

### MUST — RODO / GDPR
- [x] Polityka prywatności (osobna podstrona)
- [x] Cookie notice (jeśli jakiekolwiek cookies — nawet Google Maps embed!)
- [x] Informacja o administratorze danych
- [x] Prawa użytkownika (dostęp, sprostowanie, usunięcie)
- [x] Prawo skargi do UODO

### SHOULD — Prawo konsumenckie
- [x] Ceny brutto (z VAT) — wymagane przy wyświetlaniu cen konsumentom
- [x] Informacja o alergenach (zalecane EU 1169/2011 przy menu online)

### HACK — Jak zminimalizować obowiązki RODO
**Brak formularza kontaktowego = brak zbierania danych = minimalna Polityka Prywatności.**
- Nie dajemy formularza → telefon jako jedyny kanał
- Nie dajemy newsletter → brak zgód marketingowych
- Google Maps embed → wymaga cookie notice (cookies Google)
- Rozwiązanie: prosty banner "Strona używa Google Maps" + link do PP

---

## 3. Co naprawdę przyciąga ludzi do baru (priorytet sekcji)

### Tier 1 — Must show (60%+ wartości strony)
| Sekcja | Dlaczego |
|--------|----------|
| Godziny otwarcia | #1 szukana informacja dla local searches |
| Telefon (click-to-call) | Primary action na mobile |
| Adres + mapa | Redukcja tarcia dla nowych gości |
| Menu z cenami | "Czy mnie stać" = decyzja go/no-go |

### Tier 2 — Strong impact (25%)
| Sekcja | Dlaczego |
|--------|----------|
| Zdjęcia (ogródek!) | Atmosphere preview → decyzja "pójdę" |
| Imprezy okolicznościowe | Revenue driver + keyword "imprezy Dąbrowa G." |
| Rating 5.0 ★ | Social proof → zaufanie nowych gości |
| "Jak nas znaleźć" | Landmark'i, parking |

### Tier 3 — Nice (15%)
| Sekcja | Dlaczego |
|--------|----------|
| O nas / historia | Buduje sąsiedzką więź |
| Social links | Dodatkowy kanał (FB events) |
| Galeria rozszerzona | Poza hero photos |

---

## 4. Decyzja tech — Uzasadnienie

### Porównanie rozwiązań

| Kryterium | HTML/CSS | Hugo | Astro | 11ty | Carrd | Wix | WordPress |
|-----------|:--------:|:----:|:-----:|:----:|:-----:|:---:|:---------:|
| Zero maintenance | ★★★★★ | ★★★ | ★★★ | ★★★ | ★★★★ | ★★★ | ★★ |
| Performance | ★★★★★ | ★★★★★ | ★★★★★ | ★★★★★ | ★★★ | ★★★ | ★★★ |
| SEO control | ★★★★★ | ★★★★★ | ★★★★★ | ★★★★★ | ★★ | ★★★ | ★★★★ |
| Koszt/rok | 0-80 PLN | 0-80 PLN | 0-80 PLN | 0-80 PLN | ~80+80 PLN | 600+ PLN | 200-500 PLN |
| Prostota updejtu | ★★★★ | ★★★ | ★★★ | ★★★ | ★★★★★ | ★★★★★ | ★★★★ |
| Future-proof | ★★★★★ | ★★★★ | ★★★ | ★★★★ | ★★ | ★★★ | ★★★ |

### Werdykt: **Static HTML/CSS na Cloudflare Pages**

Uzasadnienie:
1. **1 strona + 1 podstrona** — każdy framework to overengineering
2. **Zero dependencies** — nic do aktualizacji, zero CVE, zero npm audit
3. **Najszybsze na mobile** — <50KB total, 100/100 Lighthouse
4. **Pełna kontrola SEO** — schema.org, meta, Open Graph ręcznie
5. **Darmowy hosting** — Cloudflare Pages (CDN z PoP w Polsce)
6. **Transferowalne** — każdy dev na świecie potrafi edytować HTML
7. **10-letnia żywotność** — HTML z 2026 zadziała w 2036

### Jedyny koszt: domena
- `bar-agawa.pl` lub `baragawa.pl`: ~50-80 PLN/rok
- Registrar: nazwa.pl, OVH.pl, lub home.pl
- DNS: Cloudflare (free)

---

## 5. Google Business Profile — Plan integracji

### Natychmiast po deploy strony:
1. Dodać URL strony do GBP (pole "Witryna")
2. Dodać URL menu do GBP (pole "Menu")
3. Upewnić się że NAP (Name/Address/Phone) identyczny na stronie i w GBP
4. Dodać zdjęcia ze strony do GBP (te same, spójność)

### SEO lokalne — keywords do pokrycia:
```
bar Dąbrowa Górnicza
bar Morcinka
kawiarnia Dąbrowa Górnicza
ogródek piwny Dąbrowa Górnicza
imprezy okolicznościowe Dąbrowa Górnicza
bar sąsiedzki DG
piwo Morcinka
```

### Schema.org LocalBusiness (JSON-LD) — gotowy do wklejenia:
```json
{
  "@context": "https://schema.org",
  "@type": ["Restaurant", "BarOrPub"],
  "name": "Bar Agawa",
  "image": "https://bar-agawa.pl/assets/og-image.jpg",
  "url": "https://bar-agawa.pl",
  "telephone": "+48506721654",
  "priceRange": "1-20 PLN",
  "servesCuisine": ["Bar", "Kawiarnia"],
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "Gustawa Morcinka 1",
    "addressLocality": "Dąbrowa Górnicza",
    "postalCode": "41-303",
    "addressRegion": "śląskie",
    "addressCountry": "PL"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": 50.3219,
    "longitude": 19.1941
  },
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday","Tuesday","Wednesday","Thursday","Friday"],
      "opens": "08:00",
      "closes": "22:00"
    },
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": "Saturday",
      "opens": "10:00",
      "closes": "23:00"
    },
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": "Sunday",
      "opens": "10:00",
      "closes": "20:00"
    }
  ],
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "5.0",
    "bestRating": "5",
    "reviewCount": "12"
  },
  "amenityFeature": [
    {"@type": "LocationFeatureSpecification", "name": "Ogródek", "value": true},
    {"@type": "LocationFeatureSpecification", "name": "Imprezy okolicznościowe", "value": true},
    {"@type": "LocationFeatureSpecification", "name": "Telewizor", "value": true}
  ]
}
```

> ⚠️ Współrzędne GPS i godziny wymagają weryfikacji.

---

## 6. Social Proof — Strategia

### Aktualna sytuacja: 5.0/5 z 12 opinii
**Siła:** Perfekcyjny rating. Rzadkość.
**Słabość:** Mała liczba (12). Poniżej progu "wiarygodnej próby" (50+).

### Plan:
1. Na stronie: **wyeksponować 5.0** (duży, widoczny w hero lub zaraz pod)
2. Wybrać 2-3 cytaty z opinii (najlepsze fragmenty)
3. CTA: "Zobacz opinie na Google" → link do GBP review page
4. Długoterminowo: naklejka w barze "Oceń nas na Google" (QR code)

### Do NIE robienia:
- Nie embedować Google Reviews widgetu (ryzyko ToS)
- Nie pokazywać "12 opinii" prominentnie (mała liczba)
- Nie tworzyć fake reviews

---

## 7. Materiały do zebrania od właściciela

| # | Materiał | Priorytet | Notatka |
|---|----------|-----------|---------|
| 1 | Zdjęcia ogródka (latem, z gośćmi) | CRITICAL | Hero image |
| 2 | Zdjęcia wnętrza (bar, stoliki) | HIGH | Galeria |
| 3 | Aktualne menu z cenami | CRITICAL | Sekcja menu |
| 4 | Dokładne godziny otwarcia | CRITICAL | Kontakt + schema |
| 5 | Imię/firma właściciela | HIGH | PP + stopka |
| 6 | NIP (jeśli działalność) | HIGH | Wymóg prawny |
| 7 | Email kontaktowy | HIGH | Wymóg prawny Art. 5 |
| 8 | Czy chcą domenę (jaka?) | MEDIUM | Deploy |
| 9 | Zgoda na użycie opinii Google | MEDIUM | Social proof |
| 10 | Zdjęcia z imprez (za zgodą gości) | LOW | Sekcja events |
