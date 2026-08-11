# APPENDICE C: Produzione Visiva (Immagini e Video)

## 1. Principi della generazione visiva

Il principio base dell'orchestrazione non cambia mai, che si tratti di testo, codice o immagini: usare un'IA significa fornire punti di repere stabili per fissare i confini dello spazio operativo e delimitare l'orizzonte creativo. Tuttavia, il prompting visivo nasconde insidie strutturali uniche.

Quando interroghiamo un modello multimodale per generare un'immagine, l'LLM traduce la nostra richiesta in un corollario di istruzioni per il motore grafico (come Midjourney, DALL-E o Imagen), riempiendo automaticamente i vuoti che lasciamo. È qui che molti utenti falliscono, cadendo nel **paradosso della sovraspecifica**. 

I generatori visivi sono progettati per *inferire* e creare contenuti nuovi, non per eseguire riproduzioni millimetriche. Inserire istruzioni eccessivamente stringenti o dettagli microscopici costringe il motore grafico a incastrare elementi incompatibili, generando allucinazioni visive, mostruosità anatomiche o artefatti. Nel tentativo di correggere l'errore aggiungendo ulteriori dettagli, il risultato peggiora drasticamente.

Per padroneggiare la generazione grafica, servono un ambiente dedicato (una chat isolata, mai mischiata a produzioni testuali o analitiche) e l'applicazione di queste 5 regole auree:

*   **1. Il "Backbone" Visivo (Stile, Tratto e Palette)**
    Sono lo scheletro dell'immagine. Lo stile artistico (es. *cyberpunk, acquerello, iperrealismo fotografico*), il tratto e la palette cromatica devono sempre essere specificati per primi. Stabiliscono le regole d'ingaggio fisiche e luminose e, a differenza dei dettagli narrativi, raramente entrano in conflitto logico con gli altri elementi del prompt.
*   **2. L'Inquadratura come Antidoto all'Effetto IA**
    I generatori tendono naturalmente a una composizione piatta, centrale e scolastica (il classico "tono da IA" visivo). Dichiarare la scelta dell'inquadratura e delle lenti (es. *grandangolo, inquadratura dal basso, over the shoulder, profondità di campo ridotta*) smorza immediatamente l'estetica artificiale, restituendo dinamismo e taglio cinematografico.
*   **3. Sintesi Efficace vs Sovraccarico**
    Scrivere mille parole per un'immagine non la rende migliore. Istruzioni troppo articolate saturano i token del modulo grafico, facendogli perdere la gerarchia delle informazioni. Meno dettagli superflui ci sono, maggiore sarà la coerenza dell'output.
*   **4. La Delega (Prompting Assistito)**
    Non scrivere il prompt visivo da solo. La mossa più intelligente è aprire una chat testuale parallela in cui fornisci all'LLM i concetti che hai in mente, chiedendogli di "progettare" e ottimizzare un prompt tecnico perfetto da dare poi in pasto al generatore grafico.
*   **5. La Gestione della "Reference" e il Reset (Tabula Rasa)**
    Fornire un'immagine di riferimento (*Image Prompting*) a volte vale più di mille parole, offrendo una base solida. Altre volte, però, la reference diventa una gabbia: il modello continua a ripetere gli stessi errori perché tenta di risolvere una contraddizione latente tra l'immagine fornita e il testo richiesto. Quando il generatore inizia ad allucinare, insistere con le correzioni aggrava la frammentazione. La regola è spietata: **non si corregge un contesto visivo corrotto, lo si resetta.**

---

## 2. Due pipeline video, due criteri di successo

La parola *video* può indicare prodotti radicalmente diversi. Un videoclip deve funzionare come esperienza visiva e narrativa: il pubblico giudica ritmo, atmosfera, montaggio e coerenza percettiva. Un video generato per ricavarne sprite, invece, è soltanto materiale intermedio: deve offrire sagome leggibili, frame pulibili, movimento controllato e dati esportabili.

Confondere i due obiettivi produce un errore metodologico. Nel primo caso si può trasformare un'imperfezione in linguaggio stilistico; nel secondo l'imperfezione deve essere misurata, corretta oppure scartata.

| Pipeline | Obiettivo | Unità di lavoro | Controllo principale | Output finale |
| :--- | :--- | :--- | :--- | :--- |
| **Editing video assistito dall'IA** | Costruire una narrazione audiovisiva coerente | Clip e microclip | Regia, continuità percettiva, ritmo e montaggio | Video montato e masterizzato |
| **Produzione di asset da video** | Convertire movimento generato in grafica riutilizzabile | Singoli frame | Sagoma, alpha, pivot, scala e coerenza temporale | Frame, spritesheet e manifest |

