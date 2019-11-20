### Correzione e Rilevazione dell'errore  
Gli architetti delle reti hanno sviluppato due strategie di base per gestire gli errori  
**Codifica a rilevamento d'errore (error detection)**  
Con questa strategia si cerca di identificare uno (o più) errori avvenuti durante la trasmissione, ma non di correggerlo.  La destinazione potrà successivamente chiedere il rinvio del blocco dati corrotto.  
E' utile quando il canale è affidabile.  
**Codifica a correzione d'errore (error correction)**  
Con questa strategia si cerca di correggere uno (o più) errori di trasmissione.  
E' utile in caso di trasmissioni wireless (perché è un canale molto rumoroso)    
#### Prefazione  
Occorre identificare una misura per descrivere la magnitudine degli errori, viene quindi definito il concetto di:   **distanza di Hamming** => si dice che due messaggi di uguale lunghezza sono distanti *n* se differiscono per n bit. (per fare ciò basta fare lo XOR tra le codeward e guardare il numro di bit a 1)  
