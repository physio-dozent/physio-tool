# Physiotherapie Lerntool

Ein webbasiertes Lerntool für den Physiotherapie-Unterricht: Quiz, Kurzfälle und Clinical-Reasoning-Fallbeispiele.

## Live-Adressen

- **Schüler:** https://physio-dozent.github.io/physio-tool/
- **Dozent (Dashboard):** https://physio-dozent.github.io/physio-tool/dashboard.html

## Aufbau des Repositories

```
/
├── index.html              ← Schüler-Frontend
├── dashboard.html          ← Auswertungs-Dashboard für den Dozenten
└── einheiten/
    ├── index.json          ← Liste aller verfügbaren Lerneinheiten
    ├── demo-quiz.json      ← Beispiel-Quiz
    ├── demo-shortcase.json ← Beispiel-Kurzfall
    └── demo-reasoning.json ← Beispiel-Reasoning-Fall
```

## Eine neue Lerneinheit hinzufügen

1. JSON-Datei nach Vorlage erstellen und in den Ordner `einheiten/` legen
2. Den Eintrag in `einheiten/index.json` ergänzen
3. Beide Dateien per GitHub-Web-Interface hochladen → die Änderungen sind nach 1–2 Minuten live

## Dashboard-Passwort wechseln

Standardpasswort: `aendern-bitte`

Zum Wechseln:
1. Datei `passwort-generator.html` lokal im Browser öffnen
2. Neues Passwort eingeben → SHA-256-Hash kopieren
3. In `dashboard.html` die Zeile `const DOCENT_PW_HASH = '...'` ersetzen
4. Datei committen
