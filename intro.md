# Intro
Le definizioni di rete sono molteplici, 
Ma in questo corso si userà questa :”Si definisce rete tutto ciò che può essere visto sotto forma di grafo”.

Questa definizione permette un’ampia definizione della parola rete, quindi la teoria successivamente studiata potrà essere applicata anche in cose esterne a questo corso, es. le teorie sviluppate per reti computazionali possono tornare utili anche per reti stradali e viceversa.

Le reti di informazioni possono essere categorizzate in più modi
Per ruolo dei componenti:

- Client-server
- Peer-to-Peer
- Server dislocati

Oppure in base all’estensione geografica della rete:

- PAN(Personal Area Network) 1m
- LAN(Local Area Network) 10m-1km
- PAN(Metropolitan Area Network) 10km
- WAN(Wide Area Network) 100km-100km

Esistono reti molto più piccole e molto più grandi di quelle citate qui sopra, es. internet che attraversa tutto il pianeta, ma queste categorie rappresentano la maggior parte delle reti esistenti.

Le prime reti furono progettate focalizzandosi prima sull'hardware e poi successivamente sul software. Oggi c’è un approccio modulare a livelli, dove il livello base è dedicato all'hardware. Lo scopo di ciascun livello è di offrire certi servizi al livello superiore senza mostre la sua implementazione. Tra ogni coppia livello superiore-livello inferiore è definita un interfaccia che indica quale primitive(servizi) il livello inferiore offre a quello superiore.

I livelli alla stessa altezza di componenti di rete diversi comunicano con i protocolli. Un protocollo è un accordo che definisce come avviene la comunicazione.

L'insieme di livelli e protocolli si chiama architettura di rete.

Sono presenti diverse architetture di rete, un esempio è il modello OSI(Open System Interconnection) Sviluppato dall'ISO che ha  un'implementazione generale, elegante e valida.

## OSI
I livelli del modello OSI:
1. **Physical**: si occupa di trasmettere e ricevere i bit attraverso un canale di comunicazione fisico.
2. **Data-Link**: Incapsula le unita di informazione ed identifica/corregge eventuali errori di trasmissione.
3. **Network**: controlla le operazioni della rete, dicendo quali percorsi utilizzare per la trasmissione dei dati (routing), tenendo conto di eventuali congestioni.
4. **Transport**: fornisce il trasferimento dati tra processi, assicurandosi che le comunicazioni tra i layer più alti avvengano correttamente.
5. **Session**: fornisce e mantiene le sessioni di comunicazione con una o più macchine.
6. **Presentation**: si assicura che i dati siano rappresentati nel formato opportuno.
7. **Application**: contiene una varietà di protocolli utilizzati dall'utente

Un’altro modello è il TCP/IP che ha implementazione ristretta rispetto all’OSI, ma che paradossalmente è utilizzato molto più.

Il modello TCP/IP non presenta i livelli 5-6 e unisce i livelli 1-2 in un unico livello host-to-network. Questo non definisce un vero standard d’implementazione  e mescola hardware e software.

Nasce quindi un modello ibrido, correntemente utilizzato che fonde L’OSI con il TCP/IP e consiste in cinque layer:
1. Physical
2. Data-Link
3. Network
4. Transport
5. Application
