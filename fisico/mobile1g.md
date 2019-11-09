## Mobile 1G
1982: la Bell Labs introduce il sistema AMPS  (Advanced Mobile Phone System), conosciuto in Italia come TACS (Total Access Communication System). Il sistema utilizzava una tecnologia simile a quella dell' IMTS (Improved Mobile Phone System) , ma con celle più piccole (10-20Km) che permettono un riuso più efficace delle frequenze permettendo accessibilità ad un maggior numero di utenti.

L'utilizzo di celle più piccole porta anche alla diminuzione della potenza necessaria per trasmettere, comportando un drastico calo nelle dimensioni delle batterie e nei costi dei cellulari, permettendo così la nascita di telefoni sempre più piccoli ed economici.

L'uso di celle più piccole comporta problemi di interferenza: tra due celle adiacenti ci saranno zone in cui i segnali si sovrappongono.

Una possibile soluzione a questo problema è quella di utilizzare diverse frequenze per ogni cella. Lo svantaggio è che così facendo si diminuisce drasticamente la quantità di banda utilizzabile.
è dunque necessario trovare il numero minimo di frequenze da utilizzare per mitigare il problema.
Questo è riconducibile al problema della colorazione di un grafo, problema che fu risolto nel 1976 mediante il teorema dei quattro colori: il teorema afferma che bastano 4 colori per colorare un qualunque grafo tale che ogni nodo abbia un colore differente dai suoi adiacenti.

Nella pratica non è sempre possibile utilizzare 4 colori: talvolta risulta necessario inserire delle microcelle all'interno di celle più grandi (come nel caso di grandi centri abitati) rendendo necessarie più frequenze per adattarsi a quelle già esistenti, a meno di non combinare le frequenze di tutte le celle connesse a quella rete, cosa che risulta impraticabile. Dunque in un contesto reale le frequenze utilizzate dalle celle variano da 3 a 7.

Al centro di ogni cella si trova una stazione base che comunica con tutti i telefoni che si trovano al suo interno. Ogni stazione base è collegata ad un MSC (mobile switching center). In un sistema esteso è possibile collegare più MSC a livelli diversi. Gli MSC comunicano tra loro, con le stazioni base e con la rete telefonica fissa mediante una rete a commutazione di pacchetto.

Ogni cellulare è agganciato ad una sola cella. Nel caso il segnale si indebolisca, viene effettuata una ricerca di una nuova cella in grado di fornire una ricezione migliore, nel caso venga trovata, viene effettuato il passaggio verso tale cella. Questa procedura si chiama handoff. La procedura di ricerca e di handoff è a carico della stazione base della cella a cui è collegato il cellulare: la stazione trasferisce la gestione dell'apparecchio alla cella che riceve il segnale più forte, di solito la cella in cui ora si trova il telefono. Il telefono viene così informato dell' identità della nuova centrale di controllo.

In un hard handoff, per permettere alla nuova cella di collegarsi, la cella utilizzata interrompe il collegamento con il cellulare, ma così facendo si ha un breve periodo di tempo (circa 0,3 secondi) in cui il telefono non avrà ricezione, provocando disagi nel caso si fosse nel mezzo di una chiamata.

Un soft handoff prevede invece di mantenere attiva la connessione con la cella precedente finchè non viene attivata la connessione con quella nuova. Questo richiede un onere maggiore per il cellulare che dovrà essere in grado di gestire due connessioni contemporaneamente. Il soft handoff è disponibile solo a partire dal 3G.

La tecnologia 1G vuole poter gestire un numero di utenti sempre maggiore, dunque è necessario adottare un sistema di multiplexing. AMPS usa FDM, con 832 canali simplex in trasmissione e 832 canali simplex in ricezione. Molti di questi canali non sono utilizzabili, in pratica, sono generalmente utilizzabili solo 45 canali per cella.
Questi 832 canali sono divisi in quattro categorie:
1. controllo: per la gestione del sistema
2. paging: per avvisare gli utenti delle chiamate in arrivo
3. accesso: per impostare la chiamata e l'assegnazione del canale
4. dati: per voce, fax o dati.

Ogni cellulare possiede un numero seriale di 32 bit ed un numero telefonico di 10 cifre a 34 bit. Ogni 15 minti ogni cellulare invia in broadcast i propri 32+34 bit per potersi registrare alla cella più vicina. Quesa trasmissione viene effettuata in chiaro: è possibile poter clonare un cellulare intercettando questi dati. La richiesta viene effettuata in un canale apposito (e condiviso), mentre in ricezione viene utilizzato un ulteriore canale (sempre condiviso) di paging, canale che i cellulari consultano per sapere se soono presenti chiamate che li riguardano.
