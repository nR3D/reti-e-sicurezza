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
