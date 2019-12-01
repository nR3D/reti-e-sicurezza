## Controllo del flusso
-----------------------
Il livello datalink si occupa anche di controllare il flusso dati. 
Quando trasferiamo parecchie informazioni c'è il rischio che il ricevente non riesca a gestirle.
Per ovviare al problema si può:
- Disegnare la rete in maniera da usare il datarate adeguato ma questo limita le retidinamiche su larga scala che hanno flussi variabili.
- Far interagire trasmettitore e ricevente mediante un protocollo per la gestione del flusso

**Stop-and-Wait:**
     Dopo aver spedito un blocco dati(frame) il trasmettitore si ferma e attende la conferma di ricezione
     corretta (ACK) prima di riprendere la trasmissione. 
     _vantaggio_: per questo protocollo basta un canale half-duplex
     _svantaggio_: È lento e se il mittente spedisce un pacchetto che arriva corrotto, il ricevente 
     lo scarta e non risponde. Il mittente si blocca in attesa. Si combatte ciò con una misura locale che
     non dipende dalle comunicazioni: il tempo. 
 
 **TIMEOUT:** 
     Se entro un certo tempo non ricevo l'ACK ri-invio il messaggio.
     _vantaggio_: Risolve il problema d'eliminazione del messaggio da parte del trasmittente
     _svantaggio_: Se viene perso l'ACK il ricevente assimila due volte lo stesso messaggio.
     
**PAR e ARQ:**      
     Numerare i pacchetti, ma quanto potrà essere grande il numero? con pochi bit possiamo inviare pochi 
     pacchetti mentre troppi bit sprecano banda. 
     Ma a noi interessa controllare solo frame consecutivi per distinguerli, quindi bastano due numeri
     0 e 1 alternati tra frame dispari e frame pari.
    
## Canale Full Duplex:
----------------------
Se il canale è diviso in due parti basterà una comunicazione half-duplex per parte a trasformarlo in full-duplex. Questo metodo dimezza la banda disponibile, visto che per ogni pacchetto dati ne serve un'altro di riconferma .
**Piggy-backing:**
        Invece di rispondere subito con l'ACK, il ricevente aspetta di avere un frame dati a cui aggiungere un bit 
        che funge da ACK. 
        L'over-head è minimo, ma l'attesa di un frame da spedire assiame all'ACK può causare una ritrasmissione
        dal mittente.
        Funziona bene quando il flusso dati è equilibrato, quando si aumenta coscentemente 
        il timeout del mittente, oppure un ACK e basta quando non c'è possibilita di piggy-backing.
 
   
Utilizzo della linea:
Se il canale ha capacita C(bit/s), taglia del frame S(bits) e tempo di round trip R allora l'efficenza di utilizzo della linea nei protocolli in stile stop&wait = `S / (S + C*R)` (`C*R` sono i dati che potevano essere trasmessi). Se `S<C*R` l'efficenza è minore del 50%
Un modo per aumentare l'efficenza è inviare più pacchetti prima dell'arrivo dell'ACK.
     
**Sliding Windows:**
        L'idea è quella di avere una finestra  circolare di n spicchi a cui si accede a m spicchi dove m<=n,
        a ognuno di questi è assegnato un pacchetto da spedire,
        quando ricevo l'ACK  relativo a quello spicchio lo libero e se anche gli spicchi precedenti si son liberati        la finestra si sposta a quello successivo.
        Anche il ricevitore deve essere pronto per l'arrivo di più pacchetti.
        Il ricevente tiene aperta una finestra per sugli spicchi che sta aspettando, quando il pacchetto arriva
        invia l'ack corrispondente. Se gli spicchi precedenti della finestra sono stati ricevuti sposto l'inizio 
        della finestra allo spicchio successivo.
        Due numeri importanti: l'ampiezza complessiva della finestra(n), e il grado di parallelismo(m)
        (Quanti pacchetti invio contemporaneamente)
        grado <= ampiezza

**Protocolli GoBackN:**
        Sliding window in cui il ricente i dati con grado si parallelismo=1 spicchio, funziona bene quando non ci 
        sono molti errori, ma il prodotto `C*R` è alto.
        Il rischio aumenta perchè più pacchetti sono soggetti al mondo fisico, quindi se spedisco n pacchetti 
        dovrò tenere n copie nel vengano persi. Serve un buffer da n frames. 
        e quindi un numero limitato di frame che posso spedire,timer di ritrasmissione.
        Si chiama goBackN perchè se qualcosa va male si inviano tutti i pacchetti successivi all'ultimo
        ACK ricevuto.

**Selective Repeat:**
        Parallelismo sia del ricevitore che del trasmettitore.
        
