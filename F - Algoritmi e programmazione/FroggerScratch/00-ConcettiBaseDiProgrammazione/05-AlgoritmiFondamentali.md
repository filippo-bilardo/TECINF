# Algoritmi Fondamentali

## Cosa sono gli algoritmi?

Un algoritmo è una sequenza finita di istruzioni ben definite che, se seguite correttamente, portano alla risoluzione di un problema specifico. Gli algoritmi sono alla base di qualsiasi programma informatico e rappresentano il modo in cui pensiamo alla soluzione di problemi in modo sistematico.

Puoi immaginare un algoritmo come una ricetta di cucina: contiene una serie di passaggi che, se seguiti nell'ordine corretto, producono sempre lo stesso risultato.

## Caratteristiche di un buon algoritmo

Un algoritmo efficace dovrebbe avere queste caratteristiche:

- **Finitezza**: deve terminare dopo un numero finito di passi
- **Definitezza**: ogni passo deve essere chiaro e non ambiguo
- **Input**: può ricevere zero o più valori in ingresso
- **Output**: deve produrre almeno un risultato
- **Efficacia**: deve essere realizzabile con le risorse disponibili

## Algoritmi fondamentali in Scratch

### 1. Algoritmi di ricerca

#### Ricerca lineare
Esamina ogni elemento di una lista uno dopo l'altro fino a trovare quello cercato.

**Esempio in Scratch:**
```
Quando si clicca su [bandierina verde]
Porta [trovato v] a [falso]
Porta [posizione v] a [1]
Ripeti fino a quando <<(trovato) = [vero]> o <(posizione) > (lunghezza di [lista v])>>
  Se <(elemento (posizione) di [lista v]) = (elemento da cercare)> allora
    Porta [trovato v] a [vero]
  Altrimenti
    Cambia [posizione v] di (1)
  Fine
Fine
```

### 2. Algoritmi di ordinamento

#### Ordinamento a bolle (Bubble Sort)
Confrontare coppie di elementi adiacenti e scambiarli se sono nell'ordine sbagliato.

**Esempio in Scratch:**
```
Quando si clicca su [bandierina verde]
Porta [scambiato v] a [vero]
Ripeti fino a quando <(scambiato) = [falso]>
  Porta [scambiato v] a [falso]
  Ripeti per i da (1) a (lunghezza di [lista v] - 1)
    Se <(elemento (i) di [lista v]) > (elemento (i + 1) di [lista v])> allora
      Porta [temp v] a (elemento (i) di [lista v])
      Sostituisci elemento (i) di [lista v] con (elemento (i + 1) di [lista v])
      Sostituisci elemento (i + 1) di [lista v] con (temp)
      Porta [scambiato v] a [vero]
    Fine
  Fine
Fine
```

### 3. Algoritmi di conteggio

Contare occorrenze di elementi che soddisfano determinate condizioni.

**Esempio in Scratch:**
```
Quando si clicca su [bandierina verde]
Porta [contatore v] a [0]
Ripeti per i da (1) a (lunghezza di [lista v])
  Se <(elemento (i) di [lista v]) > (50)> allora
    Cambia [contatore v] di (1)
  Fine
Fine
```

### 4. Algoritmi di somma/media

Calcolare la somma o la media di una serie di valori.

**Esempio in Scratch:**
```
Quando si clicca su [bandierina verde]
Porta [somma v] a [0]
Ripeti per i da (1) a (lunghezza di [lista v])
  Cambia [somma v] di (elemento (i) di [lista v])
Fine
Porta [media v] a ((somma) / (lunghezza di [lista v]))
```

## Tecniche di progettazione degli algoritmi

### Divide et Impera (Dividi e Conquista)

Questa tecnica consiste nel:
1. Dividere il problema in sottoproblemi più piccoli
2. Risolvere i sottoproblemi in modo ricorsivo
3. Combinare le soluzioni dei sottoproblemi per ottenere la soluzione del problema originale

### Greedy (Algoritmi Golosi)

Questa tecnica consiste nel:
1. Fare sempre la scelta che sembra migliore al momento
2. Sperare che questa scelta locale porti a una soluzione globale ottimale

## Complessità degli algoritmi

La complessità di un algoritmo misura quanto tempo e memoria richiede in funzione della dimensione dell'input.

- **Complessità temporale**: quanto tempo impiega l'algoritmo a eseguire
- **Complessità spaziale**: quanta memoria utilizza l'algoritmo

In Scratch, non ci preoccupiamo troppo della complessità, ma è importante sapere che alcuni algoritmi sono più efficienti di altri.

## Applicazione nel progetto Frogger

Nel gioco Frogger utilizzeremo algoritmi per:

- **Rilevamento delle collisioni**: determinare quando la rana collide con un ostacolo o raggiunge una destinazione
- **Movimento degli ostacoli**: gestire il movimento dei veicoli e dei tronchi
- **Calcolo del punteggio**: tenere traccia e calcolare il punteggio del giocatore
- **Gestione del livello**: aumentare la difficoltà in base al progresso del giocatore

## Esercizi pratici

### Esercizio 1: Trova il massimo
Crea un programma che trova il valore massimo in una lista di numeri.

### Esercizio 2: Conta i pari e i dispari
Crea un programma che conta quanti numeri pari e quanti numeri dispari ci sono in una lista.

### Esercizio 3: Verifica palindromo
Crea un programma che verifica se una parola è un palindromo (si legge allo stesso modo da sinistra a destra e da destra a sinistra).

## Concetti chiave da ricordare

- Gli algoritmi sono sequenze di istruzioni per risolvere problemi
- Un buon algoritmo deve essere finito, definito, avere input e output, ed essere efficace
- Gli algoritmi di base includono ricerca, ordinamento, conteggio e calcolo di somme/medie
- La complessità di un algoritmo misura l'efficienza in termini di tempo e memoria
- Le tecniche di progettazione degli algoritmi aiutano a sviluppare soluzioni efficaci

## Prossimi passi

Ora che hai completato il modulo sui concetti base di programmazione, sei pronto per iniziare a lavorare sul progetto Frogger! Applica ciò che hai imparato per creare un gioco divertente e funzionale.

## Navigazione del Corso
- [📑 Indice](../README.md)
- [⬅️ Torna ai Concetti Base](./README.md)
- [➡️ Introduzione a Scratch e primi passi](../01-IntroduzioneAScratch/README.md)