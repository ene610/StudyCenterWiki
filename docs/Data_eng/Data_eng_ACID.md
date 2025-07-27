
# ACID

ACID è un acronimo che descrive le quattro proprietà fondamentali che una transazione deve garantire in un database per essere affidabile:

Atomicità: la transazione è indivisibile; o tutte le operazioni vengono eseguite, o nessuna.
Consistenza: la transazione porta il database da uno stato valido a un altro stato valido, rispettando tutte le regole e i vincoli.
Isolamento: le transazioni concorrenti non interferiscono tra loro; ogni transazione sembra essere eseguita da sola.
Durabilità: una volta completata, una transazione è permanente; i dati non vengono persi anche in caso di crash del sistema.
Queste proprietà garantiscono integrità e affidabilità nelle operazioni sui dati.


## Proprietà ACID delle Transazioni

Le transazioni nei database devono rispettare le proprietà **ACID** per garantire affidabilità e integrità dei dati:

| Proprietà    | Descrizione                                                                 |
|--------------|-----------------------------------------------------------------------------|
| **Atomicità**    | Tutte le operazioni della transazione vengono completate oppure nessuna viene eseguita. |
| **Consistenza**  | La transazione porta il database da uno stato valido a un altro stato valido, rispettando tutte le regole e i vincoli. |
| **Isolamento**   | Le transazioni concorrenti non interferiscono tra loro; ogni transazione sembra essere eseguita da sola. |
| **Durabilità**   | Una volta completata, una transazione è permanente anche in caso di guasti di sistema. |

> **Esempio**:  
> Se trasferisci denaro da un conto A a un conto B, la transazione deve sottrarre l’importo da A e aggiungerlo a B. Se una delle due operazioni fallisce, nessuna delle due viene applicata (atomicità).
