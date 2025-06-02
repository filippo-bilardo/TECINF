# Funzioni e Procedure

## Cosa sono le funzioni e le procedure?

Le funzioni e le procedure sono blocchi di codice riutilizzabili che eseguono un compito specifico. In Scratch, questi blocchi sono chiamati "blocchi personalizzati" e permettono di organizzare il codice in modo più efficiente, evitando ripetizioni e rendendo il programma più leggibile.

## Perché sono importanti?

Le funzioni e le procedure sono fondamentali nella programmazione perché:

- Permettono di riutilizzare il codice senza doverlo riscrivere
- Rendono il programma più organizzato e facile da leggere
- Facilitano la manutenzione e la correzione degli errori
- Consentono di scomporre problemi complessi in parti più semplici

## Blocchi personalizzati in Scratch

In Scratch, puoi creare blocchi personalizzati che funzionano come funzioni o procedure:

### Come creare un blocco personalizzato

1. Vai alla categoria "I miei blocchi" nella palette dei blocchi
2. Clicca su "Crea un blocco"
3. Assegna un nome al blocco
4. Scegli se il blocco deve avere parametri (input)
5. Definisci il codice che il blocco deve eseguire

### Tipi di blocchi personalizzati

#### Blocchi senza input (procedure semplici)

Eseguono sempre la stessa sequenza di azioni.

Esempio:
```
Definisci [saluta]
Dire [Ciao!] per [2] secondi
Dire [Come stai?] per [2] secondi
```

Per usare questo blocco:
```
Quando si clicca sulla bandiera verde
[saluta]
```

#### Blocchi con input (funzioni parametrizzate)

Eseguono azioni che possono variare in base ai parametri forniti.

Esempio:
```
Definisci [saluta (nome)]
Dire [Ciao, ] unito a (nome) per [2] secondi
```

Per usare questo blocco:
```
Quando si clicca sulla bandiera verde
[saluta [Mario]]
[saluta [Luigi]]
```

#### Blocchi che restituiscono valori (funzioni con ritorno)

Eseguono calcoli e restituiscono un risultato che può essere utilizzato in altre parti del programma.

Esempio:
```
Definisci [area rettangolo (base) (altezza)]
Rispondi [(base) * (altezza)]
```

Per usare questo blocco:
```
Quando si clicca sulla bandiera verde
Imposta [risultato] a [area rettangolo [5] [3]]
Dire [L'area è: ] unito a (risultato) per [2] secondi
```

## Esempi pratici in Scratch

### Esempio 1: Animazione riutilizzabile

```
Definisci [anima salto]
Cambia y di [10]
Attendi [0.1] secondi
Cambia y di [10]
Attendi [0.1] secondi
Cambia y di [-10]
Attendi [0.1] secondi
Cambia y di [-10]
```

Utilizzo:
```
Quando si clicca sulla bandiera verde
Per sempre
  Se <tasto [spazio] premuto> allora
    [anima salto]
  Fine
Fine
```

### Esempio 2: Calcolo del punteggio

```
Definisci [calcola punteggio (livello) (monete) (tempo)]
Rispondi [((livello) * 100) + ((monete) * 10) - (tempo)]
```

Utilizzo:
```
Quando si clicca sulla bandiera verde
Imposta [punteggio finale] a [calcola punteggio (livello) (monete raccolte) (tempo impiegato)]
Dire [Punteggio: ] unito a (punteggio finale) per [2] secondi
```

### Esempio 3: Sistema di movimento

```
Definisci [muovi (direzione)]
Se <(direzione) = [su]> allora
  Punta in direzione [0] gradi
Fine
Se <(direzione) = [giù]> allora
  Punta in direzione [180] gradi
Fine
Se <(direzione) = [destra]> allora
  Punta in direzione [90] gradi
Fine
Se <(direzione) = [sinistra]> allora
  Punta in direzione [-90] gradi
Fine
Fai [10] passi
```

Utilizzo:
```
Quando si clicca sulla bandiera verde
Per sempre
  Se <tasto [freccia su] premuto> allora
    [muovi [su]]
  Fine
  Se <tasto [freccia giù] premuto> allora
    [muovi [giù]]
  Fine
  Se <tasto [freccia destra] premuto> allora
    [muovi [destra]]
  Fine
  Se <tasto [freccia sinistra] premuto> allora
    [muovi [sinistra]]
  Fine
Fine
```

## Applicazione nel progetto Frogger

Nel gioco Frogger, utilizzeremo funzioni e procedure per:

- **Gestire il movimento della rana**: Creare blocchi personalizzati per il movimento in diverse direzioni
- **Controllare le collisioni**: Creare una funzione che verifichi se la rana ha colliso con un ostacolo
- **Gestire i livelli**: Creare procedure per inizializzare e configurare ogni livello
- **Calcolare il punteggio**: Creare funzioni per calcolare il punteggio in base a vari fattori

## Esercizi pratici

1. **Sistema di dialogo**: Crea un blocco personalizzato che gestisca i dialoghi tra personaggi, accettando come parametri il testo e la durata.

2. **Generatore di forme**: Crea blocchi personalizzati per disegnare diverse forme geometriche (quadrato, triangolo, cerchio) con dimensioni parametrizzabili.

3. **Sistema di inventario**: Crea blocchi personalizzati per aggiungere, rimuovere e controllare oggetti in un inventario di gioco.

## Concetti avanzati

### Ricorsione

La ricorsione è una tecnica in cui una funzione chiama se stessa. In Scratch, un blocco personalizzato può chiamare se stesso, permettendo di creare strutture ricorsive come frattali o algoritmi che si ripetono con parametri diversi.

Esempio: Disegno ricorsivo di un albero
```
Definisci [disegna albero (lunghezza) (livello)]
Se <(livello) > [0]> allora
  Abbassa penna
  Fai (lunghezza) passi
  Alza penna
  Ruota di [30] gradi
  [disegna albero [(lunghezza) * [0.7]] [(livello) - [1]]]
  Ruota di [-60] gradi
  [disegna albero [(lunghezza) * [0.7]] [(livello) - [1]]]
  Ruota di [30] gradi
  Fai [-(lunghezza)] passi
Fine
```

### Modularità e riutilizzo del codice

Creare blocchi personalizzati ben progettati permette di costruire una "libreria" di funzionalità riutilizzabili in diversi progetti. Alcuni suggerimenti:

- Crea blocchi che svolgono una singola funzione ben definita
- Usa nomi descrittivi che spiegano chiaramente cosa fa il blocco
- Documenta i parametri richiesti e il valore restituito
- Testa i blocchi individualmente prima di integrarli nel programma principale

## Navigazione del Corso
- [📑 Indice del modulo](./README.md)
- [⬅️ Cicli e Iterazioni](./03-CicliEIterazioni.md)
- [➡️ Algoritmi Fondamentali](./05-AlgoritmiFondamentali.md)