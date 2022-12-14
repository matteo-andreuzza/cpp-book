# Basi di c++
di Matteo Andreuzza
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


## Ciclo Do - While
Il ciclo do - While è un'evoluzione del ciclo While. L'unica cosa che cambia da quest'ultimo infatti, è che il blocco di istruzioni da eseguire viene eseguito una volta, poi viene verificata la condizione e allora verrà eseguito di nuovo fino a quando la condizione non diventerà falsa.

> _esegui [blocco di istruzioni]
>fino a quando questo è vero_ [condizione]
   _esegui [blocco di istruzioni]

Vediamo quindi come inserire nel codice un ciclo while e la sua sintassi:

``` cpp
do {  
 //blocco di codice 
 }  
while (condizione);
```

Facciamo un esempio pratico:

``` cpp
int i = 0;  
do {  
  cout << i << "\n";  
  i++;  
}  
while (i < 5);
```

output:

``` shell
0
1
2
3
4
```



## Ciclo For
Il ciclo for è un ciclo più complesso del ciclo while, che permette di ripetere un blocco di istruzioni un determinato numero di volte. Come per il While, per eseguire il blocco di codice dovrà essere soddisfatta una condizione.
>_fino a quando questo è vero_ [condizione]
   _esegui [e cosa succede]

Vediamo quindi come inserire nel codice un ciclo for e la sua sintassi:

``` cpp
for(<inizializzazione>; <condizione>; <espressione_iterativa>){
	istruzione1;
	istruzione2;
	ecc;
}
```

Come possiamo notare, tra le parentesi non è presente la sola condizione che dev'essere soddisfatta, ma anche un'istruzione di inizializzazione e un'espressione iterativa.
Queste sono utili per utilizzare il ciclo for con Vettori, matrici, e altre parti del c++ che non abbiamo ancora trattato.
Ci limiteremo quindi ad inserire nel parametro di inizializzazione, la dichiarazione di una variabile contatore, e nell'espressione iterativa, l'incremento della suddetta variabile. Sia chiaro che l'espressione iterativa viene eseguita ad ogni ciclo, quindi la variabile verrà incrementata ad ogni giro.

Facciamo un esempio pratico:

``` cpp
int acc = 0;
for (int i = 0; i < 10; i ++){
    cout << "Questo è il giro numero" << i  << endl;
    acc += i;
}
```

output:

``` shell
Questo è il giro numero0
Questo è il giro numero1
Questo è il giro numero2
Questo è il giro numero3
Questo è il giro numero4
Questo è il giro numero5
Questo è il giro numero6
Questo è il giro numero7
Questo è il giro numero8
Questo è il giro numero9

```

Il ciclo stampa a schermo 10 volte la scritta, scrivendo alla fine il numero del giro.
> Chiariamo che questo è un uso estremamente riduttivo del ciclo for, tanto che questo risultato si potrebbe ottenere anche con un ciclo while.
> Ci limitiamo però a questi esempi, dato che un uso intensivo del ciclo for verrà fatto più avanti.

## Istruzioni utili nei cicli

### istruzione break
l'istruzione break serve a fermare un ciclo in un determinato momento. Questo può essere utile per terminare il ciclo quando una condizione è soddisfatta.
Esempio:
```cpp
    for (int i = 1; i < 10; i++)
    {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
    }
```
output:
```shell
1
2
3
```
il ciclo si ferma quando ```i``` diventa 4

### Istruzione continue
L'istruzione ```continue``` interrompe l'iterazione del ciclo, facendolo ripartire. Più specificatamente:

> L'istruzione `continue` ha come effetto l'interruzione dell'iterazione corrente. Il controllo di flusso rimane confinato all'interno del ciclo, ma viene reindirizzato all'iterazione successiva in conseguenza di una circostanza inattesa che invalida o rende superflua l'esecuzione di tale iterazione.

esempio:
```cpp
int i = 0;
while (i < 10) {
  if (i == 4) {
    i++;
    continue;
  }
  cout << i << "\n";
  i++;
}
```

