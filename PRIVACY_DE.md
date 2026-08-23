# Datenschutzerklärung für sName2Date

Stand: 2026-08-22

## Kurzfassung

sName2Date erhebt, speichert und übermittelt **keine** personenbezogenen Daten. Die App
arbeitet ausschließlich auf deinem Mac und stellt keine Verbindung ins Internet her.

## Welche Daten die App verarbeitet

sName2Date liest die Dateien, die du ihr ausdrücklich übergibst — durch Auswahl im
Öffnen-Dialog oder durch Ziehen auf das Fenster. Gelesen werden der Dateiname und die
Metadaten der Datei; geschrieben wird das Aufnahmedatum in genau diese Dateien.

Auf Wunsch benennt die App diese Dateien zusätzlich um und setzt ihr Erstellungs- und
Änderungsdatum. Beides ist voreingestellt aus bzw. ausdrücklich einzuschalten.

In der Betriebsart **Dateinamen** öffnet die App **keine einzige Datei**: sie liest allein den
Namen und ändert allein den Namen. Der Inhalt wird dabei weder gelesen noch geschrieben.

Ohne deine Auswahl greift die App auf keine Datei zu. macOS setzt das über die
App-Sandbox durch.

## Was die App auf deinem Mac ablegt

- **Einstellungen** in einer Datei `config.json` im geschützten App-Ordner der App.
- **Ein Diagnoseprotokoll** im selben Bereich, das nach sieben Tagen automatisch gelöscht
  wird. Es enthält Zeitpunkte und Anzahlen von Vorgängen. Du kannst es über
  Einstellungen → Diagnose sichern und weitergeben; es verlässt deinen Mac sonst nicht.
- **Die Pfade der Ordner, die du freigegeben hast**, samt der Erlaubnis von macOS, sie beim
  nächsten Start wieder zu öffnen. Nur so muss die App nicht jedes Mal erneut fragen. Die
  Liste enthält Ordnerpfade, keine Dateiinhalte, und der Knopf „Ordner wählen" zeigt sie dir.

Alles davon wird mit der App entfernt, wenn du sie löschst.

**Neben deinen Dateien legt die App nichts Neues an.** Liegt dort bereits eine Begleitdatei
mit der Endung `.xmp` — sie stammt dann von einem anderen Bildprogramm —, wird deren
Aufnahmedatum mit aktualisiert, damit Datei und Begleiter nicht Verschiedenes sagen. Was die
App darin nicht versteht, bleibt unangetastet.

## Keine Weitergabe, keine Analyse

Es gibt keine Werbung, keine Analysedienste, keine Absturzberichte an Dritte und keine
Konten.

## Kontakt

Andreas Heiligtag · andreas.heiligtag@gmx.de
