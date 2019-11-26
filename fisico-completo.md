# Physical Layer

L'obiettivo del layer fisico è quello di trasportare un flusso di bit da una macchina all'altra. Diversi medium possono essere utilizzati per adempiere a tale compito, ma in generale si può distinguere tra trasmissioni _wired_ e _wirless_.

Il layer fisico definisce gli aspetti elettrici, di temporizzazione e altre modalità con cui i bit, sotto forma di segnali, vengono spediti sui canali di comunicazione.

## Wired

- **UTP o doppino (Unshielded Twisted Pair):**
Consiste in una coppia di cavi attorcigliati. Un cavo attraversato da corrente elettrica modifica il campo magnetico circostante, interferendo con l'altro (crosstalk). Attorcigliarli annulla il campo magnetico nei punti d'intreccio. Esistono diverse categorie di UTP, come UTP3 e UTP5, con la densità di punti d'intreccio proporzionale al numero della categoria.
Più i cavi sono intrecciati meno importante è il crosstalk. Dalla categoria 7 l'UTP diventa STP (shielded twisted pair), che possiede una schermatura per ogni filo del doppino, diminuendo ulteriormente l'interferenza.
Il bandwith vara tra le categorie di UTP, da 16 MHz e 100 MHz per UTP3 e 5 fino a 250 MHz e 600 MHz per le STP6 e 7.
- **Cavo coassiale:**
Il cavo coassiale è composto da un nucleo conduttore coperto da un rivestimento isolante, a sua volta circondato da un conduttore cilindrico fatto da una maglia di conduttori sottili. Tutto avvolto da una guaina protettiva di plastica.
Ha una schermatura migliore degli UTP, maggiore ampiezza di banda e un eccellente immunità al rumore, portando i segnali più distanre.
Generalmente utilizzato per la TV via cavo e le reti MAN, con una bandwith di 1 GHz.
- **Fibra ottica:**
Micro tubo in vetro in cui passano fasci di luce, con eventuali rimbalzi al suo interno. Di solito un impulso di luce indica 1, mentre l'assenza di luce indica 0.
La trasmissione, per ogni micro tubo, è unidirezionale. Spesso infatti un singolo cavo ha pù micro tubi al suo interno .
Tipi di connessioni tra fibre:
a) _connettori_: si perde circa un 10-20% di luce;<br>
b) _allineatori_ meccanici di precisione: si perde un 10% di luce;<br>
c) _fusione dei due microtubi_: rende impossibile una futura modifica dell'infrastruttura, ma riduce la perdita di luce all'1%.<br>
La trasmissione non dipende solo dal micro tubo ma anche dal tipo di luce utilizzata: Laser o LED. Un laser permette di trasferire più dati per una distanza maggiore, mentre il LED è più economico e meno soggetto agli sbalzi di temperatura.<br>
La fibra ottica ha delgi _svantaggi_ rispetto alle connessioni in rame: costo elevato, poca flessibilità fisica del vetro, difficoltà di connessione tra fibre ottiche ed la tendenza della luce ad affievolirsi nel tempo (diventa necessario avere una componente elettrica che la ravvivi). _Vantaggi_ rispetto al rame:  bandwidth maggiore, più sicura (per intercettare un segnale devo spezzare un micro tubo interrompendo la trasmissione), per dividere o unire il segnale nelle sue frequenze basta un prisma di vetro (no componenti elettriche).

## Wireless
In alternativa all'uso delle trasmissioni cablate si può usare lo spettro elettromagnetico per inviare segnali attraverso lo spazio (anche nel vuoto), dividendo segnali diversi in diverse zone dello spettro.

