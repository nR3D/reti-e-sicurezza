## xDSL
Il caso generale è quello delle DSL (Digital Subscriber Line) che nascono per superare il limite dei 56 Kbps.
Per andare oltre tale limite si sarebbe potuto pensare di utilizzare i cavi coassiali (10 Mbps) già presenti per la TV via cavo, oppure all'utilizzo di satelliti (50 Mbps); però entrambe queste possibilità avrebbero costretto i provider a sottoscrivere costose partership con i possessori di tali infrastrutture.
Si ipotizzò quindi di sostituire i cavi UTP3 del local loop, però un'uperazione del genere sarebbe risultata troppo costosa. A questo punto viene trovata la soluzione rimuoventi i filtri antirumore, alzando così la frequenza massima da $KHz a 1.1Mhz.
In questo modo però si rischierebbe di compromettere l'uso dei telefoni, dunque ogni utente necessita di installare nella propria linea uno splitter, che divide il segnale telefonico da 4KHz da quello internet a 1.1MHz.
Ogni splitter crea però delle interferenze nella rete a cui è collegato, risulta quindi auspicabile utilizzare il numero minimo possibile di splitter all'interno di un'abitazione, generalmente solo uno.
Una soluzione ancora migliore sarebbe l'utilizzo di telefono wirless con tecnologia DECT che filtra il segnale a livello wirless senza interferire con la rete wired.
Uno dei requisiti della rete digitale risulta quindi essere quello del multiplexing, cioè trasmettere più canali nella stessa rete. Una delle soluzioni migliori è quella di utilizzare un FDM (Frequency Division Multiplexing), cioè dividere i canali in base allle frequenze utilizzate.
La DSL più utilizzata risulta essere l'ADSL (Asymmetric DSL), assimmetrico perchè analogamente o gli standard modem V.90 e V.92 dà più spazio al download che all'upload. Nell'ADSL viene lasciato un range di frequenze tra 4KHz e 25KHz per prevenire interferenze tra linea telefonica e linea internet.
Però inquesto modo sarebbero presenti un gran numero di interferenze all'interno di range di frequenza. Si è quindi pensato di utilizzare 256 canali da 4312.5Hz ciascuno che spezino lo spettro utilizzato.<br>
E' stata presa come riferimento la stessa frequenza di una connessione telefonica (4312.5Hz) per poter utilizzare le tecnologie già esistenti e ben collaudate.
Standard ADSL:<br>
- ADSL Lite: 1.5 Mbps download, 0.5 Mbps upload<br>
- ADSL: 8 Mbps download, 1 Mbps upload<br>
- ADSL2: 12 Mbps download, 1 Mbps upload<br>
- ADSL2(annex J): 12 Mbps download, 3.5 Mbps upload<br>
- ADSL2+: 24 Mbps download, 1 Mbps upload<br>
- ADSL2+(annex M): 28 Mbps download, 3.5 Mbps upload<br>
Le ADSL2+ utilizzano una banda doppia di 2.2 MHz anzichè 1.1 MHz, che però necessita di una linea particolarmente buona. Le ADSL 2 e 2+ supportano anche varianti "all-digital" in cui si rinuncia alla parte voce per guadagnare 256 Kbps in upstream.
Il limite di 28 Mbps dell'ADSL risulta però ancora limitativo, sopratutto a seguito dell'aumento dello streaming video avvenuto negli ultimi decenni. E' nato perciò un nuovo standard basato sulla crescente diffusione della fibra, che permette l'utilizzo di frequenze sempre più alte.
Nasce quindi il VDSL (Very Hight Speed DSL, o informalmente detta anche Video DSL perchè spinta dalla necessità dello streaming video).<br>
Tipologie VDSL:<br>
- VDSL(2001): QAM, 55 Mbps download, 3 Mbps upload<br>
- VDSL2(2006): FDM, 200 Mbps download, 100 Mbps upload<br>
- VDSL2+(2011): FDM, 300 Mbps download, 100 Mbps upload<br>
Tali velocità però dipendono da quanto cavo UTP3 è presente tra l'utente ed il provider, per esempio dopo 1.0 Km di UTP3 la connessione VDSL2 degrada in un ADSL2. Per quanto riguarda la banda utilizzata non è stata fissata una configurazione tra upload e download come per l'ADSL, che risultò un approccio limitativo, ed è quindi stata lasciata libertà di scelta con i band plans.
Più si ramifica l'infrastruttura telecomunicativa e più risulta necessario gestire un gran numero di comunicazioni contemporaneamente. La soluzione risiede nell'utilizzo di un multiplexing FDM attraverso group/super group con i quali si passa da 600 comunicazioni per cavo fino a 230000.
Nel caso della fibra, però, non viene più utilizzato il termine frequenza, ma lunghezza d'onda, dunque il multiplexing FDM viene chiamato WDM (Wavelength Division Multipllexing). nel 1990 era possibile trasmettere 8 canali da 2.5Gbps ciascuno attraverso un singolo cavo di fibra, nel 2007 si è arrivati a 124 canali da 50 Gbps ciascuno, fino ad arrivare ai 32000 Gbps trasmessi in singolo cavo in fibra nel 2014.
Non esiste però solo il multiplexing di frequenza (FDM), ma anche altri come il multiplexing temporale (TDM) in cui si divide il tempo di connessione per distribuire i canali utilizzati, ma maggiori saranno i canali e minore sarà la velocità di connessione (e.g. con 24 canali si hanno 1,5 Mbps).