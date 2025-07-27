# Delta Lake

Delta Lake è un livello di storage open-source che si integra con i data lake (come quelli su Amazon S3, Azure Data Lake, HDFS) per fornire affidabilità, performance e gestione transazionale dei dati.

## Caratteristiche principali

- **Transazioni ACID**: garantisce coerenza e affidabilità delle operazioni sui dati, anche in ambienti distribuiti.
- **Gestione versioni (Time Travel)**: permette di accedere e ripristinare versioni precedenti dei dati.
- **Schema enforcement & evolution**: controlla e gestisce automaticamente i cambiamenti di schema.
- **Scalabilità**: ottimizzato per grandi volumi di dati e workload di big data.
- **Performance elevate**: migliora le prestazioni delle query tramite ottimizzazioni come data skipping e file compaction.

## Vantaggi

- Unifica batch e streaming: consente di gestire dati in tempo reale e dati storici nello stesso storage.
- Riduce la duplicazione e la complessità delle pipeline dati.
- Facilita la governance e la qualità dei dati nei data lake.

## Tecnologie correlate

- **Databricks**: principale piattaforma che ha sviluppato e promuove Delta Lake.
- **Apache Spark**: Delta Lake si integra nativamente con Spark per l’elaborazione distribuita.

## Esempio di utilizzo

```python
from delta.tables import DeltaTable
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("DeltaLakeExample").getOrCreate()

# Scrittura di un DataFrame in formato Delta
df.write.format("delta").save("/mnt/datalake/delta/my-table")

# Lettura dei dati Delta
delta_df = spark.read.format("delta").load("/mnt/datalake/delta/my-table")
```

## Risorse

- [Sito ufficiale Delta Lake](https://delta.io/)
- [Documentazione Databricks Delta Lake](https://docs.databricks.com/delta/)