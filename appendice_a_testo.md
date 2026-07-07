# APPENDICE A: Produzione di Testo e Libreria dei Prompt

La differenza tra un utente e un progettista non sta nello strumento che usano, ma nel modo in cui lo istruiscono. Un prompt amatoriale delega le decisioni al modello, sperando che indovini l'intento. Un prompt architetturale fissa vincoli, stabilisce ruoli e definisce la struttura dell'output.

## Tabella Comparativa: Chiedere vs Orchestrare

| Obiettivo / Scenario | L'Approccio Superficiale (Il Prompt Pigro) | L'Approccio Architetturale (Il Metodo) | Perché l'approccio avanzato funziona |
| :--- | :--- | :--- | :--- |
| **Analisi di un testo complesso** | *"Fammi un riassunto di questo testo evidenziando le cose importanti."* | **[Strategia Monolitica]**<br>*"Agisci come un editor esperto. Analizza il testo seguente. Estrai: 1. I tre temi principali. 2. Il target di riferimento implicito. 3. Due debolezze logiche nell'argomentazione. Formatta l'output in un elenco puntato."* | Rimuove l'ambiguità del concetto di "importante". Definisce un ruolo, fornisce istruzioni dirette numerate e impone un vincolo strutturale all'output. |
| **Scrittura con tono specifico** | *"Scrivi un post LinkedIn per annunciare il mio nuovo servizio, rendilo accattivante e professionale."* | **[Strategia A Layer - Layer 1]**<br>*"Stiamo per scrivere un post. Il tono deve essere autorevole ma non accademico. Evita frasi fatte (es. 'nel vasto panorama'), usa frasi brevi e non superare le 150 parole. Nel prossimo prompt ti fornirò i dati del servizio. Conferma di aver assimilato queste regole stilistiche."* | Isola la variabile stilistica. Fornisce "istruzioni negative" (cosa non fare) ed evita di saturare il modello caricando contemporaneamente regole di stile e dati di contenuto. |
| **Risoluzione Problemi / Brainstorming** | *"Dammi 5 idee per migliorare la produttività del mio team di lavoro."* | **[Prompting Meta-cognitivo]**<br>*"Devo trovare 3 soluzioni pratiche per migliorare la produttività del mio team. Prima di proporre qualsiasi idea, fammi 3 domande diagnostiche specifiche sul mio team, sui nostri processi attuali e sui colli di bottiglia, per calibrare al meglio la tua risposta successiva."* | Ribalta la dinamica: usa il modello per fare domande, costringendo l'utente a chiarire il contesto. Evita soluzioni standardizzate (la "media statistica") e forza un output iper-personalizzato. |
| **Gestione di un errore del modello** | *(Dopo un output sbagliato)*<br>*"No, hai sbagliato, non intendevo questo. Rifallo in modo diverso."* | **[Diagnostica e Correzione]**<br>*"Analizza la risposta che mi hai appena dato. Quale parte del mio prompt precedente hai interpretato come prioritaria e perché hai tralasciato il vincolo sulla brevità? Spiegami il tuo processo prima di rigenerare il testo."* | Non combatte il sintomo, ma cerca la causa. Rende visibile il *parsing* del modello, permettendo all'utente di capire quale istruzione ha creato la deriva e come evitarla in futuro. |

---

## 1. Produzione di Testo: L'Approccio Metodico (Articoli, Social, Email)

La produzione testuale con un LLM copre un ventaglio enorme di necessità: dal post social veloce alla mail professionale, fino alla stesura di un saggio lungo o un articolo di blog. Che il testo sia breve o richieda una pianificazione a lungo termine, la procedura di base è la stessa, ma cambia la strutturazione dei prompt. 

Nel caso dei **testi rapidi e seriali**, il rischio maggiore è la pigrizia. Per evitare la banalità, la produzione deve essere divisa in fasi preparatorie:

*   **Fase 1: L'Obiettivo (La Bussola)**
    Qual è lo scopo reale di questo testo? Deve informare, persuadere, allarmare, intrattenere o far compiere un'azione? L'obiettivo è il vincolo primario che dà la direzione all'algoritmo.
*   **Fase 2: Lo Stile e il Tono (L'Abito)**
    Deve essere un testo asciutto e aziendale? Oppure colloquiale, ironico e ritmato? Impostare il tono in modo esplicito impedisce al modello di scivolare nella sua "media statistica".
*   **Fase 3: L'Impronta Personale (L'Estrazione dei Pattern)**
    Anche con un buon tono, il testo rischia di sembrare freddo. Le tecniche più efficaci sono:
    *   **Il Testo Ombra:** Fornire un proprio periodo o paragrafo come riferimento esclusivo per il ritmo e la sintassi.
    *   **Il Glossario Strategico:** Dichiarare un elenco di parole chiave e concetti da privilegiare.
    *   **Il Prompting Inverso dello Stile:** Far analizzare al modello i propri scritti precedenti per fargli mappare pattern comunicativi.
    *   **Ufficializzare le "Tare Verbali":** Il modello può e deve apprendere le imperfezioni stilistiche dell'utente (iniziare i periodi con una congiunzione, usare spesso snodi avversativi).
*   **Fase 4: La Verifica e la Ricalibrazione (Il Banco di Prova)**
    La prima risposta non è quasi mai il traguardo. Si ricorre a due test avanzati:
    *   **L'A/B Testing del Contesto:** Si apre una nuova chat e si sottopone la richiesta *senza* i vincoli. Se il testo "nudo" risulta più fluido, la struttura impostata sta soffocando il modello.
    *   **Il Cross-Model Auditing (L'Arbitro Esterno):** Si prende l'output generato e lo si fa valutare a un LLM con un'architettura diversa. Questo scontro tra matrici probabilistiche fa emergere difetti invisibili.

---

## 2. Produzione di Testi Lunghi: L'Architettura e i Riferimenti Stabili

Se per un testo breve basta una solida impalcatura iniziale, per i testi lunghi (saggi, manuali, romanzi) la pianificazione cresce in modo direttamente proporzionale. Si passa alla costruzione di un ecosistema documentale:

*   **L'Indice:** Una scaletta dettagliata che faccia da mappa di navigazione per ogni sessione di generazione.
*   **La Bibliografia di Riferimento:** Fonti e appunti fissati a monte per evitare che il modello allucini dati.
*   **Le Routine di Verifica Preimpostate:** Strumenti di diagnostica residenti nel modello stesso. Si istruisce la macchina a eseguire ciclicamente verifiche sintattiche, revisioni editoriali e controlli di coerenza incrociati con l'indice, automatizzando il controllo qualità.
