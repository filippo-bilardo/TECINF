# Condizioni e Operatori Logici

## Cosa sono le condizioni?

Le condizioni sono espressioni che vengono valutate come vere o false e permettono al programma di prendere decisioni. Grazie alle condizioni, un programma può eseguire azioni diverse in base a situazioni diverse, rendendo il software interattivo e reattivo.

## Perché sono importanti?

Le condizioni sono fondamentali nella programmazione perché:

- Permettono di creare programmi che reagiscono a situazioni diverse
- Consentono di controllare il flusso di esecuzione del programma
- Sono alla base di qualsiasi interazione con l'utente
- Rendono possibile la creazione di giochi e applicazioni dinamiche

## Strutture condizionali in Scratch

### Il blocco "Se"

Il blocco "Se" (If) è la struttura condizionale più semplice. Esegue un blocco di codice solo se la condizione specificata è vera.

Esempio:
```
Se <tocca [bordo]> allora
  Rimbalza
Fine
```

### Il blocco "Se-Altrimenti"

Il blocco "Se-Altrimenti" (If-Else) permette di eseguire un blocco di codice se la condizione è vera, e un altro blocco se la condizione è falsa.

Esempio:
```
Se <(punteggio) > [100]> allora
  Dire [Hai vinto!] per [2] secondi
Altrimenti
  Dire [Continua a giocare!] per [2] secondi
Fine
```

## Operatori di confronto

Gli operatori di confronto permettono di confrontare valori e generare un risultato booleano (vero o falso):

- **=** : Uguale a (verifica se due valori sono uguali)
- **>** : Maggiore di
- **<** : Minore di
- **>=** : Maggiore o uguale a
- **<=** : Minore o uguale a
- **≠** : Diverso da

Esempi:
```
(10) = (10)      // Risultato: vero
(5) > (3)        // Risultato: vero
(7) < (2)        // Risultato: falso
(punteggio) >= (record) // Confronta il punteggio con il record
```

## Operatori logici

Gli operatori logici permettono di combinare più condizioni:

### E (AND)

L'operatore "e" restituisce vero solo se entrambe le condizioni sono vere.

Esempio:
```
<<tocca [acqua]> e <(vite) > [0]>>
// Vero solo se il personaggio tocca l'acqua E ha più di 0 vite
```

### O (OR)

L'operatore "o" restituisce vero se almeno una delle condizioni è vera.

Esempio:
```
<<tocca [moneta]> o <tocca [stella]>>
// Vero se il personaggio tocca una moneta OPPURE una stella
```

### NON (NOT)

L'operatore "non" inverte il valore di una condizione: se la condizione è vera, restituisce falso, e viceversa.

Esempio:
```
<non <tocca [ostacolo]>>
// Vero se il personaggio NON tocca un ostacolo
```

## Esempi pratici in Scratch

### Esempio 1: Controllo dei bordi

```
Per sempre
  Se <tocca [bordo]> allora
    Vai a x: [0] y: [0]
  Fine
Fine
```

### Esempio 2: Sistema di vite

```
Se <<tocca [ostacolo]> e <non <(invincibilità) = [vero]>>> allora
  Cambia [vite] di [-1]
  Attendi [1] secondi
  Se <(vite) = [0]> allora
    Dire [Game Over] per [2] secondi
    Ferma [tutti]
  Fine
Fine
```

### Esempio 3: Raccolta di oggetti diversi

```
Se <<tocca [moneta]> o <tocca [gemma]>> allora
  Se <tocca [moneta]> allora
    Cambia [punteggio] di [1]
  Altrimenti
    Cambia [punteggio] di [5]
  Fine
Fine
```

## Applicazione nel progetto Frogger

Nel gioco Frogger, utilizzeremo condizioni e operatori logici per:

- **Rilevare collisioni**: Verificare se la rana tocca un veicolo o cade in acqua
- **Controllare i bordi**: Impedire alla rana di uscire dall'area di gioco
- **Gestire il punteggio**: Aumentare il punteggio quando la rana raggiunge la destinazione
- **Controllare il livello**: Passare al livello successivo quando vengono soddisfatte certe condizioni

## Esercizi pratici

1. **Semaforo**: Crea uno sprite che cambia colore (verde, giallo, rosso) e utilizza condizioni per far muovere un altro sprite solo quando il semaforo è verde.

2. **Quiz semplice**: Crea un quiz con tre domande. Utilizza condizioni per verificare se le risposte sono corrette e tieni traccia del punteggio.

3. **Labirinto condizionale**: Crea un piccolo labirinto dove il personaggio può muoversi solo in certe direzioni in base alla sua posizione attuale.

## Concetti avanzati

### Condizioni annidate

Le condizioni possono essere annidate, cioè inserite una dentro l'altra, per creare logiche più complesse. Questo permette di verificare condizioni in sequenza o di creare rami di decisione più articolati.

Esempio:
```
Se <(temperatura) > [30]> allora
  Dire [Fa molto caldo!] per [2] secondi
  Se <(umidità) > [80]> allora
    Dire [Ed è anche umido!] per [2] secondi
  Fine
Altrimenti
  Se <(temperatura) < [10]> allora
    Dire [Fa freddo!] per [2] secondi
  Altrimenti
    Dire [La temperatura è gradevole] per [2] secondi
  Fine
Fine
```

### Ottimizzazione delle condizioni

Quando si scrivono condizioni complesse, è importante organizzarle in modo efficiente. Alcune strategie:

- Mettere le condizioni più frequenti o più semplici da verificare per prime
- Evitare di ripetere le stesse verifiche più volte
- Utilizzare variabili booleane per memorizzare il risultato di condizioni complesse

## Navigazione del Corso
- [📑 Indice del modulo](./README.md)
- [⬅️ Variabili e Tipi di Dati](./01-VariabiliETipiDiDati.md)
- [➡️ Cicli e Iterazioni](./03-CicliEIterazioni.md)