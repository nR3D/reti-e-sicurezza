## CDMA
Code Division Multiple Access: in un ambiente CDMA non vengono utilizzati FDM/TDM; i dispositivi possono trasmettere a qualsiasi frequenza ed in qualsiasi momento. Per permettere questa tipologia di trasmissione viene assegnata una forma d'onda ad ogni dispositivo che lo identifica all'interno della rete, chiamata _chip sequence_. Il _chip_ è l'intervallo di suddivisione del tempo di trasmissione di ogni bit, diviso in m intervalli. Questo è possibile grazie all'utilizzo degli spazi multidimensionali in cui ogni asse risulta univocamente identificabile poiché ortogonale a tutte le altre, dunque il prodotto scalare tra due assi risulterà essere nullo. Tale sequenza di chip ortogonali viene generata con il _codice di Walsh_. Se viene ricevuto un segnale in cui sono state utilizzati più assi sarà quindi sufficiente effettuare il prodotto scalare tra i dispositivi registrati (ovvero gli assi disponibili, chip sequences) e considerare i risultati non nulli per trovare gli assi utilizzati in trasmissione. Per recuperare la sequenza di bit inviata da una stazione il ricevente deve conoscere in anticipo la sequenza di chip di quella stazione. Il recupero si effettua calcolando il prodotto interno normalizzato tra la sequenza di chip ricevuta e la sequenza dela stazione i cui bit vogliamo recuperare. Per ridurre il più possibile le frequenze utilizzate per costruire le onde trasmesse, vengono utilizzati simboli 1 e -1 invece che 1 e 0. Per la creazione degli assi vengono utilizzate le matrici di Hadamard, formate dai simboli utilizzati:

(integrare matrici con LaTeX)

Le due parole (1 e 0, in realtà 1 e -1) vengono trasmesse contemporaneamente (esempio 1, 1+1, -1 = 2, 0) è quindi possibile effettuare un prodotto scalare per determinare quali simboli siano stati trasmessi (es 1*2 + 1*0 = 2 != 0 quindi il segnale 1 del dispositivo associato agli assi 1, 1 è stato trasmesso), in caso il risultato sia nullo allora il dispositivo associato a quell'asse non ha trasmesso simboli, nel caso di un risultato positivo significa che il dispositivo ha inviato un 1, nel caso sia negativo un -1 (0).<br>
Uno dei problemi maggiori dello standard CDMA è che si assume che ogni dispositivo trasmetta il segnale con la stessa potenza, perché in caso contrario il prodotto scalare risulterebbe sbagliato. Però i telefoni cellulari hanno generalmente distanza variabile dalla cella a cui sono collegati, dunque la potenza varia in base a tale distanza. La soluzione consiste nell'aumentare la potenza all'aumentare della distanza dalla cella, in modo da renderla uguale per tutti i dispositivi.<br>
Uno dei pregi di CDMA è invece che la banda utilizzata non viene divisa in frequenze utilizzabili da ogni cella, ma risulta invece utilizzabile interamente dato che non ci saranno interferenze tra celle, infatti il fenomeno delle interferenze è già implementato nell'algoritmo del CDMA.<br>
Un altro vantaggio è che normalmente il traffico voce occupa solo il 35-40% del tempo di connessione, mentre il resto risultano essere momenti di pausa tra una parola e l'altra. Negli standard D-AMPS e GSM questo tempo occupa inutilmente banda, mentre nel CDMA non è presente una parte di banda assegnata, e lo spreco dovuto a questi momenti di pausa risulta così molto inferiore. Nel caso delle future connessioni a internet tale vantaggio risulta ancor di più accentat dato che il tempo di trasferimento dati web è ancor minore rispetto al tempo senza trasmissioni.

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
