# Data Quality - Appunti Tecnici

La **data quality** è un concetto centrale nei sistemi di gestione e analisi dei dati. Indica quanto i dati siano affidabili, precisi e adatti agli scopi per cui vengono utilizzati. In contesti moderni come i data lakehouse, la qualità dei dati influisce direttamente sulla capacità di prendere decisioni corrette, costruire modelli predittivi robusti e soddisfare requisiti normativi.

---

## 1. Dimensions of Data Quality

Le principali dimensioni riconosciute per valutare la qualità dei dati sono:

### - **Accuracy**
Misura quanto i dati riflettano la realtà in modo corretto. Ad esempio, un indirizzo o una data di nascita devono essere esatti rispetto alla fonte originaria. Errori di digitazione o importazione possono compromettere l'accuratezza.

### - **Completeness**
I dati devono contenere tutti gli elementi richiesti. Campi mancanti, nulli o non valorizzati possono impedire analisi accurate o generare errori a runtime.

### - **Consistency**
I dati devono mantenere coerenza tra sistemi, tabelle o fonti. Se in un sistema il cliente è attivo e in un altro è inattivo, si ha un'incongruenza.

### - **Timeliness**
I dati devono essere aggiornati e disponibili nel momento in cui servono. La latenze nei processi ETL o stream possono rendere inutili dati altrimenti validi.

### - **Uniqueness**
Ogni entità deve essere rappresentata una sola volta. Duplicazioni portano a distorsioni nelle metriche (es. doppio conteggio clienti).

### - **Validity**
I dati devono rispettare i vincoli e le regole di dominio: formati, tipi, range e pattern. Per esempio, un codice fiscale italiano deve rispettare una struttura alfanumerica ben definita.

---

## 2. Data Quality Evaluation

### Data Profiling
Analizza dataset per individuarne struttura, statistiche descrittive, distribuzioni e outlier. Strumenti come **pandas-profiling**, **Great Expectations** o **Deequ** forniscono insight automatici su nulli, cardinalità, min/max, pattern testuali, ecc.

### Data Quality Rules
Si definiscono regole personalizzate che i dati devono rispettare. Possono essere implementate in SQL, in framework come **dbt tests**, o in piattaforme come **Talend Data Quality**.

Esempio in SQL:
```sql
CHECK (email LIKE '%@%')