## Codici di correzione degli errori
---------------------------------

### Matrici di Hamming

La parità di Hamming può essere rappresentata con le matrici
es. Matrice di trasformazione dei codici (7,4)<br>
Significato della riga:<br>
|-> a 1 bit dati selezionato<br>         
| +-+-+ |->  a 1 i bit che lo proteggono<br>
1 0 0 0 | 0 1 1<br>
0 1 0 0 | 1 0 1<br>
0 0 1 0 | 1 1 0<br>
0 0 0 1 | 1 1 1<br>

Il prodotto righe per colonne tra il vettore dati lungo 4 bit e la matrice è un vettore contenente gli stessi dati con concatenati i 3 bit di parità. Si passa da uno spazio a 4 dimensioni a uno a 7.
La matrice è composta da due componenti distinte: 
una matrice identità 4x4 e una le cui colonne sono associate a un bit di parità che indica quali dati protegge. In questo esempio la prima colonna calcola il primo bit di parità ignorando il primo bit dati.<br>

*Def peso: quanti 1 contiene una stringa di bit*


### Proprietà:

- **Sono Lineari:**
Grazie all'uso delle matrici i codici possono essere elaborati solo con moltiplicazioni e addizioni.

- **Distanza minima:**
Un codice di Hamming (X,Y) e che ha distanza minima di Hamming Z viene anche detto (X,Y,Z). Con Y = lunghezza dei dati, X = lunghezza messaggio finale. es. (7,4) => (7,4,3)
- **Teorema del peso minimo:** il peso minimo dei vettori riga della matrice di Hamming (X,Y) è la distanza minima di Hamming, d. <br>
errore detecting: d-1 bit sbagliati
errore correction: (d-1)/2 bit sbagliati<br>
Hamming vs repetition codes:
con R3 banda 1/3 (33%)
con (7,4)  4/7 di banda (57%)

- **Check lineare:** per controllare la correttezza si moltiplica il messaggio ricevuto per una matrice di parità. Può essere implementato in hardware rendendolo ancora più veloce. <br>
0 0 1<br>
0 1 0 => bit di controllo<br>
1 0 0<br>
. . . .<br>   
1 1 1<br>
0 1 1 => dati controllati<br> 
1 0 1<br>
1 1 0 <br>
Se un elemento del vettore risultante è 1 vuol dire che c'è stato un errore nella trasmissione.

- **Error correction lineare** Calcolare il valore giusto più vicino è lento, ma i codici lineari possono fare error recovery ricalcolando i bit di controllo e confrontandoli con ciò che si è ricevuto.

### Codici ibridi

**Hamming (8,4)** si aggiunge un'altro parity bit calcolato sui 4 di dati (rompe la simmetria incaricando un bit di proteggerne 4 mentre gli altri ne proteggono 3). Alla matrice si accoda una colonna in più di soli 1, il peso incrementa e quindi incrementa anche la potenza di controllo ma non quella di correzione (8,4,4), Ha un data rate del 50%

**Hamming(11,7)** Ancora meno simmetrico, quindi certi bit dati sono meno protetti di altri, ma comunque si prova a mantenere il più alto grado di simmetria possibile. La matrice ha come peso minimo 5, riesce a trovare 4 errori e correggerne 2, ha un datarate del 63.7%

### Generalizzazione

L'idea di Hamming generalizza sia i codici parity bit che repetition, e quindi sono tutti codici lineari
<br>
es. parity bit su 3 bit<br>
(a b c) => (a b c P)<br>
si può generare con una matrice:<br>

1 0 0 | 1<br>
0 1 0 | 1<br>
0 0 1 | 1<br> 

la colonna rappresenta 1 bit che si prende carico di tutto.<br>
Il peso minimo è due, quindi è un codice Hamming (4,3,2)<br>

es. repetition su 3 bit<br>
(a) => (a a a)<br>
matrice:<br>
1 | 1 1<br>
quindi è un codice Hamming (3,1,3)

### Problemi pratici:

Nella realtà le interferenze si presentano sotto forma di burst: gli errori accadono su più bit consecutivi.
È un problema mostruoso per l'error correcting che può funzionare solo su pochi bit per messaggio.
Per ovviare ai burst si usa il metodo della matrice invertita (interleaving): dividiamo il blocco dati in blocchetti con bit di parità  propri e li impiliamo. Trasmettendo i messaggi per colonne (prima il primo bit di tutti i pacchetti poi il secondo, ecc.) distribuiamo un burst su pochi bit per ogni blocchetto, rendendolo correggibile dai codici di Hamming, un piccolo prezzo da pagare è un buffer dati.

#DA TRADURRE e integrare
-----------

