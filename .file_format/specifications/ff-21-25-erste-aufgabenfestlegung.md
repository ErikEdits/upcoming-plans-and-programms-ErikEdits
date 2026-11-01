# Dateiformate – erste Aufgabenfestlegung (FF-21 bis FF-25)

Status: vom Projektinhaber bestätigt  
Stand: 2026-11-01  
Geltungsbereich: vorläufige fachliche Aufgabenbeschreibung; technische Schemas folgen später.

## Grundsatz des Projektinhabers

Jedes Dateiformat soll eine eigene, klar abgegrenzte Aufgabe besitzen. Formate sollen nicht unnötig dieselben Informationen speichern oder sich gegenseitig ersetzen. Wenn später eine bislang nicht abgedeckte Aufgabe entsteht, dürfen weitere Dateiformate hinzukommen. Die vorhandenen Formate werden nicht künstlich auf eine feste Anzahl begrenzt.

Die nachfolgenden Zuständigkeiten sind erste Arbeitsdefinitionen. Bei der späteren vollständigen Spezifikation müssen Überschneidungen mit den übrigen Formaten geprüft und sauber abgegrenzt werden.

## FF-21 – `.cut`: Composition & Unified Timeline

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Eine vollständige Komposition beziehungsweise die zusammengeführte zeitliche Anordnung ihrer Bestandteile beschreiben.

Mögliche Inhalte:
- Verweise und Anordnung von Video-, Audio-, Text-, Grafik- und weiteren Spuren.
- Einbindung von Untersequenzen und verschachtelten Kompositionen.
- Zeitliche Platzierung und Beziehungen der Elemente innerhalb der Komposition.
- Referenzen auf separate Effekt-, Animations-, Medien- und andere Komponentendateien.

Abgrenzung: Die Datei soll nicht automatisch die vollständigen Definitionen aller Effekte, Animationen oder Mediendateien duplizieren. Sie beschreibt die Komposition und verweist auf die zuständigen Komponenten.

## FF-22 – `.edt`: Edit Data Tracker

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Bearbeitungsaktivitäten und Änderungen nachvollziehbar dokumentieren.

Mögliche Inhalte:
- Bearbeitungsschritte und Änderungsereignisse.
- Zeitpunkt und Urheber einer Änderung (Nutzer, KI-Agent oder automatisierter Prozess).
- Betroffene Projektkomponenten und deren IDs.
- Beschreibung der Änderung sowie Verweise auf vorherige und nachfolgende Zustände.
- Informationen, die Undo/Redo, Änderungsverlauf und Fehleranalyse unterstützen.

Abgrenzung: Das Format ist für Änderungs- und Bearbeitungsnachweise zuständig. Es ist nicht selbst die maßgebliche Speicherung des aktuellen Timeline- oder Kompositionszustands. Die konkrete Undo/Redo-Architektur wird später festgelegt.

## FF-23 – `.efx`: Effects Framework

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Einzelne Effekte, Effektparameter, Effektketten und wiederverwendbare Effektdefinitionen beschreiben.

Mögliche Inhalte:
- Effektkennung und Effektversion.
- Parameter und deren Wertebereiche.
- Reihenfolge und Verknüpfung mehrerer Effekte in einer Effektkette.
- Masken-, Tracking- oder andere erforderliche Referenzen.
- Optionale Keyframe-Referenzen, sofern die Animationsdaten selbst im zuständigen Animationsformat liegen.
- Preset- und Wiederverwendungsinformationen.

Hinweis: Der bisherige Langname lautete „Effects Framework XML“. Ob XML tatsächlich das verbindliche Speicherformat wird, ist noch offen. Die Endung und fachliche Aufgabe legen das Serialisierungsverfahren nicht automatisch fest.

Abgrenzung: `.efx` beschreibt Effektdefinitionen und deren Konfiguration. Allgemeine Bewegungs-/Animationskurven und Timeline-Platzierung gehören in die dafür zuständigen Formate.

## FF-24 – `.mt`: Motion

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Bewegungs- und Animationsdaten beschreiben.

Mögliche Inhalte:
- Position, Rotation, Skalierung und weitere animierbare Eigenschaften.
- Keyframes, Interpolation und zeitliche Kurven.
- Bezier-Kurven und benutzerdefinierte Interpolationsverläufe.
- Kamera- und Objektanimationen.
- Motion-Tracking-Daten oder Referenzen auf separate Tracking-Datensätze.
- Verknüpfungen zu den Objekten und Eigenschaften, auf die sich die Animation bezieht.

Abgrenzung: `.mt` ist für Bewegungs-/Animationsinformationen zuständig, nicht für die vollständige Definition eines Effekts oder die allgemeine Timeline-Struktur.

## FF-25 – `.raft`: Render & Assemble File Tool

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Renderaufträge und die Zusammenstellung ihrer Ausgabe beschreiben.

Mögliche Inhalte:
- Verweis auf Projekt, Sequenz oder Komposition als Renderquelle.
- Zielcontainer, Codec, Auflösung, Bildrate, Farbraum und Audioeinstellungen.
- Zu rendernder Zeitbereich.
- Renderabschnitte, Abhängigkeiten und Reihenfolge.
- Zusammenführung gerenderter Teilstücke.
- Ausgabeziele und Status-/Ergebnisreferenzen.

Abgrenzung: `.raft` beschreibt den Render- und Assemble-Auftrag. Es ist nicht das fertige Video selbst und nicht die maßgebliche Quelle der Timeline- oder Effektdefinitionen.

## Offene Punkte für die spätere Spezifikation

- Exakte Feldnamen, Datentypen, Pflichtfelder und optionale Felder.
- Welche Informationen eingebettet und welche nur referenziert werden.
- Wie Zeitwerte, Bildraten und Zeitbasen exakt repräsentiert werden.
- Wie externe Medien und fehlende Abhängigkeiten behandelt werden.
- Wie jede Datei versioniert und validiert wird.
- Ob Renderfortschritt und Renderhistorie in `.raft`, `.edt` oder getrennten Statusdateien abgelegt werden.
- Wie Effektparameter und Animationskurven über Formatgrenzen hinweg referenziert werden.

## Leitlinie für weitere Formate

Neue Dateiformate dürfen ergänzt werden, wenn eine eigenständige fachliche Aufgabe dies rechtfertigt. Vor dem Anlegen einer neuen Endung wird geprüft, ob ein vorhandenes Format diese Aufgabe bereits eindeutig abdeckt. Ziel ist eine verständliche, modulare Architektur ohne unnötige Dopplungen.
