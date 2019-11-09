# Framing
L'approccio classico è quello di prendere dai pacchetti dati dal livello superiore (network) e inserirli in appositi frame.

Uno dei problemi che seguono è quindi identificare l'inizio e la fine di questi frame.
Uno dei metodi possibili è il _character count_, cioè utilizzare un header per specificare il numero di caratteri che costituisce il corpo dati (payload), il problema di questo approccio è però che basta un singolo errore nello strato fisico per sfasciare tutta la sequenza di header.

Per risolvere questo problema di header è possibile utilizzare un _flag byte_ all'inizio e alla fine di un frame per identificare i limiti. In questo caso è però necessario un metodo di escaping in caso si voglia trasmettere un carattere uguale a quello utilizzato per il flag all'interno del flusso dati. Questa tecnica di escaping si chiama _byte stuffing_ (o character stuffing).

Quando si è passati da ASCII a UNICODE l'unità di misura del byte non era una buona scelta, perciò si è passati al _bit stuffing_, ovvero la stessa cosa del byte stuffing ma a livello di bit. Ad esempio se la sequenza flag è 111111 (6 "1"), dopo 5 bit a 1 viene inserito uno 0, indipendentempente dal bit successivo, in modo che la sequenza flag non appaia mai all'interno del messaggio. Il ricevente sa per certp che dopo 5 bit a 1 c'è uno 0 extra, che andrà a rimuovere.

Un ultimo metodo consiste nell'usare una scorciatoia a livello fisico. Prende il nome di _coding violation_. Nel livello fisico vengono usati 5 bit per rappresentarne 4, ad esempio per non avere troppi zeri di fila e perdere la sincronizzazione. Questa tecnica lascia libere delle combinazioni di bit che vengono usate come flag per delimitare i limiti del frame.

Ethernet e 802.11 usano una combinazione di queste tecniche, ad esempio entrambi mandano un preambolo di 72 bit per avvisare il ricevente dell'imminente trasmissione, in modo che questo si prepari.