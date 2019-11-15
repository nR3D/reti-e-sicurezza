## Mobile 2G
È  la prima generazione di trasmissione dati _digitale_.
Il passaggio portò un notevole guadagno di capacità trasmissiva grazie alla compressione e alla digitalizzazione della voce. Inoltre sono stati introdotti gli SMS.<br>
Anche in questo caso, non si è riusciti ad avere un unico standard globale: sono presenti 4 standard in competizione tra loro (anche se 2 di questi sono molto simili, potenzialmente compatibili con un aggiornaento software).

### D-AMPS

È lo standard Statunitense (il PDC è il corrispondente nipponico), risulta compatibile con AMPS (1G) dal quale eredita le frequenze fino a 850Mhz. In più la banda viene ampliata con le frequenze nella fascia 1850-1990Mhz.

L'utilizzo di queste frequenze permette di utilizzare antenne più piccole per ricevere il segnale. D-AMPS rispetto ad AMPS utilizza una tecnica di compressione del flusso voce chiamata Delta Modulation.
Con questa tecnica si riese a passare da 56 Kbps necessari a trasmettere il traffico voce a soli 8kbps, riuscendo così a far comunicare su una stessa linea 6 volte il numero di utenti di AMPS.

### Delta Modulation
È un esempio di compressione veloce e poco laboriosa, in cui si trasmette l'informazione relativa alla variazione dell'onda rispetto al momento precedente.
Il segnale viene poi digitalizzato con un 1 per le variazioni positive ed uno 0 per le variazioni negative.
Questa compressione peggiora la qualità delle chiamate (si dice che il tipo di compressione e' _lossy_).

### GSM

Standard Europeo, come in D-AMPS viene usato FDM con TDM dentro ogni canale del FDM.
Una differenza rispetto ad AMPS è che sono presenti canali con più banda (200Khz contro i 30Khz dell'AMPS), a vantaggio di un datarate più alto a discapito del ridotto numero di canali: 124 canali, ognuno con 8 slot temporali, circa 33kbps disponibili a ogni utente (contro gli 8 a 12kbps di AMPS) tolti i bit di overhead si ottengono circa 24.7 Kbps, e con l'utilizzo di'error correction si arriva a 13 Kbps, contro gli 8 o 4 kbps del D-AMPS. In conclusione GSM risulta migliore di D-AMPS.<br>


Il GSM utilizza diversi tipi di celle: <br>
- Macro: le più estese con raggio massimo di 35km <br>
- Micro: da piazzare sopra gli edifici urbani<br>
- Pico: utilizzabili per luoghi molto affollati, anche indoor <br>
- Umbrella: usate per coprire piccoli buchi o guasti temporanei<br>

Con GSM viene introdotta per la prima volta la SIM (Simbolic Identity Module), con con taglie variabili tra 4Kb e 512Kb, anche se il suo scopo principale non è quello di memorizzare ma contenere 2 codici identificativi:
- IMSI (International Mobile Subscriber Identity) : identifica univocamente la sim nel mondo.
- Ki: la chiave di autenticazione per evitare il clonaggio dato che l'IMSI viene inviata in chiaro.

L'operatore invia un numero all'utente che viene firmato con la chiave Ki e poi rispedito assieme all'IMSI.<br>

I cellulari sono connessi ad una BSC (base station controller) che gestisce le risorse radio delle celle e l'handoff dei dispositivi, a sua volta collegato ad un MSC che instrada le chiamate nella rete telefonica.<br>

La trasmissione e la ricezione non avvengono nello stesso intervallo temporale: le radio GSM non sono in grado di trasmettere e ricevere nello stesso momento, e passare da l'una all'altra richiede del tempo.<br>

Vengono usati i seguenti canali di controllo:
- canale di controllo broadcast: flusso continuo di dati trasmesso dalla stazione base che annuncia identità e stato della stazione.
- canale di controllo dedicato: usato per aggiornare la posizione, registrare il terminale nella rete e impostare la chiamata.
- canale di controllo comune: diviso in 3 sottocanali logici
  - canale di paging: annuncio chiamate in arrivo
  - canale ad accesso casuale: permette agli utenti di richiedere uno slot sul canale di controllo dedicato
  - canale di concessione dell'accesso: annuncio assegnazione slot dedicato dato dal precedente punto.

Per l'handoff viene usato MAHO (mobile assisted handoff), ovvero è il cellulare ad accorgersi che sta uscendo dal campo di copertura della cella controllando nei tempi di trasmissione non a lui assegnati dal TDM, inviando la richiesta ad una cella più vicina, stabilendo per un momento una doppia connessione in modo da non far mai cadere quest'ultima (soft handoff). Maggior carico di lavoro sul terminale.


### 2.5G
Chiamato GPRS(General Packet Radio Service), è un overlay del 2G (GSM e D-AMPS) che permette di trasmettere anche dati internet. Il problema è che 2G è pensato per le trasmissioni voce e la connessione dati web tende ad occupare un intero canale anche quando il traffico è ridotto.
GPRS è il primo standard ad introdurre il passaggio da message switching a packet switching. Le tariffe non vengono più calcolate in base al tempo di connessione ma in base al numero di pacchetti invitati. Nel GPRS vengono allocati dinamicamente i canali internet e voce in base alla richiesta dando generalmente priortà ai canali voce).

Esistono differenti classi di GPRS:<br>
- Classe C: richiede un settaggio manuale del canale da utilizzare, se GSM o GPRS<br>
- Classe B: La connessione al canale richiesto avviene automaticamente<br>
- Classe Pseudo A: le due di tipologie di connessioni sono aperte contemporaneamente in un singolo canale.<br>
- Classe A: le due tipologie di connessioni sono entrambe aperte su canali distinti<br>

Edge è una evoluzione del GPRS che migliora la trasmissione dati. Anche questo caso esistono diverse versioni che variano da 64Kbps a 236Kbps teorici in download.
