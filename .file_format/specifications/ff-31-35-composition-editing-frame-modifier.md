# Dateiformate – Aufgabenfestlegung FF-31 bis FF-35

Status: vom Projektinhaber bestätigt  
Stand: 2026-11-01  
Geltungsbereich: vorläufige fachliche Aufgabenbeschreibung; technische Schemas folgen später.

## Grundsatz

Jedes Dateiformat soll eine eigene, klar abgegrenzte Aufgabe haben. Die folgenden fünf Formatideen wurden bestätigt. Die endgültigen Datenfelder und Abgrenzungen werden später anhand konkreter Arbeitsabläufe festgelegt.

## FF-31 – `.vcd`: Video Composition Data

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Die eigentlichen Daten einer Videokomposition speichern.

Mögliche Inhalte:
- Kompositionsobjekte und deren IDs.
- Eigenschaften und Einstellungen der Objekte.
- Beziehungen und Verknüpfungen zwischen Objekten.
- Kompositionsbezogene Parameter und Strukturinformationen.
- Referenzen auf getrennte Timeline-, Effekt-, Animations- und Asset-Dateien.

Abgrenzung: `.vcd` soll die Kompositionsdaten selbst enthalten. Wie sich diese Daten von der Kompositionsbeschreibung in `.cut` und dem Paketformat `.vcb` unterscheiden, muss in der Gesamtspezifikation präzisiert werden.

## FF-32 – `.vcr`: Video Composition Record

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Aufzeichnungen und nachvollziehbare Zustände einer Videokomposition speichern.

Mögliche Inhalte:
- Aufgezeichnete Kompositionszustände.
- Zustandsänderungen und Ereignisse.
- Zeitpunkte und betroffene Kompositionsobjekte.
- Verweise auf vorherige oder nachfolgende Zustände.
- Informationen zur Wiederherstellung oder Analyse früherer Zustände.

Abgrenzung: `.vcr` ist für Kompositionsaufzeichnungen vorgesehen. Die Beziehung zum allgemeinen Änderungsprotokoll `.edt` und zur Speicherung separater Versionsstände muss später geklärt werden.

## FF-33 – `.ved`: Video Editing Data

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Allgemeine Bearbeitungsdaten speichern, die nicht bereits eindeutig einem spezialisierten Format zugeordnet sind.

Mögliche Inhalte:
- Allgemeine Bearbeitungsoptionen und projektbezogene Editing-Einstellungen.
- Bearbeitungsmodi und Werkzeugkonfigurationen.
- Kontextbezogene Einstellungen für bestimmte Editing-Arbeitsabläufe.
- Referenzen auf spezialisierte Komponenten, falls erforderlich.

Abgrenzung: `.ved` darf nicht zu einem Sammelformat werden, das die Zuständigkeiten von `.tlf`, `.edt`, `.efx`, `.mt` oder anderen Formaten dupliziert. Für jedes Feld muss geprüft werden, ob es ein passenderes Fachformat gibt.

## FF-34 – `.vfx`: Video Frame Xchange

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Austausch einzelner Videoframes oder Frame-Sequenzen zwischen Editor, externen VFX-Werkzeugen und Renderprozessen ermöglichen.

Mögliche Inhalte:
- Frame-Daten oder Referenzen auf Frame-Bilddaten.
- Auflösung, Pixel-/Farbraum und Bittiefe.
- Bildnummern, Zeitstempel und Zeitbasis.
- Alpha-/Transparenzinformationen.
- Metadaten für Farbraum, HDR und relevante Bildattribute.
- Informationen zur Reihenfolge und Zuordnung einer Frame-Sequenz.

Abgrenzung: Das Format beschreibt den Frame-Austausch und dessen Metadaten. Es ist nicht automatisch ein Ersatz für ein vollständiges Videoformat oder einen verlustbehafteten Videocodec. Qualitäts- und Farbintegrität müssen bei der technischen Auswahl geschützt werden.

## FF-35 – `.vm`: Video Modifier

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Nicht-destruktive Modifikatoren und Anpassungen auf Videos oder Clips beschreiben.

Mögliche Inhalte:
- Transformationen wie Position, Skalierung, Rotation und Zuschnitt.
- Geschwindigkeits- und Zeitänderungen.
- Stabilisierung und weitere Clip-Anpassungen.
- Modifikatorparameter und deren Reihenfolge.
- Verweise auf Tracking-, Animations- oder Effektkomponenten.
- Aktivierungszustand und nicht-destruktive Verarbeitungsoptionen.

Abgrenzung: `.vm` beschreibt Modifikator-Anwendungen. Allgemeine Keyframe-/Bewegungsdaten bleiben im Animationsformat, und eigenständige Effekte werden im Effektformat beschrieben.

## Noch zu klärende Abgrenzungen

- `.vcd` gegenüber `.cut`: eigentliche Kompositionsdaten gegenüber Kompositions-/Timeline-Beschreibung.
- `.vcd` gegenüber `.vcb`: Datenstruktur gegenüber gebündeltem Kompositionspaket.
- `.vcr` gegenüber `.edt`: kompositionsbezogene Aufzeichnungen gegenüber allgemeinem Bearbeitungsprotokoll.
- `.vcr` gegenüber separaten Projektversionen: Aufzeichnungen/Zustände gegenüber eigenständigen gespeicherten Versionen.
- `.ved` gegenüber allen spezialisierten Editing-Formaten: klare Zuständigkeitsgrenzen, damit es kein unkontrolliertes Sammelformat wird.
- `.vfx` gegenüber etablierten Bildsequenz-/Frame-Interchange-Formaten: Interoperabilität und verlustfreie Übertragung.
- `.vm` gegenüber `.mt` und `.efx`: Modifikator-Konfiguration gegenüber Animation und Effektdefinition.

Alle fünf Formate bleiben als bestätigte Formatideen erhalten. Die endgültige Architektur wird nicht allein anhand der Namen, sondern anhand ihrer tatsächlichen Aufgaben und Datenabhängigkeiten festgelegt.
