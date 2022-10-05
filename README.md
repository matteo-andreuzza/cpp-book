# Basi di c++
## Variabili e costanti
Per contenere dei valori utilizziamo variabili e costanti:
- variabili per contenere un valore che **può variare**
- costanti per contenere un valore che **NON può variare**

Per essere considerata esistente, una variabile o una costante dev'essere **DICHIARATA**:
**Dichiarazione di una variabile:**

```cpp
int raggio = 20;
```
Scrivo, in ordine : datatype, nome della variabile, contenuto.
- **Datatype:** tipo della variabile, varia in base a ciò che contiene (char, int, float, bool, ecc...)
- **Nome:** scelgo un nome a piacere per la variabile
- **Contenuto:** Il contenuto della variabile deve rispettare le condizioni del datatype

**Dichiarazione di una COSTANTE:**

```cpp
const float PIGRECO = 3.14;
```
Scrivo, in ordine : const, datatype, nome della variabile, contenuto.
- **const:** parola chiave per definire una costante.
- **Datatype:** tipo della costante, varia in base a ciò che contiene (char, int, float, bool, ecc...)
- **Nome:** scelgo un nome a piacere per la costante, buona norma metterlo in MAIUSCOLO.
- **Contenuto:** Il contenuto della costante deve rispettare le condizioni del datatype

ATTENZIONE:
Dopo aver **Dichiarato** una variabile, quando la si va ad utilizzare, non si deve inserire il datatipe!
```cpp
int ciao = 0;
int bella = 2
bella  = ciao;
```

 
## Funzioni di base di iostream:
Per comunicare con l'utente, il programma utilizza la finestra della conosole dove viene eseguito il programma. Per interagire con l'utente esistono due funzioni, per scrivere sulla finsestra e per leggere un dato inserito dall'utente.

**Scrivere sulla console (Stampa a schermo)**
Utilizziamo il metodo cout di iostream per stampare un messaggio a schermo:
```cpp
cout << "Hello World";
```
La **concatenazione** si effettua tramite i caratteri < e serve a unire più stringhe. Possiamo aggiungere per concatenazione un endline per far andare a capo il programma.
```cpp
cout << "Hello" << "World" << endl;
```

**Leggere dati inseriti dall'utente:**
Utilizziamo il metodo cin di iostream per leggere ciò che digita l'utente. Il contenuto verrà memorizzato in una variabile.
```cpp
cin >> raggio;
```
La combinazione di cout e cin dà vita ad una prima forma di interazione con l'utente.
```cpp
float raggio = 0;
cout << "Inserisci il valore del raggio del cerchio" << endl;
cin >> raggio;
```

## Operazioni matematiche:
Possiamo compiere semplici operazioni matematiche sfruttando gli operatori presenti in c++.
```cpp
operazione = (34.5+1552) - ((568 * 645) / 4)
```
## Funzione principale
Per la natura del c++, il programma viene eseguito in una funzione main(), è necessario quindi che il codice principale sia in una costruzione come:
```cpp
#include <iostream>
using namespace std;
int main()
{
  return 0;
}
```

# Costrutti complessi in C++ (1)
## Operatori di selezione
### Selezione semplice
Possiamo effettuare delle operazioni di **selezione** di dati o istruzioni. Parangonandola al linguaggio comune, la selezione è l'equivalente di espressioni del tipo:
>_Se accade questo_ [condizione]
   _allora_ [e cosa succede]
   _altrimenti_ [e cosa succede altrimenti]
   
**esempio 1:**
_Se bevi acido cloridrico allora potresti stare male, altrimenti non starai male._
**esempio 2:**
_Se ti metti questo vestito, allora sei bellissima, altrimenti sei bella comunque, anche senza, rimarrai la donna più bella di questo mondo._

Paragoniamo ora il primo esempio ad un codice di programmazione:

<div style="width: 100%;">
	<!-- THE LEFT COLUMN -->
		<div style="width: 48%; float: left; margin-right: 4%;">
			Se bevi acido cloridrico allora potresti stare male, altrimenti non starai male.
		</div>
	<!-- END THE LEFT COLUMN -->
	
	<!-- THE RIGHT COLUMN -->
		<div style="width: 48%; float: left;">
			if(bevi_acido_cloridiro){ <br>
				cout << "starai male" << endl;<br>
			}<br>
			else{<br>
				cout << "non starai male" << endl;<br>
			}
		</div>
	<!-- END THE RIGHT COLUMN -->
