# Ottimizzazioni possibili

## **Ottimizzazioni delle Query con Catalyst Optimizer**

Spark SQL utilizza **Catalyst Optimizer**, un motore di ottimizzazione che migliora automaticamente l’esecuzione delle query.

- **Ottimizzazione logica**: riorganizza l’ordine delle operazioni per migliorare le prestazioni.
- **Ottimizzazione fisica**: sceglie il piano di esecuzione migliore basandosi sulle statistiche dei dati.
- **Predicate Pushdown**: evita di caricare dati non necessari applicando i filtri il prima possibile.

📌 **Esempio:**

```python
df_filtered = spark.read.parquet("data.parquet").filter("age > 30")
```

Qui il filtro viene applicato **prima** di leggere i dati, riducendo l’I/O.

## **Uso Ottimale di Partizioni**

Le partizioni influiscono direttamente sulle prestazioni di Spark:

- **Troppe partizioni** → Overhead di gestione dei task.
- **Poche partizioni** → Scarso parallelismo.

🔹 **Controllare il numero di partizioni:**

```python
df.rdd.getNumPartitions()
```

```python
df = df.repartition(10)  # Aumenta il parallelismo
df = df.coalesce(5)  # Riduce il numero di partizioni senza shuffle eccessivo
```

## Uso di cache e Persistenza

Se un DataFrame viene riutilizzato più volte, è utile **memorizzarlo in cache** per evitare ricalcoli.

🔹 **Memorizzare un DataFrame in memoria:**

```python
df.cache()
df.count()  # Attiva la cache

# persiste il dataFrame
df.persist(StorageLevel.DISK_ONLY)  # Salva solo su disco

# A fine operazione ricorda di unpersisterlo
df.unpersist()
```

## **Evitare le Operazioni Costose di Shuffle**

Le operazioni come `groupBy()`, `join()`, e `distinct()` possono generare **shuffle**, rallentando le performance.

- Usa **reduceByKey()** invece di `groupByKey()`
- Usa **broadcast join** per piccoli dataset
- Riduci il numero di partizioni dello shuffle con `spark.sql.shuffle.partitions`

📌 **Esempio di Broadcast Join:**

```python
from pyspark.sql.functions import broadcast
df_large.join(broadcast(df_small), "id")
```

## **Formati di File Efficienti**

Scegliere il formato di file giusto può migliorare la velocità di lettura e scrittura:

- **Parquet** e **ORC** sono ottimizzati per Spark e supportano la compressione e il predicate pushdown.
- **Evita CSV e JSON** per dataset di grandi dimensioni.