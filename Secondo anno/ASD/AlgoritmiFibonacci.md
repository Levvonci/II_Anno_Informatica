## ***I numeri di Fibonacci*** 
>***Quanto velocemente si espanderebbe una popolazione di conigli sotto appropriate condizioni?***
>- ***Una coppia di coniglietti genera una nuova coppia***
>- ***La gestazione dura un anno***
>- ***I conigli si riproducono solo dopo il secondo anno***
>- ***I conigli sono immortali***

### ***L'albero dei conigli***
>***La riproduzione dei conigli può essere descritta in un albero:*** 
![[Pasted image 20221006114921.png]]

### ***La regola di espansione***
>- ***Nell'anno n ci sono tutte le coppie dell'anno precedente $Fn-1$***
>- ***Indicando con fn il numero di copie dell'anno n abbaimo la seguente relazione di ricorrenza:***
>$$Fn= \begin{cases}
F_{n-1}+F_{n-2}&se\ \ n\geq3\\
1& se\ \ n=1,2
\end{cases}$$

### ***Come calcoliamo Fn?***
#### ***Approccio Numerico***
>-***Funzione matematica che calcola direttamente i numeri di Fibonacci***
>-***Si può dimostrare che: 
>$$Fn=\frac{1}{\sqrt5}\cdot(\phi^n - \hat{\phi}^n)$$
>Dove:
>$$ \begin{cases}
\phi=\frac {1+\sqrt5}{2} \approx +1.618\\
\phi=\frac {1-\sqrt5}{2} \approx -0.618
\end{cases}$$

### ***Algoritmo Fibonacci1***
>Algoritmo***Fibonacci1***$(intero\ n)\implies intero$
> 1. ***$return \frac{1}{\sqrt5}\cdot(\phi^n - \hat{\phi}^n)$***
#### ***Correttezza?***
>-***Qual è l'accuratezza su $\phi \ e \ \hat{\phi}$ per ottenere un risultato corretto?***
>-***Ad esempio,con 3 cifre decimali:***
>$\phi\approx 1.618 \ e \ \hat{\phi}\approx -0.618$ 


### ***Algoritmo Fibonacci2***
>***Utilizzare direttamente la definizione ricorsiva***
>***$Algoritmo$ Fibonacci2$(intero\ n)\implies intero$***
> 1. ***$if (n\geq 2) then\ return 1$***
> 2. ***$else return$ Fibonacci2$(n-1)$ + Fibonacci2$(n-2)$***

#### ***Tempo di esecuzione***
>- ***Un modello di calcolo rudimentale: ogni linea di codice costa un'unità di tempo***
>- ***Calcoliamo il numero di linee di codice mandate in esecuzione***
>   -Misura indipendente dalla piattaforma utilizzata
>- ***Se n $\le$ 2: una sola riga di codice 
>- Se n = 3: quattro linee di codice, due per la chiamata $fibonacci2(3)$, una per la chiamata $fibonacci2(2)$ e una per la chiamata $fibonacci2(1)$

#### ***Relazione di ricorrenza***
> ***T(n)= # linee di codice eseguite (nel caso peggiore)dall'algoritmo su input n
> In ogni chiamata si eseguono due linee di codice oltre a quelle eseguite nelle chiamate ricorsive 
> $T(n)=2+T(n-1)+T(n-2)$ 
> in generale, il tempo richiesto da un algoritmo ricorsivo è pari al tempo speso all'interno della chiamata più il tempo speso nelle chiamate ricorsive 

#### ***Albero della ricorsione***
>- ***Utile per risolvere la relazione di ricorrenza***
>- ***Nodi corrispondenti alle chiamate ricorsive***
>- ***Figli di un nodo corrispondenti alle sottochiamate***
>![[Pasted image 20221006140343.png]]

#### ***Calcolare $T(n)$***
>***- Etichettando i nodi dell'albero con il numero di linee di codice eseguite nella chiamata corrispondente:***
>  ***- I nodi interni hanno etichetta 2*** 
>  ***- Le foglie hanno etichetta 1***
>***- Per calcolare $T(n)$:***
>  ***-Continuiamo con il numero di foglie***
>  -***Continuiamo il numero di nodi interni***

##### ***Lemma 1***
>***Il numero di foglie dell'albero della ricorsione di $Fibonacci2(n)$ è pari a $F_n$

##### ***Dimostrazione***
>***(Per induzione su n)***

