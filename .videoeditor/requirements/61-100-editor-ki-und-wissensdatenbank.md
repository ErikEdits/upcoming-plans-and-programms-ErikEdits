# Anforderungen 61–100: Editor, KI-Assistent und Wissensdatenbank

Status: vom Projektinhaber beantwortet  
Stand: 2026-10-31  
Dokumentationssprache: Deutsch; spätere Übersetzungen vorgesehen.

## 1. Editor-Oberfläche und Bedienung (61–80)

- **61 – Anpassbare Oberfläche: Ja.** Fenster und Panels verschieben, skalieren, ein-/ausblenden und Layouts speichern.
- **62 – Arbeitsbereiche: Ja.** Editing, Color Grading, Audio, Motion Graphics, VFX und KI-Bearbeitung.
- **63 – Mehrere Monitore: Ja.**
- **64 – Vollbildvorschau: Ja.**
- **65 – Anfänger- und Profi-Modus: Ja.**
- **66 – Mehrere Sequenzen: Ja.**
- **67 – Direkte Timeline-Bearbeitung: Ja.**
- **68 – Snapping: Ja, jederzeit an- und abschaltbar.** Freie Positionierung muss ebenfalls möglich sein.
- **69 – Clip-Gruppierung: Ja.**
- **70 – Verschachtelte Timelines/Kompositionen: Ja.**
- **71 – Möglichst Echtzeit-Vorschau: Ja.** Text und Elemente möglichst direkt platzieren und sehen; unvermeidbare Verzögerungen sind akzeptabel.
- **72 – Vorschauqualitäten: Ja.** Verschiedene Auflösungen/Qualitätsstufen.
- **73 – Mehrere Vorschaufenster: Ja, optional.**
- **74 – Separater Vergleichsmodus: Nein.**
- **75 – Referenzframes: Ja.**
- **76 – Anpassbare Tastenkürzel und Profile: Ja.**
- **77 – Mausgesten und eigene Aktionen: Ja.**
- **78 – Natürliche, mehrsprachige Befehlssuche: Ja.** Vollständige Beschreibungen in unterschiedlichen Sprachen sollen verstanden werden; passende Funktionen werden angezeigt. Jede Funktion erhält eine ausführliche Erklärung.
- **79 – Makros/Aktionsketten: Ja.** Workflows sollen importiert/exportiert werden können, beispielsweise als JSON. Externe KI-Systeme sollen anhand einer dokumentierten Aktionsbeschreibung passende Workflow-Dateien erstellen können.
- **80 – Plugin-System: Ja.** Erweiterungen für Effekte, Werkzeuge, Übergänge, Analyse und weitere Funktionen.

### Dokumentation und Tutorials

Jede Funktion soll ausführlich erklären: Was macht sie? Wo ist sie zu finden? Wie wird sie benutzt? Mit welchen anderen Funktionen kann sie kombiniert werden?

- Erklärungen als Text und Audio; für Audio sind Microsoft-Stimmen vorgesehen.
- Tutorials zusätzlich als Videos, bei deren Erstellung Claude Code unterstützen kann.
- Tutorials sollen in unabhängige Teile/Kapitel aufgeteilt und zu Playlists gruppiert werden können.
- Einzelne Videos können bei Bedarf auf Plattformen wie YouTube veröffentlicht werden.
- Dokumentation und Tutorials sollen zur jeweiligen Programmversion passen und bei Änderungen aktualisiert werden.

## 2. KI-Assistent und Projektverständnis (81–85)

- **81 – Integrierter KI-Chat: Ja.** Der Assistent soll auch Erklärungen in verschiedenen Sprachen anbieten, beispielsweise Deutsch, Englisch, Japanisch, Koreanisch und Spanisch.
- **82 – Kontext über das aktuelle Projekt: Ja.** Die KI soll Sequenzen, Clips, Effekte, Audiospuren und den aktuellen Projektzustand kennen.
- **83 – Änderungen durch natürliche Sprache: Ja.** Nutzer können Änderungen beschreiben. Alternativ können sie Elemente oder Bereiche direkt in der Timeline anklicken und die gewünschte Änderung darauf beziehen.
- **84 – Plan vor größeren Änderungen: Ja.** Die KI soll erklären, was sie vorhat, und vor größeren Änderungen eine Bestätigung einholen.
- **85 – Entscheidungen erklären: Ja.** Die KI soll auf Nachfrage begründen können, warum sie etwas vorgeschlagen oder geändert hat.

## 3. Kontrolle und Sicherheit (86–90)

