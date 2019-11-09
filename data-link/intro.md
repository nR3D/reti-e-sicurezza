# Data link layer
Il primo strato al di sopra dello strato fisico si occupa di codificare e decodificare i segnali, offrendo un'interfaccia con gli strati adiacenti, occupandosi inoltre di error control e flow control.

Il data link layer offre quattro diversi servizi per gestire lo scambio di dati:
- acknowledgment/unacknowledgment
- connection/connectionless

che possono essere combinati tra loro a seconda delle esigenze.
In particolare ci sono 3 combinazioni:
- unacknowledgment senza connessione: la sorgente invia frame indipendenti alla macchina destinazione, senza che quest'ultima ritorni conferma di ricezione. La correzione puo' essere saltata se siamo in sistemi real-time, dove necessitiamo di velocità piuttosto che qualità, oppure affidata agli strati superiori nel caso in cui siano pochi errori e di lieve entità.
- acknowledgment senza connessione: ciascun frame è inviato individualmente e si attende conferma di ricezione tramite ACK. In caso di mancata ricezione dell'ACK il mittente ritrasmette il frame. A livello data link l'ACK è un'ottimizzazione, non è fondamentale.
- servizio orientato alla connessione: in questa modalità viene aperto un canale diretto tra le macchine comunicanti, che verrà percorso da tutti i frame. In questo modo si ha un flusso bit affidabile. Al termine della comunicazione la connessione deve essere rilasciata.
