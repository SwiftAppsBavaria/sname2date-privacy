# Aiuto per sName2Date

## Che cosa fa l'app

sName2Date cerca una data nel nome del file e la scrive come data di scatto nel file di
immagine o di filmato. Se non è ancora presente una data di scatto, viene creata.

La versione completa ha per questo **due modalità**, commutabili in alto nella finestra:

| | |
|---|---|
| **Data di scatto** | scrive la data nel file — il compito principale dell'app |
| **Nomi dei file** | porta soltanto il nome nella notazione ISO, per file **di qualsiasi tipo** |

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
Nella modalità *Data di scatto*: come immagini JPEG, PNG, TIFF, HEIC e GIF, come filmati
MP4, MOV e M4V. In tutti questi l'app scrive la data nel file stesso.

Nella modalità *Nomi dei file* **non conta nessuna estensione** — lì viene modificato solo il
nome, e quello ce l'ha ogni file.

**Il mio file HEIF, WebP o AVI non compare affatto nell'elenco.**
Questi tre formati non accolgono alcuna data di scatto — l'app potrebbe solo mettere la data
accanto al file, invece di scriverla al suo interno, e non è esattamente per questo che
esiste. Vengono perciò ignorati al caricamento nella modalità *Data di scatto*; una riga
sopra l'elenco dice quanti erano.

Rinominarli è comunque possibile: per farlo passa a *Nomi dei file*.

Con HEIF spesso basta già l'estensione: gli stessi dati con `.heic` sono un altro formato e
vengono allora scritti.

**Vorrei solo mettere in ordine i nomi dei file, senza toccare i file.**
Passa a *Nomi dei file* in alto nella finestra. Allora l'app non apre nemmeno un file e
modifica solo il nome — da `Fattura 15.03.2024.pdf` nasce `2024-03-15 12-00-00 Fattura.pdf`,
e la cartella si ordina per data nel Finder. Questo vale per ogni tipo di file, anche PDF,
testi o tabelle.

Se la data deve restare là dove si trovava nel nome, disattiva «Data all'inizio».

⚠️ In questa modalità l'app accetta soltanto **cartelle**, non singoli file. Il motivo è il
rinominare stesso: modifica la voce nella cartella, e per questo macOS richiede il permesso
per la cartella — che nasce dal fatto che tu la selezioni. Una volta scelta, l'app se la
ricorda; il pulsante «Scegli cartella» elenca in un menu quelle usate per ultime.

**Accanto al mio file si trova un file con estensione `.xmp`.**
Proviene da un altro programma — Lightroom e digiKam creano simili file di accompagnamento.
sName2Date non ne crea, ma trascina con sé quello esistente quando modifica la data di
scatto. Altrimenti il file direbbe una cosa e il suo accompagnatore un'altra, e la maggior
parte dei programmi legge per prima l'accompagnatore.

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
