# Framing
L'approccio classico del layer datalink è quello di prendere i pacchetti dati dal livello superiore (network) e inviarli inserendoli in appositi frame.

Per leggere i dati è quindi necessario identificare l'inizio e la fine di questi frame.
Un possibile metodo è il _character count_, cioè utilizzare un header per specificare il numero di caratteri che costituisce il corpo dati (payload), il problema di questo approccio è che basta un singolo errore nello strato fisico per sfasciare il contenuto dell'intestazione.

Un'altro metodo consiste nel posizionare un _flag byte_ all'inizio e alla fine di un frame per identificarne i limiti. Sarà necessario un metodo di escaping in caso si voglia trasmettere un carattere uguale a quello utilizzato per il flag all'interno del flusso dati. La tecnica di escaping utilizzata si chiama _byte stuffing_ (o character stuffing), e consiste nell'anticipare ogni carattere sensibile con uno di escape.

Da quando si è passati dall'ASCII a UNICODE prendere come unità di misura il non è una buona scelta, perciò si è passati al _bit stuffing_. Ad esempio se la sequenza flag è 111111 (6 "1"), dopo 5 bit a 1 viene inserito uno 0 , indipendentempente dal bit successivo, in modo che la sequenza flag non appaia mai all'interno del messaggio. Il ricevente sa per certo che dopo 5 bit a 1 c'è uno 0 extra, che andrà a rimuovere(estremamente rapido).

Un ultimo metodo consiste nell'usare una scorciatoia del livello fisico: il _coding violation_. Es. nel livello fisico vengono usati 5 bit per rappresentarne 4,grazie a questo bit si possono riservare delle combinazioni  per i flag. Inoltre permette di non avere troppi zeri di fila e perdere la sincronizzazione. 

Ethernet e 802.11 usano una combinazione di queste tecniche, ad esempio entrambi mandano un preambolo di 72 bit per avvisare il ricevente dell'imminente trasmissione, in modo che questo si prepari.
