<p align="center">
  <img src="assets/copertina.png" alt="Copertina di LLM — Metodo, struttura e responsabilità" width="420">
</p>

# LLM — Metodo, struttura e responsabilità

**Nel lavoro con modelli linguistici generativi**  
**Giovambattista Scavo**

Manuale operativo in italiano sul lavoro con LLM: progettazione dei prompt, gestione del contesto, diagnostica, prompting meta-cognitivo, strutture complesse, BLCDD e applicazioni a testo, narrativa, produzione visiva e codice.

*Italian-language operational manual on prompting, context management, verification, AI-assisted workflows and the BLCDD method.*

**Versione 1.0.0 — settembre 2026**

## Leggi il manuale

- **[Edizione Markdown](MANUALE.md)** — leggibile direttamente su GitHub.
- **[Edizione DOCX](editions/LLM_Manuale_v1.0.docx)** — versione impaginata per lettura e distribuzione offline.

Le due edizioni condividono la stessa baseline editoriale. Il Markdown adatta soltanto gli elementi dipendenti dal mezzo: gerarchia delle intestazioni, indice, collegamenti interni e gestione delle immagini.

## Di cosa parla

Il manuale parte da un principio semplice: un LLM non è un archivio affidabile né una mente umana, ma un sistema generativo probabilistico inserito in un prodotto che può aggiungere memoria, retrieval, file, strumenti e altre forme di orchestrazione.

Da questa distinzione costruisce un metodo operativo per:

- progettare richieste più chiare e verificabili;
- scegliere tra prompting progressivo e specifiche monolitiche;
- mantenere continuità nei progetti lunghi;
- diagnosticare errori di prompt, contesto, modello, sistema e processo;
- usare il prompting meta-cognitivo come feedback sull'interazione;
- organizzare più contesti, fonti autoritative e handoff;
- governare il cambiamento attraverso **BLCDD**;
- decidere quando delegare a strumenti e agenti e quando mantenere controllo diretto.

## BLCDD

Il manuale formalizza **BLCDD** come metodo per far evolvere un progetto assistito da LLM senza perdere ciò che è già stato validato:

**Baseline → Locked Contracts → Change-impact Audit → Deliberate Minimal Intervention → Demonstrated Delivery**

L'idea centrale è semplice: una versione non diventa baseline perché è più recente, ma perché esiste evidenza sufficiente per promuoverla.

## Struttura

La **Parte I — Metodo** sviluppa i principi generali in nove capitoli: funzionamento operativo degli LLM, progettazione del prompt, continuità, diagnostica, prompting meta-cognitivo, architettura dei contesti, BLCDD e gestione dei limiti.

La **Parte II — Applicazioni** trasferisce gli stessi principi a quattro domini:

- produzione testuale;
- worldbuilding e narrativa;
- produzione visiva e pipeline ibride;
- codice e agenti.

Una quinta appendice rende trasparente la provenienza dei casi di studio reali utilizzati nel libro.

## A chi è rivolto

Il manuale è pensato per chi usa sistemi basati su LLM come strumenti di lavoro, progettazione o produzione e vuole maggiore controllo su contesto, verifiche e continuità. Non è un corso di machine learning, non richiede competenze di programmazione e non è una raccolta di prompt "magici".

## Trasparenza sull'uso dell'IA

Questo manuale è stato sviluppato con assistenza LLM. I modelli hanno partecipato a brainstorming, strutturazione, confronto, riscrittura e revisione. Il manoscritto è poi passato attraverso audit tecnici ed editoriali, baseline successive e decisioni esplicite di promozione.

È una scelta coerente con il metodo esposto nel libro: l'assistenza generativa può essere estesa; l'autorità sul risultato resta umana.

## Segnalazioni e contributi

Correzioni fattuali, refusi, problemi di chiarezza e osservazioni sul metodo sono benvenuti. Prima di proporre modifiche sostanziali, consulta **[CONTRIBUTING.md](CONTRIBUTING.md)**.

## Citazione

La repository include **[CITATION.cff](CITATION.cff)** per generare una citazione coerente del manuale attraverso GitHub.

## Versioni

Le modifiche editoriali e metodologiche sono registrate in **[CHANGELOG.md](CHANGELOG.md)**. La versione corrente è indicata anche nel file **[VERSION](VERSION)**.

## Licenza

La repository storica utilizza attualmente una licenza MIT. Prima della pubblicazione definitiva della versione 1.0 è opportuno confermare che questa scelta corrisponda ai diritti di riuso desiderati per un'opera testuale.
