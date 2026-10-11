# Mein Archiv – iPhone-PWA, Version 0.1

## Funktionsumfang
- Kamera-/Bildimport sowie PDF- und Mail-Anhang-Import aus der Dateien-App.
- Speicherung der Originaldatei im Browser (IndexedDB).
- Regelbasierte Kategorievorschläge, editierbarer Name und Dokumentdatum, Suche in Name/Kategorie/manuell hinterlegtem Text, SHA-256-Dublettencheck identischer Dateien.
- **Optional** OCR von Bildern mit Tesseract.js (Internetverbindung und externe CDN-Bibliothek beim erstmaligen Aufruf erforderlich). Noch **keine PDF-OCR**.
- Einzeldatei-Export über iOS Teilen-Menü bzw. Download. Im Teilen-Menü „In Dateien sichern“ → „iCloud Drive“ auswählen.
- Export einer CSV-Übersicht.

## Installation ohne Mac
1. Dateien dieses Verzeichnisses auf einen HTTPS-Webhost hochladen, z. B. GitHub Pages oder Netlify. `index.html` muss zusammen mit `sw.js`, `manifest.webmanifest` und `icon.svg` im gleichen Verzeichnis liegen.
2. HTTPS-Adresse auf dem iPhone mit Safari öffnen.
3. Teilen → „Zum Home-Bildschirm“ → „Hinzufügen“.
4. Kamera-/PDF-Import testen. Für mehrseitige Scans zuerst in Apples Dateien-App scannen und die erzeugte PDF importieren.
5. Dokumente einzeln exportieren und im iCloud-Drive-Ordner (z. B. `Dokumentenarchiv/Versicherungen`) speichern. In dieser ersten Version wird die Kategorie nicht automatisch als iCloud-Ordner angelegt.

## Wichtige Grenzen
- Dies ist **kein** nativer Dokumentenscanner: kein Perspektivbeschnitt, keine automatische Kantenerkennung, kein mehrseitiger Fotoworkflow. Fotos bleiben JPG/PNG, PDFs bleiben PDFs.
- iOS-Safari-Web-Apps haben keinen frei verfügbaren Hintergrundzugriff auf iCloud Drive. **Keine automatische iCloud-Ablage oder Synchronisation**; das Browserarchiv kann bei Löschung von Websitedaten verloren gehen.
- Kein automatisches Einlesen von E-Mails und kein Hintergrundjob. Mail-Anhänge zunächst manuell aus Mail/Dateien importieren.
- Kein serverbasierter KI-Dienst, keine trainierte Dokumentenklassifikation, kein zuverlässiges Datum-/Absender-Parsing.
- Diese Demo-Version ist für erste Erfassung und lokale Nutzung, nicht als einzige dauerhafte Dokumentenablage geeignet. Dokumente über iCloud sichern, bevor du das Browserarchiv bereinigst.
- Für vollautomatischen iCloud-Mail-Ablage-Workflow wären beispielsweise iOS Kurzbefehle, iCloud-Ordneraktionen auf einem Mac oder eine separat autorisierte E-Mail-Integration samt sicherem Backend nötig. Im nächsten Ausbau API/Auth, OCR von PDFs, Datenbank, automatischer iCloud-Sync über eine zulässige Apple-Integration und Regelverwaltung planen.
- Das `icon.svg` kann als Homescreen-Icon je nach iOS-Version abweichen; für breite Kompatibilität kann zusätzlich ein 180x180 PNG generiert werden.

## Datenschutz
Lokale Dateien werden in IndexedDB gehalten. OCR lädt Tesseract.js von jsDelivr und Sprachdaten aus der Tesseract.js-Konfiguration. Keine eigene Server-Verarbeitung der Dokumente vorgesehen. Wenn du einen Drittanbieterhost verwendest, prüfe dessen Datenschutzbedingungen. Kein Authentifizierungsmechanismus außer iPhone-/Browser-Schutz.
