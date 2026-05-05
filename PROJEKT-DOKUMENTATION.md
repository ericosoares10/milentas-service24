# Vollständige Projekt-Dokumentation – Alle 3 Websites

**Erstellt:** Mai 2026
**Zweck:** Komplette Übergabe-Dokumentation für KI-Assistenten (Codex, Claude, GPT etc.)
**Regel:** Wer dieses Dokument + GitHub-Zugang hat, kann alle 3 Projekte vollständig verstehen, bearbeiten und deployen.

---

## Inhaltsverzeichnis

1. [Übersicht aller Projekte](#1-übersicht-aller-projekte)
2. [Zugangsdaten & Credentials](#2-zugangsdaten--credentials)
3. [Projekt 1: Adama Global Trade GmbH](#3-projekt-1-adama-global-trade-gmbh)
4. [Projekt 2: Milentas Service24](#4-projekt-2-milentas-service24)
5. [Projekt 3: Firmenanschrift Berlin Mieten](#5-projekt-3-firmenanschrift-berlin-mieten)
6. [Deployment-Anleitung (alle Projekte)](#6-deployment-anleitung-alle-projekte)
7. [Wichtige Regeln für KI-Bearbeitung](#7-wichtige-regeln-für-ki-bearbeitung)
8. [Offene TODOs](#8-offene-todos)

---

## 1. Übersicht aller Projekte

| Projekt | Domain | Technologie | Seiten | Firma |
|---------|--------|-------------|--------|-------|
| Adama Global Trade | [adamaglobaltrade.de](https://adamaglobaltrade.de) | React 19 + Vite + Tailwind (SSG via Puppeteer) | 143 | Adama Global Trade GmbH |
| Milentas Service24 | [milentas-service24.de](https://milentas-service24.de) | Statisches HTML/CSS/JS (kein Framework) | 30 | Milentas Service 24 UG |
| Firmenanschrift Berlin | [firmenanschrift-berlin-mieten.de](https://firmenanschrift-berlin-mieten.de) | Statisches HTML/CSS/JS (kein Framework) | 9 | Milentas Service 24 UG (Marke) |

**Beziehung der Firmen:**
- **Milentas Service 24 UG (haftungsbeschränkt)** ist die Hauptfirma (Hausmeisterservice & Reinigung Berlin)
- **Firmenanschrift Berlin Mieten** ist eine Marke/Geschäftsbereich der Milentas Service 24 UG
- **Adama Global Trade GmbH** ist eine separate Firma (B2B Rohstoff-Großhandel)

**Inhaber beider Firmen:**
- Milentas: Geschäftsführer **Abudú Rodrigues Pires Da Costa**
- Adama: Geschäftsführer **Erico Soares Da Gama Vieira**

---

## 2. Zugangsdaten & Credentials

### GitHub

| Parameter | Wert |
|-----------|------|
| Username | `ericosoares10` |
| Repos | `adama`, `milentas-service24`, `firmenanschrift-berlin-mieten` |
| Token (PAT) | Wird separat mitgeteilt (Scope: `repo`) |

**Git Push:**
```bash
git push https://ericosoares10:<TOKEN>@github.com/ericosoares10/<REPO>.git main
```

### Cloudflare (Hosting & DNS)

| Parameter | Wert |
|-----------|------|
| Account ID | `c6c3c56f9197fddc30b649f2f4395e72` |
| API Token | Wird separat mitgeteilt (Scope: Cloudflare Pages Edit + Workers) |
| Nameserver 1 | `odin.ns.cloudflare.com` |
| Nameserver 2 | `tori.ns.cloudflare.com` |

**Cloudflare Zonen:**

| Domain | Zone ID | Status |
|--------|---------|--------|
| adamaglobaltrade.de | `cdb3f00780b954e6a691b7a25a3ce81e` | Active |
| firmenanschrift-berlin-mieten.de | `3c8b84678920a30c1ea061b5dc08d00c` | Active |
| milentas-service24.de | `21fa4e753b0ac261d53a1f757be558b0` | Active |

**Cloudflare Pages Projekte:**

| Projekt | Pages-Name | Custom Domain |
|---------|-----------|---------------|
| Adama | `adama-global-trade` | adamaglobaltrade.de |
| Milentas | `milentas-service24` | milentas-service24.de |
| Firmenanschrift | `firmenanschrift-berlin-mieten` | firmenanschrift-berlin-mieten.de |

### Telegram Bot (nur Adama)

| Parameter | Wert |
|-----------|------|
| Bot Username | `@Globaladama_bot` |
| Bot Token | `7972711835:AAG0qqsscDFpixW8PLswlXhl4WbOVmMZY0o` |
| Chat ID | Wird dynamisch über `getUpdates` ermittelt (Fallback: `7972711835`) |
| Konfigurationsdatei | `client/src/lib/telegram.ts` |

**Wichtig:** Der Empfänger muss einmalig `/start` im Bot drücken, damit die Chat-ID aktiv ist.

### Domain-Registrar

| Domain | Registrar | Nameserver-Konfiguration |
|--------|-----------|--------------------------|
| adamaglobaltrade.de | Namecheap | Custom DNS → Cloudflare |
| milentas-service24.de | Namecheap | Custom DNS → Cloudflare |
| firmenanschrift-berlin-mieten.de | Namecheap | Custom DNS → Cloudflare |

### E-Mail-Adressen

| Projekt | E-Mail |
|---------|--------|
| Adama | info@adamaglobaltrade.de |
| Milentas | info@milentas-service24.de |
| Firmenanschrift | info@firmenanschrift-berlin-mieten.de |

---

## 3. Projekt 1: Adama Global Trade GmbH

### Firmendaten

| Feld | Wert |
|------|------|
| Firma | Adama Global Trade GmbH |
| Geschäftsführer | Erico Soares Da Gama Vieira |
| Adresse | Anhaltinerstraße 15-16, 14163 Berlin |
| Hinweis | Nur Postanschrift – kein Kundenverkehr |
| Telefon | +49 163 330 4696 |
| E-Mail | info@adamaglobaltrade.de |
| WhatsApp | wa.me/491633304696 |
| Branche | Internationaler B2B-Großhandel (Rohstoffe) |

### Technologie-Stack

| Komponente | Lösung |
|-----------|--------|
| Framework | React 19 + Vite |
| Styling | Tailwind CSS 4 + Custom Design Tokens (oklch) |
| Routing | Wouter (Client-side SPA) |
| Animation | CSS Keyframes + IntersectionObserver (KEIN Framer Motion!) |
| Pre-Rendering | Puppeteer (`scripts/prerender.mjs`) |
| Deployment | Cloudflare Pages (Wrangler CLI) |
| Formulare | Telegram Bot API (silent fetch) |
| Sprachen | DE (primär) + EN (sekundär) |
| Fonts | DM Serif Display (Headlines), IBM Plex Sans (Body) – lokal gehostet |

### Design-System

| Token | Wert | Verwendung |
|-------|------|------------|
| `--anthracite` | `oklch(0.20 0.02 270)` | Primäre Textfarbe |
| `--copper` | `oklch(0.62 0.12 55)` | Akzentfarbe, CTAs, Buttons |
| `--copper-light` | `oklch(0.70 0.10 55)` | Hover-Zustand |
| `--warm-white` | `oklch(0.98 0.005 90)` | Helle Hintergründe |
| `--warm-gray` | `oklch(0.92 0.005 90)` | Borders |

**Dunkle Sektionen:** Verwenden Hintergrundbilder mit `rgba(15,17,23, 0.85–0.88)` Overlay statt flachem Anthrazit:
- `bg-dark-wood.webp` → About, Qualität, Vision, Produkte
- `bg-port-night.webp` → Kontakt, Logistik
- `bg-wheat-storm.webp` → Blog-Hero

**KEIN Blau auf der Seite!** Die Farbpalette ist bewusst warm (Gold/Kupfer + Anthrazit).

### Produkte (12 Stück)

| Slug (DE) | Slug (EN) | Produkt |
|-----------|-----------|---------|
| `/holzpellets` | `/en/wood-pellets` | Holzpellets |
| `/sojabohnen` | `/en/soybeans` | Sojabohnen |
| `/natursalz` | `/en/natural-salt` | Natursalz |
| `/kaffee` | `/en/coffee` | Kaffee |
| `/agrarrohstoffe` | `/en/agricultural-commodities` | Agrarrohstoffe |
| `/baustoffe` | `/en/building-materials` | Baustoffe |
| `/lebensmittel` | `/en/food-products` | Lebensmittel |
| `/gewuerze` | `/en/spices` | Gewürze |
| `/nuesse` | `/en/nuts` | Nüsse & Kerne |
| `/huelsenfruechte` | `/en/pulses` | Hülsenfrüchte |
| `/trockenfruechte` | `/en/dried-fruits` | Trockenfrüchte |
| `/zucker` | `/en/sugar` | Zucker |

### SEO-Architektur

Das System generiert automatisch Seiten aus `client/src/lib/seo-data.ts`:

| Seitentyp | Beispiel-URL | Template | Anzahl |
|-----------|-------------|----------|--------|
| Produktseiten | `/holzpellets` | `ProductPage.tsx` | 12 DE + 12 EN |
| Stadtseiten | `/holzpellets/berlin/` | `seo/CityPage.tsx` | ~52 |
| Länderseiten | `/holzpellets/oesterreich/` | `seo/CountryPage.tsx` | ~15 |
| Long-Tail-Seiten | `/holzpellets/grosshandel/` | `seo/LongTailPage.tsx` | ~40 |
| Blog | `/blog/holzpellets-vs-brennholz` | `BlogPost.tsx` | 3 (erweiterbar) |
| Statische Seiten | `/kontakt`, `/ueber-uns` | Eigene Dateien | 8 |

**Neue SEO-Seiten hinzufügen:** Nur Eintrag in `seo-data.ts` → kein weiterer Code nötig!

### Dateistruktur (wichtigste Dateien)

```
adama/
├── client/
│   ├── index.html                     ← HTML-Template
│   ├── public/
│   │   ├── sitemap.xml                ← 143+ URLs (auto-generiert)
│   │   ├── robots.txt                 ← Crawler-Regeln
│   │   ├── _headers                   ← Cloudflare Security + Cache Headers
│   │   ├── _redirects                 ← SPA Fallback (/* → /index.html 200)
│   │   ├── fonts/                     ← Lokal gehostete Fonts (woff2)
│   │   └── images/                    ← Hintergrundbilder (webp, optimiert)
│   └── src/
│       ├── App.tsx                    ← ZENTRALES ROUTING
│       ├── index.css                  ← Design-System
│       ├── components/
│       │   ├── Header.tsx             ← Navigation + Sprachumschalter
│       │   ├── Footer.tsx             ← Footer + Links
│       │   ├── SEOHead.tsx            ← Meta-Tags + Schema.org pro Seite
│       │   ├── CookieBanner.tsx       ← DSGVO Cookie-Banner
│       │   └── modules/               ← Wiederverwendbare UI-Module
│       ├── lib/
│       │   ├── content.ts             ← ALLE STATISCHEN INHALTE + siteConfig
│       │   ├── seo-data.ts            ← ALLE SEO-DATEN (Städte, Länder, Long-Tail)
│       │   ├── blog-data.ts           ← Blog-Beiträge
│       │   ├── product-content.ts     ← Erweiterte Produkt-Inhalte (FAQs etc.)
│       │   └── telegram.ts            ← Telegram Bot API
│       └── pages/                     ← Alle Seiten-Komponenten
├── scripts/
│   ├── prerender.mjs                  ← Puppeteer Pre-Rendering
│   ├── generate-sitemap.mjs           ← Sitemap-Generator
│   └── cf-deploy.py                   ← Cloudflare Direct Upload API
├── docs/
│   ├── KI-REBUILD-ANLEITUNG.md        ← Detaillierte KI-Wissensbasis
│   ├── CREDENTIALS.md                 ← Credential-Platzhalter
│   ├── content-plan-104-blogposts.md  ← Blog-Plan mit Checkboxen
│   ├── SEO-STRATEGIE.md
│   ├── CONVERSION-STRATEGIE.md
│   └── SEITEN-UEBERSICHT.md
├── content-plan-104-blogposts.md      ← Blog-Plan (Kopie im Root)
├── GOOGLE_LAUNCH_GUIDE.md             ← Google-Start-Anleitung
└── package.json                       ← Build-Scripts
```

### Build & Deploy Workflow

```bash
# 1. Dependencies installieren (nur beim ersten Mal)
pnpm install

# 2. Vite Build
pnpm build

# 3. Pre-Rendering (alle 143 Routen → statisches HTML)
node scripts/prerender.mjs

# 4. Deploy zu Cloudflare Pages
export CLOUDFLARE_API_TOKEN=<token>
export CLOUDFLARE_ACCOUNT_ID=c6c3c56f9197fddc30b649f2f4395e72
npx wrangler pages deploy dist/public --project-name=adama-global-trade
```

**Alternativ (bei großen Deployments):**
```bash
python3 scripts/cf-deploy.py
```

### Formular-Integration

Alle Formulare auf der Seite senden Daten per Telegram Bot API. Die Logik liegt in `client/src/lib/telegram.ts`:
1. Formular wird abgeschickt → `sendToTelegram()` aufgerufen
2. Chat-ID wird dynamisch über `getUpdates` ermittelt (mit Fallback)
3. Nachricht wird formatiert und per `sendMessage` gesendet
4. Benutzer sieht Bestätigungsseite (kein Redirect, kein Popup)

**E-Mail-Versand:** Noch NICHT implementiert. Geplant über SMTP/Nodemailer.

### Blog & Content-Plan

- 3 Blog-Beiträge bereits live (in `blog-data.ts`)
- 104 geplante Themen im Content-Plan (`content-plan-104-blogposts.md`)
- Format: `- [ ] **#1** Woche 1 | Titel | Keyword | Suchvolumen | Kategorie`
- Wenn ein Beitrag geschrieben wird: `[ ]` → `[x]` ändern
- Neuen Beitrag hinzufügen: Eintrag in `blog-data.ts` + Route existiert automatisch

### Logos (Adama)

| Variante | URL |
|----------|-----|
| Horizontal Farbe (Header) | `https://files.manuscdn.com/user_upload_by_module/session_file/310519663397256317/LqiyMRAqYXwCmuVF.png` |
| Horizontal Weiß (Footer) | `https://files.manuscdn.com/user_upload_by_module/session_file/310519663397256317/FohwiWsxfDuKRyfm.png` |
| Quadrat Farbe (Favicon) | `https://files.manuscdn.com/user_upload_by_module/session_file/310519663397256317/nylTNccsmhZnDMZh.png` |
| Quadrat Weiß | `https://files.manuscdn.com/user_upload_by_module/session_file/310519663397256317/pQrwnphYdfilTakM.png` |

---

## 4. Projekt 2: Milentas Service24

### Firmendaten

| Feld | Wert |
|------|------|
| Firma | Milentas Service 24 UG (haftungsbeschränkt) |
| Geschäftsführer | Abudú Rodrigues Pires Da Costa |
| Firmensitz | Soldiner Straße 37, 13359 Berlin |
| HRB | 286043 (AG Berlin Charlottenburg) |
| Telefon | +49 30 12345678 (**PLATZHALTER – muss ersetzt werden!**) |
| WhatsApp | wa.me/493012345678 (**PLATZHALTER – muss ersetzt werden!**) |
| E-Mail | info@milentas-service24.de |
| Branche | Hausmeisterservice & Gebäudereinigung Berlin |

### Technologie

- **Reines statisches HTML/CSS/JS** – kein Framework, kein Build-Prozess
- Jede Seite ist eine eigenständige `index.html` in ihrem Ordner
- CSS ist inline in jeder HTML-Datei (für Performance)
- Deployment: Einfach den gesamten Ordner zu Cloudflare Pages hochladen

### Design-System

| Variable | Wert | Verwendung |
|----------|------|------------|
| `--primary` | `#1B4D3E` | Forest Grün (Hauptfarbe) |
| `--primary-dark` | `#0F2E25` | Dunkles Grün (Hintergründe) |
| `--primary-light` | `#2D7A5F` | Helleres Grün (Hover) |
| `--accent` | `#F59E0B` | Gold/Amber (CTAs, Buttons) |
| `--accent-light` | `#FCD34D` | Helles Gold |

### Seiten (30 Stück)

**Leistungsseiten (9):**

| URL | Titel |
|-----|-------|
| `/hausmeisterservice/` | Hausmeisterservice Berlin |
| `/gebaeudereinigung/` | Gebäudereinigung Berlin |
| `/treppenhausreinigung/` | Treppenhausreinigung Berlin |
| `/buroreinigung/` | Büroreinigung Berlin |
| `/fensterreinigung/` | Fensterreinigung Berlin |
| `/grundreinigung/` | Grundreinigung Berlin |
| `/unterhaltsreinigung/` | Unterhaltsreinigung Berlin |
| `/winterdienst/` | Winterdienst Berlin |
| `/gartenarbeit/` | Gartenpflege Berlin |

**Bezirksseiten (17):**

| URL | Bezirk |
|-----|--------|
| `/charlottenburg/` | Charlottenburg |
| `/friedrichshain/` | Friedrichshain |
| `/kreuzberg/` | Kreuzberg |
| `/lichtenberg/` | Lichtenberg |
| `/marzahn/` | Marzahn-Hellersdorf |
| `/mitte/` | Mitte |
| `/neukoelln/` | Neukölln |
| `/pankow/` | Pankow |
| `/prenzlauer-berg/` | Prenzlauer Berg |
| `/reinickendorf/` | Reinickendorf |
| `/schoeneberg/` | Schöneberg |
| `/spandau/` | Spandau |
| `/steglitz/` | Steglitz |
| `/tempelhof/` | Tempelhof |
| `/treptow-koepenick/` | Treptow-Köpenick |
| `/wedding/` | Wedding |
| `/wilmersdorf/` | Wilmersdorf |

**Sonstige:**

| URL | Seite |
|-----|-------|
| `/` | Startseite |
| `/impressum/` | Impressum |
| `/datenschutz/` | Datenschutzerklärung |
| `/404.html` | Fehlerseite |

### Dateistruktur

```
milentas-service24/
├── index.html              ← Startseite
├── 404.html                ← Fehlerseite
├── sitemap.xml             ← XML-Sitemap
├── robots.txt              ← Crawler-Regeln
├── _headers                ← Security Headers
├── _redirects              ← www → non-www
├── favicon.ico             ← Favicon
├── favicon-16x16.png
├── favicon-32x32.png
├── apple-touch-icon.png
├── assets/
│   ├── logo_horizontal.png      ← Header-Logo (Desktop)
│   ├── logo_horizontal_dark.png ← Logo auf hellem Hintergrund
│   └── logo_icon_only.png       ← Icon-Logo (Mobile + Favicon)
├── hausmeisterservice/index.html
├── gebaeudereinigung/index.html
├── ... (weitere Leistungen)
├── charlottenburg/index.html
├── ... (weitere Bezirke)
├── impressum/index.html
├── datenschutz/index.html
└── README.md
```

### Formulare

**ACHTUNG:** Die Formulare auf Milentas zeigen aktuell nur eine Erfolgsmeldung, senden aber KEINE Daten irgendwohin! Die `handleSubmit`-Funktion ersetzt lediglich das Formular durch eine "Vielen Dank"-Nachricht.

**TODO:** Telegram-Integration oder E-Mail-Versand muss noch eingebaut werden.

### Logo

Das Logo liegt lokal im `assets/`-Ordner:
- `logo_horizontal.png` → Desktop-Header (auf dunklem Hintergrund)
- `logo_horizontal_dark.png` → Auf hellem Hintergrund
- `logo_icon_only.png` → Mobile-Header + Favicon

Farben: Forest Grün + Gold, Gebäude-Symbol mit "24"-Uhr und Sternen.

### Deploy

```bash
# Kein Build nötig – einfach den Ordner deployen
export CLOUDFLARE_API_TOKEN=<token>
export CLOUDFLARE_ACCOUNT_ID=c6c3c56f9197fddc30b649f2f4395e72
npx wrangler pages deploy . --project-name=milentas-service24 --branch=main
```

---

## 5. Projekt 3: Firmenanschrift Berlin Mieten

### Firmendaten

| Feld | Wert |
|------|------|
| Betreiber | Milentas Service 24 UG (haftungsbeschränkt) |
| Marke | "Firmenanschrift Berlin Mieten" |
| Geschäftsführer | Abudú Rodrigues Pires Da Costa |
| Büroanschrift | Anhaltinerstraße 15-16, 14163 Berlin (Zehlendorf) |
| Firmensitz | Soldiner Straße 37, 13359 Berlin |
| HRB | 286043 (AG Berlin Charlottenburg) |
| Telefon | +49 30 12345678 (**PLATZHALTER – muss ersetzt werden!**) |
| WhatsApp | wa.me/493012345678 (**PLATZHALTER – muss ersetzt werden!**) |
| E-Mail | info@firmenanschrift-berlin-mieten.de |
| Branche | Virtuelles Büro / Geschäftsadresse Berlin |

### Technologie

- **Reines statisches HTML/CSS/JS** – kein Framework, kein Build-Prozess
- Identische Architektur wie Milentas
- CSS inline in jeder HTML-Datei

### Design-System

| Variable | Wert | Verwendung |
|----------|------|------------|
| `--primary` | `#1E3A5F` | Dunkelblau (Hauptfarbe) |
| `--primary-dark` | `#0F1F33` | Sehr dunkles Blau |
| `--primary-light` | `#2D5F8A` | Helleres Blau |
| `--accent` | `#E8B931` | Gold (CTAs, Buttons) |
| `--accent-light` | `#F5D76E` | Helles Gold |
| `--accent-dark` | `#C49B1A` | Dunkles Gold |

### Preismodell

| Paket | Preis/Monat | Leistungen |
|-------|-------------|------------|
| Basis | 39,90€ | Ladungsfähige Adresse, Postannahme, monatliche Weiterleitung |
| Business | 59,90€ | + wöchentliche Weiterleitung + Scan-Service |
| Premium | 149,90€ | + tägliche Weiterleitung + Telefonservice mit 030-Nummer |

### Seiten (9 Stück)

| URL | Titel | Keyword |
|-----|-------|---------|
| `/` | Firmenanschrift Berlin mieten | firmenanschrift berlin mieten |
| `/firmenanschrift-mieten/` | Firmenanschrift mieten Berlin | firmenanschrift mieten |
| `/geschaeftsadresse/` | Geschäftsadresse Berlin mieten | geschäftsadresse berlin |
| `/virtuelles-buero/` | Virtuelles Büro Berlin mieten | virtuelles büro berlin |
| `/briefkasten-mieten/` | Briefkasten mieten Berlin | briefkasten mieten |
| `/postservice/` | Postservice Berlin | postservice berlin |
| `/gewerbeanmeldung-adresse/` | Adresse für Gewerbeanmeldung | gewerbeanmeldung adresse |
| `/impressum-adresse/` | Impressum-Adresse mieten | impressum adresse mieten |
| `/impressum/` | Impressum | – |
| `/datenschutz/` | Datenschutzerklärung | – |

### Dateistruktur

```
firmenanschrift-berlin-mieten/
├── index.html                      ← Startseite
├── 404.html                        ← Fehlerseite
├── sitemap.xml                     ← XML-Sitemap
├── robots.txt                      ← Crawler-Regeln
├── _headers                        ← Security Headers
├── _redirects                      ← www → non-www
├── firmenanschrift-mieten/index.html
├── geschaeftsadresse/index.html
├── virtuelles-buero/index.html
├── briefkasten-mieten/index.html
├── postservice/index.html
├── gewerbeanmeldung-adresse/index.html
├── impressum-adresse/index.html
├── impressum/index.html
├── datenschutz/index.html
└── README.md
```

### Formulare

**ACHTUNG:** Identisch zu Milentas – Formulare zeigen nur Erfolgsmeldung, senden aber KEINE Daten!

**TODO:** Telegram-Integration oder E-Mail-Versand muss noch eingebaut werden.

### Deploy

```bash
export CLOUDFLARE_API_TOKEN=<token>
export CLOUDFLARE_ACCOUNT_ID=c6c3c56f9197fddc30b649f2f4395e72
npx wrangler pages deploy . --project-name=firmenanschrift-berlin-mieten --branch=main
```

---

## 6. Deployment-Anleitung (alle Projekte)

### Voraussetzungen

```bash
# Node.js (v18+) und pnpm installieren
npm install -g pnpm wrangler

# Umgebungsvariablen setzen
export CLOUDFLARE_API_TOKEN=<token>
export CLOUDFLARE_ACCOUNT_ID=c6c3c56f9197fddc30b649f2f4395e72
```

### Adama Global Trade (React-Projekt)

```bash
cd adama
pnpm install
pnpm build
node scripts/prerender.mjs
npx wrangler pages deploy dist/public --project-name=adama-global-trade
```

### Milentas Service24 (statisches HTML)

```bash
cd milentas-service24
npx wrangler pages deploy . --project-name=milentas-service24 --branch=main
```

### Firmenanschrift Berlin (statisches HTML)

```bash
cd firmenanschrift-berlin-mieten
npx wrangler pages deploy . --project-name=firmenanschrift-berlin-mieten --branch=main
```

### Nach dem Deployment: GitHub Push

```bash
git add -A
git commit -m "Beschreibung der Änderung"
git push https://ericosoares10:<TOKEN>@github.com/ericosoares10/<REPO>.git main
```

---

## 7. Wichtige Regeln für KI-Bearbeitung

### Allgemein (alle Projekte)

1. **NIEMALS** Credentials in Code oder Commits speichern
2. **IMMER** nach Änderungen deployen UND zu GitHub pushen
3. **IMMER** Sitemap aktualisieren wenn neue Seiten hinzukommen
4. **IMMER** testen ob die Seite nach Änderungen noch funktioniert
5. **NIEMALS** die Telefonnummer +493012345678 als echte Nummer verwenden (ist Platzhalter!)

### Adama-spezifisch

1. **NIEMALS** Framer Motion importieren – CSS-Animationen verwenden (`FadeIn.tsx`)
2. **NIEMALS** `seo-data.ts` oder `App.tsx` ohne Verständnis des Systems ändern
3. **IMMER** nach Code-Änderungen den vollständigen Deploy-Workflow ausführen (Build → Prerender → Deploy)
4. **IMMER** Sitemap nach neuen Seiten generieren: `node scripts/generate-sitemap.mjs`
5. **KEIN Blau** auf der Seite – Farbpalette ist Kupfer/Gold + Anthrazit
6. Neue SEO-Seiten: Nur Eintrag in `seo-data.ts` nötig
7. Neue Blog-Beiträge: Eintrag in `blog-data.ts` + Checkbox im Content-Plan aktualisieren
8. Bilder: Lokal in `client/public/images/` oder CDN-URLs aus `content.ts`

### Milentas & Firmenanschrift-spezifisch

1. Jede Seite ist eine eigenständige HTML-Datei – Änderungen müssen in JEDER Datei gemacht werden wenn sie global sind (z.B. Header, Footer, Navigation)
2. CSS ist inline – keine externe Stylesheet-Datei
3. Kein Build-Prozess nötig – direkt deployen

---

## 8. Offene TODOs

### Priorität HOCH

| Projekt | TODO | Details |
|---------|------|---------|
| Milentas | Formulare funktionsfähig machen | Telegram-Integration oder E-Mail-Versand einbauen |
| Firmenanschrift | Formulare funktionsfähig machen | Telegram-Integration oder E-Mail-Versand einbauen |
| Milentas | Echte Telefonnummer einsetzen | +493012345678 ist Platzhalter! |
| Firmenanschrift | Echte Telefonnummer einsetzen | +493012345678 ist Platzhalter! |
| Adama | E-Mail-Versand einrichten | SMTP/Resend für info@adamaglobaltrade.de |

### Priorität MITTEL

| Projekt | TODO | Details |
|---------|------|---------|
| Alle 3 | Google Search Console einrichten | Sitemaps einreichen, Indexierung prüfen |
| Alle 3 | Google Business Profile erstellen | Lokale Sichtbarkeit |
| Adama | Blog-Beiträge schreiben | 104 Themen geplant, 2/Woche |
| Adama | Backlinks aufbauen | WLW, Europages, IHK, Branchenverzeichnisse |
| Milentas | Backlinks aufbauen | Gelbe Seiten, 11880, lokale Verzeichnisse |

### Priorität NIEDRIG

| Projekt | TODO | Details |
|---------|------|---------|
| Alle 3 | Analytics einbinden | Google Analytics oder Plausible |
| Alle 3 | Bing Webmaster Tools | Sitemap einreichen |
| Adama | Schema.org erweitern | Organization, BreadcrumbList |
| Milentas | Bewertungen sammeln | Google Reviews |

---

## Anhang: Schnellreferenz für häufige Aufgaben

### Neuen Blog-Beitrag für Adama schreiben

1. Thema aus `content-plan-104-blogposts.md` wählen
2. Beitrag in `client/src/lib/blog-data.ts` hinzufügen (Format der bestehenden 3 Beiträge folgen)
3. Checkbox im Content-Plan aktualisieren: `[ ]` → `[x]`
4. Build + Prerender + Deploy

### Neue SEO-Seite für Adama hinzufügen

1. Eintrag in `client/src/lib/seo-data.ts` (cities/countries/longTail Array)
2. Sitemap generieren: `node scripts/generate-sitemap.mjs`
3. Build + Prerender + Deploy

### Neue Leistungsseite für Milentas hinzufügen

1. Bestehende Leistungsseite kopieren (z.B. `hausmeisterservice/index.html`)
2. Titel, Meta-Tags, H1, Content anpassen
3. In `sitemap.xml` eintragen
4. Navigation in ALLEN HTML-Dateien aktualisieren (Header + Footer)
5. Deploy

### Telefonnummer auf Milentas/Firmenanschrift ändern

1. In ALLEN HTML-Dateien suchen und ersetzen:
   - `tel:+493012345678` → `tel:+49XXXXXXXXXXX`
   - `wa.me/493012345678` → `wa.me/49XXXXXXXXXXX`
   - Angezeigte Nummer im Text
2. Deploy

---

*Ende der Dokumentation. Bei Fragen: Alle Details stehen in den jeweiligen README.md und docs/ Ordnern der Repositories.*
