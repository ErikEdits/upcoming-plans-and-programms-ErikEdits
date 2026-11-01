# Dateiformate – Aufgabenfestlegung FF-36 bis FF-40

Status: vom Projektinhaber bestätigt  
Stand: 2026-11-01  
Geltungsbereich: vorläufige fachliche Aufgabenbeschreibung; technische Schemas folgen später.

## FF-36 – `.vp`: Video Project

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Zentrale Projektbeschreibung und Einstiegspunkt für das Öffnen eines Video-Editor-Projekts.

Mögliche Inhalte:
- Projekt-ID, Name, Erstellungs-/Änderungsinformationen.
- Verweise auf Projektmanifest und zentrale Projektkomponenten.
- Projektweite Einstellungen und Konfigurationen.
- Informationen über benötigte Formatversionen und Abhängigkeiten.
- Hinweise zum Wiederherstellen und Prüfen der Projektstruktur.

Abgrenzung: `.vp` soll das Projekt identifizieren und den Einstieg ermöglichen. Es soll nicht sämtliche Timeline-, Effekt-, Animations- und Mediendaten selbst enthalten. Die genaue Beziehung zur in FF-04 beschlossenen Manifestdatei muss noch festgelegt werden; es kann sein, dass `.vp` selbst diese Rolle übernimmt.

## FF-37 – `.vsm`: Video State Map

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Eine Übersicht über den Zustand wichtiger Projektbestandteile und deren Verfügbarkeit führen.

Mögliche Inhalte:
- Liste bekannter Projektkomponenten mit stabilen IDs.
- Status wie vorhanden, geladen, verändert, fehlend oder fehlerhaft.
- Beziehungen und Abhängigkeiten zwischen Komponenten.
- Prüfergebnisse und Integritätsinformationen.
- Hinweise, welche Komponenten für bestimmte Arbeitsabläufe benötigt werden.

Abgrenzung: `.vsm` bildet den Projektzustand beziehungsweise eine Zustandsübersicht ab. Es ersetzt weder die eigentlichen Komponentendateien noch das Änderungsprotokoll.

## FF-38 – `.vsp`: Video Sequence Project

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Eigenständig bearbeitbare Videosequenz-Projekte beschreiben und speichern, die später in ein Hauptprojekt eingebunden werden können.

Mögliche Inhalte:
- Sequenzidentität und Sequenzeinstellungen.
- Verweise auf die zugehörigen Timeline- und Kompositionsdaten.
- Benötigte Medien, Effekte, Animationen und Abhängigkeiten.
- Import-/Einbindungsinformationen für ein übergeordnetes Projekt.
- Optionale eigenständige Vorschau- und Exportkonfigurationen.

Abgrenzung: `.vsp` repräsentiert ein eigenständiges Sequenzprojekt beziehungsweise dessen Projektstruktur. Die eigentlichen Timeline-Daten bleiben in den zuständigen Timeline-Formaten.

## FF-39 – `.vst`: Video Style Template

**Bestätigt: Ja.**

Vorgesehene Aufgabe: Wiederverwendbare Vorlagen für Videostile und Bearbeitungsrichtungen speichern.

Mögliche Inhalte:
- Stilname, Beschreibung und Stilversion.
- Referenzparameter für Schnitt, Tempo und Bildgestaltung.
- Verweise auf passende Effektketten, Animationen, Übergänge und Presets.
- Farb-, Typografie- und Motion-Vorgaben.
- Optionale Audio-Mix- und Sounddesign-Vorgaben.
- Regeln und Empfehlungen für die Anwendung auf unterschiedliches Ausgangsmaterial.

Beispiele:
- Anime-AMV
- Gaming-Montage
- Cinematic
- Velocity
- Ein vom Nutzer definierter persönlicher Stil

Abgrenzung: `.vst` speichert eine wiederverwendbare Stilvorlage und nicht ein fertig gerendertes Video oder ein vollständiges Projekt. Stilvorlagen sollen bei Bedarf anpassbar sein und nicht erzwingen, dass jedes Ausgangsmaterial identisch behandelt wird.

## FF-40 – Neues Asset-/Medienverwaltungsformat

**Bestätigt: Ja – ein zusätzliches Format ist vorgesehen.**

Vorgesehene Aufgabe: Medien und Assets eines Projekts zentral beschreiben, katalogisieren und referenzierbar machen.

Mögliche Inhalte:
- Videos, Bilder und Audiodateien.
- Soundeffekte, Musik und weitere Audioressourcen.
- Schriftarten, Grafiken, Texturen und Partikelressourcen.
- Vorschaubilder und Proxy-Dateien.
- Stabile Asset-IDs, Dateitypen und Metadaten.
- Speicherorte, relative Pfade, Prüfsummen und Verfügbarkeitsstatus.
- Lizenz-/Herkunftshinweise, soweit für das Asset bekannt.
- Beziehungen zwischen Originalmedien, Proxys, Vorschaudateien und abgeleiteten Dateien.

Abgrenzung: Das neue Format soll die Verwaltung und Beschreibung von Assets übernehmen. Die eigentlichen Mediendaten können als separate Dateien vorliegen oder – wenn für ein Paket sinnvoll – eingebettet werden. Das Asset-Format soll keine Timeline-, Effekt- oder Animationsdaten duplizieren.

**Name und Dateiendung: Noch nicht festgelegt.** Es wird ausdrücklich kein endgültiger Name vorweggenommen. Mögliche Bezeichnungen werden in einer späteren Runde gesammelt und gegen vorhandene Endungen geprüft.

## Offene Abgrenzungen und Architekturfragen

- `.vp` gegenüber dem Projektmanifest aus FF-04: ein Format mit Manifestfunktion oder getrennte Projektdatei und Manifest?
- `.vsm` gegenüber `.edt` und `.vcr`: aktueller Zustandsüberblick gegenüber Ereignis-/Änderungsaufzeichnungen.
- `.vsp` gegenüber `.tmf`, `.tlf` und `.cut`: eigenständiges Sequenzprojekt gegenüber Timeline- und Kompositionsdaten.
- `.vst` gegenüber `.efx`, `.mt` und `.vm`: Stilvorlage verweist auf Komponenten, statt deren vollständige Zuständigkeiten zu duplizieren.
- Neues Asset-Format gegenüber eingebetteten Assets in Paketformaten: eindeutige Regeln für Referenzen, Einbettung und Wiederverwendung.

Alle bisherigen 19 Formate und das neue Asset-Format bleiben im Konzept erhalten. Die endgültige Dateiendung des neuen Formats wird später gemeinsam festgelegt.