Le due pipeline condividono la generazione probabilistica, ma divergono subito dopo. La prima conduce il materiale verso DaVinci Resolve; la seconda verso strumenti di estrazione, mascheratura, allineamento e composizione degli sprite.

---

## 3. Pipeline A — Editing video assistito dall'IA

### 3.1 La generazione non sostituisce il montaggio

Un generatore video produce clip, non un'opera conclusa. Anche quando una singola generazione appare riuscita, restano da governare la relazione con le clip adiacenti, il ritmo, la fotografia, il contrasto, la durata percepita e la coerenza del personaggio.

Il flusso adottato è quindi:

> **Concept → Storyboard → Scomposizione in microclip → Prompt vincolati → Generazione e varianti → Selezione → Upscaling → DaVinci Resolve → Color grading → Montaggio → Master**

La fase generativa viene mantenuta intenzionalmente modulare. Ogni clip riceve, quando possibile:

* una sola azione principale;
* una sola intenzione narrativa;
* un'inquadratura dichiarata;
* pochi personaggi;
* una durata breve, generalmente compresa tra 8 e 10 secondi;
* vincoli persistenti per identità, abbigliamento, postura, ambiente e direzione dello sguardo.

Questo metodo riduce il numero di variabili che il modello deve risolvere simultaneamente. Un prompt complesso non equivale a un controllo maggiore: oltre una certa soglia, moltiplica i punti nei quali la generazione può divergere.

### 3.2 Il prompt come scheda di regia

Nella produzione video il prompt più efficace non è una descrizione letteraria della scena. È una scheda di regia compatta, organizzata secondo una gerarchia stabile:

1. **Soggetto:** chi è presente e quali elementi ne fissano l'identità.
2. **Azione:** un movimento principale, espresso in modo concreto.
3. **Inquadratura:** distanza, angolo, posizione della camera e composizione.
4. **Ambiente:** solo gli elementi indispensabili alla scena.
5. **Luce e stile:** palette, contrasto, matericità e trattamento visivo.
6. **Vincoli negativi:** ciò che non deve comparire o cambiare.

Una formulazione astratta come *«rendi la scena emozionante»* delega al modello tutte le decisioni importanti. Una formulazione registica — *camera fissa, figura di spalle, un solo passo in avanti, controluce duro, nessun movimento laterale* — rende invece verificabile il risultato.

### 3.3 Case study — Video musicale e temi sociali

Il progetto dedicato alla produzione di un video musicale ha richiesto oltre 50 generazioni, delle quali più di 30 sono state selezionate per la lavorazione. Il flusso ha combinato Google Flow, Veo e Omni/Omniflash con una successiva fase di upscaling da 720p a 1080p e montaggio in DaVinci Resolve.

Il primo orientamento fotorealistico è stato progressivamente abbandonato. Le variazioni del volto, i movimenti artificiali e le superfici eccessivamente pulite rendevano evidente l'origine generativa. La soluzione non è stata inseguire un realismo ancora più fragile, ma adottare una grammatica **graphic novel/noir**:

* bianco e nero;
* alto contrasto;
* segno vicino alla china e alla rotoscopia;
* grana visibile;
* ombre controllate;
* composizioni semplici e leggibili.

L'identità del protagonista è stata vincolata tramite immagine guida e una descrizione ricorrente di età, barba, bastone, abbigliamento, postura e zaino. Questo *character lock* non ha eliminato la variabilità, ma l'ha contenuta entro una soglia gestibile in montaggio.

In DaVinci Resolve sono stati applicati interventi non puramente correttivi, ma autoriali: aumento del contrasto, ricalibrazione delle ombre, aggiunta di grana e riduzione intenzionale della continuità del movimento. Il materiale troppo fluido è stato trattato con una cadenza assimilabile allo **stop motion a circa 1 fps**, tramite ripetizione e mantenimento dei frame. Lo scatto risultante ha dissimulato parte delle interpolazioni innaturali e le ha trasformate in scelta stilistica.

Questa operazione esprime un principio generale:

> **Quando un difetto generativo è ricorrente, il montaggio può tentare di nasconderlo; la regia può invece assorbirlo in un linguaggio coerente.**

Tra i problemi incontrati:

* incoerenza del personaggio tra generazioni;
* movimenti eccessivamente fluidi o meccanici;
* texture prive di materia;
* flickering;
* differenze tra anteprima, timeline e render finale;
* perdita di controllo nei prompt con troppe azioni simultanee.

Anche i temi più sensibili sono stati trattati indirettamente, mostrando conseguenze, ambienti e reazioni anziché chiedere al modello rappresentazioni esplicite difficili da controllare. La limitazione tecnica è così diventata anche criterio narrativo.

### 3.4 Case study — Video musicale leggero / soggetto infsntile

