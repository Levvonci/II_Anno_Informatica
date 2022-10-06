### ***I numeri di Fibonacci*** 
>***Quanto velocemente si espanderebbe una popolazione di conigli sotto appropriate condizioni?***
>- ***Una coppia di coniglietti genera una nuova coppia***
>- ***La gestazione dura un anno***
>- ***I conigli si riproducono solo dopo il secondo anno***
>- ***I conigli sono immortali***

### ***La regola di espansione***
>- ***Nell'anno n ci sono tutte le coppie dell'anno precedente fn-1***
>- ***Indicando con fn il numero di copie dell'anno n abbaimo la seguente relazione di ricorrenza:***



### ***Come calcoliamo Fn?***
#### ***Approccio Numerico***
>***Funzione matematica che clcola direttamente i numeri di Fibonacci***
>Algoritmo Fibonacci1(intero n) $\implies$ intero
>	return 1/sqrt 5 (......)
>Rivedere slide pag 9


### ***Algoritmo Fibonacci2***
>***Utilizzare direttamente la definizione ricorsiva***
>***algoritmoFibonacci2(intero n)$\implies$ intero***
>		***if(n$\geq$ 2)then return 1***
>		***else return Fibonacci2(n-1) + Fibonacci2(n-2)***

#### ***Tempo di esecuzione***
>- ***Un modello di calcolo rudimentale: ogni linea di codice costa un'unità di tempo
>- ***Calcoliamo il numero di linee di codice mandate in esecuzione 
>	-

#### ***Relazione di ricorrenza 
> T(n)= #linee di codice eseguite
> In ogni chiamata si eseguono due linee di codice oltre a quelle eseguite nelle chiamate ricorsive 
> T(n)=2+T(n-1)+T(n-2) 

#### ***Albero della ricorsione***
>- ***Utile per risolvere la relazione di ricorrenza***
>- ***Nodi corrispondenti alle chiamate ricorsive***
>- ***Figli di un nodo corrispondenti alle sottochiamate***
>