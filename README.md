# Physiotherapie Lerntool

Ein webbasiertes Lerntool für den Physiotherapie-Unterricht: Quiz, Kurzfälle und Clinical-Reasoning-Fallbeispiele.

## Live-Adressen

- **Schüler:** https://physio-dozent.github.io/physio-tool/
- **Dozent (Dashboard):** https://physio-dozent.github.io/physio-tool/dashboard.html

## Aufbau des Repositories

```
/
├── index.html              ← Schüler-Frontend
├── dashboard.html          ← Auswertungs-Dashboard für den Dozenten (Login über Supabase Auth)
└── einheiten/
    ├── index.json          ← Liste aller verfügbaren Lerneinheiten
    ├── kurse.json          ← Semester, freigeschaltete Einheiten, Prüfwerte der Semester-Codes (nur über das Dashboard erzeugen)
    ├── demo-quiz.json      ← Beispiel-Quiz
    ├── demo-shortcase.json ← Beispiel-Kurzfall
    └── demo-reasoning.json ← Beispiel-Reasoning-Fall
```

## Eine neue Lerneinheit hinzufügen

1. JSON-Datei nach Vorlage erstellen und in den Ordner `einheiten/` legen
2. Den Eintrag in `einheiten/index.json` ergänzen
3. Beide Dateien per GitHub-Web-Interface hochladen → die Änderungen sind nach 1–2 Minuten live

## Anmeldung der Schüler:innen

Schüler:innen geben ihren Namen ein, beim ersten Mal zusätzlich den Code ihres Semesters. Das Semester
wählen sie nicht selbst: Die App leitet es aus dem Code ab, später aus dem Namen (letzte Einsendung).
Codes legt der Dozent im Dashboard-Tab *Sichtbarkeit* fest. Der Ablauf steht in `index.html` im Block
`ANMELDUNG`.

## Anmeldung im Dashboard

Das Dashboard nutzt **Supabase Auth** (E-Mail + Passwort). Im Quelltext steht kein Passwort und kein
Zugangs-Token mehr. Welche Konten Einsendungen lesen, ändern und löschen dürfen, legen die
Row-Level-Security-Policies der Tabelle `submissions` in Supabase fest (Prüfung der Nutzer-ID).

- Das Dozenten-Konto wird im Supabase-Dashboard unter Authentication → Users verwaltet.
- Die Sitzung gilt nur im geöffneten Tab. Tab schließen oder „Abmelden“ beendet sie.
- Schüler:innen brauchen kein Konto, ihre Einsendungen laufen weiter ohne Anmeldung.
