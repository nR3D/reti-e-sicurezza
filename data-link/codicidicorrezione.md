## Codici di correzione degli errori
---------------------------------

### Matrici di Hamming

La parità di Hamming può essere rappresentata con le matrici
es. Matrice di trasformazione dei codici (7,4)

Significato della riga:

|-> a 1 bit dati selezionato          
| +-+-+ |->  a 1 i bit che lo proteggono
1 0 0 0 | 0 1 1 
0 1 0 0 | 1 0 1 
0 0 1 0 | 1 1 0
0 0 0 1 | 1 1 1

Il prodotto righe per colonne tra il vettore dati lungo 4 bit e la matrice è un vettore contenente gli stessi dati con concatenati i 3 bit di parità. Si passa da uno spazio a 4 dimensioni a uno a 7.
La matrice è composta da due componenti distinte: 
una matrice identità 4x4 e una le cui colonne sono associate a un bit di parità che indica quali dati protegge. In questo esempio la prima colonna calcola il primo bit di parità ignorando il primo bit dati

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
0 0 1 
0 1 0 => bit di controllo
1 0 0
. . . .   
1 1 1
0 1 1 => dati controllati 
1 0 1
1 1 0 <br>
Se un elemento del vettore risultante è 1 vuol dire che c'è stato un errore nella trasmissione.

- **Error correction lineare** Calcolare il valore giusto più vicino è lento, ma i codici lineari possono fare error recovery ricalcolando i bit di controllo e confrontandoli con ciò che si è ricevuto.

### Codici ibridi

**Hamming (8,4)** si aggiunge un'altro parity bit calcolato sui 4 di dati (rompe la simmetria incaricando un bit di proteggerne 4 mentre gli altri ne proteggono 3). Alla matrice si accoda una colonna in più di soli 1, il peso incrementa e quindi incrementa anche la potenza di controllo ma non quella di correzione (8,4,4), Ha un data rate del 50%

**Hamming(11,7)** Ancora meno simmetrico, quindi certi bit dati sono meno protetti di altri, ma comunque si prova a mantenere il più alto grado di simmetria possibile. La matrice ha come peso minimo 5, riesce a trovare 4 errori e correggerne 2, ha un datarate del 63.7%

### Generalizzazione

L'idea di Hamming generalizza sia i codici parity bit che repetition, e quindi sono tutti codici lineari

es. parity bit su 3 bit
(a b c) => (a b c P)
si può generare con una matrice

1 0 0 | 1
0 1 0 | 1
0 0 1 | 1 

la colonna rappresenta 1 bit che si prende carico di tutto.
Il peso minimo è due, quindi è un codice Hamming (4,3,2)

es. repetition su 3 bit
(a) => (a a a)
matrice:

1 | 1 1

quindi è un codice Hamming (3,1,3)

### Problemi pratici:

Nella realtà le interferenze si presentano sotto forma di burst: gli errori accadono su più bit consecutivi.
È un problema mostruoso per l'error correcting che può funzionare solo su pochi bit per messaggio.
Per ovviare ai burst si usa il metodo della matrice invertita (interleaving): dividiamo il blocco dati in blocchetti con bit di parità  propri e li impiliamo. Trasmettendo i messaggi per colonne (prima il primo bit di tutti i pacchetti poi il secondo, ecc.) distribuiamo un burst su pochi bit per ogni blocchetto, rendendolo correggibile dai codici di Hamming, un piccolo prezzo da pagare è un buffer dati.
 

Storielle di Marc:
Hamming viveva nel periodo delle schede perforate, si chiede c'è un modo di usare poche schede e avere una correzione dell'errore? yess l'ha inventata lui.
