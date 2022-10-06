# Introduzione alla probabilità

## ***Fenomeno Aleatorio*** 
>***Un fenomeno è detto aleatorio se il suo esito è incerto .***
>***L'insieme dei possibili enti viene indicato con $\Omega$ .***

### ***Si divide in***:
>- ***Discreto se $\Omega$ è finito o numerabile***
>- ***Continuo se $\Omega$ è più che numerabile***

### ***Esempio discreto***:
>***$\Omega$ finito sono i possibili risultati del lancio di un dado***

### ***Esempio continuo***: 
> ***$\Omega$ numerabile sono il numero di telefonate ricevute da un centralino in un intervallo di tempo***

### ***Esempio continuo***: 
> ***Tempo di funzionamento di una lampadina rispetto ad una certa unità di misura***

### ***Famiglia degli eventi*** 
> ***Sottinsieme di $\Omega$***
> ***Tornando agli esempi:***
> - ***"esce un numero pari" $\iff$ $\set{2,4,6}$*** 
> - ***"il centralino riceve al più 2 telefonate"***$\iff$ ***$\set {0,1,2}$***  $\subset$  ***$\set{0,1,2,....}$***
> - ***"la lampadina si fulmina dopo il tempo t=5" $\iff$ (5, $\infty$ ) $\subset$ (0, $\infty$ ).***

### ***Corrispondenza tra operazioni logiche e operazioni insiemistiche***

>- ***Somma logica***  $$A\lor B\longleftrightarrow A\cup B$$ 
>- ***Prodotto logico***$$A\land B \longleftrightarrow A\cap B$$
>- ***Negazione*** $$\overline{A} \longleftrightarrow A^C = \Omega \setminus A$$

### ***$\sigma$ Algebra***
>***Sia $\Omega$ un insieme non vuoto e sia $A\subset\mathcal{P}(\Omega)$***
>***Allora A è una $\sigma$ Algebra se:***
> i) ***$\Omega\in A$***
> 	ii) ***$\forall A \in A \implies A^C \in A$*** 
> 		iii) ***$\forall\{A_n\}_{n\geq1}\subset A \implies\bigcup_{n\geq1} A_n \in A$***  

### ***Misura di Probabilità***
>***Sia Ω un insieme non vuoto e A una σ-algebra di eventi.
>***Una funzione $P:A\implies [0,\infty)$  è una misura di probabilità se:
>- $\mathcal{P}(\Omega) =1$  
>- $\forall {A_{n} }_{n \geqslant 1} \subset \mathcal{A}$ t.c. $A_{m}\cap A_{n}: \forall : m\neq n$ si ha  $P(\bigcup_{n\geq1} A_n)= \sum_{n\geq 1} P(An)$

### ***Conseguenze della misura di Probabilità

>***$P(\varnothing)=0$
>Se si considera $An=\varnothing$  $\forall \geq1$







