Capitolo 2
==
Blockchain e Bitcoin: cosa sono e quali sono gli elementi che li definiscono
==

## *Chiave Pubblica, Chiave Privata e Firma Digitale*

In Bitcoin viene usata la crittografia a chiave pubblica per la generazione di una coppia di chiavi composta da una chiave pubblica e una privata. La chiave pubblica viene utilizzata per ricevere fondi e può essere paragonata al numero di un conto in banca; la chiave privata serve per firmare le transazioni e spendere i fondi rappresentando l’analogo del PIN che permette di controllare il conto.

La chiave privata consiste in un numero particolarmente elevato che deve essere assolutamente calcolato in maniera **casuale**. A partire da esso, utilizzando una funzione crittografica non invertibile, ovvero la moltiplicazione su curve ellittiche, viene generata la chiave pubblica. Da quest’ultima, utilizzando un’altra funzione crittografica non invertibile, una funzione di hash, viene generato un indirizzo bitcoin. La conoscenza di una chiave privata è alla base del controllo su tutti i fondi associati al corrispondente indirizzo, per tale ragione deve essere calcolata in maniera del tutto random e mantenuta segreta senza il rischio di perderla. La chiave privata è utilizzata per la creazione delle firme necessarie per dimostrare la proprietà dei bitcoin che si vuole spendere.
Il motivo per cui viene utilizzata la crittografia asimmetrica (chiave pubblica/privata) risiede nel fatto che rende possibile per ciascuno verificare la firma su ogni transazione, garantendo che solo chi possiede le chiavi private possa fornire delle firme valide.

Come già accennato, il punto fondamentale nella creazione delle chiavi è trovare una fonte sicura di entropia o casualità; di fatto creare una chiave privata equivale essenzialmente a prendere un numero tra 1 e 2256, pertanto il modo in assoluto più sicuro di farlo sarebbe quello di tirare una moneta 256 volte, ottenendo la rappresentazione binaria della chiave stessa. La dimensione dello spazio delle chiavi private bitcoin, 2256, è un numero incredibilmente grande, circa 1077 in notazione decimale, paragonabile al numero degli atomi dell’universo visibile (stimati essere nell’ordine dei 1080).

La chiave pubblica è calcolata a partire dalla chiave privata utilizzando la moltiplicazione su curve ellittiche, che è irreversibile: K = k * G, dove k è la chiave privata e, G è una costante chiamata punto generatore e K è la chiave pubblica risultante. L’operazione inversa, conosciuta come problema dei logaritmi finiti (calcolare k conoscendo K), è difficile tanto quanto provare tutti i possibili valori di k. Questo strumento matematico è la base per firme digitali sicure e non soggette a contraffazione che provino la proprietà dei fondi in bitcoin.

Un indirizzo bitcoin è una stringa di numeri e lettere che può essere condivisa con chiunque voglia inviarci del denaro; è quanto comunemente appare in una transazione come destinatario dei fondi. Esso viene ricavato dalla chiave pubblica attraverso un “algoritmo di hash” non invertibile che produce un’impronta digitale o “hash” di un input di qualsiasi dimensione. **Quindi un indirizzo bitcoin non coincide con una chiave pubblica**.

Lo scopo delle firme digitali è simile a quello delle firme scritte a mano: garantiscono che un messaggio sia stato generato da chi lo firma, non possono essere alterate e chi le utilizza non può negare di averlo fatto. Il protocollo di firma digitale si compone di due parti, un algoritmo a chiave pubblica, che fornisce l’algoritmo matematico asimmetrico sottostante, e uno schema di firma digitale che propone un modo di  utilizzare questo algoritmo asimmetrico per arrivare ad una firma digitale funzionante.
Come visto poco sopra, vi è una chiave privata corrispondente a ciascuna chiave pubblica e di conseguenza a ciascun indirizzo bitcoin. Le chiavi pubbliche possono essere interpretate come numeri di conti bancari, mentre le chiavi private come le firme che possono sbloccare i conti. Per spendere i bitcoin, la transazione che autorizza la spesa deve essere firmata con la chiave privata.
Un punto tecnico in merito alle firme digitali è che il messaggio potrebbe essere di lunghezza arbitraria e questo può essere un problema poiché gli algoritmi implementati dalla crittografia a chiave pubblica sono lenti. La soluzione è quella di prendere l’hash del messaggio e di firmare questo invece del messaggio originale. L’output di una funzione di hash è sempre della stessa (più corta) lunghezza, indipendentemente dalla grandezza dell’input.
Per firmare un messaggio deve essere generato un nonce, ovvero un numero random effimero usato una sola volta per ciascuna chiave privata. E’ essenziale che questo nonce non sia più riutilizzato, altrimenti è come rendere nota la propria chiave privata e quindi buttare via i propri fondi bitcoin.

## *Transazioni*

