# APPENDICE C: Produzione Visiva (Immagini e Video)

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
