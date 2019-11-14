## Trasmissione in banda base
Forma più naturale di modulazione digitale, usa NRZ (non-return-to-zero). Tensione positiva per 1, negativa per 0. Se il segnale viene attenuato e distorto il ricevente assegna il valore più vicino al valore effettivo assunto dall'onda.

### Efficienza di banda
La lunghezza di banda (bandwidth) è una misura fisica che indica l'insieme di frequenze trasmissibili su un canale, ed è generalmente misurata in Hz.<br>
Il data-rate è invece una misura informativa (astratta) che può essere ricondotta a due diverse misure:<br>
- bit-rate: quanti bit al secondo vengono trasmessi.<br>
- baud-rate (symbol rate): quanti simboli al secondo vengono trasmessi, utile in caso si stia associando un differente simbolo ad ogni forma d'onda.
In generale, `bitrate = baudrate x log(2)V`, dove V è il numero di simboli trasmessi, quindi il bitrate sarà sempre maggiore del baudrate quando si trasmettono più di due simboli.<br>
Infatti il bitrate sarà sempre maggiore del baudrate quando si trasmettono più di due simboli. Il bitrate non è altro che il baudrate nel caso specifico in cui vengano trasmessi solo due simboli, 1 e 0.<br>
Naturalmente maggiore è la frequenza di trasmissione e più alto sarà il datarate, però frequenze troppo alte sono generalmente poco applicabili ai canali di comunicazione reali.<br>
È dunque necessario trovare un buon compromesso tra alte frequenze e capacità di trasmissione, infatti la potenza di trasmissione cresce col quadrato della frequenza trasmessa, perciò è presente un limite di banda, cioè un limite di potenza impiegata.

### Teorema di Nyquist
Il data-rate massimo (bit al secondo) è: `2*B*log(2) L`
dove B e la banda massima, L sono i livelli del segnale che vengono usati.
Nel caso del telegrafo L=2 (0, 1) -> data-rate massimo è 2B.
Nella pratica non vale perché ci sono interferenze: il teorema vale solo in condizioni ideali.
Bisogna considerare la potenza del rumore R.

### Teorema di Shannon
Generalizzazione del teorema di Nyquist considerando il rumore R.
max\_data\_rate = `B*log(2) (1+S/N)`
dove S/N è il rapporto tra la potenza del segnale S e la potenza del rumore del canale R, che dipende dalla qualità del mezzo.
Si indica in decibel -> `10*log(10) S/N = SNR`.
Nel caso ottimo, con alto S/N, il massimo data rate è `(B/3)*SNR`.

### Clock recovery
Tutte le strategie di codifica prevedono che il ricevente sia tenuto a conoscere quando un simbolo termina e il successivo inizia. Con _NRZ_ una sequenza lunga di 1 o 0 manda fuori sincronia il ricevente se non si dispone di un clock molto preciso, il quale è molto costoso per l'uso domestico. Una possibile soluzione è miscelare il segnale di clock con i dati usando una XOR, cosi da usare una sola connessione. Questo tipo di approccio si chiama codifica di Manchester. A causa del clock richiede il doppio di banda del NRZ.<br>
Si è sviluppato perciò _NRZI_ (NRZ inverted), che codifica l'1 come cambiamento di fase dell'onda. Dunque lunghe sequenze di 0 sono ancora un problema.<br>
Il codice 4B/5B risolve questo problema. Ogni gruppo di 4 bit è associato ad una sequenza di 5 bit secondo una tabella di conversione nota. Provoca un overhead del 25%.<br>
Un approccio alternativo è mettere in XOR i dati con sequenze pseudocasuali di bit (_scrambling_). Il ricevente applicherà una XOR ai bit con la stessa sequenza casuale. Non aggiunge overhead di banda o di tempo. Segnali casuali tendono ad avere la loro energia distribuita su tutte le componenti di frequenza. Tuttavia non viene garantito che non ci siano lunghe sequenze di simboli uguali.

### Segnali bilanciati
Segnali che presentano una tensione tanto positiva quanto negativa, la loro media è 0. Non hanno componenti in corrente continua, ed è un vantaggio poiché alcuni canali trasmissivi attenuano fortemente queste componenti. Inoltre uno dei metodi per collegare il ricevente al canale, chiamato _accoppiamento capacitivo_ lascia transitare solo corrente alternata.<br>
Il bilanciamento aiuta ad aggiungere transizioni per il clock recovery e sincronizza i riceventi in quanto è possibile calcolare la media del segnale e usarla come soglia decisionale per la decodifica.<br>Un esempio per realizzare il bilanciamento è assegnare +1V e -1V per rappresentare un 1 (usati in modo alterno, _codifica bipolare_), 0V per lo 0.

## Trasmissione in banda passante
Gamma di frequenze che non inizia dallo 0. Utile per realizzare FDM. Il valore assoluto della frequenza non influenza la capacità di trasferimento dati, tutto dipende dall'ampiezza o dalla banda di frequenza.<br>
Possiamo quindi prendere un segnale in banda base che va da 0 a B Hz e traslarlo in banda passante che va da S a B+S Hz. Il ricevente effetturà la trasposizione al contrario.<br>
Possiamo modulare l'ampiezza, la frequenza o la fase del segnale portante:<br>
- ASK (amplitude shift keying): due ampiezze diverse usate per rappresentare 0 e 1.
- FSK (frequency shift keying): si usano due o più frequenze per 1 e 0.
- PSK (phase shift keying): l'onda portante è traslata di 0 o 180 gradi all'inizio della trasmissione di ogni simbolo. In questo caso, essendoci 2 fasi, prende il nome di BPSK (binary PSK). Qui binario si riferisce ai due simboli 0 e 1.<br>Uno schema migliore e più efficiente è QPSK (quadrature PSK), 2 bit di informazione per simbolo. Per trasmettere più bit per simbolo si possono combinare le tecniche e usare più livelli. Solo una tra frequenza e fase può essere modulata ogni volta.

E' possibile arrivare a più di 2 bit per simbolo. Ad esempio con _QAM-16_ (quadrature amplitude modulation) si arriva a 4 bit per simbolo. Con _QAM-64_ si arriva a 16. Queste ultime tecniche vengono usate nella modulazione digitale. Esistono QAM di dimensione superiore, ma il tasso di errore aumenta esponenzialmente.<br>
Per capirlo basta osservare il _costellation diagram_ di queste modulazioni, in cui più sono vicini i punti che rappresentano i simboli più alto è il tasso di errore. Un diagramma perfetto sarebbe circolare, purtroppo è difficile da realizzare. I puntini vengono quindi disposti a quadrato, limitando la potenza del QAM.<br>
Un perfezionamento di QAM è il _Gray code_, che associa a simboli adiacenti sequenze differenti di solo 1 bit, in modo che l'errore sia risolvibile ai livelli superiori.