</div>
Vediamo quindi come costruire un costrutto di selezione:

```cpp
if(condizione){
	// blocco di codice da eseguire se la condizione è vera
}
else{
	// blocco di codice da eseguire se la condizione risulta falsa
}
```
La prima parte contiene la parola chiave ```if``` che ordina al computer di **verificare** le condizioni presenti all'interno delle parentesi ed eseguire blocco di codice contenuto nelle parentesi graffe in caso le condizioni siano vere.
La seconda parte contiene la parola chiave ```else``` che ordina al computer di eseguire il blocco di codice contenuto nelle parentesi graffe se la condizione risulta falsa.

Per comprendere meglio, analizziamo il funzionamento del costrutto:
1. Il computer verifica le condizioni all'interno delle parentesi tonde. Una condizone vera è ad esempio 1 == 1, una falsa è ad esempio 1== 2.
> ATTENZIONE!
> Per fare un'operazione di confronto, occorre inserire due simboli di uguale ( == ), in quanto un solo = corrisponde ad un'operazione di ASSEGNAZIONE, ad esempio float a = 2.

2. Se la condizione è VERA, viene eseguito il blocco di codice contenuto nelle parentesi graffe, se è falsa invece, si passa al passo 3.
3. Se la condizione è FALSA, viene eseguito il blocco di codice contenuto nelle parentesi graffe dell'else. 

### Selezione annidata
La selezione annidata è un'estensione della selezione semplice, che consiste nell'inserimento di uno o più if all'interno di un'altro if.
Nel linguaggio comune un'operazione di selezione annidata potrebbe corrispondere ad un'espressione del tipo:
_Se avrò dei figli, se questi avranno dei figli allora sarò nonna, altimenti, se non avranno figli, rimarrò madre, se non avrò figli, rimarrò sola._
Applichiamo una subordinazione grafica alla frase per comprenderla meglio:

_Se avrò dei figli_
	 &#8192 _se questi avranno figli_
	 &#8192&#8192	_sarò nonna
	 &#8192 se non avranno figli_
	 	&#8192&#8192_rimarrò madre
Se non avrò figli
	&#8192rimarrò sola._

Paragoniamo ancora una volta con un linguaggio di programmazione:

<div style="width: 100%;">
	<!-- THE LEFT COLUMN -->
		<div style="width: 48%; float: left; margin-right: 4%;">
			Se avrò dei figli, se questi avranno dei figli allora sarò nonna, altimenti, se non avranno figli, rimarrò madre, se non avrò figli, rimarrò sola.
		</div>
	<!-- END THE LEFT COLUMN -->
	
	<!-- THE RIGHT COLUMN -->
		<div style="width: 48%; float: left;">
			if(avrò dei figli){ <br>
				if(avranno dei figli){ <br>
					cout << "sarò nonna" << endl; <br>
				}<br>
				else{<br>
					cout << "rimarrò madre" << endl;<br>
				}<br>
			}<br>
			else{<br>
				cout << "rimarrò sola" << endl;<br>
			}<br>
			<!-- END THE RIGHT COLUMN -->
</div>
</div>
Vediamo quindi come costruire un costrutto di selezione annidata:

``` cpp
if(condizione){
	if(condizione2){
		// blocco di codice da eseguire se la condizione2 è vera
	}
	else{
		// blocco di codice da eseguire se la condizione2 risulta falsa
	}
	// blocco di codice da eseguire se la condizione è vera
}
else{
	// blocco di codice da eseguire se la condizione risulta falsa
}
```
Un secondo if si può inserire anche nell'else:

``` cpp
if(condizione){
	// blocco di codice da eseguire se la condizione è vera
}
else{
	if(condizione2){
		// blocco di codice da eseguire se la condizione2 è vera
	}
	else{
		// blocco di codice da eseguire se la condizione2 risulta falsa
	}
	// blocco di codice da eseguire se la condizione risulta falsa
}
```

