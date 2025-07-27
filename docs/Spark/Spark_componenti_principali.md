# Componenti Principali

Apache Spark è un framework open-source per l'elaborazione distribuita dei dati, progettato per velocità, facilità d'uso e analisi avanzate. È ampiamente utilizzato nell'ingegneria dei dati per gestire grandi volumi di dati in modo efficiente.

il cuore del framework e fornisce funzionalità essenziali come:

- Gestione della memoria e delle operazioni di calcolo distribuito.
- Pianificazione dei task e ottimizzazione dell'esecuzione.
- API di base per RDD (Resilient Distributed Dataset), l'elemento fondamentale per la gestione dei dati distribuiti in Spark.

https://spark.apache.org/docs/latest/

### **Spark SQL**

Modulo per l'elaborazione di dati strutturati. Le caratteristiche principali includono:

- Supporto per SQL standard e DataFrame API.
- Integrazione con database e data warehouse.
- Ottimizzazione automatica delle query grazie al motore Catalyst.

### **Spark Streaming**

Consente l'elaborazione di dati in tempo reale tramite micro-batch. Caratteristiche principali:

- Elaborazione di flussi di dati provenienti da Kafka, Flume, HDFS, e altri.
- Supporto per trasformazioni complesse come join e aggregazioni su flussi.
- Fault tolerance e scalabilità nativa.

### **MLlib (Machine Learning Library)**

Libreria per l'apprendimento automatico su larga scala, con strumenti per:

- Regressione, classificazione, clustering e riduzione della dimensionalità.
- API ottimizzate per operazioni distribuite.
- Integrazione con strumenti esterni come TensorFlow e scikit-learn.

### **GraphX**

Modulo per la computazione su grafi distribuiti, con supporto per:

- Rappresentazione efficiente di strutture di grafi.
- Algoritmi per analisi di reti (es. PageRank, Connected Components).
- Estensione delle API RDD per operazioni sui grafi.

### **SparkR e PySpark**

- **SparkR**: Integrazione di Spark con R, utile per analisi statistiche avanzate.
- **PySpark**: API per interagire con Spark usando Python, ampiamente adottata per la data science.

### **Struttura di Esecuzione di Spark**

Spark si basa su un'architettura master-worker:

- **Driver**: Coordina l'esecuzione e gestisce le applicazioni Spark.
- **Cluster Manager**: Gestisce le risorse di esecuzione (YARN, Mesos o Kubernetes).
- **Executor**: Esegue i task sui nodi worker.