output
```shell
0
1
2
3  # <= manca il 4
5
6
7
8
9
```
Possiamo notare che quando ```i``` è uguale a 4, la corrente iterazione del ciclo viene interrotta.

> Nota bene:
> Come vedi nell'output c'è un `#` prima della freccia che indica l'assenza del 4. Questo **NON** fa parte dell'output. L'indicatore `#` è un commento (come `//` in c++) nel linguaggio shell.


# Arrays in C++
In c++, come in ogni linguaggio di programmazione che li supporta, gli arrays servono ad immagazzinare più elementi all'interno di una variabile. 
Ci sono due tipi di arrays, i vettori e le matrici. Vediamo ora i Vettori.
## Vettori
Detti anche array monodimensionali, sono caratterizzati da:
- Il tipo di elementi che deve contenere
- La lunghezza dell'array
- Gli elementi che contiene
- Gli indici degli elementi
Questa rappresentazione ci aiuta a capire la struttura dell'array:
![[Array1.jpg]]
Un array è costituito da delle "caselle" immaginarie. Queste caselle devono essere tante quante la lunghezza dell'array (nell'immagine: Array lenght). Ad ogni "casella" è assegnato un numero che la rappresenta, questo numero è chiamato indice.
> **Nota bene**
> Gli indici delle "caselle" partono da 0. Questo significa che la prima casella avrà indice 0, la seconda 1 e così via. 

Le caselle possono essere riempite con degli elementi, a patto che questi elementi siano del tipo dell'array, ma adesso vedremo meglio.

### L'array nel codice c++
Vediamo ora come usare gli array nei nostri programmi c++:
Come per le variabili, anche gli arrays vanno inizializzati:
La struttura per inizializzare un vettore è la seguente:
```cpp
tipo nome[lunghezza] = contenuto;
```
Per inizializzare un vettore di 5 elementi contenente i primi 5 numeri naturali, scriverò:
```cpp
int numeri[5] = {1, 2, 3, 4, 5}
```
>Nota bene:
>in un array gli elementi sono separati da una virgola e contenuti dentro parentesi graffe.

#### Usare gli arrays:
Possiamo utilizzare i vettori in svariati modi. Per ricavare un valore in una determinata posizione in un vettore usiamo la sintassi:
```cpp
int numeri[5] = {1, 2, 3, 4, 5};
cout << numeri[1];
```
output:
```shell
2
```

