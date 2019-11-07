## Capacità di trasmissione
La lunghezza di banda (bandwidth) è una misura fisica che indica l'insieme di frequenze trasmissibili su un canale, ed è generalmente misurata in Hz.<br>
Il data-rate è invece una misura informativa (astratta) che può essere ricondotta a due diverse misure:<br>
- bit rate: quanti bit al secondo vengono trasmessi.<br>
- baud rate: quanti simboli al secondo vengono trasmessi, utile in caso si stia associando un differente simbolo ad ogni forma d'onda.
In generale, _bitrate=baudrate x log(2)V_, dove V è il numero di simboli trasmessi, quindi il bitrate sarà sempre maggiore del baudrate quando si trasmettono più di due simboli.<br>
Infatti il bitrate sarà sempre maggiore del baudrate quando si trasmettono più di due simboli. Il bitrate non è altro che il baudrate nel caso specifico in cui vengano trasmessi solo due simboli, 1 e 0.<br>
Naturalmente maggiore è la frequenza di trasmissione e più alto sarà il datarate, però frequenze troppo alte sono generalmente poco applicabili ai canali di comunicazione reali.<br>
È dunque necessario trovare un buon compromesso tra alte frequenze e capacità di trasmissione, infatti la potenza di trasmissione cresce col quadrato della frequenza trasmessa, perciò è presente un limite di banda, cioè un limite di potenza impiegata.

## Teorema di Nyquist
Il data-rate massimo (bit al secondo) è: _2*B*log(2) L_
dove B e la banda massima, L sono i livelli del segnale che vengono usati.
Nel caso del telegrafo L=2 (0, 1) -> data-rate massimo è 2B.
Nella pratica non vale perché ci sono interferenze: il teorema vale solo in condizioni ideali.
Bisogna considerare la potenza del rumore R.

## Teorema di Shannon
Generalizzazione del teorema di Nyquist considerando il rumore R.
max_data_rate = _B*log(2) (1+S/N)_
dove S/N è il rapporto tra la potenza del segnale S e la potenza del rumore del canale R, che dipende dalla qualità del mezzo.
Si indica in decibel -> 10*log(10) S/N = SNR.
Nel caso ottimo, con alto S/N, il massimo data rate è (B/3)*SNR.