Nel progetto dedicato ad un altro video musicale il problema dominante non era l'estetica (su toni pastello anziché noir stavolta) ma la continuità di un personaggio infantile all'interno di una narrazione illustrata. Le prime prove hanno mostrato due derive opposte:

* con una reference troppo vincolante, il soggetto tendeva a deformarsi;
* senza reference, il modello sostituiva progressivamente il protagonista con bambini differenti.

La risposta è stata la creazione di un personaggio persistente, accompagnato da prompt più brevi e centrati sull'azione. Invece di ridescrivere ogni volta tutto il personaggio, il sistema separava l'identità stabile dall'evento richiesto nella singola clip.

La pianificazione più estesa ha organizzato circa 158 secondi in 29 microclip. La grammatica visiva combinava:

* libro pop-up;
* illustrazione ad acquerello vintage;
* aperture e chiusure costruite con frame iniziali e finali;
* transizioni motivate dalla pagina e dalla materia illustrata;
* *match cut* per rappresentare la crescita dal bambino al ragazzo;
* assenza di audio, sottotitoli e testo generato nelle singole clip.

Anche qui il generatore non è stato incaricato di costruire l'intero video. Ha prodotto unità narrative circoscritte, successivamente organizzate attraverso il montaggio. Le prove troppo statiche, simili a slideshow, e quelle soggette a deriva fotorealistica hanno dimostrato l'importanza di specificare un'azione visibile e coerente con il mezzo pittorico.

I due case study conducono a conclusioni differenti ma complementari. Il primo mostra come il montaggio possa trasformare instabilità e fluidità artificiale in stile. Il secondo mostra come la scomposizione, la persistenza del personaggio e le transizioni progettate possano sostenere una narrazione lunga senza affidarne la continuità alla memoria del generatore.

---

## 4. Pipeline B — Produzione di asset grafici da video

### 4.1 Il video come materia prima

Nella produzione di sprite, il video generato non è destinato alla visione finale. È un contenitore temporale dal quale estrarre pose utili. Di conseguenza, qualità cinematografica, movimento realistico e ricchezza dello sfondo diventano secondari o persino dannosi.

La pipeline dello **Sprite Studio** è stata progettata secondo questa sequenza:

> **Generate → Import Video → Extract Frames → Chroma Key / Mask → Crop & Resize → Align → Clean → Select → Compose Layers → Preview Animation → Export**

Ogni passaggio riduce l'incertezza generativa e la converte in dati controllabili.

### 4.2 Generazione vincolata con WAN e WanGP

La generazione locale impiega WAN 2.2 attraverso WanGP, eseguito in un ambiente Python 3.11 isolato. Il sistema normalizza il risultato in due elementi:

* `generated_video.mp4`, contenente la clip;
* `generation_manifest.json`, contenente parametri richiesti, parametri effettivi e metadati della generazione.

Il prompt non cerca una scena completa. Richiede un singolo personaggio a figura intera, movimento semplice, camera fissa, scala costante, orientamento dichiarato e sfondo uniforme. Per una camminata isometrica, per esempio, i vincoli principali diventano:

* identità e abbigliamento invariati;
* orientamento a tre quarti costante;
* camminata sul posto;
* piedi nella stessa area di contatto;
* nessuna rotazione verso la camera;
* nessuna deriva di posizione o scala;
* assenza di morphing e motion blur;
* sfondo chroma key `#00FF00`.

Il generatore può comunque violare questi vincoli. In un test documentato, il verde richiesto `RGB(0,255,0)` è diventato uno sfondo quasi nero, rilevato come `RGB(13,13,8)`. Per questo la pipeline non presume che il prompt sia stato rispettato: misura l'output effettivo e adatta la maschera al materiale ricevuto.

### 4.3 Maschere alpha e rimozione dello sfondo

La rimozione dello sfondo non viene trattata come un semplice comando *remove background*. È un processo composto da:

1. campionamento di uno o più colori da escludere;
2. calcolo della distanza cromatica;
3. regolazione di tolleranza e morbidezza;
4. pulizia delle piccole regioni residue;
5. decontaminazione cromatica dei bordi;
6. controllo manuale della sagoma e dell'alpha.

Nei test documentati sono stati usati, come punto di partenza, tolleranza `45`, softness `15`, cleanup radius `4` ed edge decontamination `100`. Questi valori non costituiscono un preset universale: dipendono dal colore reale dello sfondo, dalla compressione e dalla contaminazione dei bordi.

Lo strumento consente inoltre di includere nella maschera un bordo esterno dell'immagine, espandere controllatamente la regione di sfondo verso la sagoma, aggiungere colori multipli e intervenire manualmente tramite selezioni rettangolari o lasso. La maschera automatica propone; l'operatore verifica.