Le bande di frequenze sono propietarie (assegnate in base a un'asta o al beneficio che può trarne una tecnologia), Tranne per la banda ISM (Industrial Scientific Medical), cioè una banda libera e utilizzabile da chiunque ne necessiti. Questa è distribuita a pezzi per tutto lo spettro, così da coprire le necessità di uso si frequenze specifiche.

Il numero delle oscillazioni di un'onda è chiamato frequenza, e si misura in Hz (Hertz). La distanza tra due massimi o minimi consecutivi è la lunghezza d'onda e si indica con lambda (λ).

La maggior parte delle trasmissioni usa un'unica banda di frequenze ristretta per ottenere una migliore ricezione, ma in certi casi si usa la banda larga in tre modi:
1. spettro distribuito a frequenza variabile, in cui il trasmettitore passa da una frequenza all'altra centinaia di volte al secondo (comunicazioni militari);
2. spettro distribuito a sequenza diretta: fa uso di una codifica per dividere la banda, ad esempio il CDMA.
3. UWB (ultra wideband): trasmette i dati tramite segnali brevi in una banda estremamente ampia (usato nelle PAN - personal area network).

### Onde radio
Sono omnidirezionali, quindi non necessitano di particolari allineamenti tra trasmettitore e ricevente. La radio AM è a basse frequenze: le onde di attraversano bene gli ostacoli ma si disperdono più facilmente. Le onde FM sono ad una frequenza maggiore di quelle AM, dunque hanno bisogno di antenne direzionali e sono più facili da bloccare; in compenso hanno una minore dispersione nello spazio.

### Microonde
Frequenze maggiori di 100 Mhz. Perdono l'omnidirezionalità e viaggiano approssimativamente in linea retta; è dunque più semplice focalizzare il segnale su un unico ricevente e inviarlo per distanze maggiori.
Di contro necessitano di ripetitori, a causa della curvatura terrestre, non attraversano bene gli edifici e gli ostacoli in generale, comprese condizioni meteorologiche sfavorevoli.

### Infrarosso
Dette anche onde millimetriche, per via della lunghezza d'onda, vengono utilizzate in dispositivi quali i telecomandi per la TV. Sono ancora più direzionali delle microonde e bloccabili con maggiore facilità. Uno dei maggiori vantaggi di queste onde è che sono molto economiche da generare, e contemporaneamente anche un mezzo di trasmissione molto sicuro, essendo difficili da intercettare data la loro natura direzionale.

### Lightwave
L'utilizzo delle onde luminose come mezzo di comunicazione è stato usato molto frequente nel corso della storia. Al giorno d'oggi la frequenza della luce visibile è utilizzata per dispositivi quali i laser, che permettono di focalizzare il segnale su un unico ricevente anche molto distante, il grande problema di questa frequenza è che è facilmente bloccabile: basta una semplice foschia presente nell'atmosfera.

## Comunicazioni satellitari
Un aspetto di fondamentale importanza nelle comunicazionei satellitari è l'altezza di orbita del satellite.
Se vogliamo coprire interamente la superficie terreste usando un'orbita bassa sarà necessario usare molti satelliti.
Se vogliamo usare meno satelliti siamo costretti ad utilizzare orbite alte, sacrificando la possibilità di avere un segnale a bassa latenza.
Inoltre, bisogna considerare che c'e' una proporzionalità quatratica tra potenza necessaria alla trasmissione e l'altitudine del satellite. Questo significa che trasmettere lo stesso segnale da altezze maggiori richiede una quantità di energia non indifferente.
Un'altro problema che sorge con le trasmissioni inviate dai satelliti più alti è che queste devono fare i conti con la presenza di due fasce di particelle ioniche intrappolate nel campo magnetico terrestre: queste fasce, dette di Van Allen, non solo rendono difficile trasmettere, ma complicano anche la messa in orbita dei satelliti.
Sono presenti tre orbite in cui i satelliti vengono posizionati, diversificate per la loro altitudine: GEO, MEO E LEO.
Comprendere i vantaggi e gli svantaggi di ogni orbita permette di capire le potenzialità dei vari servizi.

### GEO
Questi sono i satelliti geostazionari posizionati al di sopra delle fasce di Van Allen.
L'unica orbita geostazionaria che non richiede correzioni di rotta per non perdersi nello spazio è quella equatoriale. Vista la convenienza dell'orbita, questa si è presto sovraffolata, causando problemi di interferenza e difficoltà nell'inserire un nuovo satellite senza farlo collidere con quelli già presenti.
È stato fissato un limite di 180 satelliti per quest'orbita.
In orbita GEO ci sono i satelliti spia, i satilliti metereologici e i satelliti per le trasmissioni televisive Direct Signal Broadcast.

### MEO
Sono i satelliti ad orbita media: si trovano tra le due fasce di Van Allen.
Un esempio di tecnologia che utizza i stelliti in orbita media è il GPS: composto da circa 30 satelliti della difesa statunitense, questa tecnologia venne ufficialmente resa pubblica nel 1983 a seguito di un incidente aereo in territorio Russo. In un primo momento fu resa pubblica con una precisione di 100 metri, ma viste le potenzialità nel 2000 la precisione venne aumentata a 20 metri.
Il GPS ha un tempo fisso di "fix" in cui il chip identifica i satelliti più vicini che permettono di triangolare il segnale; esiste l'Assisted-GPS che utilizza le celle telefoniche (fisse sul territorio e la cui posizione è nota) per velocizzare il processo di identificazione dei satelliti vicini, oppure tramite l'uso di un barometro per capire la propria altitudine.
Oltre al GPS, un altro sistema di localizzazione è l'alternativa russa GLONASS. GLONASS usa 28 satelliti e può essere utile per un controllo incrociato con il GPS.
Prima di queste tecnologie, per la localizzaione si utlilizzava TRANSIT, che consisteva in piccoli satelliti con radio trasmettitori, che transitando veloci sopra la superficie terrestre ed emettendo brevi segnali radio, rendevano possibile approssimare la propria posizione usando l'effetto Doppler.


### LEO
Sono i satelliti ad orbita bassa, posizionati al di sotto delle due fasce di Van Allen
Il loro basso tempo di latenza li rende ottimi per l'impiego in applicazioni di telecomunicazione satellitari, anche se data la bassa altitudine saranno necessari più satelliti per una copertura ottimale della superfiie terrestre.
Iridium con 77 satelliti (poi diminuiti a 66) è stato il primo sistema di telecomunicazione globale in grado di coprire anche luoghi non precedentemente raggiungibili. Ogni satellite iridium ha 48 celle telefoniche. Il segnale una volta inviato al satellite viene inoltrato attraverso la rete di satelliti (quindi senza le interferenze presenti nell'atmosfera terrestre). Il maggior problema del sistema Iridium, oltre ai costi di gestione, è che l'utente necessita di un cellulare con un'antenna adeguata ad una comunicazione satellitare, che rende scomodo l'utilizzo ed il trasporto del dispositivo.
Un altro esempio di telecomunicazione satellitare è il sistema Globestar, che tenta di abbassare la gestione dell'infrastruttura satellitare attraverso una riduzione dell'utilizzo dei satelliti; I satelliti Globestar vengono infatti usati solamente per ricevere il segnale dell'utente e consegnarlo al ricevente, mentre la trasmissione del segnale tra questi due satelliti avviene via terra attraverso dei ripetitori. Il punto debole di questo servizio è stato l'eccessivo risparmio sulle tecnologie satellitari, infatti un satellite Globestar ha una vita media di 7,5 anni rispetto ai 23 di un satellite Iridium.

Il problema più rilevante dei satelliti è che hanno una durata ben definita: alla fine della loro vita i satelliti non più utilizzati restano in orbita, accumulandosi, e contribuendo al problema dei detriti spaziali. La soluzione adottata al giorno d'oggi è quella di spedire i satelliti non più usati in un'orbita riservata.
I detriti spaziali di dimensione superiore ai 10 cm sono tracciati dalla Inter-Agency Space Debris Coordination Commitee, che si occupa di informare i proprietari dei satelliti sulla probabilità di collisione tra satellite e rottame. Di media si ricevono 10 segnalazioni a settimana.

## SATELLITI VS FIBRA
Fino a 40 anni fa si sarebbe potuto pensare che il futuro delle comunicazioni sarebbero state le comunicazioni satellitari;
infatti il sistema telefonico non era cambiato significativamente da 100 anni e non c'erano segni di cambiamento.
Ci fu però un cambiamento radicale quando gli USA approvarono il revised telecommunication act, successivamente approvato anche in Europa:
questo prevedeva la liberalizzazione della rete telefonica, ovvero qualsiasi gestore aveva il diritto di utilizzare parte della banda della rete di una grande azienda (come AT&T), previo pagamento. Inoltre spezzò AT&T in tante piccole aziende, distruggendo completamente il monopolio che aveva tenuto fermo lo sviluppo della telefonia per parecchio tempo, con un successivo abbassamento delle tariffe per la fruizione di tali tecnologie per gli utenti finali e uno sviluppo notevole della rete, ad esempio sostituendo molti collegamenti in rame con la fibra. Le comunicazioni satellitari si sono ridotte quindi ad un utilizzo di nicchia, dove le tecnologie terrestri non potevano arrivare:<br>
- una singola fibra ottica ha, in teoria, una maggiore banda di qualsiasi satellite mai lanciato, però tale banda viene limitata dai provider per permettere a più utenti di connettersi contemporaneamente, una limitazione che può essere bypassata nelle comunicazioni satellitari attraverso l'uso di antenne;<br>
- le comunicazioni in broadcast sono molto più efficienti attraverso i satelliti;<br>
- una comunicazione satellitare non necessita di una infrastruttura nel luogo di utilizzo, dunque può essere fruita anche in zone di guerra o sottosviluppate.<br>
Un ulteriore vantaggio dei satelliti sulla fibra era quello delle trasmissioni mobili non cablate, vantaggio poi svanito con l'introduzione delle reti wireless.

### Efficienza di banda
L'ampiezza di banda (bandwidth) è una misura fisica che indica l'insieme di frequenze trasmissibili su un canale, ed è generalmente misurata in Hz.<br>
Il data-rate misura quante informazioni possono essere trasmesse, e può essere ricondotta a due diverse misure:<br>
- bit-rate: quanti bit vengono trasmessi al secondo.<br>
- baud-rate (symbol rate): quanti simboli al secondo vengono trasmessi al secondo, utile in caso se si associa un differente simbolo ad ogni forma d'onda.
In generale, `bitrate = baudrate x log(2)V`, dove V è il numero di simboli trasmessi.
Il bitrate sarà sempre maggiore del baudrate quando si trasmettono più di due simboli.<br>
Il bitrate non è altro che il baudrate nel caso specifico in cui vengano trasmessi solo due simboli, 1 e 0.<br>
Naturalmente, maggiore è la frequenza di trasmissione, più alto sarà il datarate. In ogni caso, frequenze troppo alte sono difficilmente applicabili ai canali di comunicazione reali.<br>
È dunque fondamentale trovare un buon compromesso tra l'impiego delle alte frequenze e la capacità di trasmissione.
La potenza necessaria alla trasmissione è proporionale al quadrato della frequenza trasmessa, quindi il limite di banda sarà dettato anche dalla potenza impiegata.


### Teorema di Nyquist
Il teorema di Nyquist afferma che:
- Dato un mezzo di trasmissione con ampiezza di banda B
- Un segnale analogico approssimato con le sue prime L componenti della trasformata di Fourier
Il data-rate massimo[bps] = `2*B*log(2) L`
Nel caso del telegrafo L=2 (0, 1), il data-rate massimo è 2B.
Nella pratica però, dobbiamo considerare anche il rumore. Il teorema di Nyquist vale solo in condizioni ideali: per applicare concretamente il teorema bisogna considerare la potenza del rumore R.

### Teorema di Shannon
È una generalizzazione del teorema di Nyquist che tiene in considerazione rumore R.
il data-rate massimo[bps] = max\_data\_rate = `B*log(2) (1+S/N)`
dove S/N è il rapporto tra la potenza del segnale S e la potenza del rumore del canale R, che dipende dalla qualità del mezzo.
Il rapporto S/N si indica in decibel -> `10*log(10) S/N = SNR`.
Nel caso ottimo, con alto S/N, il massimo data rate è `(B/3)*SNR`.

### Trasmissione in banda base
È la forma più naturale di modulazione digitale, il segnale reppresentato con tensione positiva per 1, negativa per 0 chiamata anche NRZ (non-return-to-zero). Se il segnale viene attenuato o distorto, il ricevente assegna il valore più vicino al valore effettivo assunto dall'onda.

### Clock recovery
Tutte le strategie di codifica prevedono che il ricevente sia tenuto a conoscere quando un simbolo termina e il successivo inizia. Con _NRZ_ una sequenza lunga di 1 o di 0 manda fuori sincronia il ricevente. Un'altra codifica che ovvia al problema è la Manchester che consiste nel dividere il segnale del 1 in due parti la prima alta e la seconda bassa, cosa analoga succede per lo zero ma le parti sono invertire. A siccome i segnali inviati sono lunghi la meta è necessaria il doppio della banda di NRZ.<br>
Si è sviluppato _NRZI_ (NRZ inverted), che codifica l'1 come cambiamento di fase dell'onda ma lunghe sequenze di 0 rimangono un problema.<br>
Il codice 4B/5B risolve questo problema. Ogni gruppo di 4 bit è associato ad una sequenza di 5 bit secondo una tabella di conversione nota. Provoca un overhead del 25%.<br>
Un approccio alternativo è di inviare il risultato dello XOR tra i dati e delle sequenze pseudocasuali di bit (_scrambling_). Il ricevente applicherà lo XOR ai bit ricevuti con la stessa sequenza pseudo casuale. Non si aggiunge overhead di banda o di tempo. Segnali casuali tendono ad avere la loro energia distribuita su tutte le componenti di frequenza. Tuttavia non viene garantito che non ci siano lunghe sequenze di simboli uguali.

### Segnali bilanciati
I segnali che presentano una tensione tanto positiva quanto negativa, hanno tensione media 0. Questi, non hanno componenti in corrente continua, ed è vantaggioso poiché le linee elettriche attenuano fortemente le componenti continue. Uno dei metodi per collegare il ricevente al canale, chiamato _accoppiamento capacitivo_ lascia transitare solo corrente alternata.<br>
Il bilanciamento aiuta ad aggiungere transizioni per il clock recovery e sincronizza i riceventi: è possibile calcolare la media del segnale e usarla come soglia decisionale per la decodifica.<br>
Un esempio è assegnare +1V e -1V per rappresentare un 1 (usati in modo alterno, _codifica bipolare_), 0V per lo 0.

## Trasmissione in banda passante
Il valore assoluto della frequenza usata per la comunicazione non influenza la capacità di trasferimento dati, questa dipende dalla banda.<br>
Possiamo quindi prendere un segnale in banda base che va da 0 a B Hz e traslarlo in banda passante che va da S a B+S Hz. Il ricevente effetturà la trasposizione al contrario.<br>

Possiamo modulare l'ampiezza, la frequenza o la fase del segnale portante:<br>
- ASK (amplitude shift keying): due ampiezze diverse usate per rappresentare 0 e 1.
- FSK (frequency shift keying): si usano due o più frequenze per 1 e 0.
- PSK (phase shift keying): l'onda portante è traslata di 0 o 180 gradi all'inizio della trasmissione di ogni simbolo. In questo caso, essendoci 2 fasi, prende il nome di BPSK (binary PSK). Qui binario si riferisce ai due simboli 0 e 1.<br>
Uno schema migliore e più efficiente è QPSK (quadrature PSK, 2 bit di informazione per simbolo). Per trasmettere più bit per simbolo si possono combinare le tecniche e usare più livelli. Siccome la frequenza è il cambiamento di fase nel tempo non si potranno combinare FSK e PSK.

È possibile superare i 2 bit per simbolo. Ad esempio con _QAM-16_ (quadrature amplitude modulation) si arriva a 4 bit per simbolo. Con _QAM-64_ si arriva a 16. Queste ultime tecniche vengono usate nella modulazione digitale. Esistono QAM di dimensione superiore, ma aumenta il tasso d'errore.<br>
Per capirlo basta osservare il _costellation diagram_ di queste modulazioni, più sono vicini i punti che rappresentano i simboli, più è alto il tasso di errore. Un diagramma perfetto sarebbe circolare, che è difficile da realizzare. I punti vengono disposti a quadrato, limitando la potenza del QAM.<br>
Un perfezionamento di QAM è il _Gray code_, che associa a simboli adiacenti sequenze differenti di solo 1 bit, l'errore divent a facilmente corregibile ai livelli superiori.

## Trasformata di Fourier
Nel XIX secolo fu provato che qualsiasi funzione periodica sufficientemente regolare g(t) con periodo T, può essere costruita con la somma di un numero (anche infinito) di funzioni seno e coseno.<br>
Ciò risulta utile nelle comunicazioni di dati in quanto è possibile utilizzare un numero finito di onde per trasmettere un segnale non altrimenti riproducibile sotto forma di singole onde sinusoidali.

## Attenuazione
Ogni impulso elettromagnetico trasmesso in un mezzo che non sia il vuoto, subisce attenuazione di potenza[dB]. L'attenuazione può essere calcolata attraverso la formula:
Attenuazione = `-10 x log(10) x (Pout/Pin)`  dove Pout=potenza\_trasmessa e Pin=potenza\_ricevuta.
L'attenuazione dipende anche dalla frequenza: una forma d'onda, in generale, subisce diverse modifiche a seconda delle componenti della sua trasformata di Fourier.
La bandwidth è limitata e dipende dal mezzo di trasporto utilizzato. Di conseguenza, per ottimizzare la trasmissione a livello fisico, viene utilizzato il numero minimo di simboli che permettono di ricostruire il segnale meno soggetti ai fenomeni di distorsione legati al mezzo fisico.

## Dispersione
La dispersione risulta essere un problema più grave dell'attenuazione: in questo caso parte del segnale viene perso, rendendo più difficile ricostruire la forma d'onda originale.
Una possibile soluzione potrebbe essere quella di utilizzare un gran numero di ripetitori per ritrasmettere e correggere il segnale quando la dispersione è minima. Tale soluzione non risulta però conveniente. Una soluzione migliore consiste nell'utilizzo di onde solitoniche. I solitoni sono onde che hanno dispersione quasi nulla. L'incostro di due solitoni opposti sullo stesso canale. Di conseguenza un canale half-duplex può diventare automaticamente full-duplex.

## Rete telegrafica
Uno dei primi esempi di reti globali "wired" è il telegrafo (tele=lontano, graphein=scrivere).
Ancor prima dell'epoca elettrica erano presenti i primi esempi di comunicazione telegrafica attraverso i così detti telegrafi ottici che trasmettevano comunicazione attraverso l'uso di segnali luminosi.
Nel 1837 Morse ebbe l'idea di migliorare il telegrafo elettric (all'epoca già esistente) attraverso l'uso di ripetitori che furono la vera rivoluzione nel campo telecomunicativo, infatti precedentemente i telegrafi risultavano inutilizzabili nelle lunghe distanze.
Un successivo salto qualitativo avvenne nel 1850 con l'introduzione di cablaggi sottomarini al fine di connettere il territorio inglese con il continente europeo.
A partire dal 1855, ispirato dall'impresa inglese, l'americano Cyrius Field (occhio pazzo ragazzo cazzo) avviò la sua impresa di connettere l'America con l'Europa. Dopo una serie di fallimenti l'impresa fu portata a termine nel 1858.
La connessione transatlantica appena formatasi era composta da un cavo composto da 7 cavi interni in rame ricoperti da 3 strati di gomma isolante.
Il data-rate di questa prima connessione era di 0.1 parole al minuto, troppo basso per poter intraprendere una conversazione in tempi rapidi. Venne dunque tentato un aumento di voltaggio per poter trasmettere più velocemente, però il tentativo finì con l'irreversabile fusione della prima connessione transoceanica.
A seguito di un ulteriore tentativo fallito Cyrius Field (occhio pazzo ragazzo cazzo) riconnetè i due continenti nel 1866, questa volta utilizzando un cavo migliore che fu sviluppato in questi anni. Il data-rate di questa nuova connessione era 8 parole al minuto, sufficienti per iniziare le prime conversazioni translatlantiche. Dopo pochhe settimane fu anche aggiunto un secondo cavo parallelo alla precendente connessione, cavo recuperato da un precedente tentativo fallito. Solo nel 1956 fu aggiunto un nuovo cavo per portare la comunicazione a 120 parole al minuto, grazie anche all'inserimento dei primi ripetitori.
Al giorno d'oggi sono presenti molte altre grandi reti di comunicazione che interconnettono il mondo intero. Nel 1902 viene steso il primo cavo nel Pacifico permettendo una prima vera connessione globale. Nel 1988 venne installato il TAT8, cioè il primo cavo transatlantico in fibra ottima.

## Rete Telefonica
Il sistema telefonico fu la seconda più grande rete mai creata, inizialmente sviluppata come overlay della grande rete telegrafica.
All'inizio del 1876 una linea telefonica (point-to-point) era composta da una coppia di telefoni, direttamente collegati tra loro. Risultò subito chiaro che non era possibile avere una connessione fisica tra tutti i telefoni presenti (relazione quadratica tra telefoni e connessioni necessarie).
Nel 1878 ci fu il passaggio agli switching center (centralini telefonici) che avevano il compito di creare la linea tra due telefoni connettendo fisicamente il cavo del chiamante con quello del ricevente.
Col diffondersi dei telefoni, i centralini iniziarono però ad avere troppe connessioni da gestire, e si decise dunque di creare dei centralini di secondo livello che avevano il compito di connettere tra loro quelli di primo livello.
Questo innalzamento di livello provoca però un maggiore tempo di attesa per un utente prima di venire collegato all'altra linea. Tale situazione scalò fino ad arrivare a cinque livelli, creando la così detta PSTN (Public Switching Telephone Network).
Il "local loop" (in italiano detto l' "ultimo miglio") è la rete UTP3 (cavi poco performanti) che connette la rete centrale con i singoli telefoni degli utenti.
Tra le varie centrali di commutazione si fa largo uso di cavi coassiali, microonde, e soprattutto, fibre ottiche.

Nel 1984 gli Stati Uniti liberalizzarono il mercato delle telecomunicazioni, permettendo a nuovi competitor di inserirsi nell'infrastruttura di rete.
Nel 1995 il termine telecomunicazioni fu ulteriormente esteso includendo anche connessioni quali la TV via cavo.
L'anno successivo fu anche sancito il diritto di portabilità del numero telefonico.

Generalmente, una conversazione telefonica è convertita in digitale (binario) tranne che per il local loop.
Per convertire il segnale è utilizzato un modulatore ed un demodulatore. Viene utilizzata una corrente alternata per trasmettere il segnale.
Esistono tre modi per modulare il segnale:
- ampiezza: variando l'ampiezza per determinare il valore dei bit trasmessi
- frequenza: utilizzando frequenze diverse, anche detta "frequency shift keying"
- fase: detta anche "phase shift keying", si basa sullo spostamento della fase dell'onda, anche mantenendo frequenza e ampiezza invariate; quando la fase cambia allora si identifica un cambio di bit, oppure si utilizzano delle forme d'onda per determinare ogni simbolo utilizzato

Quando si utilizzano 4 sfasamenti diversi allora la modulazione viene chiamata QPSK (Quadrature Phase Shift Keying). Aumentando gli sfasamenti considerati è possibile aumentare anche il bitrate a parità di bandrate (es. con quattro simboli, ognuno dei quali rappresenta due bit, il bitrate è doppio del bandrate), in questo modo però gli sfasamenti risultano sempre più indistinguibili l'uno dall'altro, andando quindi incontro a possibili errori di modulazione.<br>
Per migliorare il datarate è anche possibile combinare due delle tre tipologie di modulazione, mantenendone una fissa di riferimento. Con il QAM-16 si è deciso di mantenere fissa la frequenza (che aiuta a mantenere invariato il ciclo di clock), mentre si utilizza fase e ampiezza per modulare il segnale.<br>
Con una costellation diagram è possibile rappresentare graficamente le forme d'onda utilizzate dalle varie tipologie di modulazione.<br>
Piu' fasi d'onda diverse si utilizzano e maggiore sarà il rapporto tra bitrate e bandrate:<br>
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
Il limite di 35 kbps può però essere portato a 70 kbps nel caso in cui la connessione sia tra un utente e il provider, e non tra due utenti finali. Infatti dal lato provider non è presente un gap prestazionale dovuto al local loop del lato utente.
Con una modulazione ottimale si potrebbe quindi arrivare a 64 kbps utilizzando 8 bit per i dati, però negli USA è stato scelto di adottare uno standard che utilizza solo 7 bit, di fatto, diminuendo la bandwidth a 56 kbps. Ogni connessione al mondo effettuata attraverso modem risulta quindi essere il 15% meno performante della capacità fisica effettiva.
Gli standard più veloci a questo punto risultarono essere quelli asimmetrici, dato che un utente medio scarica più dati di quelli che invia:
- V. 90 (1998): 56 kbps in downstream e 33.6 kbps in upstream
- V. 92 (1999): 56 kbps in downstream e 48 kbps in upstream

In questo stesso periodo, nascevano i primi standard per i fax. I primi fax nascono nel XIX secolo come overlay del sistema telefonico, ma sono diventati popolari solo nel secolo successivo per la necessità di trasmettere ideogrammi. In un fax moderno è possibile selezionare la risoluzione delle immagini da inviare (da un minimo di 100\*100 dpi fino ad un massimo di 400\*400 dpi per i fax di gruppo 3.
Standard modulazione fax:
- V. 27 (1988): 4.8 kbps, PSK
- V. 29 (1988): 9.6 kbps, QAM
- V. 17 (1991): 14.4 kbps, TCM
- V. 34 (1994): 28.4 kbps, QAM
- V. 34bis (1996): 34.6 kbps, che risulta essere un limite fisico in quanto la connessione avviene inevitabilmente tra due utenti collegati al local loop e non tra utente e provider.

## xDSL
Le DSL (Digital Subscriber Line) che nascono per superare il limite dei 56 Kbps.
Per scavalcarlo si sarebbero potuti usare i cavi coassiali (10 Mbps) già presenti per la TV via cavo, oppure ai satelliti (50 Mbps); però gli internet provider avrebbero dovuto sottoscrivere costose partership con i possessori di tali infrastrutture.
Si ipotizzò quindi di sostituire i cavi UTP3 dell'ultimo miglio, ma è un operzaione troppo costosa. La soluzione adottata consiste nel  rimuovere i filtri antirumore dalle cabine, alzando così la frequenza massima passante da 4KHz a 1.1Mhz.
In questo modo però si compromette l'uso dei telefoni, il problema è ovviato da uno splitter collegato alla presa del doppino di casa che divide il segnale telefonico da 4KHz da quello internet a 1.1MHz.
Gli splitter creano delle interferenze nella rete a cui sono collegati, si consiglia di usarne pochi per casa per evitare disturbi.
Un'altra soluzione è l'utilizzo del telefono con tecnologia DECT che permette di usare un canale wireless per le cornette di casa senza interferire con la rete wired.

Uno dei requisiti della rete digitale risulta è quello del multiplexing, cioè avere più canali di comunicazione in un unica rete. Una delle soluzioni migliori è quella di utilizzare l'FDM (Frequency Division Multiplexing), cioè dividere i canali su varie porzioni distinte della banda.
La DSL più utilizzata è l'ADSL (Asymmetric DSL), assimmetrica perchè si da più banda al download che all'upload. Nell'ADSL vi è un  range di frequenze tra 4KHz e 25KHz inutilizzato, per prevenire interferenze tra linea telefonica e linea internet. Upload e download Si sono ulteriormente divise in 256 canali da 4312.5Hz, limitando i disturbi su una certe frequenze solo ai canali che le contengono .<br>
È stata presa come riferimento la stessa banda di una connessione telefonica (4312.5Hz) per poter utilizzare le tecnologie già esistenti e ben collaudate.
Standard ADSL:<br>
- ADSL Lite: 1.5 Mbps download, 0.5 Mbps upload<br>
- ADSL: 8 Mbps download, 1 Mbps upload<br>
- ADSL2: 12 Mbps download, 1 Mbps upload<br>
- ADSL2(annex J): 12 Mbps download, 3.5 Mbps upload<br>
- ADSL2+: 24 Mbps download, 1 Mbps upload<br>
- ADSL2+(annex M): 28 Mbps download, 3.5 Mbps upload<br>

Le ADSL2+ utilizzano una banda doppia di 2.2 MHz anzichè 1.1 MHz, che però necessita di una linea particolarmente buona. Le ADSL 2 e 2+ supportano anche varianti "all-digital" in cui si rinuncia alla parte voce per guadagnare 256 Kbps in upstream.
Il limite di 28 Mbps dell'ADSL risulta però ancora limitativo, sopratutto a seguito dell'aumento dello streaming video avvenuto negli ultimi decenni. È nato perciò un nuovo standard basato sulla crescente diffusione della fibra, che permette l'utilizzo di frequenze sempre più alte: la VDSL (Very Hight Speed DSL, o informalmente detta anche Video DSL perchè spinta dalla necessità dello streaming video).<br>
Tipologie VDSL:<br>
- VDSL(2001): QAM, 55 Mbps download, 3 Mbps upload<br>
- VDSL2(2006): FDM, 200 Mbps download, 100 Mbps upload<br>
- VDSL2+(2011): FDM, 300 Mbps download, 100 Mbps upload<br>

Tali velocità però dipendono da quanto cavo UTP3 separa l'utente dal provider, per esempio dopo 1.0 Km di UTP3 la connessione VDSL2 degrada in ADSL2. Per quanto riguarda la banda utilizzata non esiste un unica divisione fissa tra upload e download come per l'ADSL, ma viene data della libertà di scelta con i band plans.
Più si ramifica l'infrastruttura telecomunicativa e più risulta necessario gestire un gran numero di comunicazioni contemporaneamente. La soluzione risiede nell'utilizzo di un multiplexing FDM attraverso group/super group con i quali si passa da 600 comunicazioni per cavo fino a 230000.
Nel caso della fibra, però, non viene più utilizzato il termine frequenza, ma lunghezza d'onda, dunque il multiplexing FDM viene chiamato WDM (Wavelength Division Multipllexing). Nel 1990 era possibile trasmettere 8 canali da 2.5Gbps ciascuno attraverso un singolo cavo di fibra, nel 2007 si è arrivati a 124 canali da 50 Gbps ciascuno, fino ad arrivare ai 32000 Gbps trasmessi in singolo cavo in fibra nel 2014.
Non esiste però solo il multiplexing di frequenza (FDM), ma anche altri come il multiplexing temporale (TDM) in cui si divide il tempo di connessione per distribuire i canali utilizzati temporalmente e non sulla banda, ma più sono i canali e minore sarà la velocità di connessione (e.g. con 24 canali si hanno 1,5 Mbps).

## Telefonia Mobile
Nel campo della telefonia Mobile l'Europa risulta molto competitiva con gli Stati Uniti:
- In Europa è presente uno standard unico per la gestione mobile, mentre gli USA, improntati su un eccessivo liberismo, sono finiti per utilizzare diversi standard incompatibili tra loro.
- In Europa è presente un principio trasparente di conoscenza tariffaria: esiste una distinzione tra numeri fissi e cellulari, dunque il chiamante sa se viene applicata la tariffa mobile oppure fissa. Negli Stati Uniti non c'è una distinzione tra i numeri fissi e mobili, ma siccome le chiamate cellulari costano di più, e al chiamante non è chiaro che tipo di linea stia chiamando, il costo aggiuntivo viene addebitato al ricevente, che può decidere di non pagare (non rispondendo alla chiamata).
- Negli USA le riforme economiche introdotte negli anni '80 hanno portato una grande competizione nel mercato della telefonia fissa, decretandone un costo molto basso. codeon l'introduzione del mobile (che costava più del fisso), non si è avvertita l'esigenza di effettuare il passaggio. Al contrario in Europa gli alti costi della telefonia fissa, favoreggiarono il passaggio al mobile.

Per lo sviluppo della tecnologia mobile si creò un problema di divisione territoriale. Inoltre inizialmente, non fu una tecnologia digitale: le prime due generazioni (0g e 1g) furono analogiche.

### 0G
Deriva dalle trasmissioni radio che si sono poi evolute nei PTT(push to talk, walkie-talkie), in cui era presente un unico canale di trasmissione comune half-duplex. Perchè push-to-talk? Tenere fisicamente premuto un pulsante incentivava a liberare il canale. Negli anni 60 nasce la prima generazione di telefonia: l'IMTS Improved Mobile Telephone System, in cui si dispone di più canali a frequenze distinte di trasmissione.
IMTS era dotato di un sistema per la privacy: non trasferiva le comunicazioni in chiaro.
Le celle utilizzate disponevano di 23 canali ciascuna con frequenze da 150-450Mhz. Queste coprivano un raggio di centinaia di chilometri e dunque risultano pratiche in zone poco affollate. Lo 0g si può trovare ancora oggi in zone rurali e difficili da raggiungere, ad esempio certe parti del Canada.

## Mobile 1G
1982: la Bell Labs introduce il sistema AMPS (Advanced Mobile Phone System), conosciuto in Italia come TACS (Total Access Communication System). Il sistema utilizzava una tecnologia simile a quella dell' IMTS (Improved Mobile Phone System) , ma con celle più piccole (10-20Km) che permettono un riuso più efficace delle frequenze permettendo accessibilità ad un maggior numero di utenti.

L'utilizzo di celle più piccole porta anche alla diminuzione della potenza necessaria per trasmettere, comportando un drastico calo nelle dimensioni delle batterie e nei costi dei cellulari, permettendo così la nascita di telefoni sempre più piccoli ed economici.

L'uso di celle più piccole comporta problemi di interferenza: tra due celle adiacenti ci saranno zone in cui i segnali si sovrappongono.

Una possibile soluzione a questo problema è quella di utilizzare diverse frequenze per ogni cella. Lo svantaggio è che così facendo si diminuisce drasticamente la quantità di banda utilizzabile.
è dunque necessario trovare il numero minimo di frequenze da utilizzare per mitigare il problema.
Questo è riconducibile al problema della colorazione di un grafo, problema che fu risolto nel 1976 mediante il teorema dei quattro colori: il teorema afferma che bastano 4 colori per colorare un qualunque grafo tale che ogni nodo abbia un colore differente dai suoi adiacenti.

Nella pratica non è sempre possibile utilizzare 4 colori: talvolta risulta necessario inserire delle microcelle all'interno di celle più grandi (come nel caso di grandi centri abitati) rendendo necessarie più frequenze per adattarsi a quelle già esistenti, a meno di non combinare le frequenze di tutte le celle connesse a quella rete, cosa che risulta impraticabile. Dunque in un contesto reale le frequenze utilizzate dalle celle variano da 3 a 7.

Al centro di ogni cella si trova una stazione base che comunica con tutti i telefoni che si trovano al suo interno. Ogni stazione base è collegata ad un MSC (mobile switching center). In un sistema esteso è possibile collegare più MSC a livelli diversi. Gli MSC comunicano tra loro, con le stazioni base e con la rete telefonica fissa mediante una rete a commutazione di pacchetto.

Ogni cellulare è agganciato ad una sola cella. Nel caso il segnale si indebolisca, viene effettuata una ricerca di una nuova cella in grado di fornire una ricezione migliore, nel caso venga trovata, viene effettuato il passaggio verso tale cella. Questa procedura si chiama handoff. _La procedura di ricerca e di handoff è a carico della stazione base della cella a cui è collegato il cellulare_: la stazione trasferisce la gestione dell'apparecchio alla cella che riceve il segnale più forte, di solito la cella in cui ora si trova il telefono. Il telefono viene così informato dell' identità della nuova centrale di controllo.

In un hard handoff, per permettere alla nuova cella di collegarsi, la cella utilizzata interrompe il collegamento con il cellulare, ma così facendo si ha un breve periodo di tempo (circa 0,3 secondi) in cui il telefono non avrà ricezione, provocando disagi nel caso si fosse nel mezzo di una chiamata.

Un soft handoff prevede invece di mantenere attiva la connessione con la cella precedente finchè non viene attivata la connessione con quella nuova. Questo richiede un onere maggiore per il cellulare che dovrà essere in grado di gestire due connessioni contemporaneamente. Il soft handoff è disponibile solo a partire dal 3G.

La tecnologia 1G vuole poter gestire un numero di utenti sempre maggiore, dunque è necessario adottare un sistema di multiplexing. AMPS usa FDM, con 832 canali simplex in trasmissione e 832 canali simplex in ricezione. Molti di questi canali non sono utilizzabili, in pratica, sono generalmente utilizzabili solo 45 canali per cella.
Questi 832 canali sono divisi in quattro categorie:
1. controllo: per la gestione del sistema
2. paging: per avvisare gli utenti delle chiamate in arrivo
3. accesso: per impostare la chiamata e l'assegnazione del canale
4. dati: per voce, fax o dati.

Ogni cellulare possiede un numero seriale di 32 bit ed un numero telefonico di 10 cifre a 34 bit. Ogni 15 minti ogni cellulare invia in broadcast i propri 32+34 bit per potersi registrare alla cella più vicina. Quesa trasmissione viene effettuata in chiaro: è possibile poter clonare un cellulare intercettando questi dati. La richiesta viene effettuata in un canale apposito (e condiviso), mentre in ricezione viene utilizzato un ulteriore canale (sempre condiviso) di paging, canale che i cellulari consultano per sapere se soono presenti chiamate che li riguardano.

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

## CDMA
È un acronimo che sta per Code Division Multiple Access.
CDMA non utilizza FDM o TDM: i dispositivi trasmettono contemporaneamente sulla stessa banda. Per permettere questa tipologia di trasmissione, viene usata una applicazione delle matrici di Hadamard.

Una matrice di Hadamard è una matrice contenente solo 1 e -1, tali che le sue righe siano mutualmente ortogonali.
è possibile costruire una matrice di Hadamard in maniera ricorsiva mediante il metodo di Sylvester, replicando la matrice H nella seguente maniera: <br>
H(1) = 1

H(n) =

| H(n-1) | H(n-1) |
| - | - |
| H(n-1) | -H(n-1) |

Nota bene: il negato di una matrice di Hadamard è esso stesso una matrice di Hadamard.

L'idea che sta alla base di questo tipo di multiplexing è la seguente: immaginiamo il canale come uno spazio multidimensionale, in cui ogni vettore della sua base è associato ad uno dei dispositivi che comunicano.
In realtá ad ogni dispositivo viene assegnata una forma d'onda che lo identifica all'interno della rete, chiamata _chip sequence_ che con il giusto paio di occhiali possiamo interpretarla come un vettore e un _chip_ come un suo componente.
Il messaggio inviato nel canale è quindi la combinazione lineare dei vettori dei vari dispositivi. 
Un dispositivo moltiplica il suo messaggio per 1 se vuole inviare un 1 logico, per -1 se vuole inviare uno 0 logico e per 0 se non comunica. <br>
Ogni dispositivo invia il messaggio sul canale, e la stazione riceve la somma di questi messaggi.
La stazione è in grado di estrapolarne, mediante una proiezione il messaggio inviato da ogni dispositivo.
Se il numero di dispositivi che vogliono trasmettere aumenta, bisogna aumentare opportunamente il numero di assi dello spazio.
Si pone quindi il problema di come ideare dei linguaggi che siano tra di loro ortogonali in maniera da mantenere le proprietà dello spazio descritto precedentemente.
Le matrici di Hadamard rispondono a questo problema in maniera eccellente: è possibile aumentare tale tipologia di matrici molto semplicemente ed in potenza di due, permettendo di generare spazi multidimensionali ampi abbastanza da gestire la mole di utenti delle reti moderne.


Esempio:
prendiamo uno spazio a due dimensioni.
La matrice di Hadamard(2) associata a quello spazio è la matrice: 

| 1 | 1 |
| - | - |
| 1 | -1 |

I vettori di questo spazio, sono quindi: V1=(1; 1) e V2=(1; -1). 
Questo significa che: 
- Lo spazio sarà in grado di gestire 2 dispositivi che vogliono comunicare
- I codici adottati dai due dispositivi sono i seguenti: V1=(1; 1) e V2=(1; -1).

Ipotizziamo una comunicazione in cui il dispositivo D1 vuole trasmettere un 1 logico e il dispositivo D2 vuole trasmettere uno 0 logico;
Il dispositivo D1 trasmetterà sul canale 1*(1; 1);
Il dispositivo D2 trasmetterà sul canale -1*(1; -1);

Siccome il canale wireless è condiviso, la cella riceverà la somma dei segnali inviati ovvero:
(1; 1)+(-1; +1) = Vsomma(0; 2);

La cella ricevente moltiplica Vsomma per V1 ed ottiene:
(0; 2) * (1; 1) = 2. 
Questo significa che V1 ha trasmesso e ha trasmesso un 1 logico;
La cella ricevente moltiplica Vsomma per V2 ed ottiene:
(0; 2) * (1; -1) = -2. 
Questo significa che V1 ha trasmesso e ha trasmesso uno 0 logico;


Il CDMA ha alcune criticità:
i telefoni cellulari hanno generalmente distanza variabile dalla cella a cui sono collegati, dunque la potenza del segnale ricevuto può variare alterando la ricomposizione dei singoli messaggi. La soluzione consiste nell'aumentare la potenza di trasmissione all'aumentare della distanza dalla cella, cosí riceverá i messaggi tutti con lo stesso "volume" .<br>
Uno dei pregi di CDMA è che la banda utilizzata non viene divisa come in AMPS o D-AMPS, ma invece rimane interamente utilizzabile dato che non sorge il problema del riuso delle frequenze.<br>
Inoltre, normalmente il traffico voce occupa solo il 35-40% del tempo di connessione, mentre il resto risultano essere momenti di pausa tra una parola e l'altra. Negli standard D-AMPS e GSM questo tempo occupa inutilmente banda, mentre CDMA è in grado di e lo spreco di banda in CDMA risulta così molto inferiore. Nel caso delle future connessioni a internet tale vantaggio risulta ancor di più accentuato dato che il tempo di trasferimento dati web è ancor minore rispetto al tempo senza trasmissioni.

## 3G
Offre più datarate ed un numero maggiore di utenti supportati, grazie all'utilizzo di bande di frequenza più larghe.<br>
Sono presenti due standard principali: <br>
- WCDMA (Wideband CDMA): utilizzato in Europa ed in Giappone, conosciuto anche con il nome di UMTS.
Utilizza una banda per canale molto larga (5 Mhz), con un datarate di 384 Kbps.
- CDMA2000: utilizzato negli USA, offre un datarate da 144 Kbps, con bande più ristrette da 1.25 Mhz.
L'utilizzo del CDMA richiede però la trasmissione di segnali a potenza variabile, impattando cosi sulla durata delle batterie.

## 3.5G
- HSDPA (High Speed Downlink Packet Access) è l'evoluzione dell'UMTS, retrocompatibile con CDMA e QAM.
Offre diverse varianti che spaziano da 1.8 Mbps a 14.4 Mbps.
- HSUPA (High Speed Uplink Packet Access) nasce come un'evoluzione del HSDPA, cercando di offrire maggiore velocità in upload.
Risultò però fallimentare rispetto alla velocità in download che si scopri si potesse raggiungere con lo HSPA+.
- HSPA+ è un'evoluzione del HSDPA che permette una velocità in download di 28 Mbps e in upload di 11 Mbps, con un massimo
raggiungibile di 42 Mbps in download e 22 Mbps in upload.

## 4G
HSOPA(High Speed OFDM Packet Access), detto anche LTE o E-UTRA. Per la prima volta nella telefonia mobile si hanno bande variabili da 125Mhz fino a 20Mhz, con velocità massima da 1.2Gbps in downlink e 600Mbps in upLink. Per arrivare a questi risultati il 4g utilizza sempre più banda e usa tecniche aggiuntive di FDM e TDM. Utilizzando sempre più banda si è arrivati ad interferire con le frequenze utilizzate dal digitale Terrestre: ciò richiese agli utenti di quest'ultimo di aggiungere un filtro per bloccare le interferenze con il 4G LTE.
## 5G
Tecnologia ancora in fase di sperimentazione, non ha ancora uno standard definito. L'utilizzo di una nuova banda tenderà però ad utilizzare sempre più frequenze dedicate al digitale terrestre, è stato quindi ridefinito uno standard per il digitale (DVB-T2) per portarlo a frequenze più alte, in aggiunta a ciò le televisioni adotteranno un nuovo standard per la compressione video: H.265.<br>
Un'alternativa sviluppata da Qualcomm è quella di utilizzare frequenze oltre a quelle utilizzate nelle normali telecomunicazioni, andando ad utilizzare una banda una banda corrispondente alle microonde ed infrarosso, con il corrispondente utilizzo di antenne direzionali per inviare e ricevere tali segnali.
