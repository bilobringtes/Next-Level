# NEXT LEVEL
### Lernen. Spielen. Aufsteigen.

**Ein Konzept von Bülent Uslu**
© 2026 Bülent Uslu · Alle Rechte vorbehalten.

---

## Was ist das?
Ein klickbarer HTML/CSS/JavaScript-Prototyp einer gamifizierten Lern-App für Mitarbeiter. Premium Apple-Keynote-Look in Schwarz-Rot-Weiß, mit permanent sichtbarem Handy-Rahmen (Desktop **und** Mobile).

**Dies ist Stufe 1 von 3** — 5 vollständig funktionale Screens:
1. **Splash** (1.5s beim ersten Öffnen)
2. **Startseite** (Hallo Michael, Level 7, 2450 XP, 6-Kachel-Menü)
3. **Missionen-Liste** (5 Themen: eSIM, 5G, GigaCube, Roaming, Telefonie)
4. **Quiz** (5 Fragen pro Mission, 100 XP je richtiger Antwort, Vibration, Sparkles, Confetti-Abschluss)
5. **Fortschritt** (Streak, KPIs, Stärken, XP-Verlauf-Chart, Liga)

Alle anderen Buttons/Kacheln zeigen einen Toast **„Kommt in Stufe 2 🚀"**.

---

## Wie öffnen?

### Desktop
Einfach `index.html` doppelklicken. Öffnet sich in Chrome, Safari, Firefox oder Edge — der Handy-Rahmen bleibt zentriert sichtbar.

### Auf einen Webserver hochladen
Alle Dateien (`index.html`, `manifest.json`, `sw.js`, `icons/`) in ein Verzeichnis hochladen. Fertig.

> **Hinweis:** Der Service Worker (`sw.js`) funktioniert nur über `http(s)://` — beim direkten Doppelklick per `file://` schlägt die Registrierung still fehl, aber die App läuft trotzdem. Für die vollständige „Zum Startbildschirm hinzufügen"-Erfahrung bitte auf einen Webserver hochladen (auch GitHub Pages, Netlify, Vercel — alle kostenlos).

### Als App aufs Handy installieren
1. URL im mobilen Browser öffnen (Safari auf iOS · Chrome auf Android)
2. **iOS Safari:** Teilen-Icon → „Zum Home-Bildschirm"
3. **Android Chrome:** Menü (⋮) → „Zum Startbildschirm hinzufügen" oder „App installieren"

Die App startet dann im Vollbild, ohne Browser-Chrome — genau wie eine native App.

---

## Wo den Content anpassen?

Alles in **einer Datei**: `index.html`

- **Quiz-Fragen** — Kommentar `/* -------- QUIZ-INHALT · HIER ANPASSEN -------- */` im `<script>`-Block. Struktur: `MISSIONS[i].questions[j] = { q, a:[…], correct:0 }`. Antwort mit Index `correct` ist die richtige.
- **Missionen-Meta** (Titel, Untertitel, Fortschritt, Icon) — dieselbe `MISSIONS`-Konstante am Anfang.
- **Benutzerdaten (Startwerte)** — `DEFAULT_STATE` direkt darüber (Name, Level, XP, Streak).
- **Farben & Design-System** — CSS-Custom-Properties ganz oben in `<style>`, `:root { --bg, --red, --white, … }`.
- **XP pro Antwort** — im `finishQuiz()`-Code (aktuell `quizState.correctCount * 100`).
- **Level-Formel** — `Math.ceil(state.xp / 500)` in `finishQuiz()`.

---

## Roadmap · Stufe 2

- **Battle-Screen** — 1-vs-1 Duell in Echtzeit gegen Kolleg\*innen
- **Rangliste** — Wochen-, Monats- und Gesamtranking mit Filialen-Filter
- **Profil-Screen** — Avatar-Anpassung, Einstellungen, Push-Notifications
- **Erfolge / Badges** — Sammlung, Fortschritt pro Badge, Freischalt-Animationen
- **Mehr Missionen** — Live-Content-Verwaltung über CMS-Backend

## Roadmap · Stufe 3

- **Backend-Anbindung** — echte User-Accounts, XP-Synchronisation, cross-device
- **Admin-Cockpit** — Content-Redaktion, Kampagnen, Analytics
- **AI-Fragengenerator** — automatisches Erstellen von Quiz-Fragen aus Produktunterlagen
- **Sprachversionen** — mehrsprachige Ausspielung

---

## Technische Umsetzung

- **Standalone** — eine einzige `index.html` mit inline CSS & JavaScript
- **Kein Framework, kein Build-Step** — reines Vanilla JS
- **Google Fonts** via `<link>` (Space Grotesk · Inter)
- **PWA** — `manifest.json` + `sw.js` mit Basic-Cache für Offline
- **State** — `localStorage` unter Schlüssel `nextlevel_user`
- **Vibration** — `navigator.vibrate` (in `try/catch`, kein Crash auf Desktop)

---

## Kontakt & Urheberrecht

**Konzept & Urheber:** Bülent Uslu
**Copyright:** © 2026 Bülent Uslu · Alle Rechte vorbehalten.

Dieser Prototyp ist eine Konzeptvorschau. Weitergabe, Nachbau oder kommerzielle Nutzung nur mit ausdrücklicher schriftlicher Zustimmung des Urhebers.
