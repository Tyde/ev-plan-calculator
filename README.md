# EV-Ladepreis Vergleich

Ein einfaches Tool zum Vergleichen von Elektroauto-Ladetarifen in Deutschland.

## Features

- Vergleich verschiedener Lade-Abos (Grundgebühr + kWh-Preis)
- Zwei Diagramme: Effektiver Preis pro kWh und Gesamtkosten pro Monat
- Zoom-Funktion in den Diagrammen
- Anzeige des günstigsten Tarifs je nach Verbrauch
- Tarife ein-/ausblenden
- Import/Export von Tarifen als JSON
- Standardtarife werden aus `tarife.json` geladen

## Deployment auf GitHub Pages

1. Erstelle ein neues Repository auf GitHub

2. Lade die Dateien hoch:
   - `index.html`
   - `tarife.json`

3. Aktiviere GitHub Pages:
   - Gehe zu **Settings** → **Pages**
   - Unter **Source** wähle **Deploy from a branch**
   - Wähle **main** (oder **master**) und **/ (root)**
   - Klicke **Save**

4. Nach wenigen Minuten ist die Seite unter `https://<username>.github.io/<repository>/` erreichbar.

## Tarife anpassen

Bearbeite die Datei `tarife.json` im Repository:

```json
[
  {
    "name": "Tarif Name",
    "monthlyFee": 4.99,
    "kwhPrice": 0.39,
    "enabled": true
  }
]
```

Nach dem Commit werden die neuen Tarife automatisch geladen.

## Lokales Testen

Da die Seite `fetch()` verwendet, muss sie über einen lokalen Server geöffnet werden:

```bash
# Mit Python 3
python -m http.server 8000

# Mit Node.js (npx)
npx serve .
```

Dann öffne `http://localhost:8000` im Browser.

## Technologie

- React 18 (via CDN)
- Recharts für Diagramme
- Tailwind CSS für Styling
- Vanilla JavaScript, keine Build-Tools nötig
