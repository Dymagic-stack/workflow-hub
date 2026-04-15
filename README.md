# Workflow Hub

Persönliche PWA für Alltags-Workflows. Einmal installieren, alle Workflows über einen Hub erreichen.

## Setup (GitHub Pages)

1. Neues GitHub Repository erstellen (z.B. `workflow-hub`)
2. Alle Dateien in das Repository pushen
3. **Settings → Pages → Source: `main` branch** aktivieren
4. Warten bis die Seite live ist unter `https://DEIN-USERNAME.github.io/workflow-hub/`

## Auf dem Handy installieren

1. URL in Chrome öffnen
2. Drei-Punkte-Menü → **"App installieren"** oder **"Zum Startbildschirm hinzufügen"**
3. Fertig – App erscheint als eigenständiges Icon

## Neuen Workflow hinzufügen

1. HTML-Datei in `/workflows/` ablegen (z.B. `workflows/einkaufsliste.html`)
2. In `index.html` eine neue Tile einfügen:

```html
<a href="workflows/einkaufsliste.html" class="tile">
  <div class="tile-icon">🛒</div>
  <div>
    <div class="tile-label">Einkaufsliste</div>
    <div class="tile-desc">Wöchentliche Einkäufe</div>
  </div>
  <div class="tile-status">aktiv</div>
</a>
```

3. Workflow-Count im Header anpassen
4. Commit & Push – fertig

## Dateistruktur

```
workflow-hub/
├── index.html              ← Hub/Dashboard
├── manifest.json           ← PWA-Konfiguration
├── sw.js                   ← Service Worker (Offline-Cache)
├── README.md
├── icons/
│   ├── icon-192.png
│   └── icon-512.png
└── workflows/
    └── auto-reinigung.html ← Dein erster Workflow
```

## Wichtig

- `manifest.json`: Falls dein Repo NICHT `workflow-hub` heißt, passe `start_url` an
- Falls du das Repo unter einem Subpath hostest (z.B. `username.github.io/workflow-hub/`), 
  ändere `start_url` in `/workflow-hub/index.html`
