
# Principi SOLID (modifica con singole pagine)

I **principi SOLID** sono cinque linee guida fondamentali per scrivere codice orientato agli oggetti che sia **manutenibile, estendibile e scalabile**.

### **Single Responsibility Principle (SRP)**

**Ogni classe dovrebbe avere una sola responsabilità (o motivo per cambiare).**

**Cattiva pratica:** una classe che crea, gestisce e stampa il report da sola.

The concept of **responsibility** in this context may be pretty subjective. Having a single responsibility doesn’t necessarily mean having a single method. Responsibility isn’t directly tied to the number of methods but to the core task that your class is responsible for, depending on your idea of what the class represents in your code. However, that subjectivity shouldn’t stop you from striving to use the SRP.

### Open/Closed Principle (OCP)

**Il codice dovrebbe essere aperto all'estensione ma chiuso alla modifica.**
❌ **Cattiva pratica:** usare `if` o `switch` ogni volta che aggiungi un tipo di `Shape`.

### Liskov Substitution Principle (LSP)

**Le classi figlie devono poter essere usate al posto delle classi genitrici senza rompere il comportamento.**

Se crei una sottoclasse `Penguin(Bird)` che non può volare, stai violando il principio.

### Interface Segregation Principle (ISP)

**Non costringere le classi ad implementare interfacce che non usano.**

Cattiva pratica: un’unica interfaccia con `print()`, `scan()`, `fax()` usata anche da chi non ha bisogno di tutti i metodi.

### Dependency Inversion Principle (DIP)

**Le classi di alto livello non dovrebbero dipendere da classi di basso livello, ma da astrazioni.**