I bitcoin esistono in quanto presenti sulla Blockchain, un database distribuito, sul quale non sono presenti i conti e i saldi di chi li possiede, ma solamente le transazioni che li spostano da un proprietario ad un altro.

Ogni transazione è composta da una lista di input (TxIn) e di output (TxOut). Ogni output è composto da un importo e dall’“indirizzo” al quale è destinato; solamente chi può accedere a quell’indirizzo è in grado di  disporre dei bitcoin ad esso corrispondenti. Ciascun input, invece, contiene un riferimento all’output precedente (in questo modo le transazioni sono tra loro legate ed è possibile ripercorre la storia di ciascuna moneta) e la firma digitale che autorizza la spesa dei relativi TxOut; la firma deve essere associata all’“indirizzo” al quale sono stati inviati i bitcoin.

Una transazione raggruppa più TxIn e TxOut con lo scopo di redistribuire i fondi dei primi verso i secondi. Gli input si riferiscono sempre ad output precedenti, i quali non devono essere già stati spesi precedentemente perché la transazione sia valida. Si intuisce inoltre facilmente come sia necessario che la somma degli importi dei TxIn sia maggiore o uguale alla somma dei TxOut. La differenza tra i due importi rappresenta una fee che verrà riscossa da chi per primo riuscirà a verificare la validità della transazione.

Un output deve essere speso completamente; se l’importo degli output è maggiore dell’importo da spendere, viene generato un change, ovvero un output aggiuntivo che viene indirizzato a chi sta spendendo i TxOut della transazione. Concretamente si tratta di qualcosa di analogo al resto che si riceve in un tradizionale acquisto con gli euro in moneta o banconota; l’“indirizzo” utilizzato non coincide con nessuno degli indirizzi da cui provengono gli output in modo da garantire una maggiore privacy.

(immagine, tipo Figura 6.1 a pagina 100 di Pedro Franco)

Il software Bitcoin mantiene l’insieme di tutti gli output non ancora spesi (UTXO), in modo che sia facile verificare la validità di una transazione, in quanto tale struttura occupa molto meno spazio dell’intera blockchain e può essere gestita dalla RAM. **Si può quindi affermare che i bitcoin in circolazione siano gli output non spesi delle transazioni presenti sulla blockcahin**.

Ogni TxOut contiene un puzzle matematico che deve essere risolto per poter spendere l’importo in bitcoin associato, pertanto ciascun TxIn deve contenere la soluzione al puzzle dell’output a cui si riferisce, ovvero la firma associata all’”indirizzo” al quale sono stati inviati i bitcoin.

## *Consenso distribuito e Proof Of Work*

Il vero grande successo del protocollo **Bitcoin** è quello di aver dato vita ad un sistema elettronico di pagamenti *peer-to-peer*, sicuro e affidabile, che non richiede fiducia in una Autority centrale, ma fondato su un algoritmo di consenso distribuito. Questo traguardo è stato possibile grazie alla **Blockchain**, un registro pubblico, distribuito e inalterabile, contenente la storia di tutte le transazioni.

Un sistema centralizzato sarebbe infatti esposto a diversi rischi. La presenza di un unico agente alla base dell'intero ecosistema comporta una fragilità intrinseca, il cosiddetto *Single Point of Failure*: l'ente centrale ha il potere di alterare o censurare i dati presenti nel registro.

I rischi derivanti da questo accentramento possono essere superati solo attraverso una ridistribuzione del potere dell'Autority. Tuttavia in questo contesto sorge una ulteriore difficoltà: ogni individuo che partecipa alla rete ha la possibilità di scrivere all'interno del registro. Come è possibile garantire che tale registro sia univoco e accettato da tutti? Tale criticità può essere ricondotta a quella formalizzata per la prima volta da Marshall Pease, Robert Shostak e Leslie Lamport nel 1982 e nota con il nome di *"Problema dei Generali Bizantini"*.

Nel loro articolo, [*"The Bizantine Generals Problem"*](http://research.microsoft.com/en-us/um/people/lamport/pubs/byz.pdf), gli autori immaginano una situazione in cui diversi generali di un esercito devono decidere la strategia di attacco potendo comunicare tra di loro solo attraverso dei messaggeri. Tra di essi potrebbero esserci dei traditori. Per la buona riuscita dell'attacco è necessario che i generali si accordino su un univoco piano di azione e che un numero esiguo di traditori non possa alterarne il risultato.

L'analogia con la rete *peer-to-peer* utilizzata nel protocollo Bitcoin risiede proprio nella necessità di trovare un consenso univoco sulle transazioni da scrivere nella Blockchain, impedendo ai nodi che agiscono in modo scorretto di alterare la storia delle transazioni.

La soluzione proposta da Satoshi Nakamoto è basata sul fornire un incentivo di natura economica.

## *Mining*
