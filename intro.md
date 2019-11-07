# Intro
Le definizioni di rete sono molteplici, ma una di queste è `Viene chiamata rete tutto ciò al cui interno si può identificare un grafo`.

Questa definizione permette in ampia definizione della parola rete, ciò implica che la teoria successivamente studiata potrà essere applicata in un numero indefinito di casi, es. teorie sviluppate per le reti computazionali possono tornare utili anche per le reti stradali e viceversa.

Le reti di informazioni possono essere di diverse forme: client-server, peer-to-peer, reti di server dislocati, ecc...
Tali tipologie di rete di reti assumono utilità differenti in casistiche differenti, un modo per categorizzale è in base alla distanza tra i vari componenti di tale rete:

- PAN(Personal Area Network) 1m;
- LAN(Local Area Network) 10m-1km;
- PAN(Metropolitan Area Network) 10km;
- WAN(Wide Area Network) 100km-100km;

Esistono ovviamente reti molto più piccole e molto più grandi di quelle citate qui sopra, es. internet che attraversa tutto il pianeta, ma sono anche quelle a cui si riconducono la maggiorparte delle reti esistenti.

Le prime reti furono costruite focalizzandosi sull'hardware e poi successivamente sul software, ma questo approccio non funziona più. Le reti Software ora sono strutturate a livelli, con un livello di base dedicato all'hardware. Lo scopo di ciascun livello è di offrire certi servizi al livello superiore, schermandolo dai dettagli di come sia implementato tale sefvizio. Tra ogni coppia di livelli è definita un interfaccia che definisce quale primitive il servizio inferiore eroga a quello superiore.

Ad ogni livello vi sono dei protocolli, questo insieme si chiama pila di protocolli. Un protocollo è un accordo tra le parti che comunicano sul modo in cui deve procedere la comunicazione.

Le entità che formano i livelli di pari grado sui diversi computer sono chiamati peer; questi ultimi utilizzano i protocolli.

L'insieme di livelli e protocolli si chiama architettura di rete.

Sono presenti diverse architetture di rete, un esempio su tutti è il modello OSI(Open Sistem Interconnection) Sviluppato dall'iso che ha il vantaggio di avere un'implementazione generale e valida.

## OSI
Il modello OSI ha  livelli:
1. **Physical**: si occupa di trasmettere e ricevere i bit attraverso un canale di comunicazione
2. **Data-Link**: Incapsula le unita di uinformazione ricevute/trasmesse ed identifica eventuali errori di trasmissione
3. **Network**: contolla le operazioni della sottorete, dicendo quali percorsi utilizzare per la trasmissione dei dati (routing), controllando eventuali congestioni
4. **Trasnport**: fornisce il traferimento dati trai processi, assicurandosi che le comunicazioni tra i layer più alti avvengano correttamente
5. **Session**: fornisce e mantiene le sessioni di comunicazione tra diverse macchine
6. **Presentation**: si assicura che i dati siano rappresentati nel formato opportuno
7. **Application**: contiene una varietà di protocolli generalmente utilizzati dall'utente

Un modello contrapposto all'OSI è il TCP/IP che ha un'applicazione più ristretta, ma che paradossalmente è utilizzato molto più dell'OSI.

Il modello TCP/IP non presenta i livelli 5-6 e unisce i livelli 1-2 nel livello host-to-network che non definisce un vero standard dall'implementazione tra tale livello di collegamento tra hardware e software, e la sua implementazione varia da host a host, e da newtork a network. Un compromesso di seguito usato è il modello ibrido (_hybrid layer_) che consiste in cinque layer:
1. Physical
2. Data-Link
3. Network
4. Transport
5. Application
