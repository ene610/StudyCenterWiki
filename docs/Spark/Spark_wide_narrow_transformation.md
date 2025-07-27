# Wide / Narrow Trasformation

### 🔹 Narrow Transformation

Una **narrow transformation** è un'operazione in cui ogni partizione dell'output **dipende da una sola partizione dell'input**. Non comporta lo shuffle dei dati tra i nodi.

### 🔸 Wide Transformation

Una **wide transformation** è un'operazione in cui i dati devono essere **ridistribuiti** tra più nodi, spesso tramite **shuffle**. L’output di una partizione può dipendere da più partizioni dell’input.

### Shuffle

In **Apache Spark**, i dati sono divisi in partizioni elaborate in parallelo da worker su nodi del cluster. Con operazioni come `map` o `filter`, ogni partizione viene elaborata indipendentemente e velocemente.

Con **groupBy** o **join**, invece, occorre combinare dati da partizioni diverse, anche su macchine diverse. Spark deve quindi riorganizzare i dati affinché quelli con la stessa chiave si trovino insieme - questo è la **shuffle**.

Durante la shuffle, Spark **sposta i dati** tra partizioni e nodi, scrivendo temporaneamente su disco e trasferendoli via rete. Questo processo è più lento delle operazioni che non richiedono spostamenti.

È come riordinare documenti sparsi su più scrivanie per cognome: devi **passare i documenti** tra le scrivanie per raggruppare quelli con lo stesso cognome.

Spark cerca di **minimizzare le shuffle**: `reduceByKey` è più efficiente di `groupByKey` perché elabora dati **localmente** prima di spostarli.