È possibile che tra trasmissioni contigue con un grado di parallelismo troppo alto, si sovrappongano su stessi slotdando problemi di duplicazione dei pacchetti. Il problema non si propone se grado di parallelismo <= ampiezza/2, così trasmissioni adiacenti non potranno sovrapporsi.
Ma i problemi del controllo di flusso non sono finiti: Il tempo di ACK è molto variabile e potrebbe causare delle ritrasmissioni inutili. La soluzione sta nel impostare il timeout un po' più alto della media e aggiungere alla comunicazione il NAK (Not ACK) che comunica una cattiva ricezione del messaggio, permettendo il bypass del timeout.     
     HDLC (High-Level Datalink Control):
         ha alcune varianti LAP LAPB. Creato da IBM e si usa ancora nelle reti dei bancomat, modem e fax.
         Frames delimitati con il bit stuffing; 
         Pacchetto:
         ```
            | 01111110 |
            | address |:
                8bit, piccolo indirizzamento locale 
            | control |:
                8bit, controllo di flusso e direttive del protocollo
                controllo di flusso mediante sliding window con 3bit (8spicchi, buono per un delay alto 
                satelliti)
                - primo bit a 0
                - 3bit CONTROL per il controllo di flusso
                - 3bit NEXT per l'ack piggyback
                - 1bit P/F che gestisce l'inizio e la fine della trasmissione
                Frame supervisor:
                comandi di alto livello per il datalink
                - primo bit a 1 secondo a zero
                - type 2bit: 0=ACK usato quando il flusso è sbilanciato
                             1=REJECT, NAK generalizzato, ritrasmissione di tutto quello che è sliding 
                             windows a partire dal NEXT
                             2=RECIVE NOT READY indica problemi di congestione nel reciver, seguito da un
                             ACK quando si libera
                             3=SELECTIVE REJECT, NAK classico NEXT indica il pacchetto da ritrasmettere 
                - Ultimi bit P/F e NEXT
                FRAME UNUMBERED:
                contiene messaggi per la comunicazione
                    -primo bit a 1 secondo a 1
                    DISC: disconnect chiude le comunicazioni 
                    SNRM: Comando duale che segnala la nuova entrata di una macchina, indica un canale
                    asimmetrico
                    SABM: modalità di connessione bilanciata
                    FRMR: indica che è stata ricevuta una sequenza non corretta
                    anche questi comandi sono unnumbered e quindi senza controllo di flusso
                    -> comando dedicato UA (Unumbered ACK)
            | dati >= 0 bit |
            | checksum |:
                16bit solo controllo errore, calcolato con CRC) 
            | 01111110 |
            ```
    PPP (Point-to-Point Protocol):
        protocollo utilizzato in internet
        FRAMING: Utilizza il Byte-Stuffing, un protocollo più moderno usa una tecnica meno efficente
            
        CONTROLLO DI FLUSSO: questa parte di PPP si chiama LCP (Link Control Protocol)
                             Altra parte NCP (Network Control Protocol) per l'interazione
                             con lo strato superiore 
        FRAME: 
        ```
        | 01111110 | Flag
        | 11111111 | Address: non usato
        | 00000011 | Control: non usato, non usa numbering o ACK
        | Protocol | 1 o 2 byte: informazione su quale classe di comandi andiamo ad implementare
                     Due tipi di protocolli: primo bit 1 tipo negoziazione
                                             primo bit 0 tipo interazione strato di rete
                     LCP: 11 comandi
                          4 comandi di configurazione
                            - Configure-request: propone varie opzioni di comunicazione (es lung payload)
                            - Configure-ACK (ACK implementato nel LCP)
                            - Configure-NAK: alcune cose non vanno bene
                            - Configure-Reject: tutto non va bene, nessuna negoziazione 
                            Es. posso scegliere se il controllo dell'errore può usare 2 o 4 bytes
                                , quanto grande fare il campo protocol
                                , la grandezza del payload default: 1500bytes
                                per evitare gli sprechi si può decidere se eliminare i campi address
                                e control
                          2 di terminazione
                            - terminate-request: chiudiamo il canale
                            - terminate-ACK:
                          2 di rifiuto
                            - Code-reject: codice non riconosciuto
                            - Protocol-reject: non interpreta il campo protocol (magari roba nuova)
                          2 di echo
                            - Echo-request
                            - Echo-reply
                            Servono per misurare la qualità della linea di comunicazione
                          1 di test
                            - Discard-request: non fa nulla, scartato da chi lo riceve
                            primo test della linea: c'è la linea? la scheda funziona?
                            la seconda serve per trovare i loop di rete
        | Payload  | lunghezza variabile
        | Checksum | 2 o 4 byte: error detection ma non recovery 
        ```          