##Codici di livello 2:
----------------------
I codici di livello due non prendono piu` come unita` il singolo bit ma gruppi, questo permette di correggere errori molto piu` grandi.
Ad esempio  i cd supportano un burst fino a 4000bit senza dover usare usare il trucco della matrice invertita. In oltre hanno una feature aggiuntiva: 
riuscire a correggere le erasures, ovvero le mancanze di informazione. Sono piu` facili da correggere di un errore perche` individui la posizione subito: non valgono ne 0 ne 1;
I codici di secondo livello Reed-Salomon RS(x,y) correggono fino a x-y erasures, il doppio degli errori.
Oltretutto riescono a correggere contemporaneamente errori ed erasures basta che sia verificata la disequazione:
2nErrori + nErasures < X-Y
Sono usati nei CD,DVD,ADSL,BLU RAY, WiMax e nella TV Digitale si usa RS(204,188), datarate 92% e 16bit di correzione.
Nell'ambiente aero-spaziale si utilizza il codice di Hadamard che interpreta il rumore come una delle componenti della comunicazione CDMA e lo ignora;

### Limiti: Error Rate vs Data Rate

- Repetition b: 
Aumentando n ottengo un error rate molto basso ma altrettando basso diventa il datarate (1/n)

- codici Hamming:
Perdono meno banda dei Rn ma la decrescita è simile, aggiungendo bit di controllo il data rate cala a picco.

Shannon dimostrò che per l'error-rate che tende a zero il limite massimo del datarate non tende a zero ma a un numero maggiore di zero:
e` possibile sviluppare un codice che sta leggeremente sopra il 50% della banda.
La dimostrazione diche che dato un certo tasso d'errore x si può arrivare a un datarate massimo che è pari all'entropia del canale usato.
es dischi con tasso di errore 0.1 vogliamo un tasso di errore 10^-15, usando le tecnologie classiche in stile Hamming servono 60 dischi, Shannon dimostra che ne bastano due.

Esistondo dei codici che si avvicinano molto al limite come LDPC(low density parity check) usato da tv Digitale e wimax
Faccio il controllo di parità sul messaggio,  e metto in comunicazione i bit di parità con un grafo con cui possono scambiarsi informazione, e` sempre un codice lineare: basta una matrice per fare il check ma il decoding dei dati è NP-completo, ovvero ha alta complessità computazionale.


####CRC: codici a ridondanza ciclica
Sono basati sull'arimtetica polinomiale in modulo 2 e in grado di rilevare gli errori ma non di correggerli.
Possiamo vedere un numero binario come i coefficenti di un polinomio in GF(2)[] (spazio dei polinomi in modulo 2)
Sommare in modulo 2 è come fare lo xor, in più addizione e sottrazione  sono la stessa cosa.
- Encoding:
I bit di parità sono dati dal resto della divisione R(x) tra i polinomi messaggio M(x) e generatore detto G(x)
Il messaggio T(x) è M(x) concatenato a R(x). Scegliamo un polinomio G(x) qualunque, Se deg(G(x))>deg(M(x)) allora R(x) = M(x) e T(x) sarebbe M(x) due volte di fila, che è equivalente al  repetition 2.
Per risolvere questo problema prima di dividere moltiplichiamo M(x) per x^(deg(G(x)), che equivale a shiftarlo a sinistra di deg(G(x)), così il resto della divisione con G(X) rappresenterà sempre un informazione migliore di Repetition 2. N.B. M(x) è trasmesso non shiftato
- Decoding: 
Banale, basta togliere i bit di parità facendo lo shift a destra di deg(G(X)).
- Error Detection:
Il messaggio ricevuto T(x) può essere visto come x^deg(G(x)) \* M(x) + R(x)
ma siccome in  GF(2)[] somma e sottrazione sono la stessa cosa allora il messaggio x^deg(G(x)) \* M(x) - R(x),
sottraendo il resto ottengo un multiplo di G(X) e quindi se faccio la divisione tra messaggio ricevuto e G(x) il resto dovrà essere zero.

Qual'è la potenza di questo metodo:
Un errore sono dei bit flippati, in GF(2)[] possiamo interpretarlo come un polinomio E(x) e sommato al nostro messaggio (T(x)). Quindi ciò che arriva al ricevente è T(x) + E(x) allora il calcolo dell'errore diventa (T(x) + E(x)) mod G(x), sappiamo che T(x) mod G(x) = 0 e quindi (T(x) + E(x))mod G(x) == E(x)mod G(x) quindi l'errore non viene identificato se e solo se E(x) è divisibile per G(x).
L'idea è quella di scegliere un polinomio generatore che minimizza le possibilità di aveare un falso positivo.
- Singolo errore: E(x) = x^i 
Se G(x) ha due o più membri allora E(x) non potrà mai essere suo multiplo e il resto non sarà zero.

- Doppio errore: E(x) = x^i + x^j = x^j \* (x^(i-j) + 1)
Se G(x) non è divisibile per questi due fattori allora individuerò tutti gli errori.

Prendo un G(x) con (x+1) come fattore:

G(x) = (x+1) * tot
E(x) = G(x) * tot 2 <- caso in cui si perde
     = (x+1) * tot * tot2

E(1) = (1+1) * tot(1) * tot2(1) => 0
=> vince in tutti i casi in cui c'è un numero dispari di 1

- I burst error: E(x)= x^i(x^j+x^j-1+ ...+x+1)

se deg G(x) > j li becco perchè non il resto non potra mai essere zero 

in generale  +1 è una buona scelta
oltre possiamo moltiplicare polinomi con certe proprietà per combinarle

oppure scegliere polinomi irriducibili "primi" 

la sua potenza aumenta in maniera esponenziale rispetto al grado
non becchiamo il burst di lunghezza più lunga di j con probabilià di 1/2^deg(G(x)), La probablitaà che i bit del burst siano uguali a G(X)


-----------------------------------------------

Storielle di Marc:
Hamming viveva nel periodo delle schede perforate, si chiede c'è un modo di usare poche schede e avere una correzione dell'errore? yess l'ha inventata lui.
