# Aiuto per sName2Date

## Che cosa fa l'app

sName2Date cerca una data nel nome del file e la scrive come data di scatto nel file di
immagine, di filmato o audio. Se non è ancora presente una data di scatto, viene creata.

In alto nella finestra ci sono per questo due caselle, che non si escludono a vicenda:

| | |
|---|---|
| **Scrivi la data nel file** | mette la data come data di scatto nel file stesso — il compito principale dell'app |
| **Converti i nomi dei file** | porta il nome nella notazione ISO, per file **di qualsiasi tipo** |

Le due insieme sono il caso normale. Se è attiva solo la seconda, l'app non apre alcun file e
si limita a rinominare.

## Primi passi

1. Scegli un file con «Scegli file…» oppure trascinalo sulla finestra. La versione completa
   accetta anche intere cartelle con le loro sottocartelle.
2. L'elenco mostra per ogni file la data riconosciuta e, se presente, la data di scatto già
   impostata.
3. «Scrivi la data» esegue la modifica.

## Domande frequenti

**Per un file compare «Nessuna data trovata nel nome».**
Il nome non contiene alcuna indicazione di data riconoscibile. Vengono riconosciuti tra
l'altro `2024-01-15 10-30-00`, `IMG_20240115_103000`, `2024-01-15`, `2024 01 15`,
`2024_01_15`, `15.01.2024`, `15-01-2024`, `15.01.24` nonché i nomi dei mesi per esteso come
`15 gen. 2024`, `15 marzo 2024` oppure `January 15 2024`. Vengono letti anche `2016 04` e
`04-2016` — allora vale il primo del mese, e la riga lo indica.

L'app riconosce i nomi dei mesi nella lingua del tuo sistema e in inglese. Una grafia diversa
da quella prevista non viene riconosciuta — in tedesco, per esempio, `15 Maerz 2024` con
ae/oe/ue al posto della dieresi; in quel caso inserisci la data a mano nella riga, a destra.

**Una data viene letta con il giorno sbagliato.**
Il 3 aprile in italiano si scrive `3.4.`, in inglese `4/3` — le stesse due cifre con
significato invertito. Con `15-03-2024` questo non fa differenza, un mese 15 non esiste.
Solo quando entrambi i numeri possono valere come mese (`03-05-2024`) occorre decidere:
allora sopra l'elenco compare una barra arancione con entrambe le letture da scegliere, e le
righe interessate sono contrassegnate. L'impostazione predefinita è la notazione della tua
regione di sistema.

**Il nome contiene due indicazioni di data.**
Vince la prima: in `IMG_20240115_modificato_2019-03-02` quindi la ripresa, non l'annotazione
successiva. Un'indicazione con orario ha sempre la precedenza su una senza.

**Il nome contiene solo una data, nessun orario.**
Allora viene assunto un orario — per impostazione predefinita le 12 di mezzogiorno. Si può
cambiare nelle impostazioni.

**Vorrei datare una vecchia foto digitalizzata.**
Si può fare: le date inserite a mano risalgono fino al 1826, l'anno della più antica
fotografia conservata.

**La mia foto perde qualità?**
No. I dati dell'immagine vengono ripresi invariati, un JPEG non viene ricompresso. Nei
filmati le tracce vengono trasferite così come sono, non si ricodifica nulla.

**Quali formati sono supportati?**
L'app scrive la data di scatto nel file stesso per le immagini (JPEG, PNG, TIFF, HEIC, GIF),
i filmati (MP4, MOV, M4V) e le registrazioni audio (M4A, M4B) — il segno di spunta nella riga
è allora verde.

L'elenco accetta però **qualsiasi** file. Dove il formato non accoglie alcuna data di
scatto — un PDF per esempio, un file di testo o una tabella —, l'app imposta invece la data di
creazione e di modifica del file; il segno di spunta è allora arancione. Applicazioni, alias
e documenti in formato pacchetto non compaiono nell'elenco.

**Per il mio file HEIF, WebP o AVI il segno di spunta è blu.**
Questi tre formati non accolgono alcuna data di scatto. L'app la scrive perciò in un file di
accompagnamento con lo stesso nome e l'estensione `.xmp`, che i programmi di fotografia come
Lightroom o digiKam leggono insieme al file.

Con HEIF spesso basta già l'estensione: gli stessi dati con `.heic` sono un altro formato e
vengono allora scritti nel file stesso.

**Vorrei solo mettere in ordine i nomi dei file, senza toccare i file.**
In alto nella finestra disattiva «Scrivi la data nel file» e attiva «Converti i nomi dei
file». Allora l'app non apre nemmeno un file e modifica solo il nome e, se attivato nelle
impostazioni, la data di creazione e di modifica — da `Fattura 15.03.2024.pdf` nasce
`2024-03-15 12-00-00 Fattura.pdf`, e la cartella si ordina per data nel Finder. Questo vale
per ogni tipo di file, anche PDF, testi o tabelle.

Se la data deve restare là dove si trovava nel nome, disattiva «Data all'inizio».

Rinominare modifica la voce nella cartella, e per questo macOS richiede il permesso per la
cartella. Se nella versione completa scegli subito la cartella, il permesso è concesso così.
Se hai scelto singoli file — in sName2Date Lite sempre —, l'app chiede una sola volta la
cartella; ne basta una di livello superiore, e il permesso vale anche dopo un riavvio. Nella
versione completa il pulsante «Scegli cartella» elenca in un menu quelle usate per ultime.

**Accanto al mio file si trova un file con estensione `.xmp`.**
O proviene da un altro programma — Lightroom e digiKam creano simili file di
accompagnamento —, oppure l'ha creato sName2Date perché il formato non accoglie da sé la data
di scatto (HEIF, WebP, AVI; il segno di spunta è allora blu). ⌘Z rimuove un file di
accompagnamento creato in questo modo. L'app trascina con sé quello esistente quando modifica
la data di scatto: altrimenti il file direbbe una cosa e il suo accompagnatore un'altra, e la
maggior parte dei programmi legge per prima l'accompagnatore.

**Con una cartella grande l'app chiede se continuare a leggere.**
Riguarda solo la versione completa: sName2Date Lite non accetta cartelle. A partire da
5000 file — per esempio con la cartella utente e le sue sottocartelle — si ferma e chiede.
Durante la lettura e l'analisi mostra un contatore e una barra di avanzamento; si può
scrivere solo quando l'elenco è completo. Si fa prima con una cartella più piccola o senza
«Includi le sottocartelle».

**Posso annullare una modifica?**
Sì. ⌘Z ritira un'intera esecuzione — data di scatto, data di creazione e di modifica e, se
attivato, anche il nome del file modificato. ⌘⇧Z la ripristina.

Un'avvertenza comunque: prima di elaborare una raccolta di grandi dimensioni crea una copia
di sicurezza. L'annullamento ripristina i valori, ma non sostituisce una copia di sicurezza.

**Rinominare non ha funzionato, ma la data è nel file.**
Se è stato scelto un singolo file, l'app può lavorare solo su quel file, non nella sua
cartella — e rinominare modifica la voce nella cartella. Scegli la cartella invece del
singolo file, oppure concedi l'autorizzazione quando l'app la richiede. Un'autorizzazione
concessa una volta vale anche dopo un riavvio e copre tutte le sottocartelle.

## Qualcosa non va?

Impostazioni → Diagnosi → «Salva protocollo…» raccoglie i messaggi degli ultimi sette giorni
in un file di testo. Allegalo volentieri alla descrizione dell'errore.

## Contatto

SwiftAppsBavaria · SwiftAppsBavaria@gmx.net
