# Dateiformat-Grundarchitektur – Entscheidungen FF-01 bis FF-20

Status: vom Projektinhaber beantwortet  
Stand: 2026-11-01

Diese Datei hält die bestätigten Grundentscheidungen für die nativen Projekt- und Komponentenformate fest. Sie ist eine Architekturentscheidungssammlung, noch keine vollständige technische Spezifikation der einzelnen Formate.

## Bestätigte Anforderungen

- **FF-01 – Klare Aufgabenverteilung: Ja.** Jedes Format soll eine klar abgegrenzte Aufgabe haben. Beispielsweise gehören Timeline-Daten nicht unnötig in Effektdateien.
- **FF-02 – Verknüpfbarkeit: Ja.** Formate dürfen aufeinander verweisen, etwa Timeline auf Effekte, Animationen und Medien.
- **FF-03 – Projektordner aus Einzeldateien: Ja.** Ein Projekt soll aus mehreren eigenständigen Dateien in einem gemeinsamen Projektordner bestehen.
- **FF-04 – Kleine Haupt-/Manifestdatei: Ja.** Eine zentrale Datei soll die Komponenten und ihre Speicherorte auflisten, damit das Projekt vollständig wiederhergestellt werden kann.
- **FF-05 – Komponenten einzeln bearbeiten: Ja.** Teil-Dateien sollen möglichst unabhängig vom gesamten Projekt geöffnet und bearbeitet werden können.
- **FF-06 – Menschenlesbarkeit: Nicht zwingend.** Nicht jedes Format muss menschenlesbar sein. Das Format wird nach Zweck und Anforderungen gewählt.
- **FF-07 – Binäre Formate: Ja, wenn sinnvoll.** Binäre Speicherung ist zulässig, sofern sie keine Qualitätseinbußen verursacht.
- **FF-08 – Paketformate: Ja.** Ein Format darf mehrere zugehörige Dateien bündeln, beispielsweise Effekte, Bilder, Vorschauen und Einstellungen.
- **FF-09 – Einheitlicher Dateikopf: Ja.** Formate sollen eine gemeinsame Grundstruktur besitzen, etwa Formatkennung, Versionsnummer, Projekt-ID und Erstellungsdatum.
- **FF-10 – Vollständige Dokumentation: Ja.** Jedes Format benötigt eine Erklärung aller Felder und ihrer Bedeutung.
- **FF-11 – Fehlende Komponenten erkennen: Ja.** Das Programm soll fehlende Dateien erkennen und konkret anzeigen, was fehlt.
- **FF-12 – Verschobene Projektordner finden: Ja.** Das Programm soll Komponenten nach einem Umzug oder auf einem anderen Computer wiederfinden können.
- **FF-13 – Eindeutige IDs: Ja.** Wichtige Komponenten erhalten stabile IDs, damit Verknüpfungen auch nach Umbenennungen erhalten bleiben.
- **FF-14 – Komponenten wiederverwenden: Ja.** Einzelne Komponenten wie Animationen oder Effektaufbauten sollen zwischen Projekten kopiert werden können.
- **FF-15 – Versionsstände: Separat als Dateien.** Unterschiedliche Bearbeitungsstände sollen als separate Dateien gespeichert werden, nicht als mehrere interne Stände in einer einzelnen Komponentendatei.
- **FF-16 – Externe Nutzung/API: Ja.** Formate sollen dokumentiert und über eine API von externen Programmen genutzt werden können.
- **FF-17 – Austausch mit anderen Schnittprogrammen: Ja.** Import und Export für Programme wie After Effects, DaVinci Resolve und Premiere Pro sind vorgesehen. Der tatsächlich mögliche Funktionsumfang muss je Zielformat geprüft werden.
- **FF-18 – Unbekannte Felder erhalten: Ja.** Ältere Programmversionen sollen unbekannte zukünftige Felder möglichst erhalten, damit Speichern keine neueren Daten zerstört.
- **FF-19 – Migration: Ja.** Alte Formate sollen auf neuere Versionen migriert werden können, ohne das Original zu überschreiben.
- **FF-20 – Format-Validator: Ja.** Ein Validator soll Struktur, Pflichtfelder, Referenzen und Kompatibilität überprüfen.

## Abgeleitete Architekturprinzipien

1. **Modular statt monolithisch:** Das Projekt besteht aus getrennten Komponenten-Dateien.
2. **Manifest als Einstiegspunkt:** Eine kleine Hauptdatei beschreibt die Projektstruktur und verweist auf die Komponenten.
3. **Stabile Identitäten:** Verknüpfungen beruhen auf IDs und nicht allein auf Dateinamen oder Ordnerpfaden.
4. **Nicht-destruktive Migration:** Konvertierungen erzeugen neue Dateien; Originale bleiben erhalten.
5. **Datenintegrität vor Kompaktheit:** Binäre oder gepackte Speicherung ist nur dann sinnvoll, wenn sie die Qualität und verlustfreie Wiederherstellbarkeit nicht beeinträchtigt.
6. **Vorwärts-Kompatibilität soweit möglich:** Unbekannte Felder und Erweiterungen sollen beim Laden und Speichern erhalten bleiben.
7. **Offene Spezifikation:** Dokumentation und APIs sollen Drittanbieter-Integrationen ermöglichen.
8. **Validierung:** Projektdateien und ihre Beziehungen müssen automatisiert prüfbar sein.

## Noch zu definieren

- Konkreter Aufbau und Dateiendung des Projekt-Manifests.
- Welche bestehenden Formate jeweils welche Daten besitzen.
- Ob Formate JSON, XML, CBOR, MessagePack, ZIP-basierte Container oder eigene binäre Strukturen verwenden.
- Wie IDs, relative Pfade, Prüfsummen und externe Asset-Referenzen funktionieren.
- Wie Konflikte bei gleichzeitig geänderten Komponenten erkannt werden.
- Welche Daten verlustfrei zwischen Fremdformaten übertragen werden können.
- Wie Formatversionen, Schema-Versionen und Migrationen nummeriert werden.
- Welche Felder unbekannte ältere Versionen sicher erhalten müssen.
