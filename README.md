# Familien-Einkaufsliste – Version 3

## Installation
Die Dateien `index.html`, `app.js`, `styles.css`, `sw.js`, `manifest.webmanifest` und `icon.svg` gemeinsam in ein GitHub-Pages-Repository hochladen. Jeder öffnet dieselbe PWA-Adresse und kann sie am iPhone zum Home-Bildschirm hinzufügen. Keine Registrierung und keine Datenbank nötig.

## Gemeinsame Nutzung ohne Datenbank
1. Einen **gemeinsamen iCloud-Drive-Ordner** in der Apple-App „Dateien“ anlegen und mit der Familie teilen. Alternativ Backup-Dateien an eine gemeinsame Apple-Notiz anhängen.
2. Eine Person trägt Artikel ein und tippt unter **Backup → Backup exportieren**. Die erzeugte `.json`-Datei in den geteilten Ordner speichern.
3. Vor dem nächsten Einkauf laden andere Familienmitglieder die neueste Datei über **Backup importieren** in die PWA.
4. Nach eigenen Änderungen wieder ein neues Backup exportieren und im Ordner ablegen. **Das geschieht nicht automatisch.**

Es ist sinnvoll, die jeweils neueste Datei im geteilten Ordner kenntlich zu machen und alte Backups aufzubewahren oder später zu archivieren. Die PWA kann auf dem iPhone nicht von selbst Änderungen in Apple Notizen oder iCloud Drive erkennen.

## Daten und Zusammenführen
- Ein Import führt Stammdaten, aktive und entfernte Listeneinträge sowie Einkaufsereignisse anhand ihrer IDs zusammen, anstatt alles zu ersetzen. Eine lokale Sicherung wird vorher heruntergeladen.
- Die Historie unterscheidet `added` und `purchased`; Käufe, die rückgängig gemacht wurden, sind storniert. Entfernte erledigte Einträge werden intern als entfernt markiert, damit sie bei einem alten Backup nicht wieder auftauchen.
- **Grenze:** Wenn zwei Personen denselben Eintrag auf unterschiedlichen Geräten gleichzeitig verändern, entscheidet der letzte Änderungszeitstempel. Uhrzeit-Unterschiede der Geräte können die Konfliktauflösung beeinflussen. Auch gibt es keinen automatischen Abgleich: Alle müssen Backups bewusst austauschen.
- Backup-Dateien enthalten alle Artikel und die gesamte Einkaufsstatistik und sollten nur mit vertrauten Personen geteilt werden.

## Bedienung
Nur Artikelnamen eingeben. Stammdaten und Kategorie entstehen automatisch, die Kategorie ist manuell korrigierbar. Einkaufsort ist optional. Sortieren nach Name, Einkaufsort und Kategorie. Eingekauft abhaken, erledigte Artikel wahlweise ausblenden oder entfernen, ohne die Statistik zu verlieren.


## Version 4 – Bedarfsintervall
Im Reiter Statistik wird jetzt aus den Zeitpunkten der Listenaufnahmen pro Artikel berechnet, in welchem mittleren Abstand der Artikel benötigt wird (z. B. „Etwa alle 4 Tage benötigt“). Es werden mindestens zwei Listenaufnahmen benötigt. Dies ist ein rückblickender Durchschnitt, keine Vorhersage oder Erinnerungsfunktion. Käufe verändern den Bedarfsabstand nicht. Daten und Backup-Format bleiben unverändert.
