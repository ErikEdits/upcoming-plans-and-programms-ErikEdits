# Dateiformate – Aufgabenfestlegung FF-26 bis FF-30

Status: vom Projektinhaber bestätigt  
Stand: 2026-11-01  
Geltungsbereich: vorläufige fachliche Aufgabenbeschreibung; technische Schemas folgen später.

## Grundsatz

Jedes Format erhält eine eigene, klar abgegrenzte Aufgabe. Die folgenden Aufgaben wurden vom Projektinhaber bestätigt. Die genaue Trennung zwischen ähnlich klingenden Timeline-Formaten wird in der späteren technischen Spezifikation präzisiert, damit keine unnötigen Dopplungen entstehen.

## FF-26 – `.tap`: Timeline Assembly Package

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Ein übertragbares Paket aus mehreren zusammengehörigen Timeline-Bestandteilen bereitstellen.

Mögliche Inhalte:
- Eine oder mehrere Timeline-Dateien beziehungsweise ausgewählte Timeline-Abschnitte.
- Verweise auf benötigte Effekte, Animationen, Medien und weitere Abhängigkeiten.
- Paketmanifest mit Komponenten-IDs und relativen Referenzen.
- Informationen zum Importieren und Einfügen in ein anderes Projekt.
- Optional benötigte Vorschaudaten und Paketmetadaten.

Abgrenzung: `.tap` ist ein Austausch-/Transportpaket. Es ersetzt nicht die spezialisierten Quelldateien der enthaltenen Komponenten und ist nicht automatisch das vollständige Projektmanifest.

## FF-27 – `.tlf`: Timeline File

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Die eigentlichen strukturellen und zeitlichen Timeline-Daten speichern.

Mögliche Inhalte:
- Spuren und ihre Reihenfolge.
- Clips und deren In-/Out-Punkte.
- Positionen, Dauer, Schnitte und Überblendungsbereiche.
- Clip-Reihenfolge und zeitliche Beziehungen.
- Referenzen auf Medien, Effekte, Animationen und verschachtelte Sequenzen.
- Zeitbasis und Bildratenbezug.

Abgrenzung: `.tlf` enthält die eigentliche Timeline-Struktur. Reine Ansichts-/Arbeitsoberflächenzustände gehören in `.tls`; übergeordnete Verwaltung mehrerer Sequenzen wird mit `.tmf` abgestimmt.

## FF-28 – `.tls`: Timeline Length & State

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Timeline-Zustände und zugehörige Statusinformationen speichern. Die genaue Bedeutung des Bestandteils „Length“ muss in der späteren Spezifikation geklärt werden.

Mögliche Inhalte:
- Timeline-Länge beziehungsweise relevante Zeitbereichsgrenzen, soweit nicht bereits maßgeblich in der Timeline-Struktur enthalten.
- Ansichtsstatus wie Zoomstufe und Scrollposition.
- Aktuelle Auswahl und fokussierte Spur.
- Abspielkopfposition und Arbeitsbereich.
- Weitere wiederherstellbare Benutzer-/Arbeitszustände.

Abgrenzung: `.tls` soll nicht unkontrolliert die Clip- und Spurstruktur aus `.tlf` duplizieren. Es muss später festgelegt werden, welche Längeninformationen hier eigenständig gespeichert werden und welche nur aus der Timeline abgeleitet werden.

## FF-29 – `.tmf`: Timeline Master File

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Übergeordnete Verwaltung und Organisation der Timelines eines Projekts übernehmen.

Mögliche Inhalte:
- Liste und Identitäten der Sequenzen und Timelines.
- Beziehungen zwischen Hauptsequenzen, Untersequenzen und verschachtelten Timelines.
- Zentrale Timeline-Einstellungen und Zuordnungen.
- Verweise auf die zuständigen `.tlf`- und `.tls`-Dateien.
- Projektweite Reihenfolge oder Organisationsstruktur der Sequenzen.

Abgrenzung: `.tmf` verwaltet und verbindet Timeline-Dateien, statt sämtliche einzelnen Clipdaten selbst zu enthalten.

## FF-30 – `.vcb`: Video Composition Bundle

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Ein gebündeltes Paket einer Videokomposition bereitstellen.

Mögliche Inhalte:
- Kompositionsdefinition und zugehörige Komponentenreferenzen.
- Benötigte Effekte, Animationen und Einstellungen.
- Medienreferenzen und optional eingebettete Assets, soweit rechtlich und technisch zulässig.
- Paketmanifest, Abhängigkeiten und Versionsinformationen.
- Optionale Vorschaudaten.

Abgrenzung: `.vcb` ist ein Kompositionspaket. Es kann mehrere spezialisierte Dateien bündeln, soll deren fachliche Zuständigkeiten aber nicht ersetzen. Ob es ein vollständiges, eigenständig öffnbares Paket oder ein wiederverwendbares Teilpaket ist, wird später festgelegt.

## Noch zu klärende Abgrenzungen

Insbesondere folgende Formatbeziehungen benötigen in der technischen Spezifikation besondere Aufmerksamkeit:

- `.tap` gegenüber `.vcb`: Timeline-Transportpaket gegenüber Videokompositionspaket.
- `.tlf` gegenüber `.tmf`: einzelne Timeline-Struktur gegenüber übergeordneter Timeline-Verwaltung.
- `.tls` gegenüber `.tlf`: Timeline-Zustand/Länge gegenüber eigentlichen Clip- und Spurdaten.
- `.cut` gegenüber `.tlf` und `.tmf`: Kompositionsbeschreibung gegenüber Timeline-Struktur und deren Verwaltung.

Diese Formate bleiben zunächst bestehen. Die endgültige Datenaufteilung wird anhand konkreter Beispieldateien und Nutzungsszenarien geprüft.