- **86 – Berechtigungsstufen: Ja.** Beispielsweise nur analysieren, Vorschläge machen, Änderungen vorbereiten oder Änderungen ausführen.
- **87 – Rückgängigmachen: Ja.** KI-Aktionen müssen nachvollziehbar und rückgängig zu machen sein.
- **88 – Originaldateien schützen: Ja.** Originale werden nicht verändert. Änderungen werden nicht-destruktiv in Projekt-/Metadatendateien gespeichert; beim erneuten Öffnen wird der Bearbeitungszustand wiederhergestellt. Falls eine Kopie für einen bestimmten Arbeitsablauf erforderlich ist, darf sie erstellt werden, aber das Original bleibt unangetastet.
- **89 – Aufwandsschätzung: Ja.** Vor größeren Aktionen sollen ungefähre Renderzeit, Speicherbedarf und Rechenaufwand angezeigt werden.
- **90 – Aktionsverlauf: Ja.** Sichtbar machen, welche KI-Aktionen wann ausgeführt wurden und welche Projektdateien beziehungsweise Zustände betroffen sind.

## 4. Mehrere KI-Systeme und Agenten (91–95)

- **91 – Agenten manuell auswählen: Ja, optional.** Später können spezialisierte Agenten für bestimmte Aufgaben hinzukommen und bei Bedarf ausgewählt werden.
- **92 – Übergeordnete Orchestrierung: Ja.** Ein koordinierender Agent verteilt Aufgaben und führt Ergebnisse zusammen.
- **93 – Gegenseitige Qualitätskontrolle: Ja, optional.** Agenten können die Ergebnisse anderer Agenten prüfen.
- **94 – Modelle vergleichen: Ja, bei Bedarf.** Verschiedene Modelle sollen für dieselbe Aufgabe ausprobiert werden können.
- **95 – Aufgabenübergabe: Ja.** Ein Agent kann eine Aufgabe an einen besser geeigneten Agenten übergeben.

## 5. Lernen, Workflows und technische Kontrolle (96–100)

- **96 – Aus manuellen Bearbeitungen lernen: Ja.** Die KI soll Präferenzen und Arbeitsweisen aus manuellen Bearbeitungen ableiten können. Dies ist von der ausdrücklich kontrollierten Aufnahme in Trainingsdatensätze zu unterscheiden.
- **97 – Wiederverwendbare KI-Workflows: Ja, bei Bedarf.** Beispiele: Anime-AMV, Gaming-Montage, Cinematic Trailer.
- **98 – Workflows bearbeiten, importieren, exportieren und teilen: Ja.**
- **99 – Wissensdatenbank zur Problemlösung: Ja.** Die KI soll nach passenden Lösungen suchen und ihre Empfehlungen erklären.
- **100 – Expertenmodus: Ja.** Direkter Zugriff auf technische Einstellungen, Modellparameter, FFmpeg-Befehle, Renderoptionen und detaillierte KI-Konfigurationen.

## 6. Kontinuierlich wachsende Wissensdatenbank

Zusätzliche Anforderung aus der Antwort des Projektinhabers:

Die Wissensdatenbank soll fortlaufend erweitert werden und nicht nur aus intern erstellten Informationen bestehen. Sie soll auch öffentlich verfügbare Informationen von Websites, Plattformen und anderen geeigneten Quellen berücksichtigen können.

Daraus ergeben sich folgende noch zu spezifizierende Anforderungen:

- Quellen und Herkunft jeder Information nachvollziehbar speichern.
- Abrufdatum und möglichst Veröffentlichungs-/Aktualisierungsdatum erfassen.
- Informationen auf Aktualität und Widersprüche prüfen.
- Urheberrecht, Lizenzen, Nutzungsbedingungen und Zugriffsbeschränkungen beachten.
- Nicht ungeprüft annehmen, dass öffentlich lesbare Inhalte automatisch zum Kopieren, dauerhaften Speichern oder Trainieren verwendet werden dürfen.
- Zwischen internem Wissen, extern referenziertem Wissen und ausdrücklich freigegebenen Trainingsdaten unterscheiden.
- Quellenlinks und Belege für KI-Antworten anzeigen.
- Veraltete Informationen markieren und aktualisieren können.

## 7. Noch offene technische Entscheidungen

- Welche Sprachen zum Start vollständig unterstützt werden.
- Wie Microsoft-Stimmen eingebunden werden und welche Nutzungsbedingungen gelten.
- Wie Tutorial-Videos erstellt, geprüft, versioniert und aktualisiert werden.
- Welche JSON-Workflow-Schemata und Sicherheitsprüfungen gelten.
- Welche Plugin-Schnittstellen und Berechtigungen angeboten werden.
- Wie Agenten, Modelle und Aufgaben technisch orchestriert werden.
- Wie Nutzerpräferenzen aus manuellen Bearbeitungen gespeichert werden, ohne diese automatisch als Trainingsfreigabe zu behandeln.
- Welche öffentlichen Quellen die Wissensdatenbank verwenden darf und wie deren Lizenz-/Nutzungsbedingungen geprüft werden.

## 8. Grundsätze

1. Originalmedien bleiben unverändert.
2. KI-Aktionen sind nachvollziehbar und rückgängig zu machen.
3. Größere Änderungen werden vor Ausführung erklärt und bestätigt.
4. Optionale Automatisierung bleibt kontrollierbar.
5. Externe Wissensquellen werden mit Herkunft und Nutzungsrechten dokumentiert.
6. Das Ableiten von Nutzerpräferenzen ist nicht automatisch eine Freigabe für Modelltraining.
