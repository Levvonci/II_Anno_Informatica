### *Macchina di Turing*
>![[Pasted image 20221011104706.png]]
>- ***Struttura di basso livello, troppo differente ai calcolatori reali***
>- ***Utile per la calcolabilità ma meno utile per l'efficienza***

#### *Modello più realistico*
>***Macchina a registri (RAM)***
>  - ***Un programma finito***
>  - ***Un nastro in ingresso ed uno in uscita***
>  - ***Memoria strutturata come un array***
> 	 - ***Ogni cella può contenere un qualunque valore intero/reale***
>***La ram è un'astrazione dell'architettura di Neumann***

### *Macchina a registri*
>![[Pasted image 20221011105815.png]]
>***Pc : Program Counter, prossima istruzione da eseguire***
>***ACC : Mantiene operandi le istruzioni correnti***

### *Modello di calcolo*
>- ***L'analisi della complessità di un algoritmo è basata sul concetto di passo elementare***
>- ***Passi elementari su RAM***
>  - ***Istruzione ingresso/uscita***
>  - ***Opeazione aritmetico/logica***
>  - ***Accesso/modifica del contenuto della memoria*** 

#### *Criteri di costo: quanto costa*
>***Criterio di costo uniforme***
>  - ***Tutte le operazioni hanno lo stesso costo***
>  - ***Complessità temporale misurata come numero di passi elementari eseguiti***
>***Criterio di costo logaritmico***
>  - ***Il costo dell'operazione dipende dalla dimensione degli operandi***
>  - ***Un'operazione su un operando X ha costo log x***
>  - ***È un criterio di costo che modella meglio la complessità di algoritmi “numerici”***
>         
>         ***Generalmente si usa costo uniforme*** 

### *Caso peggiore, migliore e medio*
>- ***Misurazione di tempo su un algoritmo in funzione della dimensione n delle istanze***
>- ***Istanze diverse, a parità di dimensione potrebbero però richiedere tempo diverso***
>- ***Distinguiamo quindi ulteriormente tra analisi nel caso peggiore, migliore e medio

#### *Caso peggiore*
>- ***Sia tempo (i) il tempo di esecuzione di un algorimto sull'istanza i***
>$T_{worst} (n) = max_{istanze \ i\ \ di \ dimensione \ n} \ {tempo(i)}$
>- ***Intuitivamente, $T_{worst}(n)$ è il tempo di esecuzione sulle istanze di ingresso che comportano più lavoro per l'algoritmo***
>- ***Rappresenta una garanzia sul tempo di esecuzione di ogni istanza***

#### *Caso migliore*
>- ***Sia tempo (i) il tempo di esecuzione di un algoritmo sull'istanza i***
>$T_{best}(n) = min_{istanze \ i \ di \ dimensione \ n} \ {tempo (i)}$
>- ***Intuitivamente, $T_{best} \ (n)$ è il tempo di esecuzione sulle istanze di ingresso che comportano meno lavoro per l'algoritmo***
>-***Significa davvero qualcosa?***

#### *Caso medio*
>-***Sia $P(i)$ la probabilità di occorrenza dell'istanza $i$***
>$T_{avg} \ (n) = \sum_istanze \ i \ di \ dimensione \ n \ {P(i) \ tempo (i)}$
>- ***Intuitivamente, $T_{avg}(n)$ è il tempo di esecuzione nel caso medio, ovvero sulle istanze di ingresso "tipiche" per il problema***
>- ***Come faccio a conoscere la distribuzione di probbailità sulle istanze?***
>- ***Semplice : (di solito) non posso conoscerla*** $\implies$ ***Assunzione***
>-***Spesso è difficile fare assunzioni realistiche***

### *Notazione Asintotica*
#### *Intuizioni*
>- ***Complessità di un algoritmo espressa con una funzione T(n)
>- T(n): # passi elementari eseguiti su una RAM nel caso peggiore su un'istanza di dimensione n***
>- ***Idea: Descrivere T(n) in modo qualitativo. Ovvero perdere la precisione ma guadagnare in semplicità***

#### ***T(n): # passi elementari eseguiti su una RAM nel caso peggiore su un'istanza di dimensione n***
>***Esempio***
>$$T(n)=\begin{cases} 71n^2+100\lfloor \frac{n}{4} \rfloor + 7 & se \ n \ è \ pari \\
\\
70n^2+150\lfloor \frac{n+1}{4} \rfloor + 5& se \ n \ è \ dispari 
\end{cases} $$
***Scriveremo: T(n)= $\Theta (n^2)$
Questo vuol dire che T(n) è proporzionale  a  $n^2$
Cioè ignoro:***
-***Costanti moltiplicative***
-***Termini di ordine inferiore (che crescono più lentamente)***

