# Alert Tinder

> Tinder-Style Alert-Triage-Trainer für Tier-1 SOC-Analysten. Mobile-first, eine HTML-Datei, keine Abhängigkeiten.

**🎮 [Jetzt spielen →](https://hundert1.github.io/Alert-Tinder/)**

[![License: AGPL v3](https://img.shields.io/badge/Code-AGPL_v3-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)
[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/Inhalte-CC_BY--NC--SA_4.0-green.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

---

## Was ist das?

Alert Tinder ist ein kostenloses Open-Source-Trainingstool für SOC-Tier-1-Analysten. Du swipest durch über 100 realistische Alert-Cases, entscheidest in Sekunden True Positive oder False Positive und kriegst sofort Feedback mit ausführlicher Lesson und MITRE-ATT&CK-Mapping.

Gebaut für die Art, wie Analysten wirklich lernen: in kurzen Bursts, in der Bahn, zwischen zwei Tickets. Kein Login, kein Tracking, keine Installation. Link aufmachen, swipen.

### Features

- **102+ realistische Alert-Cases** — Windows, Linux, macOS, Active Directory, M365, AWS, Kubernetes, Email-Security, Insider-Threats, Cloud-IAM, OT/IoT
- **MITRE-ATT&CK-Mapping** für jeden Case
- **260+ Glossar-Begriffe** mit kategorisiertem, durchsuchbarem Browser
- **Mobile-first Swipe-UI** inspiriert von Dating-Apps — schnelle Entscheidungen, schnelles Feedback
- **Didaktisch aufgebaut** — jede falsche Antwort kommt mit ausführlicher Erklärung
- **Severity-Lügen** — Cases bei denen die Severity-Anzeige bewusst trügt, damit Analysten lernen, dem Score nicht blind zu vertrauen
- **Hint-System** — begrenzte Hints pro Schicht wie ein echter Zeitbudget-Workflow
- **Streak-Tracking** und Rang-System (SOC Intern → Threat Hunter)
- **Keine Abhängigkeiten** — eine HTML-Datei, läuft offline nach erstem Aufruf

### Für wen ist das?

- **Tier-1 SOC-Analysten** die ihre Reflexe schärfen wollen
- **Tier-2/3 Senior-Analysten** die einen unterhaltsamen Weg zum Onboarding von Junioren suchen
- **Quereinsteiger** in der Vorbereitung auf SOC-Bewerbungsgespräche
- **Cybersecurity-Studierende** die realistische Praxis suchen
- **SOC-Manager** die ein niederschwelliges Trainings-Add-on wollen

---

## Spielen

1. Link öffnen
2. Es erscheint eine Karte mit einem Alert: Rule, Source, Host, User, Description, MITRE-Techniques
3. **Rechts swipen** (✕ Close) wenn du denkst, es ist ein False Positive
4. **Links swipen** (⚠ Escalate) wenn du denkst, es ist ein True Positive
5. Sofort-Feedback mit Verdict und ausführlicher Lesson
6. Nach jeder Schicht (5 Karten): Rang-Auswertung und Review der Fehler
7. Tippe auf unterstrichene Begriffe in einer Karte für die Glossar-Definition

Tippe auf das (i)-Icon für die Quick Reference. Tippe auf das Archiv-Icon, um alle gespielten Alerts und das vollständige Glossar zu durchstöbern.

---

## Tech-Stack

Eine HTML-Datei. Kein Build, kein Bundler, kein Framework, kein Backend.

- Vanilla JavaScript
- CSS (kein Tailwind, kein Preprocessor)
- LocalStorage für Fortschritt (kein Server)
- Google Fonts für die Typografie

Die ganze App ist eine Datei, weil das der ehrlichste Weg ist, ein Tool dieser Größe auszuliefern. Du kannst forken, speichern, irgendwo statisch hosten.

---

## Lokal laufen lassen

```bash
git clone https://github.com/hundert1/alert-tinder.git
cd alert-tinder
# Einfach index.html im Browser öffnen.
open index.html       # macOS
xdg-open index.html   # Linux
start index.html      # Windows
```

Für Entwicklung mit Live-Reload reicht jeder Static-Server:

```bash
npx serve .
# oder
python3 -m http.server 8000
```

---

## Mitmachen

Die wertvollsten Beiträge sind **neue Cases**. Wenn du als SOC-Analyst einen interessanten Alert gesehen hast, den du teilen willst — nur zu.

Siehe [CONTRIBUTING.md](CONTRIBUTING.md) für die Details. Quick-Links:

- 🆕 [Neuen Case einreichen](https://github.com/hundert1/alert-tinder/issues/new?template=case-suggestion.yml)
- 🐛 [Bug melden](https://github.com/hundert1/alert-tinder/issues/new?template=bug-report.yml)
- 💡 [Feature vorschlagen](https://github.com/hundert1/alert-tinder/issues/new?template=feature-request.yml)

Alle Cases müssen sein:
- **Realistisch** — basierend auf echten SOC-Patterns, kein Filmhacker-Stoff
- **Sanitized** — keine echten Firmennamen, IPs, Credentials, internen Projekte
- **Didaktisch wertvoll** — die Lesson soll ein übertragbares Prinzip vermitteln, nicht nur die Antwort

---

## Lizenz

Alert Tinder nutzt ein **Dual-License-Modell**:

- **Quellcode** unter [AGPL-3.0-or-later](LICENSE-CODE). Wer den Code modifiziert und als Service betreibt, muss den modifizierten Source veröffentlichen. Schützt vor stiller Kommerzialisierung.
- **Inhalte** (Cases, Glossar, Lessons, Hints) unter [CC BY-NC-SA 4.0](LICENSE-CONTENT). Du darfst sie für **nicht-kommerzielle** Zwecke teilen und anpassen, mit Namensnennung und unter gleicher Lizenz.

Im Klartext: **forken, lernen, fürs eigene Team einsetzen, zurückbeitragen. Nur nicht verkaufen.**

Wenn du die App kommerziell nutzen willst (z.B. als Teil eines bezahlten SOC-Trainings-Services oder als kundenseitiges Produkt), bitte ein Issue öffnen und Lizenz besprechen.

---

## Credits

Gemacht von **Torben Hallemann** ([@hundert1](https://github.com/hundert1)).

Gewidmet dem kollektiven Herzinfarkt aller SOC-Analysten, die nachts aus dem Bett geklingelt werden, weil das neue Backup-Skript vom Admin exakt so aussieht wie ein massiver Datenklau.

---

## English note

Alert Tinder is a German-language SOC training tool. The UI, all 102+ alert cases, the glossary, lessons, and hints are in German. An English version is not currently planned.

If you're interested in helping with internationalization, please [open a discussion](https://github.com/hundert1/alert-tinder/discussions).
