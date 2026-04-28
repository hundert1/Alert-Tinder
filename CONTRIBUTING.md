# Mitmachen bei Alert Tinder

Danke fürs Vorbeischauen. Das Wertvollste, was du beitragen kannst, ist **deine Erfahrung aus dem echten SOC-Alltag**. Neue Cases von aktiven Analysten machen dieses Tool schärfer als alles, was ich allein schreiben kann.

---

## Quick-Links

- 🆕 [Neuen Case einreichen](https://github.com/hundert1/alert-tinder/issues/new?template=case-suggestion.yml)
- 🐛 [Bug melden](https://github.com/hundert1/alert-tinder/issues/new?template=bug-report.yml)
- 💡 [Feature vorschlagen](https://github.com/hundert1/alert-tinder/issues/new?template=feature-request.yml)
- 💬 [Discussion eröffnen](https://github.com/hundert1/alert-tinder/discussions) (allgemeine Fragen, Q&A)

---

## Neue Cases einreichen

Das ist das Herz des Projekts. **Eröffne ein Issue** mit dem [Case-Vorschlag-Template](https://github.com/hundert1/alert-tinder/issues/new?template=case-suggestion.yml) — du musst nicht forken oder Code schreiben. Wenn der Case passt, integriere ich ihn.

### Was macht einen guten Case aus?

**1. Realistisch.** Basiert auf echten SOC-Patterns. Filmhacker-Stoff wird abgelehnt. Wenn du sagen kannst „genau dieses Pattern habe ich in Production-Logs gesehen" — perfekt. Wenn es eher „so könnte vielleicht ein APT theoretisch vorgehen" ist — weniger gut.

**2. Sanitized.** Keine echten:
- Firmennamen (nutze generisches wie `corp.local`, `ACME Corp`)
- IPs (nutze RFC1918-interne, public TEST-NET-Bereiche oder erfundene Hosting-ASNs)
- Usernames, die echten Mitarbeitern entsprechen
- Interne Projektnamen, Kundennamen, System-Identifier
- Echte Domains, die jemandem gehören (nutze `example.com`, ausgedachte Domains oder bekannte Test-Domains)

**3. Didaktisch wertvoll.** Die Lesson soll ein übertragbares Prinzip vermitteln. „Das war Malware" ist keine Lesson. „Sysmon-1 mit `OpenProcess+WriteProcessMemory` von einem Microsoft-signierten Updater ist ein Click-to-Run-Hot-Patching-Pattern, keine Injection — Detections sollten auf unsigned Injectors getuned werden" ist eine Lesson.

**4. Severity-realistisch.** Wenn es CRITICAL ist, soll es CRITICAL sein. Wenn du einen „Severity-lügt"-Case einreichst (z.B. HIGH/FP weil die Rule überreagiert), mache das in der Lesson explizit — solche Cases gehören zu den besten.

### Case-Struktur

Wenn du das Issue ausfüllst, siehst du Felder, die dem In-App-Schema entsprechen:

```
rule:        Detection-Name (wie er im SIEM stehen würde)
severity:    critical | high | medium | low
source:      Sensor/Quelle des Alerts (z.B. "Sysmon Event 1", "EDR Behavioral")
fields:      Key-Value-Paare, die der Analyst auf der Karte sieht
description: 2-4 Sätze Kontext
isReal:      true (TP) | false (FP)
verdict:     Warum TP oder FP — die Begründung der Analystin
lesson:      Verallgemeinerbare Erkenntnis, max ~4 Sätze
mitre:       MITRE-ATT&CK-Technique-IDs und Namen
hint:        Frage, die in die richtige Richtung schubst, ohne die Lösung zu verraten
```

### Themen-Lücken

Aktuell besonders willkommen:
- **macOS-spezifische Cases** (unterrepräsentiert)
- **Linux/Cloud-Native** (Kubernetes, GCP, Azure jenseits von M365)
- **OT/ICS** (falls du diese Spezialisierung hast)
- **Subtile Insider-Patterns** ohne Termination-Trigger
- **Severity-lügt-Cases** (LOW/TP und CRITICAL/FP)

Aktuell weniger gebraucht: noch mehr Active-Directory-Cases (gut abgedeckt) und generisches Windows-Phishing.

---

## Bugs melden

Nutze das [Bug-Report-Template](https://github.com/hundert1/alert-tinder/issues/new?template=bug-report.yml). Wichtig:
- Browser + Version
- Mobile oder Desktop
- Schritte zur Reproduktion
- Was du erwartet hast vs. was passiert ist
- Screenshot bei visuellen Bugs

---

## Features vorschlagen

Nutze das [Feature-Request-Template](https://github.com/hundert1/alert-tinder/issues/new?template=feature-request.yml). Bei größeren Ideen (neue Spielmodi, Multiplayer, etc.) bitte zuerst eine [Discussion eröffnen](https://github.com/hundert1/alert-tinder/discussions), damit wir vor PR-Arbeit reden können.

---

## Code-Beiträge

Bei Code-Änderungen:

1. Repository forken
2. Branch erstellen: `git checkout -b fix/kurze-beschreibung`
3. Änderungen machen — bleib bei einer einzigen HTML-Datei, keine Build-Pipeline
4. Auf Mobile testen (iOS Safari + Chrome Android) und Desktop
5. Pull Request einreichen

### Code-Stil

- Vanilla JavaScript, keine Frameworks
- 2-Space-Einrückung
- Inline-CSS in `<style>`-Tags ist OK — die Single-File-Architektur soll bleiben
- Keine Bundler, keine Transpiler, keine Dependencies, die `npm install` brauchen
- Nicht-offensichtliche Logik kommentieren, besonders rund um Swipe-Gesten und UEBA-Style-Scoring

### Was ich annehme

- Bug-Fixes
- Performance-Verbesserungen (besonders auf schwacheren Android-Geräten)
- Accessibility-Verbesserungen (Tastaturnavigation, Screenreader-Support)
- Neue Cases (über Issue, aber kleine PRs mit Cases sind auch willkommen)
- Übersetzungen (vorher Issue eröffnen, damit wir uns abstimmen)

### Was ich wahrscheinlich ablehne

- Größere architektonische Änderungen (React-Rewrite, Build-Pipeline, etc.) — Single-File ist ein Feature
- Features, die ein Backend brauchen, ohne starke Begründung
- Tracking, Analytics oder Telemetry über das hinaus, was schon da ist (nichts)
- Monetarisierungs-Features

---

## Code of Conduct

Sei nett. SOC-Leute stehen meistens unter Druck und sind müde. Sei nicht das Arschloch in den Comments.

Diskriminierung, Belästigung und persönliche Angriffe werden nicht toleriert. Meinungsverschiedenheiten zu technischen Entscheidungen sind OK — und erwünscht.

---

## Lizenz

Mit deinem Beitrag stimmst du zu, dass:

- **Code-Beiträge** unter [AGPL-3.0-or-later](LICENSE-CODE) lizenziert sind
- **Inhalts-Beiträge** (Cases, Glossar, Lessons) unter [CC BY-NC-SA 4.0](LICENSE-CONTENT) lizenziert sind

Du behältst das Copyright an deinem Beitrag, gibst dem Projekt aber das Recht, ihn unter diesen Lizenzen zu vertreiben.

---

Danke nochmal. Schon ein einziger gut geschriebener Case hilft jedem Analysten, der das Tool nach dir spielt.

— Torben (@hundert1)