vediamo per esempio come stampare tutti i valori di un vettore:
```cpp
int numeri[5] = {1, 2, 3, 4, 5};
for(int i = 0; i<5; i++){
	cout << numeri[i] << endl;
}
```
Notare come il ciclo for risulta molto utile in questi casi, dato che ci permette di eseguire determinate operazioni su un vettore un determinato numero di volte. Sapendo la dimensione del vettore (che dev'essere definita) utilizzare tutti gli elementi.
La sintassi vista qui sopra è utile in diversi casi. 





**Il seguente testo NON riguarda il programma di SECONDA superiore**

# Stringhe in c++

## Gestione delle stringhe
In C++, puoi usare l'operatore di concatenazione `+` per concatenare due stringhe. Ad esempio:

In C++, puoi usare l'operatore di concatenazione `+` per concatenare due stringhe. Ad esempio:

```cpp
#include <iostream> 
#include <string>  
int main() {   
	std::string s1 = "ciao";   
	std::string s2 = " mondo";    
	std::string s3 = s1 + s2;   
	std::cout << s3 << std::endl; // stamperà "ciao mondo"    
	return 0; 
}
```

Inoltre, puoi anche usare il metodo `append` per concatenare una stringa ad una stringa già esistente. Ad esempio:

```cpp
#include <iostream> 
#include <string>  
int main() {   
	std::string s1 = "ciao";   
	std::string s2 = " mondo";    
	s1.append(s2);   
	std::cout << s1 << std::endl; // stamperà "ciao mondo"    
	return 0; 
}
```

Infine, puoi anche usare il metodo `+=` per concatenare una stringa ad una stringa già esistente. Ad esempio:

```cpp
#include <iostream>
#include <string>

int main() {
  std::string s1 = "ciao";
  std::string s2 = " mondo";

  s1 += s2;
  std::cout << s1 << std::endl; // stamperà "ciao mondo"

  return 0;
}```


```cpp
#include <iostream> 
#include <string>  
int main() {   
	std::string s1 = "ciao";   
	std::string s2 = " mondo";    
	std::string s3 = s1 + s2;   
	std::cout << s3 << std::endl; // stamperà "ciao mondo"    
	return 0; 
	
}
```

Inoltre, puoi anche usare il metodo `append` per concatenare una stringa ad una stringa già esistente. Ad esempio:

```cpp
#include <iostream> 
#include <string>  
int main() {   
	std::string s1 = "ciao";   
	std::string s2 = " mondo";    
	s1.append(s2);   
	std::cout << s1 << std::endl; // stamperà "ciao mondo"    
	return 0; 
}
```

Infine, puoi anche usare il metodo `+=` per concatenare una stringa ad una stringa già esistente. Ad esempio:

```cpp
#include <iostream>
#include <string>

int main() {
  std::string s1 = "ciao";
  std::string s2 = " mondo";

  s1 += s2;
  std::cout << s1 << std::endl; // stamperà "ciao mondo"

  return 0;
}
```

## inserimento di caratteri nelle stringhe
Per inserire un carattere tra un carattere e l'altro di una stringa in c++, puoi utilizzare la funzione `insert` della classe `string`. La sintassi per utilizzare questa funzione è la seguente:

`stringa.insert(posizione, carattere_da_inserire);`

In questo caso, `stringa` è la stringa in cui vuoi inserire il nuovo carattere, `posizione` è la posizione in cui vuoi inserire il carattere (nota che la prima posizione di una stringa in c++ ha indice 0) e `carattere_da_inserire` è il carattere che vuoi inserire nella stringa.

Ecco un esempio di come utilizzare la funzione `insert` per inserire un carattere nella stringa "ciao":

```cpp
#include <iostream> 
#include <string>  
using namespace std;  
int main() {   
	string s = "ciao";    // Inserisci una 'x' nella posizione 2 della stringa 
	s.insert(2, "x");    
	cout << s << endl;    
	return 0; 
}
```

Se esegui questo programma, dovresti vedere che viene stampata la stringa "cixao" a schermo, poiché abbiamo inserito una 'x' nella posizione 2 della stringa originale "ciao".


## matrici di stringhe

In C++, una matrice è un tipo di dato che può contenere più valori di uno stesso tipo. Una matrice di stringhe può quindi essere utilizzata per memorizzare una serie di stringhe. Per dichiarare una matrice di stringhe, dovresti scrivere qualcosa del genere:

``` cpp
string nome_matrice[numero_di_righe][numero_di_colonne]; 
``` 

Dove `numero_di_righe` e `numero_di_colonne` specificano rispettivamente il numero di righe e il numero di colonne della matrice. Ad esempio, la seguente istruzione dichiara una matrice di stringhe di 3 righe e 4 colonne:

```cpp
string matrice_stringhe[3][4];
```

Per assegnare un valore a una stringa in una matrice, puoi usare la sintassi seguente:

``` cpp
nome_matrice[riga][colonna] = "valore";
```

Ad esempio, per assegnare il valore "ciao" alla prima riga e alla seconda colonna della matrice di stringhe dichiarata in precedenza, potresti usare il seguente codice:

```cpp
matrice_stringhe[0][1] = "ciao";
```

Per stampare il contenuto di una matrice di stringhe, puoi usare un ciclo `for` per scorrere le righe e le colonne della matrice e utilizzare il seguente codice per stampare il valore di ogni cella:

```cpp
cout << nome_matrice[riga][colonna] << endl;
```

Ad esempio, il seguente codice stampa il contenuto di ogni cella della matrice di stringhe precedentemente dichiarata:

``` cpp
for (int i = 0; i < 3; i++) {     
	for (int j = 0; j < 4; j++) {         
		cout << matrice_stringhe[i][j] << endl;     
	}
}
```

