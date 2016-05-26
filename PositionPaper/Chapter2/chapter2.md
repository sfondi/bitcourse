Capitolo 2
==
Blockchain e Bitcoin: cosa sono e quali sono gli elementi che li definiscono
==

## *Consenso distribuito e Proof Of Work*

Il vero grande successo del protocollo **Bitcoin** è quello di aver dato vita ad un sistema elettronico di pagamenti *peer-to-peer*, sicuro e affidabile, che non richiede fiducia in una Autority centrale, ma fondato su un algoritmo di consenso distribuito. Questo traguardo è stato possibile grazie alla **Blockchain**, un registro pubblico, distribuito e inalterabile, contenente la storia di tutte le transazioni.

Un sistema centralizzato sarebbe infatti esposto a diversi rischi. La presenza di un unico agente alla base dell'intero ecosistema comporta una fragilità intrinseca, il cosiddetto *Single Point of Failure*: l'ente centrale ha il potere di alterare o censurare i dati presenti nel registro.

I rischi derivanti da questo accentramento possono essere superati solo attraverso una ridistribuzione del potere dell'Autority. Tuttavia in questo contesto sorge una ulteriore difficoltà: ogni individuo che partecipa alla rete ha la possibilità di scrivere all'interno del registro. Come è possibile garantire che tale registro sia univoco e accettato da tutti? Tale criticità può essere ricondotta a quella formalizzata per la prima volta da Marshall Pease, Robert Shostak e Leslie Lamport nel 1982 e nota con il nome di *"Problema dei Generali Bizantini"*.

Nel loro articolo, [*"The Bizantine Generals Problem"*](http://research.microsoft.com/en-us/um/people/lamport/pubs/byz.pdf), gli autori immaginano una situazione in cui diversi generali di un esercito devono decidere la strategia di attacco potendo comunicare tra di loro solo attraverso dei messaggeri. Tra di essi potrebbero esserci dei traditori. Per la buona riuscita dell'attacco è necessario che i generali si accordino su un univoco piano di azione e che un numero esiguo di traditori non possa alterarne il risultato.

L'analogia con la rete *peer-to-peer* utilizzata nel protocollo Bitcoin risiede proprio nella necessità di trovare un consenso univoco sulle transazioni da scrivere nella Blockchain, impedendo ai nodi che agiscono in modo scorretto di alterare la storia delle transazioni.

La soluzione proposta da Satoshi Nakamoto è basata sul fornire un incentivo di natura economica.


## *Mining*