### 4.4 Ritaglio, ridimensionamento e allineamento

Dopo la generazione dell'alpha, il soggetto viene:

* ritagliato eliminando spazio inutile;
* ridimensionato sul canvas di destinazione;
* posizionato tramite pivot globale o per-frame;
* allineato usando il contatto a terra e ancore anatomiche;
* confrontato mediante onion skin e anteprima in loop.

Il solo allineamento dei piedi non è sempre sufficiente. Oscillazioni della testa o del torace possono rendere instabile una camminata tecnicamente centrata. Per questo lo Sprite Studio usa anche ancore isometriche e consente correzioni manuali frame per frame.

### 4.5 Pulizia e cherry-picking

Una clip di 21, 53 o 81 frame non deve necessariamente produrre un'animazione dello stesso numero di pose. La riduzione è deliberata. Si selezionano soltanto i frame che:

* mantengono identità e proporzioni;
* presentano una silhouette leggibile;
* appartengono a fasi differenti del movimento;
* non contengono arti duplicati o deformazioni;
* conservano equipaggiamento e dettagli essenziali;
* producono un ciclo comprensibile quando messi in sequenza.

Questo è il significato operativo del *cherry-picking*: non scegliere semplicemente i frame più belli, ma il gruppo minimo capace di descrivere il movimento.

Gli interventi di clean-up includono cancellazione su alpha, pittura pixel, selezione rettangolare, lasso poligonale, correzione dei bordi e propagazione controllata delle modifiche agli altri frame. La pulizia automatica accelera il lavoro; quella manuale conserva la decisione artistica.

### 4.6 Esportazione degli asset

Un test reale ha trasformato una clip di `480×848`, 21 frame e 0,875 secondi in una camminata composta da 4 frame:

* canvas: `96×96` pixel;
* pivot: `[48,88]`;
* riproduzione: `12 fps`;
* spritesheet: griglia `4×1`, dimensione totale `384×96`;
* formato: `.webp`;
* direzione di partenza: sud-ovest;
* variante sud-est ottenuta tramite mirroring controllato.

L'esportazione non produce soltanto immagini. Comprende frame individuali, spritesheet, manifest e informazioni necessarie a ricostruire direzioni, pivot, durata e ordine dell'animazione nel motore di gioco.

---

## 5. Prompt operativo per una clip destinata agli sprite

Il seguente esempio è una ricostruzione fedele dei vincoli utilizzati nei test con WAN 2.2; non è presentato come trascrizione letterale di un singolo prompt storico.

```text
Animate the exact character shown in the reference image.

Preserve the character's identity, proportions, facial features, clothing,
torn poncho, belts, equipment and forearm device.

Strict 16-bit pixel-art appearance. Full-body character performing a
restrained two-step walk-in-place cycle.

Maintain the same South-East three-quarter orientation for the entire
sequence. The character must not turn toward the camera or change direction.

Keep the character centered and at a constant scale. Feet remain within
the same ground-contact area. Static camera, fixed framing and perspective.

Use a flat, uniform chroma-key green background: #00FF00.
No scenery, props, environmental elements or background texture.

The movement must be readable and suitable for extracting individual
animation frames for a game sprite.
```

Negative prompt:

```text
front view, side view, back view, direction change, body rotation,
turning toward camera, camera movement, camera shake, zoom, pan, tilt,
character drift, scale change, perspective change, cropped feet,
identity change, clothing change, missing equipment, extra accessories,
malformed hands, malformed feet, duplicated limbs, anatomical deformation,
morphing, flickering, motion blur, realistic rendering, smooth antialiasing,
painterly style, dynamic lighting, cast shadows, textured background,
scenery, objects, text, subtitles, watermark
```

La struttura del prompt è più importante delle singole parole: prima si fissa ciò che deve restare stabile, poi si descrive il solo movimento ammesso, infine si escludono le derive già osservate.

---

## 6. Il principio comune: generare, misurare, trasformare

I due flussi convergono su una stessa lezione. Il prompt non è il prodotto, e la generazione non è la conclusione del lavoro.

Nel videoclip, l'autore seleziona e trasforma le clip attraverso regia, contrasto, cadenza, fotografia e montaggio. Nello Sprite Studio, seleziona e trasforma i frame attraverso maschere alpha, ritaglio, allineamento, pulizia e composizione.

> **L'IA genera possibilità. La pipeline le rende utilizzabili. L'autore decide quali meritano di diventare opera o strumento.**

La responsabilità non consiste soltanto nello scrivere un buon prompt. Consiste nel verificare cosa è stato realmente prodotto, riconoscere le derive, documentare i fallimenti e applicare un processo capace di trasformare materiale probabilistico in un risultato intenzionale.
