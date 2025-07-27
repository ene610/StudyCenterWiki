# Delta Lake Transaction Log

Il transaction log di Delta Lake, spesso chiamato **Delta Log**, è un registro ordinato di tutte le transazioni eseguite su una tabella sin dalla sua creazione. Questo log rappresenta la fonte di verità per lo stato e la storia della tabella. Ogni volta che si interroga la tabella, Spark consulta il transaction log per determinare la versione più recente dei dati.

Ogni transazione confermata viene registrata in un file JSON. Questo file contiene dettagli essenziali sulle operazioni eseguite, come il tipo di operazione (inserimento, aggiornamento, ecc.) e le eventuali condizioni o filtri utilizzati.

Oltre a tracciare le operazioni, il log registra anche i nomi di tutti i file di dati coinvolti in queste operazioni.

Queste capacità transazionali vengono sfruttate da Delta Lake per garantire la conformità ACID durante il recupero e