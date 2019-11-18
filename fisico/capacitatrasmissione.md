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
