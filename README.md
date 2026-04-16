# Workflow Hub

Persönliche PWA für Alltags-Workflows mit Google-Login und Cloud-Sync via Firebase.

## Features

- Workflows mit Phasen, Schritten und Varianten erstellen
- Materialien mit Preisen und Kategorien verwalten
- Fortschritt per Checkboxen tracken
- Google-Login mit automatischem Cloud-Sync (Firestore)
- Offline-fähig als installierbare PWA
- Matrix-Terminal-Design

## Hosting

Die App wird über **Firebase Hosting** bereitgestellt:

```
https://workflow-hub-8b61c.web.app
```

### Deployment

```bash
npm install -g firebase-tools   # einmalig
firebase login                  # einmalig
firebase deploy                 # bei jeder Änderung
```

### Auf dem Handy installieren

1. URL in Chrome öffnen
2. Drei-Punkte-Menü → **"App installieren"** oder **"Zum Startbildschirm hinzufügen"**

## Dateistruktur

```
workflow-hub/
├── index.html          ← App (SPA)
├── firebase.json       ← Firebase Hosting Config
├── .firebaserc         ← Firebase Projekt-Referenz
├── manifest.json       ← PWA-Konfiguration
├── sw.js               ← Service Worker (Offline-Cache)
├── icons/
│   ├── icon-192.png
│   └── icon-512.png
└── workflows/
    └── auto-reinigung.html
```

## Firebase-Konfiguration

- **Authentication**: Google Sign-In
- **Firestore**: Workflows werden pro User gespeichert (`collection("workflows")`, gefiltert nach `authorId`)
- **Autorisierte Domains**: `workflow-hub-8b61c.web.app` (Firebase Console + Google OAuth Redirect-URI)
