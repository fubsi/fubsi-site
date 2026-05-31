# 🎨 Frontend Architektur-Dokumentation: `fubsi.win`

Dieses Dokument beschreibt die reine Frontend-Architektur der persönlichen Website. Das Projekt ist als leichtgewichtige Single-Page-Application (SPA) konzipiert, die auf maximale Performance, sauberen Code und ein modernes "Tech-Boutique"-Design setzt.

## 1. Tech-Stack

* **Core-Framework:** Vue.js 3 (Nutzung der modernen Composition API via `<script setup>`)
* **Build-Tool:** Vite (für blitzschnelles Hot-Module-Replacement und hochoptimierte Produktions-Builds)
* **Routing:** Vue Router 4 (Client-Side Navigation)
* **Styling:** Natives CSS (Mobile-First, CSS-Variablen, Scoped Styles)

---

## 2. Verzeichnisstruktur

Die Codebase folgt einer strikten Trennung zwischen Layout-Rahmen, dynamischen Seiten und globalen Assets.

```text
src/
├── assets/         # Globale Stylesheets und statische Assets
│   └── agency.css  # Definition der CSS-Variablen (Theming) und des Hintergrund-Rasters
├── components/     # Wiederverwendbare, in sich geschlossene UI-Bausteine
│   ├── AppSidebar.vue
│   └── AppNav.vue
├── router/         # Konfiguration der SPA-Routen
│   └── index.js
├── views/          # Komplette Seiten-Ansichten (werden vom Router geladen)
│   ├── HomeView.vue
│   └── ProjectsView.vue
├── App.vue         # Root-Komponente und globales Layout-Gerüst
└── main.js         # Einstiegspunkt der Anwendung und Plugin-Initialisierung

```

---

## 3. Component-Architektur & Routing

Das User Interface ist in logische, modulare Bausteine unterteilt, um den Code wartbar und skalierbar zu halten:

* **Das Root-Layout (`App.vue`):** Dient als starrer Rahmen der Applikation. Hier werden statische Elemente wie das dekorative Hintergrund-Raster und die Navigation (`AppSidebar.vue`, `AppNav.vue`) verankert. Der eigentliche Seiteninhalt wird dynamisch über das `<router-view>` Element injiziert.
* **Views (Seiten-Komponenten):** Repräsentieren eigenständige Ansichten (z.B. Startseite, Projektübersicht). Sie bündeln den inhaltsspezifischen Code und agieren unabhängig voneinander.
* **Lazy Loading:** Um die initiale Ladezeit (Time-to-Interactive) drastisch zu reduzieren, werden nicht sofort benötigte Unterseiten (wie die `ProjectsView.vue`) im Router per dynamischem Import (`() => import(...)`) erst dann in den Browser geladen, wenn der User den entsprechenden Link anklickt.

---

## 4. Design-System & Styling-Strategie

Das Projekt verzichtet bewusst auf schwere CSS-Frameworks, um vollen Einfluss auf das maßgeschneiderte Design zu behalten und die Bundle-Größe minimal zu halten.

* **Globales Theming:** Farbpaletten (Backgrounds, Accents) und Typografie werden als CSS-Variablen im `:root`-Selektor der `agency.css` zentral verwaltet. Ein Farbwechsel (z.B. von Peach auf Ice-Blue) erfordert so nur die Änderung weniger Hex-Werte.
* **Mobile-First:** Das Basis-CSS innerhalb der Komponenten ist primär für mobile Viewports geschrieben. Komplexe Desktop-Layouts (wie die seitlich fixierte Sidebar oder das versetzte Raster) werden additiv über `@media (min-width: 768px)` Breakpoints aktiviert.
* **Scoped Styling:** Komponenten nutzen konsequent das Attribut `<style scoped>`. Dadurch generiert Vue einzigartige Daten-Attribute für die Klassen. Dies isoliert das CSS strikt auf die jeweilige Komponente und verhindert gefährliches Style-Bleeding im restlichen Projekt.