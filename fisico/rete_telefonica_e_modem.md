## Rete Telefonica
Il sistema telefonico fu la seconda grande rete mai creata, inizialmente sviluppata come overlay della grande rete telegrafica.
All'inizio del 1876 una linea telefonica (point-to-point) era composta da una coppia di telefoni, direttamente collegati tra loro. Risultò subito chiaro che non era conveniente avere un grafo super connesso tra tutti i telefoni presenti in una rete (relazione quadratica tra telefoni e connessioni necessarie). Nel 1878 ci fu il passaggio agli switching center (centralini telefonici) che avevano il compito di creare la linea tra due telefoni connettendo fisicamente il cavo del chiamante con quello del ricevente.
Col diffondersi dei telefoni i centralini iniziarono però ad avere troppe connessioni da gestire, si decise dunque di creare dei centralini di secondo livello che avevano il compito di connettere tra loro quelli di primo livello.
Questo innalzamento di livello provoca però un maggiore tempo di attesa per un utente prima che venga collegato all'altra linea. Tale situazione scalò fino ad arrivare a cinque livelli, creando la così detta PSTN (Public Switching Telephone Network).
Il "local loop" (in italiano detto l' "ultimo miglio") è la rete UTP3 (cavi poco performanti) che connette la rete centrale con i singoli telefoni degli utenti.
Tra centrali di commutazione si fa largo uso di cavi coassiali, microonde e, soprattutto, fibre ottiche.

Nel 1984 gli Stati Uniti liberalizzarono il mercante delle telecomunicazioni permettendo ai nuovi competitor il diritto di inserimento nell'infrastruttura comunicatuva.
Nel 1995 il termine telecomunicazioni fu ulteriormente esteso includendo anche connessioni quali la TV via cavo.
L'anno successivo fu anche sancito il diritto di portabilità del numero telefonico.

Generalmente una conversazione telefonica è convertita in digitale (binario) tranne che per il local loop.
Per convertire il segnale è utilizzato un modulatore ed un demodulatore. Viene utilizzata una corrente alternata per trasmettere il segnale.
Esistono tre modi per modulare il segnale:
- ampiezza: variando l'ampiezza per determinare i bit trasmessi
- frequenza: utilizzando frequenze diverse, anche detta "frequency shift keying"
- fase: detta anche "phase shift keying", si basa sullo spostamento della fase dell'onda, anche mantenendo frequenza e ampiezza invariate; quando la fase cambia allora si identifica un cambio di bit, oppure si utilizzano delle forme d'onda per determinare ogni simbolo utilizzato

Quando si utilizzano 4 sfasamenti diversi allora la modulazione viene chiamata QPSK (Quadrature Phase Shift Keying). Aumentando gli sfasamenti considerati è possibile aumentare anche il bitrate a parità di bandrate (es. con quattro simboli, ognuno dei quali rappresenta due bit, il bitrate è doppio del bandrate), in questo modo però gli sfasamenti risultano sempre più indistinguibili l'uno dall'altro, andando quindi incontro a possibili errori di modulazione.<br>
Per migliorare il datarate è anche possibile combinare due delle tre tipologie di modulazione, mantenendone una fissa di riferimento. Con il Qam-16 si è deciso di mantenere fissa la frequenza (che aiuta a mantenere invariato il ciclo di clock), mentre si utilizza fase e ampiezza per modulare il segnale.<br>
Con una costellation diagram è possibile rappresentare graficamente le forme d'onda utilizzate dalle varie tipologie di modulazione.<br>
Maggiori sono gli angoli utilizzati per le fasi d'onda e maggiore sarà il rapporto tra bitrate e bandrate:<br>
- QPSK: 4 fasi, bitrate doppio del bandrate
- QAM-16: 16 fasi, bitrate quadruplo del bandrate
- QAM-64: 64 fasi, bitrate sestuplo del bandrate

Esistono però modi migliori di disporre i segnali nel diagramma, per prevenire ulteriormente l'interferenza tra le singole fasi e permettendo così un maggiore margine di incertezza dovuto alla dispersione e ai rumori esterni. Un esempio sono le modulazioni circolari QAM (es immagine QAM-8).
In generale si tende però a preferire l'ultilizzo di angoli più facili da generare e (de)codificare.

## Modem
Modem significa _modulator demodulator_. Si colloca tra il computer (digitale) e il sistema telefonico (analogico).<br>
Principali standard utilizzati dai modem:
- V.21 (1964): modulazione a frequenza, 300 bps
- V.22 (1980): modulazione di fase, 1.2 kbps
- V.22bis (1984): QAM-16, 2.4 kbps (retrocompatibile con V.22)
- V.32 (1990): QAM-32 con error correction, diventato necessario per l'elevato numero di simboli utilizzati (32), 9600 bps
- V.32bis (1991): modulazione multipla molto complessa con 128 simboli, 14.4 kbps
- V.34 (1994): anch'esso complicato, 12 bit per simbolo, 28.8 kbps
- V.34bis (1996): complesso con 14 bit per simbolo, 33.6 kbps

Se si calcola il limite fisico di Shannon della linea telefonica tra due utenti che utilizzano una connessione modem, si ottiene che il limite è di 35 kbps.
Con il protocollo V. 34bis si sarebbe quindi raggiunto il limite fisico della connessione modem.
La situazione non viene migliorata dal fatto che la banda telefonica sia filtrata nel local loop a circa 4 kHz, per evitare interferenze dannose per l'utente finale e garantire quindi un suono più pulito.
Il limite di 35 kbps può però essere portato a 70 kbps nel caso in cui la connessione sia tra un utente e il provider e non tra due utenti finali, infatti dal lato provider non è presente un gap prestazionale dovuto al local loop del lato utente.
Con una modulazione ottimale si potrebbe quindi arrivare a 64 kbps utilizzando 8 bit per i dati, però per vari motivi negli USA è stato scelto uno standard che utilizzi solo 7 bit, diminuendo la connessione massima a 56 kbps. Ogni connessione al mondo effettuata attraverso modem risulta quindi essere il 15% meno performante della capacità fisica effettiva.
Gli standard più veloci a questo punto risultarono essere quelli asimmetrici, dato che un utente medio scarica più dati di quelli che invia:
- V. 90 (1998): 56 kbps in downstream e 33.6 kbps in upstream
- V. 92 (1999): 56 kbps in downstream e 48 kbps in upstream

Contemporaneamente a questo periodo nascevano i primi standard per i fax. I primi fax nascono nel XIX secolo come overlay del sistema telefonico, ma diventati popolari solo nel secolo successivo per la necessità delle comunicazioni asiatiche di trasmettere ideogrammi come immagini. Successivamente il fax si è evoluto come overlay della linea telefonica. In un fax moderno è possibile selezionare la risoluzione delle immagini da inviare (da un minimo di 100*100 dpi fino ad un massimo di 400*400 dpi per: fax di gruppo 3).
Standard modulazione fax:
- V. 27 (1988): 4.8 kbps, PSK
- V. 29 (1988): 9.6 kbps, QAM
- V. 17 (1991): 14.4 kbps, TCM
- V. 34 (1994): 28.4 kbps, QAM
- V. 34bis (1996): 34.6 kbps, che risulta essere un limite fisico in quanto la connessione avviene inevitabilmente tra due utenti collegati al local loop e non tra utente e provider.