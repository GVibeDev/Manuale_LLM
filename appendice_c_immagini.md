@@ -72,9 +72,9 @@ Nella produzione video il prompt più efficace non è una descrizione letteraria

Una formulazione astratta come *«rendi la scena emozionante»* delega al modello tutte le decisioni importanti. Una formulazione registica — *camera fissa, figura di spalle, un solo passo in avanti, controluce duro, nessun movimento laterale* — rende invece verificabile il risultato.

### 3.3 Case study — Video musicale "noir"
### 3.3 Case study — Video musicale "pastello"

Entrambi i progetti, quello dedicato al video "noir" e quello dedicato al video "pastello", hanno richiesto circa 50 generazioni, delle quali circa 30 hanno passato la selezione per la lavorazione. Il flusso ha combinato Google Flow, Veo e Omni/Omniflash con una successiva fase di upscaling da 720p a 1080p e montaggio in DaVinci Resolve.

Il primo orientamento fotorealistico è stato progressivamente abbandonato. Le variazioni del volto, i movimenti artificiali e le superfici eccessivamente pulite rendevano evidente l'origine generativa. La soluzione non è stata inseguire un realismo ancora più fragile, ma adottare una grammatica **graphic novel/noir**


@@ -104,14 +104,14 @@ Tra i problemi incontrati:

Anche i temi più sensibili sono stati trattati indirettamente, mostrando conseguenze, ambienti e reazioni anziché chiedere al modello rappresentazioni esplicite difficili da controllare. La limitazione tecnica è così diventata anche criterio narrativo.

### 3.4 Case study — Il video pastello
### 3.4 Case study — Video musicale leggero 

Nel progetto dedicato al video "pastello" il problema dominante non era l'estetica noir, ma la continuità di un personaggio infantile all'interno di una narrazione illustrata. Le prime prove hanno mostrato due derive opposte:
Nel progetto dedicato a questo video musicale il problema dominante non era l'estetica (su toni pastello anziché noir stavolta) ma la continuità di un personaggio all'interno di una narrazione illustrata. Le prime prove hanno mostrato due derive opposte:

* con una reference troppo vincolante, il soggetto tendeva a deformarsi;
* senza reference, il modello sostituiva progressivamente il protagonista con bambini differenti.

La risposta è stata la maggiore caratterizzazione del personaggio persistente, accompagnato da prompt più brevi e centrati sull'azione. Invece di descrivere ogni volta tutto il personaggio, il sistema separava l'identità stabile dall'evento richiesto nella singola clip.
La risposta è stata la creazione di un personaggio persistente, accompagnato da prompt più brevi e centrati sull'azione. Invece di ridescrivere ogni volta tutto il personaggio, il sistema separava l'identità stabile dall'evento richiesto nella singola clip.

La pianificazione più estesa ha organizzato circa 158 secondi in 29 microclip. La grammatica visiva combinava:

@@ -124,7 +124,7 @@ La pianificazione più estesa ha organizzato circa 158 secondi in 29 microclip.

Anche qui il generatore non è stato incaricato di costruire l'intero video. Ha prodotto unità narrative circoscritte, successivamente organizzate attraverso il montaggio. Le prove troppo statiche, simili a slideshow, e quelle soggette a deriva fotorealistica hanno dimostrato l'importanza di specificare un'azione visibile e coerente con il mezzo pittorico.

I due case study conducono a conclusioni differenti ma complementari. Il "noir" mostra come il montaggio possa trasformare instabilità e fluidità artificiale in stile. Il "pastello" mostra come la scomposizione, la persistenza del personaggio e le transizioni progettate possano sostenere una narrazione lunga senza affidarne la continuità alla memoria del generatore.
I due case study conducono a conclusioni differenti ma complementari. Il primo mostra come il montaggio possa trasformare instabilità e fluidità artificiale in stile. Il secondo mostra come la scomposizione, la persistenza del personaggio e le transizioni progettate possano sostenere una narrazione lunga senza affidarne la continuità alla memoria del generatore.

---