## Gli operatori logici
Come in logica e matematica, anche nell'informatica esistono 3 operatori logici. 
- Or (o questo o quello)
- And (e)
- Not (non)
I loro corrispettivi in linguaggio di programmazione:
- ```||```
- ```&&```
- ```!=```
Facciamo degli esempi di comparazione tra proposizioni logiche e in linguaggio di programmazione:
_Se queste mele pesano meno di 7 o più 10 le compro._

``` cpp
float peso_mele
if(peso_mele < 7 || peso mele < 10){
	cout << "Compro le mele" << endl;
}
```
_Se queste palle da basket sono rosse e gialle, le compro._
_(Tengo rosso come R e giallo come G)_

```c++
char colore_palle, colore_palle2;
cin >> colore_palle;
cin >> colore_palle2;
if(colore palle == 'G' && colore_palle2 == 'R'){
	cout << "Compro le palle" << endl;
}
```

# Cicli in C++
In c++, come in ogni altro linguaggio di programmazione, i cicli sono dei costrutti che servono a ripetere delle istruzioni per un numero di volte, in base alla veridicità di una condizione.
## Ciclo While
Il ciclo While si presenta come il ciclo più semplice. Il suo scopo è quello di ripere un blocco di codice se una determinata condizione è vera. Quando questa diventerà falsa, il blocco di istruzioni non verrà più eseguito, ed il programma uscirà dal ciclo. 

>_fino a quando questo è vero_ [condizione]
   _esegui [e cosa succede]

Vediamo quindi come inserire nel codice un ciclo while e la sua sintassi:

``` cpp
while(condizione){
	istruzione1;
	istruzione2;
	ecc;
}
```

Facciamo un esempio pratico:

``` cpp
int a = 5;

while(a > 0){
	cout<<"Il ciclo è in funzione. Giro numero " << a << endl;
	a++;
}
```

output:

``` shell
Il ciclo è in funzione. Giro numero 0
Il ciclo è in funzione. Giro numero 1
Il ciclo è in funzione. Giro numero 2
Il ciclo è in funzione. Giro numero 3
Il ciclo è in funzione. Giro numero 4
Il ciclo è in funzione. Giro numero 5
Il ciclo è in funzione. Giro numero 6
Il ciclo è in funzione. Giro numero 7
Il ciclo è in funzione. Giro numero 8
Il ciclo è in funzione. Giro numero 9
```

Notiamo che dopo aver completato il decimo ciclo, il programma è uscito dal ciclo, non eseguendo più le istruzioni contenute nelle parentesi graffe.
Per verificare questo avvenimento, inseriamo un cout dopo il ciclo, per vedere quando il ciclo sarà terminato.
``` cpp
int a = 5;

while(a > 0){
	cout<<"Il ciclo è in funzione. Giro numero " << a << endl;
	a++;
}
cout << "Il programma è uscito dal ciclo"
```

output:

``` shell
Il ciclo è in funzione. Giro numero 0
Il ciclo è in funzione. Giro numero 1
Il ciclo è in funzione. Giro numero 2
Il ciclo è in funzione. Giro numero 3
Il ciclo è in funzione. Giro numero 4
Il ciclo è in funzione. Giro numero 5
Il ciclo è in funzione. Giro numero 6
Il ciclo è in funzione. Giro numero 7
Il ciclo è in funzione. Giro numero 8
Il ciclo è in funzione. Giro numero 9
Il programma è uscito dal ciclo
```

Visto? Appena il programma esce dal ciclo, esso esegue le istruzioni che compaiono successivamente.
 
 >**NOTA BENE | valore della variabile:**
 >	Come puoi vedere, il valore della variabile nell'ultimo giro è 9, non 10, eppure il ciclo ha compiuto 10 giri.
 >	Questo è una conseguenza del fatto che in informatica i numeri partono dallo 0, e non da 1.
 >	Questo ci tornerà molto utile più avanti.
 
  >**NOTA BENE | incremento di una variabile**
 >	Come puoi notare, l'ultima istruzione all'interno del ciclo è `a++` .
 >	 `a++` è l'equivalente di scrivere  `a = a+1`  
 
