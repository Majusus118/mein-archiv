# Mein Archiv – iPhone v0.3

## GitHub Pages aktualisieren
1. Dieses ZIP entpacken. **Den Inhalt des Ordners** `MeinArchiv_v03_iPhone` (nicht den Ordner selbst) in das bestehende GitHub-Pages-Repository hochladen.
2. Bestehende `index.html`, `sw.js`, `manifest.webmanifest` und `icon.svg` ersetzen bzw. überschreiben und Änderungen committen.
3. In Safari die GitHub-Pages-Adresse öffnen und ggf. einmal neu laden. PWA erneut öffnen.

## Mehrseiten-Dokumente
- **Fotografieren**: erste Seite aufnehmen.
- **＋ Seite fotografieren**: weitere Seiten aufnehmen.
- Mit Pfeilen sortieren, ↻ drehen, × löschen.
- **Mehrseiten-PDF erstellen** zeigt die zusammengefasste Datei an; **Ins Archiv aufnehmen** erstellt ebenfalls ein PDF aus allen Seiten.
- Ein einzelnes Foto wird in Version 0.3 ebenfalls zu einer PDF.
- Zur PDF-Erstellung wird die öffentliche JavaScript-Bibliothek pdf-lib beim ersten Einsatz von jsDelivr geladen. Keine bewusste Dokumentenübertragung an diesen Server, aber externe Skripte sind ein Vertrauensrisiko. Keine Offline-Garantie beim ersten PDF-Export.

## Titel und Datum
- Datum steht **immer** vorne (YYYY-MM-DD). Eingabefeld `Dokumentdatum` kontrollieren: Die App kennt bei Fotos zunächst nur das aktuelle Datum, erkennt den tatsächlichen Briefdatumswert noch nicht zuverlässig.
- Vorschlag basiert auf Schlagworten im Dateinamen/ggf. OCR und Kategorie, nicht auf KI. Titel vor dem Speichern korrigierbar.

## Grenzen
- Speicherung lokal im Safari-Browser und erst nach explizitem Export in iCloud Drive. Die iPhone-App ist weiterhin nicht direkt mit dem Windows-Importdienst verbunden.
- Keine automatische iCloud-Synchronisation aus der Web-App. Große PDFs können den lokalen Speicherplatz belasten.
- Bestehende v0.1-Dokumente bleiben im selben IndexedDB-Speicher; die Dateinamen werden nicht nachträglich umbenannt.
- Keine automatische Kameraranderkennung und keine sichere automatische OCR aus allen PDF-Seiten.
- Sensible Dateien nicht im GitHub-Repository hochladen.
