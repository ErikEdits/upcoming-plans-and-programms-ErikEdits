# Eigene Dateiformate – Übersicht und Architekturentwurf

Status: Entwurf – noch keine endgültigen Format-Spezifikationen  
Stand: 2026-10-31

Dieses Verzeichnis sammelt die geplanten Dateiformate des Video-Editors. Die Dateinamen und Kurzbezeichnungen stammen aus den bisherigen Projektideen. Die Zuordnungen in dieser README sind Vorschläge zur Strukturierung und müssen noch gemeinsam bestätigt werden.

## Grundidee

Das Projekt soll aus mehreren spezialisierten Dateien bestehen, statt alle Informationen in einer einzigen riesigen Projektdatei zu speichern.

Ein Projekt soll beim Öffnen aus seinen verknüpften Teil-Dateien wiederhergestellt werden können. Dazu braucht es eine klare Referenzstruktur, stabile IDs, Versionsinformationen und Regeln für fehlende oder inkompatible Dateien.

Wichtig:
- Originalmedien werden nicht verändert.
- Projektdateien speichern Bearbeitungsschritte, Verweise, Parameter, Keyframes und Zustände.
- Große Originalvideos, Audiodateien und andere Medien müssen nicht in jede Projektdatei hineinkopiert werden.
- Eine Projektdatei kann auf Medien über Pfad, Asset-ID und optional Prüfsumme verweisen.
- Das Format soll modular, versionierbar, dokumentiert und möglichst von anderen Programmen lesbar sein.
- Ein Projekt muss nach Schließen und erneutem Öffnen zuverlässig seinen vorherigen Zustand wiederherstellen.

## Bereits vorhandene Formatideen

Die folgenden Dateien existieren bereits in diesem Ordner. Aktuell enthalten sie jeweils nur den Namen beziehungsweise eine Kurzbeschreibung, noch keine technische Spezifikation.

| Endung | Bisherige Bezeichnung | Mögliche Zuständigkeit (Vorschlag) |
|---|---|---|
| `.cut` | Composition & Unified Timeline | Komposition und zusammengeführte Timeline-Struktur |
| `.edt` | Edit Data Tracker | Änderungs-/Bearbeitungsverlauf und Edit-Metadaten |
| `.efx` | Effects Framework XML | Effektdefinitionen und Effektparameter |
| `.mt` | Motion | Bewegungsdaten und Motion-Parameter |
| `.raft` | Render & Assemble File Tool | Render- und Zusammenbau-Aufträge |
| `.tap` | Timeline Assembly Package | Paket aus Timeline-Teilen und zugehörigen Referenzen |
| `.tlf` | Timeline File | Einzelne Timeline |
| `.tls` | Timeline Length & State | Timeline-Länge und Timeline-Zustand |
| `.tmf` | Timeline Master File | Zentrale Timeline-Übersicht/Verknüpfung |
| `.vcb` | Video Composition Bundle | Zusammengehörige Kompositionsdateien als Paket |
| `.vcd` | Video Composition Data | Daten einer Komposition |
| `.vcr` | Video Composition Record | Kompositionsinformationen/Protokoll |
| `.ved` | Video Editing Data | Allgemeine Bearbeitungsdaten |
| `.vfx` | Video Frame Xchange – Visual Effects | Frame-bezogene VFX-Daten oder Austauschformat |
| `.vm` | Video Modifier | Modifikatoren für Clips, Ebenen oder Medien |
| `.vp` | Video Project | Projekt-Einstiegspunkt und Projektinformationen |
| `.vsm` | Video State Map | Zuordnung von Projekt-/Editor-Zuständen |
| `.vsp` | Video Sequence Project | Sequenz- beziehungsweise Unterprojekt |
| `.vst` | Video Style Template | Stilvorlagen und wiederverwendbare Look-/Edit-Vorgaben |

## Erste Architektur-Empfehlung

Die Formate sollten nicht alle dieselbe Aufgabe erfüllen. Einige Namen überschneiden sich derzeit möglicherweise. Bevor Implementierung beginnt, brauchen wir eine eindeutige Zuständigkeit pro Format.

Ein mögliches Prinzip:
1. Eine kleine Projekt-Einstiegsdatei enthält Projekt-ID, Projektversion und Verweise auf die Teil-Dateien.
2. Timeline- und Sequenzdateien enthalten Schnittstruktur und Abspielreihenfolge.
3. Effekt-, Motion-, Audio- und Farbdateien enthalten spezialisierte Bearbeitungsparameter.
4. Asset-/Medien-Dateien verwalten Referenzen auf Originalmedien und wiederverwendbare Ressourcen.
5. Renderdateien beschreiben Renderaufträge und Exportprofile.
6. Verlauf-/Statusdateien halten Änderungen und Wiederherstellungsinformationen fest.

