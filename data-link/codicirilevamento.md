## Rilevazione dell'errore  
Per effettuare un error control sarà necessario l'utilizzo di informazioni aggiuntive all'interno del frame. Avremo dunque una fase di **encoding**, in cui vengono aggiunti dei bit di protezione, e una fase di **decoding**, in cui i bit di protezione vengono controllati e rimossi (l'error control è quindi nella fase di decoding).  
### Parity bit  
Uno dei primi metodi di *error controol* fu quello dei bit di parità, dove ogni n bit viene inserito uno 0 oppure un 1 in caso la somma degli n bit sia rispettivamente pari o dispari;  
e.g.:  
1. 01 => 01**1**  
1. 01111 => 01**1**11**0**  
Nel casoo del *parity bit*, con un qualsiasi *n* si ha comunque distanza 2, ciò significa che sarà possibile identificare 1 singolo errore. Abbiamo quindi un **error rate** *(cioé il numero di errori identificabili)* di **1/(n+1)** e un **data rate** effettivo di **n/(n+1)**  
## Repetition code
Un altro algoritmo di **error control** è il **repetition code** Rn, dove ogni bit viene ripetuto **n** volte  
e.g.:(con n=3)  
010 => 0**00**1**11**0**00**  
In questo modo la distanza tra messaggi correttu sarà **n**, poichè saranno necessari errori di potenza **n** per corrompere il flusso di dati, rendendo l'algoritmo funzionante per messaggi a distanza **n-1**.  
Questo algoritmo permette quindi di alzare il livello di controllo arbitrariamente, a discapito però del data rate, che si attesta sul **1/n**. Oltre all'error detection il repetitin code permette anche un eventuale **error correction**, a condizione che la potenza dell'errore sia minore di **n/2** ( possiamo fare **error correction** fino a **n-1)/2** ), se fosse maggiore si avrebbero infatti messaggi accettabili più vicini all'errore rispetto alla distanza che il messaggio originale ha con l'errore  
e.g.:  

| Messaggio da inviare | Messaggio codificato con R3 |
| :-: | :-: |
| 0 | 000 |
| **Messaggio decodificato erroneamente** | **mesaggio ricevuto** |
| 1 | 101 |
## Built-in error detection  
Un altro approcio all'error detection è l'utilizzo di codici di controllo; in particolare nel **built-in** error detection questi codici vengono inseriti direttamente all'interno del dato trasmesso, e non sotto forma di codifica della trasmissione, rendendo così l'error detection indipendente dal metodo di trasmissione.  
Un esempio di **built-in error detection** è il **codice di Luhn**. Il suo funzionamento è analogo al parity bit, ma è concepito per l'utilizzo anche da parte di persone, dunque è in base 10. Il codice di Luhn permette l'individuazione di un errore, oppure dello scambio di due cifre vicine che non siano 9 e 0 ( e.g. "25" => "52"). E' un algoritmo che viene usato nelle carte di credito, nelle quali l'ultima cifra indica proprio il codice di controllo.
## Codici di Hamming  
Fanno parte della famiglia dei codici lineari ( cioè processabili on somme e moltiplicazioni ). Sono codici a blocco, che utilizzano comunque dei bit di parità, ma in modo più efficiente.  
Un codice di **H(X,Y)** identifica una codifica di Y bit con un dato totale ( dato+bit parità) di X bit.
