Capitolo 2
==
Blockchain e Bitcoin: cosa sono e quali sono gli elementi che li definiscono
==

## *Chiave Pubblica, Chiave Privata e Firma Digitale*

In Bitcoin viene usata la crittografia a chiave pubblica per la generazione di una coppia di chiavi formata da una chiave pubblica e una privata. La chiave pubblica viene utilizzata per ricevere fondi e può essere paragonata al numero di un conto in banca; a chiave privata serve per firmare le transazioni e spendere i fondi e corrisponde analogicamente al PIN che permette di controllare il conto.

## *Transazioni*

I bitcoin esistono in quanto presenti sulla Blockchain, un database distribuito, sul quale non sono presenti i conti e i saldi di chi li possiede, ma solamente le transazioni che li  spostano da un proprietario ad un altro.

Ogni transazione è composta da una lista di input (TxIn) e di output (TxOut). Ogni output è composto da un importo e dall’“indirizzo” al quale è destinato; solamente chi può accedere a quell’indirizzo è in grado di  disporre dei bitcoin ad esso corrispondenti. Ciascun input, invece, contiene un riferimento all’output precedente (in questo modo le transazioni sono tra loro legate ed è possibile ripercorre la storia di ciascuna moneta) e la firma digitale che autorizza la spesa dei relativi TxOut; la firma deve essere associata all’“indirizzo” al quale sono stati inviati i bitcoin. 

Una transazione raggruppa più TxIn e TxOut con lo scopo di redistribuire i fondi dei primi verso i secondi. Gli input si riferiscono sempre ad output precedenti, i quali non devono essere già stati spesi precedentemente perché la transazione sia valida. Si intuisce inoltre facilmente come sia necessario che la somma degli importi dei TxIn sia maggiore o uguale alla somma dei TxOut. La differenza tra i due importi rappresenta una fee che verrà riscossa da chi per primo riuscirà a verificare la validità della transazione.

Un output deve essere speso completamente; se l’importo degli output è maggiore dell’importo da spendere, viene generato un change, ovvero un output aggiuntivo che viene indirizzato a chi sta spendendo i TxOut della transazione. Concretamente si tratta di qualcosa di analogo al resto che si riceve in un tradizionale acquisto con gli euro in moneta o banconota; l’“indirizzo” utilizzato non coincide con nessuno degli indirizzi da cui provengono gli output in modo da garantire una maggiore privacy.

(immagine, tipo Figura 6.1 a pagina 100 di Pedro Franco)

Il software Bitcoin mantiene l’insieme di tutti gli output non ancora spesi (UTXO), in modo che sia facile verificare la validità di una transazione, in quanto tale struttura occupa molto meno spazio dell’intera blockchain e può essere gestita dalla RAM. **Si può quindi affermare che i bitcoin in circolazione siano gli output non spesi delle transazioni presenti sulla blockcahin**.

Ogni TxOut contiene un puzzle matematico che deve essere risolto per poter spendere l’importo in bitcoin associato, pertanto ciascun TxIn deve contenere la soluzione al puzzle dell’output a cui si riferisce, ovvero la firma associata all’”indirizzo” al quale sono stati inviati i bitcoin.

## *Consenso distribuito e Proof Of Work*

Schema:
* limiti del sistema centralizzato

* sistema decentralizzato

* problema dei generali bizantini

* Blockchain & Proof of Work

Il vero grande successo del protocollo **Bitcoin** è quello di aver dato vita ad un sistema elettronico di pagamenti sicuro che non richiede fiducia in una Autority centrale, ma fondato su un algoritmo di consenso distribuito. Questo traguardo è stato possibile grazie alla **Blockchain**, un registro pubblico, distribuito e inalterabile contenente la storia di tutte le transazioni.

Un sistema centralizzato è esposto infatti a diversi rischi. La presenza di un unico agente alla base dell'intero ecosistema comporta una fragilità intrinseca, il cosiddetto *Single Point of Failure*. L'ente centrale ha il potere di alterare o censurare, anche in buona fede, i dati.

Il superamento di questi limiti può essere raggiunto solo attraverso una ridistribuzione del potere dell'Autority. Tuttavia in questo contesto sorge il problema di come raggiungere il consenso (un'informazione condivisa da tutti). Tale problema, irrisolto fino all'avvento di Bitcoin, è noto come il problema dei Generali Bizzantini.

 Per poter andare oltre a questi limiti è necessario muoversieliminare l'Autority centrale e muoversi verso un sistema

Un registro pubblico decentralizzato consente di superare questi limiti, mettendo  attraverso il consenso distribuito.


consente di ris risulta invulnerabile alla censconsente transazioni anche in assenza di fiducia tra le parti senza un garante esterno.

## *Mining*