Die Projekt-Einstiegsdatei soll klein bleiben. Sie ist ein Manifest/Index, keine Datei, in der sämtliche Videodaten und Bearbeitungsschritte gesammelt werden.

## Mögliche zusätzliche Formate

Diese Endungen sind Vorschläge und noch nicht beschlossen. Vor der Einführung muss geprüft werden, ob sie mit bestehenden Endungen/Programmen kollidieren und ob die Funktion nicht bereits sinnvoll in einem vorhandenen Format liegt.

| Vorgeschlagene Endung | Möglicher Zweck |
|---|---|
| `.vmedia` | Medienkatalog und Referenzen auf Originalvideos, Bilder und Audio |
| `.vasset` | Asset-Bibliothek, Asset-Metadaten, Versionen und Lizenzhinweise |
| `.vproxy` | Proxy-Datei-Zuordnung und Einstellungen für Vorschau-Medien |
| `.vkey` | Keyframes, Kurven, Interpolation und Animationskanäle |
| `.vnode` | Node-Graph-Strukturen und Verbindungen zwischen Effekten |
| `.vmask` | Masken, Rotoscoping-Daten und Masken-Keyframes |
| `.vaudio` | Audio-Clip-Struktur, Routing und Bearbeitungsparameter |
| `.vcolor` | Color-Grading-Parameter, Farbmanagement und Looks |
| `.vtrans` | Übergangsdefinitionen und Übergangsparameter |
| `.vtitle` | Text-/Titel-Layouts, Typografie und Textanimationen |
| `.vcaption` | Untertitel, Transkriptsegmente und Zeitinformationen |
| `.vmeta` | Technische Medienmetadaten wie Codec, FPS, Auflösung und Farbraum |
| `.vqueue` | Render-/Analyse-Warteschlangen und Job-Metadaten |
| `.vbackup` | Backup-Manifest und Wiederherstellungsinformationen |
| `.vplugin` | Plugin-Manifeste, Abhängigkeiten und Kompatibilitätsangaben |
| `.vworkflow` | Importierbare Automations- und KI-Workflows |

## Gemeinsame technische Anforderungen für alle Formate

Noch zu spezifizieren, aber als Ziel vorgesehen:
- Eindeutige Formatkennung und Schema-Version.
- Version der Anwendung, die die Datei erzeugt hat.
- Eindeutige Projekt-, Sequenz-, Clip- und Asset-IDs.
- Definierte Referenzen auf andere Dateien.
- Klare Regeln für relative und absolute Medienpfade.
- Prüfsummen oder andere Integritätsprüfungen für referenzierte Dateien, wo sinnvoll.
- Rückwärtskompatibilität und definierte Migrationswege.
- Verständliche Fehlermeldungen bei unbekannten Versionen oder fehlenden Referenzen.
- Möglichst menschenlesbare Struktur für Debugging und externe Tools.
- Dokumentierte API beziehungsweise Spezifikation für Drittanbieter.
- Sichere Verarbeitung: Importierte Dateien dürfen keine beliebigen Programme oder Befehle ausführen.

## Noch offene Grundsatzentscheidungen

1. Welches Format ist der offizielle Projekteinstieg: `.vp` oder ein anderes?
2. Welche der bestehenden Formate sind eigenständig und welche sind redundant?
3. Sollen die Dateien intern JSON, XML, SQLite, CBOR oder ein anderes Datenmodell verwenden?
4. Welche Dateien sind einfache Textdateien und welche dürfen Container/Archive sein?
5. Wie werden externe Medien referenziert, verschoben und wiedergefunden?
6. Wie werden Projekte zwischen Computern und Cloud übertragen?
7. Wie werden fehlende Assets, Plugins und Schriftarten behandelt?
8. Wie funktionieren Migration, Kompatibilität und Wiederherstellung?
9. Welche Formate sollen öffentlich vollständig dokumentiert und von Drittprogrammen bearbeitbar sein?
10. Wie werden sensible Daten, Zugangsdaten und private Informationen von exportierbaren Projektdateien getrennt?

## Arbeitsregel

Die Vorschläge in dieser Datei sind keine endgültigen Entscheidungen. Bestehende Dateinamen werden nicht gelöscht oder umbenannt, bevor ihre Bedeutung geklärt ist. Neue Formate werden erst dann als festgelegt markiert, wenn Zweck, Inhalt, Beziehungen, Versionierung und Beispieldatei beschrieben sind.
