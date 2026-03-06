# Making Competences Visible

## Abstract
Dieses Repository enthaelt die Praesentations- und Deploy-Struktur fuer das Projekt **Making Competences Visible** (PKM Summit 2026).

Ziel des Projekts ist es, Kompetenzen sichtbar, anschlussfaehig und vermittelbar zu machen, indem Inhalte in einem klaren Story-Format als Slide-Deck aufbereitet und ueber GitHub Pages publiziert werden.

Die fachlichen Inhalte liegen im Slidev-Deck unter `slidev/slides.md`, ergaenzt um Assets, Komponenten und Snippets.

## Projektstruktur
- `slidev/`: Slidev-Projekt (Praesentation, Assets, Konfiguration)
- `.github/workflows/deploy.yml`: GitHub Actions Workflow fuer Build und Deployment nach GitHub Pages

## Development
### Voraussetzungen
- Node.js (empfohlen: aktuelle LTS-Version)
- npm

### Lokale Entwicklung starten
```bash
cd slidev
npm install
npm run dev
```

Danach ist die Praesentation lokal im Browser verfuegbar (standardmaessig ueber Slidev auf Port 3030).

### Production Build
```bash
cd slidev
npm run build
```

Das Build-Ergebnis liegt unter `slidev/dist`.

### Export (optional)
```bash
cd slidev
npm run export
```

## Deployment
Das Deployment erfolgt ueber GitHub Actions mit dem Workflow `/.github/workflows/deploy.yml`.

Trigger:
- automatisch bei Push auf `main`
- manuell ueber `workflow_dispatch`

Der Workflow:
1. installiert Abhaengigkeiten in `slidev/`
2. baut das Deck mit passendem Base-Pfad fuer GitHub Pages
3. deployed `slidev/dist` nach GitHub Pages

## Lizenz
Dieses Projekt steht unter der MIT-Lizenz. Details siehe `LICENSE`.
