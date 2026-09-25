# Hilfe zu sName2Date

## Was die App tut

sName2Date sucht im Dateinamen nach einem Datum und schreibt es als Aufnahmedatum in die
Bild-, Film- oder Tondatei. Ist noch kein Aufnahmedatum vorhanden, wird es angelegt.

Oben im Fenster stehen dafür zwei Haken, die sich nicht ausschließen:

| | |
|---|---|
| **Datum in die Datei schreiben** | legt das Datum als Aufnahmedatum in die Datei selbst — die Hauptaufgabe der App |
| **Dateinamen umstellen** | bringt den Namen in die ISO-Schreibweise, für **jede** Dateiart |

Beide zusammen sind der Normalfall. Ist nur der zweite gesetzt, öffnet die App keine Datei
und benennt nur um.

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
In die Datei selbst schreibt die App das Aufnahmedatum bei Bildern (JPEG, PNG, TIFF, HEIC,
GIF), Filmen (MP4, MOV, M4V) und Tonaufnahmen (M4A, M4B) — dann ist der Haken in der Zeile
grün.

Die Liste nimmt aber **jede** Datei. Wo das Format kein Aufnahmedatum aufnimmt — eine PDF
etwa, eine Textdatei oder eine Tabelle —, setzt die App stattdessen Erstellungs- und
Änderungsdatum der Datei; der Haken ist dann orange. Programme, Aliasse und Dokumente im
Paketformat erscheinen nicht in der Liste.

**Bei meiner HEIF-, WebP- oder AVI-Datei ist der Haken blau.**
Diese drei Formate nehmen kein Aufnahmedatum auf. Die App schreibt es deshalb in eine
Begleitdatei mit demselben Namen und der Endung `.xmp`, die Fotoprogramme wie Lightroom oder
digiKam mitlesen.

Bei HEIF hilft oft schon die Endung: dieselben Daten heißen als `.heic` ein anderes Format
und werden dann in die Datei selbst geschrieben.

**Ich möchte nur die Dateinamen aufräumen, ohne die Dateien anzufassen.**
Oben im Fenster „Datum in die Datei schreiben" ausschalten und „Dateinamen umstellen"
einschalten. Dann öffnet die App keine einzige Datei und ändert nur den Namen und, falls in
den Einstellungen eingeschaltet, Erstellungs- und Änderungsdatum — aus `Rechnung 15.03.2024.pdf` wird `2024-03-15 12-00-00 Rechnung.pdf`,
und der Ordner sortiert im Finder nach Datum. Das gilt für jede Dateiart, auch PDF, Text oder
Tabellen.

Soll das Datum dort stehen bleiben, wo es im Namen stand, schaltest du „Datum voranstellen"
aus.

Umbenennen ändert den Ordnereintrag, und dafür braucht macOS die Erlaubnis für den Ordner.
Wählst du in der Vollversion gleich den Ordner, ist sie damit erteilt. Hast du einzelne
Dateien gewählt — in der Lite-Ausgabe immer —, fragt die App einmal nach dem Ordner; ein
übergeordneter genügt, und die Freigabe gilt auch nach einem Neustart. In der Vollversion
führt der Knopf „Ordner wählen" die zuletzt benutzten in einem Menü.

**Neben meiner Datei liegt eine Datei mit der Endung `.xmp`.**
Entweder stammt sie von einem anderen Programm — Lightroom und digiKam legen solche Begleiter
an —, oder sName2Date hat sie angelegt, weil das Format das Aufnahmedatum selbst nicht
aufnimmt (HEIF, WebP, AVI; der Haken ist dann blau). ⌘Z nimmt eine so angelegte wieder
zurück. Eine vorhandene zieht die App mit, wenn sie das Aufnahmedatum ändert: sonst sagte die
Datei das eine und ihr Begleiter das andere, und die meisten Programme lesen den Begleiter
zuerst.

**Bei einem großen Ordner fragt die App, ob sie weiter einlesen soll.**
Ganze Ordner auf einmal liest die Vollversion ein. Ab 5 000 Dateien — etwa beim Benutzerordner samt Unterordnern — hält sie an und fragt.
Während des Einlesens und Auswertens zeigt sie einen Zähler und einen Fortschrittsbalken;
geschrieben werden kann erst, wenn die Liste vollständig ist. Schneller geht es mit einem
kleineren Ordner oder ohne „Unterordner einbeziehen".

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

SwiftAppsBavaria · SwiftAppsBavaria@gmx.net
