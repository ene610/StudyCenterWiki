# Differenza tra Managed Table ed External Table in Databricks

In Databricks, le tabelle possono essere di due tipi principali: **Managed (interne)** ed **External (esterne)**. La scelta tra questi due tipi influisce su come vengono gestiti i dati sottostanti e sulle responsabilità di gestione dello storage.

---

## Managed Table (Tabella Gestita)

- **Definizione**: Databricks gestisce sia i metadati che i dati fisici della tabella.
- **Percorso dati**: I dati vengono salvati in una directory gestita dal workspace Databricks (tipicamente sotto `/user/hive/warehouse`).
- **Cancellazione**: Se si elimina la tabella, vengono eliminati sia i metadati che i dati fisici.
- **Use case**: Consigliata quando si vuole che Databricks gestisca completamente il ciclo di vita dei dati.

**Esempio di creazione:**
```sql
CREATE TABLE vendite (
  id INT,
  prodotto STRING,
  importo DOUBLE
);
```

---

## External Table (Tabella Esterna)

- **Definizione**: Databricks gestisce solo i metadati; i dati fisici risiedono in un percorso esterno specificato dall’utente (ad esempio, un bucket S3 o una directory su ADLS).
- **Percorso dati**: L’utente specifica il percorso fisico dei dati tramite la clausola `LOCATION`.
- **Cancellazione**: Se si elimina la tabella, vengono rimossi solo i metadati; i dati fisici restano intatti.
- **Use case**: Utile quando si vogliono condividere dati tra più sistemi o mantenere il controllo diretto sui file.

**Esempio di creazione:**
```sql
CREATE TABLE clienti_esterni (
  id INT,
  nome STRING
)
USING PARQUET
LOCATION '/mnt/datalake/tabelle/clienti/';
```

---

## Tabella Comparativa

| Caratteristica         | Managed Table                | External Table                   |
|----------------------- |-----------------------------|----------------------------------|
| Gestione dati fisici   | Databricks                  | Utente                           |
| Eliminazione tabella   | Cancella dati e metadati    | Cancella solo metadati           |
| Percorso dati          | Interno (warehouse)         | Esterno (specificato dall’utente)|
| Use case tipico        | Dati temporanei, sandbox    | Dati condivisi, storage esterno  |

---

## Sintesi

- **Managed Table**: gestione automatica, dati cancellati con la tabella.
- **External Table**: controllo sul percorso dati, dati persistenti anche dopo