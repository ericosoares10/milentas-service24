# Milentas Service24 – Hausmeisterservice & Reinigung Berlin

## Projekt-Übersicht

| Eigenschaft | Wert |
|---|---|
| **Domain** | [milentas-service24.de](https://milentas-service24.de) |
| **Cloudflare Pages** | milentas-service24.pages.dev |
| **Unternehmen** | Milentas Service 24 UG (haftungsbeschränkt) |
| **Geschäftsführer** | Abudú Rodrigues Pires Da Costa |
| **Adresse** | Soldiner Straße 37, 13359 Berlin |
| **HRB** | 286043 (AG Berlin Charlottenburg) |
| **Technologie** | Statisches HTML/CSS/JS (kein Framework) |
| **Hosting** | Cloudflare Pages |
| **Repository** | github.com/ericosoares10/milentas-service24 |

---

## Deployment

### Automatisches Deployment via Wrangler CLI

```bash
# Voraussetzung: Node.js & npm installiert
npm install -g wrangler

# Deployment ausführen (Zugangsdaten siehe CREDENTIALS.md)
CLOUDFLARE_API_TOKEN="<siehe CREDENTIALS.md>" \
CLOUDFLARE_ACCOUNT_ID="<siehe CREDENTIALS.md>" \
wrangler pages deploy . --project-name=milentas-service24 --branch=main
```

### Zugangsdaten

| Service | Zugangsdaten |
|---|---|
| **GitHub Repo** | github.com/ericosoares10/milentas-service24 |
| **Pages Project** | milentas-service24 |
| **Custom Domain** | milentas-service24.de |
| **Weitere Zugangsdaten** | Siehe CREDENTIALS.md (nicht im Repo) |

---

## SEO-Strategie

### Primäre Keywords (Fokus)

| Keyword | Suchvolumen (geschätzt) | Schwierigkeit |
|---|---|---|
| Hausmeisterservice Berlin | Hoch | Mittel |
| Hausmeisterdienst Berlin | Mittel | Mittel |
| Reinigungsservice Berlin | Hoch | Hoch |
| Gebäudereinigung Berlin | Hoch | Hoch |
| Hausmeister Berlin | Hoch | Mittel |

### Sekundäre Keywords

- Treppenhausreinigung Berlin
- Winterdienst Berlin
- Grünpflege Berlin
- Objektbetreuung Berlin
- Büroreinigung Berlin
- Unterhaltsreinigung Berlin
- Grundreinigung Berlin
- Fensterreinigung Berlin
- Facility Management Berlin

### Long-Tail Keywords

- Hausmeisterservice Berlin 24 Stunden
- Professionelle Gebäudereinigung Berlin
- Hausmeister für Hausverwaltung Berlin
- Reinigungsservice Gewerbe Berlin
- Hausmeisterdienst Wedding Berlin
- Treppenhausreinigung Berlin Preise

### Lokale SEO-Keywords

- Hausmeisterservice Berlin Wedding
- Hausmeisterservice Berlin Mitte
- Hausmeisterservice Berlin Reinickendorf
- Reinigungsservice Berlin Nord

---

## SEO-Maßnahmen (implementiert)

1. **Title Tag** optimiert mit Haupt-Keyword + Brand
2. **Meta Description** mit Call-to-Action und Keywords
3. **Schema.org Structured Data** (LocalBusiness, Service, FAQPage)
4. **H1-Tag** mit primärem Keyword
5. **Semantische HTML-Struktur** (header, nav, main, section, footer)
6. **FAQ-Section** mit Schema-Markup für Featured Snippets
7. **Lokale SEO** – Bezirke-Section mit allen Berliner Bezirken
8. **Mobile First** – Responsive Design, Sticky CTA
9. **Performance** – Kein Framework, minimales CSS inline
10. **robots.txt** und **sitemap.xml** konfiguriert
11. **Canonical URL** gesetzt
12. **Open Graph** Tags für Social Sharing
13. **Security Headers** via Cloudflare (_headers)

---

## Dateistruktur

```
milentas-service24/
├── index.html          # Hauptseite (SEO-optimiert)
├── 404.html            # Fehlerseite
├── sitemap.xml         # XML-Sitemap für Suchmaschinen
├── robots.txt          # Crawler-Anweisungen
├── _headers            # Cloudflare Security Headers
├── _redirects          # Cloudflare Redirects (www → non-www)
└── README.md           # Diese Dokumentation
```

---

## Nächste Schritte (optional)

- [ ] Google Search Console einrichten und Sitemap einreichen
- [ ] Google My Business Eintrag erstellen
- [ ] Backlinks von lokalen Verzeichnissen aufbauen (Gelbe Seiten, 11880, etc.)
- [ ] Kontaktformular mit Backend verbinden (z.B. Formspree, Netlify Forms)
- [ ] Google Analytics / Plausible Analytics einbinden
- [ ] Regelmäßig Blog-Beiträge zu lokalen Themen veröffentlichen
- [ ] Bewertungen auf Google sammeln

---

## Kontakt

Bei Fragen zum Projekt: info@milentas-service24.de
