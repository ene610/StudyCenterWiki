# Delta Lake Time Travel

Delta Lake introduce una potente funzionalità chiamata **Time Travel**, che consente di accedere, interrogare e ripristinare versioni precedenti di una tabella. Questa caratteristica è fondamentale per garantire la tracciabilità, la sicurezza e la qualità dei dati, offrendo la possibilità di recuperare dati cancellati o modificati per errore, effettuare audit e analisi retrospettive, e supportare casi d’uso di data recovery.



## Delta Table Time Travel

Delta Lake fornisce funzionalità di time travel, permettendo di interrogare versioni precedenti dei dati.

### Che cos'è il Time Travel?

Il time travel consente di:

- Accedere ai dati così com'erano in uno specifico timestamp o numero di versione
- Ripristinare facilmente modifiche o cancellazioni accidentali
- Eseguire audit sullo storico dei dati per conformità e controllo
- Analizzare l’evoluzione dei dati nel tempo



## Come funziona

Delta Lake mantiene uno **storico delle versioni** di ogni tabella tramite il transaction log (Delta Log). Ogni modifica (inserimento, aggiornamento, cancellazione) crea una nuova versione della tabella, che può essere richiamata in qualsiasi momento tramite query specifiche.



### Sintassi

#### Query per versione

```sql
SELECT * FROM delta.`/path/to/table` VERSION AS OF 5;
```

#### Query per timestamp

```sql
SELECT * FROM delta.`/path/to/table` TIMESTAMP AS OF '2024-07-01T12:00:00';
```


#### Restore di una tabella tramite Transaction Log

Il **restore** permette di riportare una tabella Delta Lake a una versione precedente, annullando modifiche indesiderate o errori. Questo processo sfrutta il transaction log, che contiene la cronologia completa delle operazioni sulla tabella. Quando si esegue un restore, Delta Lake applica le informazioni del log per ricostruire lo stato esatto della tabella a una determinata versione o timestamp.

**Esempio di restore tramite SQL:**
```sql
RESTORE TABLE nome_tabella TO VERSION AS OF 10;
```
Oppure tramite timestamp:
```sql
RESTORE TABLE nome_tabella TO TIMESTAMP AS OF '2024-07-01T12:00:00';
```
Dopo il restore, la tabella viene aggiornata allo stato corrispondente a quella versione, mantenendo comunque la possibilità di accedere alle versioni precedenti grazie al transaction log.



## Esempi di utilizzo

- **Recupero dati cancellati accidentalmente**  
  Se una riga è stata cancellata per errore, puoi recuperarla interrogando la versione precedente della tabella.
- **Audit e controllo**  
  Puoi verificare come erano i dati in un determinato momento per esigenze di audit o conformità.
- **Analisi retrospettiva**  
  Analizza l’evoluzione dei dati confrontando diverse versioni della stessa tabella.



## Vantaggi del Time Travel

- Migliora la sicurezza e la governance dei dati
- Facilita il debugging e il data recovery
- Supporta processi di audit e compliance