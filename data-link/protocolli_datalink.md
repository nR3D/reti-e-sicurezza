# Protocolli livello datalink  
## Protocollo stop-and-wait  
Come dal nome, il **sender** aspetta l'ack di conferma del pacchetto prima di mandarne un altro al receiver.  
Quindi basta un canale half duplex, in quanto in un dato momento solo il **sender** (con un pacchetto dati), o il **receiver** (con ack di conferma ) spediscono attraverso il canale.  
**Problemi**:  
1)Senza un controllo di flusso il **sender** potrebbe sommergere il **receiver** di pacchetti, provocando la perdita di quest'ultimi. **Soluzione** => dopo aver passato il pacchetto allo strato network il **receiver** spedisce un piccolo frame senza dati (dummy) (in questo caaso l'ack), che dal al **sender** il permesso di inviare il frame sucessivo. Il **sender** è obbligato dal protocollo ad aspettare fino all'arrivo dell'ack.  
2)Procedendo in questo modo se l' **ack** di un qualsiasi frame viene perso, il **receiver** rimarrebbe potenzialmente fermo per sempre. **Soluzione** => introduciamo un **Timeout** (concetto locale che risolve un concetto globale). Quindi, se entro un tot non si riceve un ack dal **receiver**, il **sender** rispedisce il pacchetto.  
3)Nel caso precedente senza un controllo della sequenzialità del pacchetto, il **receiver** non si accorgerebbe che ha tra le mani un pacchetto duplicato, **Soluzione** => dato che la possibile ambiguità sta tra il frame m e m+1, un solo bit sarà sufficiente.  
Esempi di questo tipo di protocolli sono il **PAR** e l' **ARQ**.  
## Funzionamento generale:  
Dopo la trasmissione del frame il **sender** avvia il timer, se il timer era già stto avviato viene resettato e fatto ripartire. L'intervallo di tempo deve essere scelto in modo che il **frame** abbia il tempo di arrivare al **sender**, essere elaborato, e infine il frame di **ack** deve avere il tempo di tornare indietro. Dopo aver spedito un frame la sorgente aspetta che accada qualcosa: possono avvenire tre cose:  
1. Arriva un frame di ack intatto => il **sender** prende un nuovo pacchetto dallo strato network e lo mette nel buffer.
1. Arriva un frame di ack con errori => nel buffer rimane il frame precendente, non viene cambiato il numero di sequenza e viene lancoato un duplicato  
1. Non arriva ack e scatta il **Timer** => nel buffer rimane il frame precendente, non viene cambiato il numero di sequenza e viene lancoato un duplicato  
### Problema generale dello stop and wait:  
se **bandwidth*round-trip-delay** è grande, significa che stiamo sottoutilizzando la banda; ed è proprio quello che avviene con questo protocollo.  
## Calcolo utilizzo linea  
**Capacità** c (bit/s)  
**Taglia frame** s (bits)  
**Round trip** r ( tempo impiegato da un pacchetto perarrivare a destinazione e ack arrivi al sender)  
**Utilizzo linea**= **s/(s+c*r)**  
In tutto questo possiamo notare un problema: ogni frame genera un altro frame, stiamo quindi dimezzando la banda.  
**Soluzione**  
## Piggybacking  
Il **receiver** quando riceve un frame dati, non invia immediatamente un frame di ack, ma aspetta che lo strato network gli passi un altro pacchetto, l'ack viene quindi aggiunto al frame dati in uscita, utilizzando un campo ack nell'header del frame. Questo campo ack non occuperà più di qualche bit, mentre costruire un intero frame separato richiederebbe un'intestazione, un ack e un checksum. E' ovvio che se un pacchetto dallo strato network arriva velocemente al **receiver**, questo potrà utilizzarlo per inviare anche l'ack, in caso contrario l'ack verrà spedito da solo. Il **Timer** dovrà tenere conto di questa "miglioria".  
## Protocolli sliding window  
In questi protocolli, il **sender** tiene traccia di un insieme di frame che è autorizzato ad inviare ( cioè che sono nella **finestra di invio** ), e il **receiver** mantiene una **finestra di ricezione**, che corrisponde all'insieme dei frame che può accettare. Ogni frame in uscita contiene un **numero di sequenza** da 0 ad una potenza di 2 (per motivi implementativi). I frame trasmessi dal **sender** sono mantenuti in un buffer nell'eventualit' alcuni andassero persi.  
### Protocollo GoBackN  
Con questo protocollo nel caso di errori durante la trasmissione, il **receiver** scarta tutti i frame sucessivi all'errore, ma continua a trasmettere ack (anche con piggybacking) dell'ultimo frame arrivato con successo. Questo comportamento corrisponde ad una finestra di ricezione pari a **1**. Puo' succedere che ad un certo punto la finestra del **sender** si saturi, quando ( e se ) la sorgente va in timeout, rispedira' tutti i frame a partire dal primo danneggiato o perso.  
### Ripetizione selettiva  