##### ***Lemma 2***
>***Il numero di nodi interni di un albero in cui ogni nodo interno ha due figli è pari al numero di foglie -1***

##### ***Dimostrazione***
>***(Per induzione sul numero di nodi dell'albero $n$)

>***In totale le linee di codice eseguite sono:
>$F_{n}+2 \cdot(F_{n}-1)=3F_{n}-2$

##### ***Osservazioni***
>***$Fibonacci2$ è un algoritmo lento:***
>$T(n) \approx F_n \approx \phi^n$
>***Linee di codice eseguite***
>***$n=45 \ \ T(n)=3\cdot F_{45}-2 = 3\cdot 1.134903.170-2=3.404.709.508$ 
>Possiamo fare meglio? 
>![[Pasted image 20221006144318.png]]
>![[Pasted image 20221006144415.png]]

### ***Algoritmo Fibonacci3***
>***Perchè l'algoritmo $Fibonacci2$ è lento? Perchè continua a ricalcolare ripetutamente la soluzione dello stesso sottoproblema. Perchè non memorizzare allora in un array le soluzioni dei sottoproblemi?***
>
>Algoritmo***Fibonacci3******$(intero \ n )\implies intero$***
> ***|sia Fib un array di n interi|
> |Fib[1]$\leftarrow$Fib[2]$\leftarrow$ 1|***
> 1.$for$ ***i=3 $to$ n $do$***
>          ***|Fib[i]$\leftarrow$Fib[i-l]+Fib[i-2]|***
> 2.$return$ ***Fib[n]

#### ***Calcolo del tempo di esecuzione***
> - ***Linee 1,2 e 5 eseguite una sola volta 
> - Linea 3 eseguita $\leq$ n volte
> - Linea 4 eseguita $\leq$ n volte 
> - $T(n)$: numero di linee di codice mandate in esecuzione da Fibonacci3
> $T(n)\leq n + n + 3 = 2n + 3$ 
> $T(45)\leq 93$
>(38 milione di volte più dell'algoritmo $Fibonacci2$!)
>- L'algoritmo $Fibonacci3$ impiega tempo proporzionale a n invece di esponenziale in n come Fibonacci2
>- Tempo effettivo richiesto da implementazioni in C dei due algoritmi su piattaforme obsolete:
>![[Pasted image 20221006164740.png]]
>

#### ***Occupazione di memoria***
> -***Il tempo di esecuzione non è la sola risorsa di calcolo che ci interessa. Anche la quantità di memoria necessaria può essere cruciale.***
>-***Se abbiamo un algoritmo lento, dovremo solo attendere più a lungo per ottenere il risultato***
>-***Ma se un algoritmo richiede più spazio di quello a disposizione, non otterremo mai la soluzione, indipendentemente da quanto attendiamo!***

### ***Algoritmo Fibonacci4***
>Algoritmo***Fibonacci4***$(intero \ n)\implies intero$
>     ***|a$\leftarrow$b$\leftarrow$ 1|***
>    1. $for$ i=3 $to$ n $do$
>       ***c $\leftarrow$ a+b***
>       ***b $\leftarrow$ a***
>       ***a $\leftarrow$ c***
>    2. $return$ a
>-***Fibonacci3 usa un array di dimensione n prefissata***
>-***In realtà non ci serve mantenere tutti i valori di $F_n$ precedenti, ma solo gli ultimi 
   due, riducendo lo spazio a poche variabili in tutto***

#### ***Algoritmo Fibonacci 5***
>Algoritmo***Fibonacci5***$(intero \ n)\implies intero$
> 
>     $for$ i=1 $to$ n-1 $do$
>     
>     $return$ M [0], [0]
>
>- ***Il tempo di esecuzione è ancora O(n)***

#### ***Cosa si guadagna?***
>- ***Si può calcolare la n-esima potenza elevando al quadrato la ($\lfloor$$\frac {n}{2}\rfloor$)-esima potenza***
>- ***Se n è dispari eseguiamo un'ulteriore moltiplicazione***

#### ***Esempio***
>$3^2=9$            $3^4=9^2=81$            $3^8=81^2=6561$ $\implies$
>$\implies$ ***Si eseguono solo 3 prodotti invece di 7***
>         3 $\cdot$ 3 $\cdot$ 3 $\cdot$ 3 $\cdot$ 3 $\cdot$ 3 $\cdot$ 3 = $3^8$

### ***Algoritmo Fibonacci 6***
>***Algoritmo***Fibonacci6$(intero \ n )\implies intero$
>       
>
