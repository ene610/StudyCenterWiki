# Executor / driver / worker

### 🔹 1. **Driver**

- È il **cuore della Spark Application**.
    - Esegue il **main()** del programma Spark.
    - Coordina l'esecuzione di job, stage e task.
    - Tiene in memoria il **DAG Scheduler**, lo **SparkContext** e le informazioni sul piano di esecuzione.

📌 Funzioni principali:

- Analizza il piano logico e lo trasforma in job/stage/task
- Invia i task agli executor
- Raccoglie i risultati parziali o finali

### 🔹 2. **Executor**

- Processo **distribuito** che esegue i **task** su un Worker.
    - Ogni Executor ha **memoria dedicata**, **thread pool**, e **cache locale**.
    - Viene avviato all'inizio dell'applicazione e chiuso alla fine.

📌 Funzioni principali:

- Esegue i task (lettura dati, trasformazioni, scrittura)
- Caching dei dati in memoria (con `.cache()`)
- Restituisce i risultati al driver

🧠 Ogni Spark Application ha **i suoi executors** isolati (non condivisi).

### 🔹 3. **Worker**

È un **nodo fisico o virtuale del cluster** che ospita uno o più executor.

- Gestisce le risorse (CPU, memoria) assegnate agli executor.
- Esegue anche il **Driver** in modalità *cluster*.

📌 In un cluster Spark:

- Ogni worker riceve risorse dal **Cluster Manager** (YARN, Kubernetes, etc)
- Ogni worker può eseguire più executor (a seconda della configurazione)

---

## Flusso di esecuzione

1. Il **Driver** contatta il **Cluster Manager** e richiede risorse.
2. Il Cluster Manager avvia gli **Executors** sui **Worker Nodes**.
3. Il Driver suddivide il lavoro in **task** e li distribuisce agli executors.
4. Gli **Executors** eseguono i task e restituiscono i risultati al Driver.
5. Alla fine, Driver e Executors vengono terminati.