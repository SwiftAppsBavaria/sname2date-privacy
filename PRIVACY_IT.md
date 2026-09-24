# Informativa sulla privacy di sName2Date

Aggiornamento: 2026-09-24

## In breve

sName2Date **non** raccoglie, non memorizza e non trasmette dati personali. L'app lavora
esclusivamente sul tuo Mac e non stabilisce alcuna connessione a internet.

## Quali dati elabora l'app

sName2Date legge i file che le consegni espressamente — selezionandoli nella finestra di
dialogo di apertura oppure trascinandoli sulla finestra. Vengono letti il nome del file e i
metadati del file; la data di scatto viene scritta esattamente in questi file.

Su richiesta l'app rinomina inoltre questi file (disattivato per impostazione predefinita).
Ne imposta anche la data di creazione e di modifica (attivato per impostazione predefinita,
disattivabile nelle Impostazioni). Per i file che non possono contenere una data di scatto —
ad esempio PDF o testo —, imposta invece sempre soltanto queste due date.

Se la casella **Scrivi la data nel file** è disattivata, l'app **non apre nemmeno un file**:
legge soltanto il nome e modifica soltanto il nome e, se impostato, la data di creazione e
di modifica. Il contenuto non viene né letto né scritto.

Senza la tua selezione l'app non accede ad alcun file. macOS lo impone attraverso la sandbox
dell'app.

Se l'app esamina una cartella in cui si trova la cartella «Musica», macOS può chiedere se
può accedere a «Libreria e Apple Music». L'app non legge né la tua libreria né la tua
cronologia di ascolto. Lì, come ovunque, lavora soltanto con i file e scrive la data nei
file audio e video il cui nome ne contiene una.

## Che cosa l'app deposita sul tuo Mac

- **Le impostazioni** in un file `config.json` nella cartella protetta dell'app.
- **Un protocollo diagnostico** nella stessa area, che viene cancellato automaticamente dopo
  sette giorni. Contiene orari e conteggi delle operazioni. Puoi salvarlo e inoltrarlo
  tramite Impostazioni → Diagnosi; per il resto non lascia il tuo Mac.
- **I percorsi delle cartelle che hai autorizzato**, insieme al permesso di macOS di
  riaprirle al prossimo avvio. Solo così l'app non deve chiedere ogni volta di nuovo.
  L'elenco contiene percorsi di cartelle, non contenuti di file, e il pulsante
  «Scegli cartella» te lo mostra.

Tutto questo viene rimosso insieme all'app quando la elimini.

**Accanto ai tuoi file l'app crea qualcosa in un solo caso:** se un file di foto, video o
audio non può contenere da sé la data di scatto (ad esempio HEIF, WebP o AVI), l'app la
scrive in un file di accompagnamento con lo stesso nome e con estensione `.xmp`, che anche
molti programmi per foto leggono. ⌘Z lo annulla. Accanto ad altri file, ad esempio PDF o
testo, non ne nasce mai uno. Se lì si trova già un file di accompagnamento — proviene allora
da un altro programma per immagini —, la sua data di scatto viene aggiornata insieme,
affinché il file e il suo accompagnatore non dicano cose diverse. Ciò che l'app non
comprende al suo interno resta intatto.

## Nessuna trasmissione, nessuna analisi

Non c'è pubblicità, non ci sono servizi di analisi, non ci sono segnalazioni di arresti
anomali a terzi e non ci sono account.

## Contatto

Andreas Heiligtag · SwiftAppsBavaria@gmx.net
