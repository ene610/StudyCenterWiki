# Data Mesh

Negli ultimi anni, sempre più aziende si sono rese conto che **i dati sono un asset fondamentale** per guidare le decisioni, ottimizzare processi e creare nuovi servizi. Il problema è che, man mano che le organizzazioni crescono, **gestire i dati in modo centralizzato** diventa sempre più difficile.

Tradizionalmente, le aziende hanno seguito un approccio chiamato **data lake o data warehouse centralizzato**: tutti i dati vengono raccolti da vari sistemi (vendite, marketing, produzione, ecc.), puliti e trasformati da un **team centrale** (spesso chiamato “data team”), e poi messi a disposizione degli utenti business.

Sulla carta suona bene, ma in pratica questo modello ha diversi problemi:

- Il team centrale diventa un **collo di bottiglia**.
- I dati arrivano in ritardo o in forma non aggiornata.
- Chi conosce veramente il significato dei dati (cioè i team di dominio, come marketing o logistica) **non è coinvolto** direttamente nella loro gestione.
- Si creano incomprensioni, errori, e si perde fiducia nella qualità dei dati.

Ed è proprio qui che entra in gioco il concetto di **Data Mesh**.

---

### Cos'è il Data Mesh?

Il **Data Mesh** è un **modello organizzativo e architetturale** per la gestione dei dati su larga scala, proposto da **Zhamak Dehghani**. Invece di accentrarli, promuove un’idea semplice ma potente:

> “I dati devono essere trattati come un prodotto e gestiti decentralmente da chi li conosce meglio: i team di dominio.”
> 

---

### I principi chiave del Data Mesh

1. **Domini decentralizzati**
    
    Ogni team che produce dati (es. il team vendite o HR) è responsabile **dell'intero ciclo di vita** di quei dati. Sa cosa significano, sa come cambiarli, e può metterli a disposizione di altri in modo chiaro e aggiornato.
    
2. **Dati come prodotto**
    
    I dati non sono più solo un "output" tecnico, ma diventano **prodotti veri e propri**, curati, documentati, accessibili, affidabili — con qualcuno responsabile della loro qualità, proprio come un product owner.
    
3. **Piattaforma self-service**
    
    Per supportare i team, serve una **piattaforma dati comune**, che metta a disposizione strumenti facili per fare ingestion, trasformazioni, accesso, governance, sicurezza… ma senza costringere tutti a passare da un unico team tecnico centrale.
    
4. **Governance federata**
    
    La governance dei dati non sparisce, ma diventa **collaborativa**. I principi fondamentali (privacy, qualità, sicurezza) vengono condivisi tra i team e applicati in modo coerente grazie a strumenti comuni e automazione.
    

---

### Ma quindi… è una questione tecnica o organizzativa?

Entrambe, ma **soprattutto organizzativa**.

Il Data Mesh non è una tecnologia specifica. Non si compra come un software. È un **cambiamento culturale**, che richiede:

- Dare autonomia e responsabilità ai team.
- Cambiare il modo in cui si lavora coi dati.
- Costruire una piattaforma di supporto davvero efficace.

In pratica, non stai solo cambiando l’architettura dei dati, ma **ripensando il modo in cui l’azienda collabora intorno ai dati**.

---

### Perché adottarlo?

Il Data Mesh diventa interessante per aziende che:

- Hanno **molti team e tanti dati eterogenei**.
- Si scontrano con i limiti di un **data lake centralizzato**.
- Vogliono **scalare** l’uso dei dati in modo agile, senza ingolfare un singolo team.