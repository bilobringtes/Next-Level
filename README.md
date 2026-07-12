# NEXT LEVEL — v1.1
### Die Lern-App, die sich anfühlt wie ein Spiel.

**Ein Konzept von Bülent Uslu**
© 2026 Bülent Uslu · Alle Rechte vorbehalten.

---

## Was ist neu in v1.1?

Basierend auf deinem Review-Feedback:

- ✨ **Karrierepfad-System** (Sales / Service / Leadership) — jeder Nutzer wählt seinen Track, Missionen filtern sich entsprechend
- ✅ **Battle raus aus Stufe 1** → Battle-Kachel zeigt „Kommt in Stufe 2 🚀"
- ✅ **Rangliste** ist jetzt voll klickbar (Podium, Top 12, „Mein Track / Alle / Diese Woche"-Filter)
- ✅ **Profil-Screen** neu — Avatar, Track-Badge, KPI-Karten, Menü (Fortschritt · Erfolge · Karrierepfad wechseln · Benachrichtigungen · Demo zurücksetzen)
- ✨ **Leitidee** „Die Lern-App, die sich anfühlt wie ein Spiel." als sichtbares Element auf Splash + Home
- ✨ **Track-Wechsel** jederzeit möglich (via Home-Chip, Profil-Menü, oder Missionen-Hint)

---

## Die 7 Screens

1. **Splash** — 1,5 s Intro mit Leitidee
2. **Karrierepfad-Auswahl** — Sales / Service / Leadership (nur beim ersten Öffnen oder auf Wunsch)
3. **Startseite** — Hallo Michael, Track-Chip, Level 7, 2450 XP, 6-Kachel-Menü
4. **Missionen** — 3 Missionen pro Track (also 9 total), Track-Hinweis oben mit Wechsel-Link
5. **Quiz** — 5 Fragen je Mission, 100 XP je richtiger Antwort, Vibration, Sparkles, Confetti-Ergebnis
6. **Rangliste** — Podium, Filter (Mein Track / Alle / Diese Woche / Filiale), DU rot hervorgehoben
7. **Fortschritt** — Streak-Karte, 3 KPIs, Stärken-Balken, XP-Chart, Liga
8. **Profil** — Avatar, Track-Badge, Menü zum Wechseln des Tracks

„Battle · Puzzle" → zeigen Toast „Kommt in Stufe 2 🚀"

---

## Content in `index.html` anpassen

Alle Bearbeitungspunkte sind im JavaScript-Block klar markiert:

- **Karrierepfade** → Konstante `TRACKS = { sales, service, leadership }`
- **Missionen pro Track** → Konstante `MISSIONS` (jede Mission hat `track:"sales"` / `"service"` / `"leadership"`)
- **Quiz-Fragen** → `MISSIONS[i].questions[j] = { q, a:[…], correct: 0 }`
- **Rangliste** → Konstante `LEADERBOARD = { sales:[…], service:[…], leadership:[…] }`
- **Startwerte** → Konstante `DEFAULT_STATE`
- **Farben** → CSS-Custom-Properties `:root { --red, --bg, … }` ganz oben im `<style>`-Block

---

## Wie öffnen?

### Desktop
Einfach `index.html` doppelklicken.

### iPhone / Android
Ordner auf einen Webserver hochladen (GitHub Pages, Netlify, Vercel — kostenlos), URL im mobilen Browser öffnen → Teilen → **„Zum Startbildschirm hinzufügen"** → App startet im Vollbild.

---

## Empfohlener Version-Plan (aus Review)

### Version 1 (dieses Paket)
- Login (Track-Auswahl als leichte Onboarding-Version)
- Missionen (Karrierepfad-basiert)
- Quiz
- XP · Level
- Rangliste
- Profil
- Fortschritt

### Version 2 (später)
- Battle (1-vs-1 Live-Duell)
- Puzzle
- Wochen-Challenges
- Mystery-Boxen

### Version 3 (Skalierung)
- Backend, echte User-Accounts, cross-device Sync
- Admin-Cockpit (Content-Redaktion, Kampagnen, Analytics)
- KI-Fragengenerator aus Produktunterlagen
- Mehrsprachigkeit

---

## Technische Umsetzung

- Standalone `index.html` mit inline CSS & JS — kein Framework, kein Build
- Google Fonts (Space Grotesk · Inter)
- PWA-Manifest + Service Worker
- State via `localStorage` unter `nextlevel_user`

---

## Kontakt & Urheberrecht

**Konzept & Urheber:** Bülent Uslu
**Copyright:** © 2026 Bülent Uslu · Alle Rechte vorbehalten.
