# Hilfe zu sName2Date

## Was die App tut

sName2Date sucht im Dateinamen nach einem Datum und schreibt es als Aufnahmedatum in die
Bild- oder Filmdatei. Ist noch kein Aufnahmedatum vorhanden, wird es angelegt.

Die Vollversion hat dafür **zwei Betriebsarten**, umschaltbar oben im Fenster:

| | |
|---|---|
| **Aufnahmedatum** | schreibt das Datum in die Datei — die Hauptaufgabe der App |
| **Dateinamen** | bringt nur den Namen in die ISO-Schreibweise, für **beliebige** Dateien |

## Erste Schritte

1. Datei über „Datei wählen…" aussuchen oder auf das Fenster ziehen. Die Vollversion nimmt
   auch ganze Ordner samt Unterordnern.
2. Die Liste zeigt zu jeder Datei das erkannte Datum und, falls vorhanden, das bereits
   gesetzte Aufnahmedatum.
3. „Datum schreiben" führt die Änderung aus.

## Häufige Fragen

**Bei einer Datei steht „Kein Datum im Namen gefunden".**
Der Name enthält keine erkennbare Datumsangabe. Erkannt werden unter anderem
`2024-01-15 10-30-00`, `IMG_20240115_103000`, `2024-01-15`, `2024 01 15`, `2024_01_15`,
`15.01.2024`, `15-01-2024`, `15.01.24` sowie ausgeschriebene Monatsnamen wie
`15. Jan. 2024`, `15 März 2024` oder `January 15 2024`. Auch `2016 04` und `04-2016` werden
gelesen — dann gilt der Erste des Monats, und die Zeile sagt es dazu.

Monatsnamen erkennt die App in deiner Systemsprache und auf Englisch. Ein Name wie
`15 Maerz 2024` mit ae/oe/ue statt Umlaut wird nicht erkannt; trag das Datum dort rechts in
der Zeile von Hand ein.

**Ein Datum wird als falscher Tag gelesen.**
Der 3. April heißt auf Deutsch `3.4.`, auf Englisch `4/3` — dieselben zwei Zahlen mit
umgekehrter Bedeutung. Bei `15-03-2024` macht das nichts aus, einen Monat 15 gibt es nicht.
Nur wenn beide Zahlen als Monat durchgehen (`03-05-2024`), muss entschieden werden: dann
erscheint über der Liste eine orange Leiste mit beiden Lesarten zur Auswahl, und die
betroffenen Zeilen sind gekennzeichnet. Voreingestellt ist die Schreibweise deiner
Systemregion.

**Der Name enthält zwei Datumsangaben.**
Die erste gewinnt: in `IMG_20240115_bearbeitet_2019-03-02` also die Aufnahme, nicht die
spätere Notiz. Eine Angabe mit Uhrzeit hat immer Vorrang vor einer ohne.

**Der Name enthält nur ein Datum, keine Uhrzeit.**
Dann wird eine Uhrzeit angenommen — voreingestellt 12 Uhr mittags. Ändern lässt sie sich
in den Einstellungen.

**Ich möchte ein eingescanntes altes Foto datieren.**
Das geht: von Hand eingetragene Daten reichen zurück bis 1826, dem Jahr der ältesten
erhaltenen Fotografie.

**Verliert mein Foto an Qualität?**
Nein. Die Bilddaten werden unverändert übernommen, ein JPEG wird nicht neu komprimiert.
Bei Filmen werden die Spuren durchgereicht, es wird nicht neu kodiert.

**Welche Formate werden unterstützt?**
In der Betriebsart *Aufnahmedatum*: Bilder JPEG, PNG, TIFF, HEIC und GIF, Filme MP4, MOV und
M4V. In alle diese schreibt die App das Datum in die Datei selbst.

In der Betriebsart *Dateinamen* zählt **keine Endung** — dort wird nur der Name geändert, und
den hat jede Datei.

**Meine HEIF-, WebP- oder AVI-Datei erscheint gar nicht in der Liste.**
Diese drei Formate nehmen kein Aufnahmedatum auf — die App könnte das Datum dort nur
danebenlegen, statt es hineinzuschreiben, und genau dafür ist sie nicht da. Sie werden
deshalb in der Betriebsart *Aufnahmedatum* beim Laden übergangen; eine Zeile über der Liste
sagt, wie viele es waren.

Umbenennen lassen sie sich trotzdem: dafür auf *Dateinamen* umschalten.

Bei HEIF hilft oft schon die Endung: dieselben Daten heißen als `.heic` ein anderes Format
und werden dann geschrieben.

**Ich möchte nur die Dateinamen aufräumen, ohne die Dateien anzufassen.**
Oben im Fenster auf *Dateinamen* umschalten. Dann öffnet die App keine einzige Datei und
ändert nur den Namen — aus `Rechnung 15.03.2024.pdf` wird `2024-03-15 12-00-00 Rechnung.pdf`,
und der Ordner sortiert im Finder nach Datum. Das gilt für jede Dateiart, auch PDF, Text oder
Tabellen.

Soll das Datum dort stehen bleiben, wo es im Namen stand, schaltest du „Datum voranstellen"
aus.

⚠️ In dieser Betriebsart nimmt die App nur **Ordner** entgegen, keine einzelnen Dateien. Der
Grund ist das Umbenennen selbst: es ändert den Ordnereintrag, und dafür braucht macOS die
Erlaubnis für den Ordner — die entsteht, indem du ihn auswählst. Einmal gewählt, merkt sich
die App ihn; der Knopf „Ordner wählen" führt die zuletzt benutzten in einem Menü.

**Neben meiner Datei liegt eine Datei mit der Endung `.xmp`.**
Die stammt von einem anderen Programm — Lightroom und digiKam legen solche Begleiter an.
sName2Date erzeugt keine, zieht eine vorhandene aber mit, wenn es das Aufnahmedatum ändert.
Sonst sagte die Datei das eine und ihr Begleiter das andere, und die meisten Programme lesen
den Begleiter zuerst.

**Kann ich eine Änderung rückgängig machen?**
Ja. ⌘Z nimmt einen ganzen Durchgang zurück — Aufnahmedatum, Erstellungs- und Änderungsdatum
und, falls eingeschaltet, auch den geänderten Dateinamen. ⌘⇧Z stellt ihn wieder her.

Ein Hinweis dennoch: Lege vor der Bearbeitung einer großen Sammlung eine Sicherung an. Das
Rückgängig stellt die Werte wieder her, ist aber kein Ersatz für eine Sicherungskopie.

**Das Umbenennen hat nicht geklappt, das Datum steht aber in der Datei.**
Wurde eine einzelne Datei gewählt, darf die App nur an dieser Datei arbeiten, nicht in ihrem
Ordner — und Umbenennen ändert den Ordnereintrag. Wähle den Ordner statt der einzelnen
Datei, oder erteile die Freigabe, wenn die App danach fragt. Eine einmal erteilte Freigabe
gilt auch nach einem Neustart und deckt alle Unterordner mit ab.

## Etwas geht schief?

Einstellungen → Diagnose → „Protokoll sichern…" legt die Meldungen der letzten sieben Tage
in eine Textdatei. Schick sie gern mit der Fehlerbeschreibung mit.

## Kontakt

Andreas Heiligtag · andreas.heiligtag@gmx.de
