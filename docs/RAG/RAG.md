# RAG - retrive Augumented Generation

**RAG** è un tipo di intelligenza artificiale che combina **due capacità**:

1. **Cercare informazioni** (Retrieval)
2. **Generare testo** (Generation)

In pratica, quando fai una domanda a un sistema basato su RAG, lui **prima va a cercare** le informazioni più utili in una raccolta di documenti, e **poi crea la risposta** usando quelle informazioni.

In questo modo, si rende l’intelligenza artificiale **più utile nei casi d’uso della vita reale**, dato che può "leggere" nuove fonti e darti risposte basate su di esse, invece di inventare.

## Cos’è RAG – Retrieval-Augmented Generation

**RAG** è un'architettura ibrida proposta da Facebook AI (2020) che combina i modelli di **retrieval** (recupero informazioni) con i **modelli generativi pre-addestrati** (es. BART, T5 o GPT). L’obiettivo è potenziare la generazione di testo tramite l'accesso a **documenti esterni** durante l’inferenza.

- **Recupero (Retrieval)**: Quando un utente pone una domanda, il sistema RAG non la invia direttamente all'LLM. Prima, esegue una ricerca in un database di conoscenza esterno e autorevole, che può contenere documenti, articoli, database aziendali, o qualsiasi altro tipo di informazione. Questa ricerca si basa sulla "similarità semantica", trovando i documenti o i "pezzi" di testo più rilevanti per la domanda dell'utente. Questa fase è spesso facilitata da un "database vettoriale", che converte il testo in rappresentazioni numeriche (vettori) per una ricerca più rapida ed efficiente.
- **Aumento (Augmentation)**: Le informazioni recuperate nella fase precedente vengono "aumentate", cioè aggiunte alla domanda originale dell'utente. Si crea così un "prompt" più ricco e contestualizzato.
- **Generazione (Generation)**: Il prompt aumentato viene quindi inviato all'LLM. A questo punto, l'LLM non si basa solo sulla sua conoscenza pre-esistente, ma ha a disposizione un contesto aggiuntivo e specifico, che lo guida nella generazione di una risposta più precisa, pertinente e basata sui fatti.