# Tikker PWA (iPhone-ready, no App Store)

Dies ist die PWA-Version deiner HTML-App. Läuft auf iOS wie eine App (Vollbild, Icon), ohne Kosten und ohne Anmeldung.

## Struktur
- `index.html` – deine App, PWA-Metatags integriert
- `manifest.webmanifest` – App-Metadaten + Icons
- `sw.js` – Service Worker für Offline/Cache
- `icons/` – App-Icons (192, 512, 180 für iOS)

## Lokal testen
Ein einfacher Weg ist ein lokaler Webserver (z. B. Python):
```bash
cd tikker-pwa
python3 -m http.server 8080
```
Dann `http://localhost:8080` im Browser öffnen. Auf iPhone testest du am besten über ein LAN-Share (gleicher Router) oder legst direkt online ab (siehe Deploy).

## Deploy (gratis)
### GitHub Pages
1. Neues Repo `tikker-pwa` erstellen.
2. Inhalt dieses Ordners hochladen (index.html, manifest, sw.js, icons/).
3. In den Repo-Settings **Pages** aktivieren → Branch `main` → `/ (root)`.
4. Nach 1–2 Min ist die Seite online (URL steht in den Pages-Settings).

### Cloudflare Pages
1. Auf pages.new gehen, Repo verbinden oder Ordner hochladen.
2. Build-Einstellungen: **kein Build** (static), Output: `/`.
3. Fertig, danach bekommst du eine *.pages.dev-URL.

## Auf iPhone installieren
1. URL im **Safari** öffnen.
2. Teilen-Icon → **Zum Home-Bildschirm**.
3. Icon/Name anpassen → **Hinzufügen**.
4. Start über das Icon: läuft im Vollbild (Standalone).

## Hinweise (iOS)
- iOS zeigt **kein automatisches Install-Prompt**. Installation immer manuell über „Zum Home-Bildschirm“.
- Cross-Origin (Tailwind-CDN) wird nicht offline gecacht (bewusst). Online ist das ok; wenn du 100% offline willst, bundel Tailwind lokal.
- Bei inhaltlichen Änderungen: Seite neu laden, ggf. SW-Cache invalidieren (Version in `CACHE_NAME` erhöhen).

Viel Spaß 🚀