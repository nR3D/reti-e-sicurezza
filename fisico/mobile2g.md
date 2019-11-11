## Mobile 2g
Risulta essere la prima generazione _digitale_. Il passaggio a digitale ha portato un notevole guadagno di capacità trasmissiva grazie alla compressione e digitalizzazione della voce. Ha inoltre introdotto gli SMS.<br>
Anche in questo caso non si è riusciti ad avere uno unico standard globale, ma sono presenti 4 standard in competizione tra loro (anche se 2 di questi sono molto simili, potenzialmente compatibili con un aggiornaento software).

### D-AMPS
È uno standard statunitense (il pdc è il corrispondente nipponico che risulta molto simile), risulta compatibile con AMPS(1G) dal quale eredita le frequenze fino a 850Mhz che vengono ampliate 1850-1990Mhz. un questa banda le onde sono corte (16 cm) e dunque bastano antenne più piccole per ricevere il segnale. D-AMPS rispetto a AMPS utilizza una tecnica di compressione del flusso voce chiamata Delta Modulation, grazie all'utilizzo della trasmissione in digitale. Con questa compressioni si riescono ad abbassare i 56 Kbps utilizzati a 8kbps (a volte anche 4K bps), riuscendo così a far comunicare su una stessa linea 6 volte gli utenti di AMPS. Un esempio di compressione, che è veloce e poco laboriosa, è la delta modulation, in cui si trasmette la variazione dell'onda rispetto al momento precedente. Il segnale viene poi digitalizzato con un 1 per le variazioni positive ed uno 0 per le variazioni negative. Questa comperessione peggiora la qualita delle chiamate (lossy) che risulterà degradata rispetto a quella dell'1G.
Con l'aumento dei dispositivi, L'handoff risulta essere un dovere troppo grande per la cella e dunque, a partire dal 2g l'handoff è a carico del cellulare, questo monitora continuamente il segnale ricevuto dalla cella e nel caso di segnale troppo basso può decidere di disconnettersi e a una nuova cella più vicina. Questa tecnica si chiama MAHO (Mobile Assisted HandOff). Nella comunicazione telefonica viene utilzzato il multiplexing temporale (TDM).
### GSM
Standard diffusissiomo in europa, come nel D-AMPS viene usato un FDM con divisione TDM dentro ogni canale del FDM. Una differenza con l'AMPS è che sono presenti canali più ampi (200Khz contro i 30Khz dell'AMPS) e quindi un datarate più alto, a discapito di un numero di canali che risulta inferiore all'AMPS: 124 canali, ognuno con 8 slot temporali, circa 33kbps disponibili a ogni utente  (contro gli 8 a 12kbps dell'AMPS) tolti i bit di overhead si ottengono circa a 24.7 Kbps, e con l'utilizzo dell'error correction si arriva a 13 Kbps, contro gli 8 o 4 kbps del D-AMPS quindi in conclusione il GSM ha una qualita` migliore.<br>
Il GSM è strutturato in celle variabili: <br>
- Macro: le più estese con raggio massimo di 35km <br> 
- Micro: da piazzare sopra gli edifici urbani<br>
- Pico: utilizzavile in luoghi molto affollati, anche indoor <br>
- Umbrella: usate per coprire picchili buchi o quasti di rete<br>
Con il gsm viene introdotta per la prima volta la SIM (Simbolic Identity Module), con con taglie variabili tra 4Kb e 512Kb, ma il suo scopo principale non è quello di memorizzare ma l'importante è che contenga 2 codici identificativi:
IMSI (International Mobile Subscriber Identity che identifica univocamente la sim nel mondo)
Ki, la chiave di autenticazione per evitare il clonaggio dato che l'IMSI viene inviata in chiaro.
L'operatore invia un numero call'utente che viene firmato con la Ki e poi rispedito assieme all'IMSI.<br>
I cellulari sono connessi ad un BSC (base station controller) che gestisce le risorse radio delle celle e l'handoff dei dispositivi, a sua volta collegato ad un MSC che instrada le chiamate nella rete telefonica.<br>
Trasmissione e ricezione non avvengono nello stesso intervallo temporale perchè le radio GSM non sono in grado di trasmettere e ricevere nello stesso momento, passare da un'operazione all'altra richiede del tempo.<br>
Vengono usati i seguenti canali di controllo:
- canale di controllo broadcast: flusso continuo di dati trasmesso dalla stazione base che annuncia identità e stato della stazione.
- canale di controllo dedicato: usato per aggiornare la posizione, registrare il terminale nella rete e impostare la chiamata.
- canale di controllo comune: diviso in 3 sottocanali logici
  - canale di paging: annuncio chiamate in arrivo
  - canale ad accesso casuale: permette agli utenti di richiedere uno slot sul canale di controllo dedicato
  - canale di concessione dell'accesso: annuncio assegnazione slot dedicato dato dal precedente punto.

Per l'handoff viene usato MAHO (mobile assisted handoff), ovvero è il cellulare ad accorgersi che sta uscendo dal campo di copertura della cella controllando nei tempi di trasmissione non a lui assegnati dal TDM, inviando la richiesta ad una cella più vicina, stabilendo per un momento una doppia connessione in modo da non far mai cadere quest'ultima (soft handoff). Maggior carico di lavoro sul terminale.
### 2.5G
Chiamato GPRS(General Packet Radio Service) che è un overlay del 2G (GSM e D-AMPS) che permette di trasmettere anche dati internet. il problema risulta essere che il 2g è pensato per trasmissioni voce e dunque la connessione dati web tende ad occupare un intero canale voce anche quando il traffico è ridotto. Il GPRS è il primo standard ad introdurre il passaggio da message switching a packet switching, e dunque le tariffe non vengono più calcolate in base al tempo di connessione ma in base al numero di pacchetti invitati. Nel GPRS vengono allocati dinamicamente i canali internet e voce in base alla richiesta dando generalmente priorta` ai canali voce) 
Esistono differenti classi di GPRS:<br>
- Classe C: richiede un settaggio manuale del canale da utilizzare, se GSM o GPRS<br>
- Classe B: La connessione al canale richiesto avviene Automaticamente<br>
- Classe Pseudo A: le due di tipologie di connessioni sono aperte contemporaneamente in un singolo canale.<br>
- Classe A: C le due tipologie di connessioni sono entrambe aperte su canali distinti<br>
Edge: è un evolucione del GPRS che migliora la trasmissione dati. Anche questo Caso esistono diverse versioni che variano da 64Kbps a 236Kbps teorici in download.