#### ***Una vecchia tabella: numero asintotico di pesate***
***Assunzione: ogni pesata richiede un minuto***
>![[Pasted image 20221011122317.png]]

#### *Dalla bilancia al computer*
>***Tempi di esecuzione di differenti algorimi per istanze
di dimensione crescente su un processore che sa eseguire un milione di istruzioni di alto livello al secondo.  
L’indicazione very long indica che il tempo di calcolo supera 1025 anni.***
>![[Pasted image 20221011122837.png]]

### *Notazione Asintotica $\mathcal {O}$*
>$f(n) = \mathcal {O} (g(n))$ ***se $\exists$ due costanti $C \geq 0 \ e \ n_{0} \geq 0$ t.c $0 \leq f(n) \leq c \cdot g(n)$***
>![[Pasted image 20221011124559.png]]
>***Esempi:***
>***Sia $f(n) = 2n^2 + 3n$, allora 
>  -$f(n) = \mathcal {O}(n^3)$            $(c=1, n_{0}=3)$ 
>  -$f(n) = \mathcal {O} (n^2)$           $(c = 3, n_{0} = 3)$ 
>  -$f(n) \ne \mathcal {O} (n)$ 

>$\mathcal {O}(g(n))={f(n)} \ | \ \exists \ c \geq 0 \ e \ n_{0} \geq 0$ ***t.c*** $0 \leq f(n) \leq c \cdot g(n) \ \forall \ n \geq n_0$
>-***La scrittura:***
>      ***$2n^2+4= \mathcal {O}(n^3)$
>- è un abuso di notazione per:
>      $2n^2+4 \in \mathcal {O}(n^3)$
>![[Pasted image 20221011172433.png]]

#### *Notazione Asintotica $\Omega$*
>$f(n)= \Omega (g(n))$ ***se $\exists$ due costanti $c>0$ e $n_0\geq 0$ t.c $f(n) \leq c\cdot g(n) \geq 0$ per ogni $n \geq n_0$***
>![[Pasted image 20221011173211.png]]
>***Esempi:***
>-$f(n) = \Omega (n)$                $(c=1, n_0=2)$
>-$f(n)= \Omega (n^2)$               $(c=1, n_0=3)$
>-$f(n) \ne \Omega (n^3)$

>$\Omega (g(n))={f(n)} \ | \ \exists \ c \geq 0 \ e \ n_{0} \geq 0$ ***t.c*** $0 \leq c \cdot g(n) \leq f(n) \ \forall \ n \geq n_0$
>-***La scrittura:***
>      $2n^2+4 = \Omega (n)$
>-***è un abuso di notazione per:***
>      $2n^2 + 4 \in \Omega (n)$
>![[Pasted image 20221011175145.png]]

#### *Notazione Asintotica $\Theta$*
>	$f(n) = \Omega(g(n))$ se $\exists$ ***tre costanti*** $c1, c2 > 0$ e $n_0 \geq 0$ t.c $c1 \cdot g(n) \geq f(n) \geq c2 \cdot g(n)$ $\forall$ $n\geq n_0$
>![[Pasted image 20221011175839.png]]
>***Esempi:
>Sia $f(n) = 2n^2 - 3n$, allora***
>- $f(n)= \Theta (n^2)$               $(c1= 1, c2= 2, n_0=3)$
>- $f(n) \ne \Theta (n)$ 
>- $f(n) \ne \Theta (n^3)$

>$\Theta(g(n))={f(n)} \ | \ \exists \ c1, c2 >0 \ e \ n_0 \geq 0$ ***t.c*** $c1\cdot g(n) \leq f(n) \leq c2 \cdot f(n) \ \forall \ n \geq n_0$
>-***La scrittura:***
>     $2n^2 + 4 = \Theta (n^2)$
>-***è un abuso di notazione per:***
>     $2n^2 + 4 \in \Theta (n^2)$

>***Notare che:***
>![[Pasted image 20221011181237.png]]

#### *Notazione Asintotica $\mathcal {o}$*
>***Data una funzione g(n): $N \implies R$, si denota con $\mathcal {o} (g(n))$ l'insieme delle funzioni*** $f(n): N \implies R:$ 
>  $\mathcal {o}(g(n))= {f(n):\forall \ c>0, \exists \ n_0 \ t.c \ \forall \ n\geq n_0 \ \  0 \leq f(n) <c \cdot g(n) }$ 
>***Notare:***
>     $\mathcal {o}(g(n)) \subset \mathcal {O}(g(n))$
>***Definizione alternativa:***
>     $f(n)