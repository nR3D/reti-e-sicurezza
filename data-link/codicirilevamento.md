## Rilevazione dell'errore  
Per effettuare un error control sarà necessario l'utilizzo di informazioni aggiuntive all'interno del frame. Avremo dunque una fase di **encoding**, in cui vengono aggiunti dei bit di protezione, e una fase di **decoding**, in cui i bit di protezione vengono controllati e rimossi (l'error control è quindi nella fase di decoding).  
### Parity bit  
Uno dei primi metodi di *error controol* fu quello dei bit di parità, dove ogni n bit viene inserito uno 0 oppure un 1 in caso la somma degli n bit sia rispettivamente pari o dispari;  
e.g:  
1. 01 => 01**1**  
1. 01111 => 01**1**11**0**  
Nel casoo del *parity bit*, con un qualsiasi *n* si ha comunque distanza 2, ciò significa che sarà possibile identificare 1 singolo errore. Abbiamo quindi un **error rate** *(cioé il numero di errori identificabili)* di **1/(n+1)** e un **data rate** effettivo di **n/(n+1)**  
