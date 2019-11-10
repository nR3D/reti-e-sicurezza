## xDSL
Le DSL (Digital Subscriber Line) che nascono per superare il limite dei 56 Kbps.
Per scavalcarlo si sarebbero potuti usare i cavi coassiali (10 Mbps) già presenti per la TV via cavo, oppure ai satelliti (50 Mbps); però gli internet provider avrebbero dovuto sottoscrivere costose partership con i possessori di tali infrastrutture.
Si ipotizzò quindi di sostituire i cavi UTP3 dell'ultimo miglio, ma è un operzaione troppo costosa. La soluzione adottata consiste nel  rimuovere i filtri antirumore dalle cabine, alzando così la frequenza massima passante da 4KHz a 1.1Mhz.
In questo modo però si compromette l'uso dei telefoni, il problema è ovviato da uno splitter collegato alla presa del doppino di casa che divide il segnale telefonico da 4KHz da quello internet a 1.1MHz.
Gli splitter creano delle interferenze nella rete a cui sono collegati, si consiglia di usarne pochi per casa per evitare disturbi.
Un'altra soluzione è l'utilizzo del telefono con tecnologia DECT che permette di usare un canale wireless per le cornette di casa senza interferire con la rete wired.

Uno dei requisiti della rete digitale risulta è quello del multiplexing, cioè avere più canali di comunicazione in un unica rete. Una delle soluzioni migliori è quella di utilizzare l'FDM (Frequency Division Multiplexing), cioè dividere i canali su varie porzioni distinte della banda.
La DSL più utilizzata è l'ADSL (Asymmetric DSL), assimmetrica perchè si da più banda al download che all'upload. Nell'ADSL vi è un  range di frequenze tra 4KHz e 25KHz inutilizzato, per prevenire interferenze tra linea telefonica e linea internet. Upload e download Si sono ulteriormente divise in 256 canali da 4312.5Hz, limitando i disturbi su una certe frequenze solo ai canali che le contengono .<br>
E' stata presa come riferimento la stessa banda di una connessione telefonica (4312.5Hz) per poter utilizzare le tecnologie già esistenti e ben collaudate.
Standard ADSL:<br>
- ADSL Lite: 1.5 Mbps download, 0.5 Mbps upload<br>
- ADSL: 8 Mbps download, 1 Mbps upload<br>
- ADSL2: 12 Mbps download, 1 Mbps upload<br>
- ADSL2(annex J): 12 Mbps download, 3.5 Mbps upload<br>
- ADSL2+: 24 Mbps download, 1 Mbps upload<br>
- ADSL2+(annex M): 28 Mbps download, 3.5 Mbps upload<br>
Le ADSL2+ utilizzano una banda doppia di 2.2 MHz anzichè 1.1 MHz, che però necessita di una linea particolarmente buona. Le ADSL 2 e 2+ supportano anche varianti "all-digital" in cui si rinuncia alla parte voce per guadagnare 256 Kbps in upstream.
Il limite di 28 Mbps dell'ADSL risulta però ancora limitativo, sopratutto a seguito dell'aumento dello streaming video avvenuto negli ultimi decenni. E' nato perciò un nuovo standard basato sulla crescente diffusione della fibra, che permette l'utilizzo di frequenze sempre più alte: la VDSL (Very Hight Speed DSL, o informalmente detta anche Video DSL perchè spinta dalla necessità dello streaming video).<br>
Tipologie VDSL:<br>
- VDSL(2001): QAM, 55 Mbps download, 3 Mbps upload<br>
- VDSL2(2006): FDM, 200 Mbps download, 100 Mbps upload<br>
- VDSL2+(2011): FDM, 300 Mbps download, 100 Mbps upload<br>
Tali velocità però dipendono da quanto cavo UTP3 separa l'utente dal provider, per esempio dopo 1.0 Km di UTP3 la connessione VDSL2 degrada in ADSL2. Per quanto riguarda la banda utilizzata non esiste un unica divisione fissa tra upload e download come per l'ADSL, ma viene data della libertà di scelta con i band plans.
Più si ramifica l'infrastruttura telecomunicativa e più risulta necessario gestire un gran numero di comunicazioni contemporaneamente. La soluzione risiede nell'utilizzo di un multiplexing FDM attraverso group/super group con i quali si passa da 600 comunicazioni per cavo fino a 230000.
Nel caso della fibra, però, non viene più utilizzato il termine frequenza, ma lunghezza d'onda, dunque il multiplexing FDM viene chiamato WDM (Wavelength Division Multipllexing). Nel 1990 era possibile trasmettere 8 canali da 2.5Gbps ciascuno attraverso un singolo cavo di fibra, nel 2007 si è arrivati a 124 canali da 50 Gbps ciascuno, fino ad arrivare ai 32000 Gbps trasmessi in singolo cavo in fibra nel 2014.
Non esiste però solo il multiplexing di frequenza (FDM), ma anche altri come il multiplexing temporale (TDM) in cui si divide il tempo di connessione per distribuire i canali utilizzati temporalmente e non sulla banda, ma più sono i canali e minore sarà la velocità di connessione (e.g. con 24 canali si hanno 1,5 Mbps).
