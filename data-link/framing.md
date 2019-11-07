# Framing
L'approccio classico e' quello di prendere dai pacchetti dati dal livello superiore (network) e inserirli in appositi frame.

Uno dei problemi che seguono e' quindi identificare l'inizio e la fine di questi frame.
Uno dei metodi possibili e' il character count, cioe' utilizzare un header per specificare il numero di caratteri che costituisce il corpo dati (payload), il problema di questo approccio e' pero' che basta un singolo errore nello strato fisico per sfasciare tutta la sequenza di header. Per risolvere questo problema di header e' possibile utilizzare un flag byte all'inizio e alla fine di un frame per identificare i limiti. In questo caso e' pero' necessario un metodo di escaping in caso si voglia trasmettere un carattere uguale a quello utilizzato per il flag all'interno del flusso dati. Questa tecnica di escaping si chiama byte stuffing (o character stuffing).
