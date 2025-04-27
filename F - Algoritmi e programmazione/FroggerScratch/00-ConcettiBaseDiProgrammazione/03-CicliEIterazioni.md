# Cicli e Iterazioni

## Cosa sono i cicli?

I cicli (o iterazioni) sono strutture di programmazione che permettono di ripetere un blocco di istruzioni più volte. Invece di scrivere lo stesso codice ripetutamente, puoi utilizzare un ciclo per eseguirlo automaticamente il numero di volte desiderato o finché una certa condizione rimane vera.

## Perché sono importanti?

I cicli sono fondamentali nella programmazione perché:

- Riducono la ripetizione del codice, rendendo i programmi più brevi e leggibili
- Permettono di automatizzare compiti ripetitivi
- Consentono di elaborare grandi quantità di dati in modo efficiente
- Sono essenziali per creare animazioni, simulazioni e comportamenti dinamici

## Tipi di cicli in Scratch

### Ciclo "Ripeti"

Il ciclo "Ripeti" esegue un blocco di codice un numero specifico di volte.

Esempio:
```
Ripeti [10] volte
  Fai [10] passi
  Ruota di [36] gradi
Fine
```
Questo codice fa muovere lo sprite in un percorso a forma di decagono (10 lati).

### Ciclo "Per sempre"

Il ciclo "Per sempre" esegue continuamente un blocco di codice fino a quando il programma non viene interrotto. È utile per azioni che devono essere controllate costantemente, come il movimento di un personaggio o il rilevamento di collisioni.

Esempio:
```
Per sempre
  Se <tasto [freccia destra] premuto> allora
    Punta in direzione [90] gradi
    Fai [10] passi
  Fine
Fine
```

### Ciclo "Ripeti fino a quando"

Il ciclo "Ripeti fino a quando" esegue un blocco di codice ripetutamente finché una condizione specifica diventa vera.

Esempio:
```
Ripeti fino a quando <(punteggio) > [100]>
  Attendi [1] secondi
  Cambia [punteggio] di [punteggio_per_secondo]
Fine
```

## Esempi pratici in Scratch

### Esempio 1: Animazione semplice

```
Quando si clicca sulla bandiera verde
Ripeti [5] volte
  Passa al costume [costume1]
  Attendi [0.2] secondi
  Passa al costume [costume2]
  Attendi [0.2] secondi
Fine
```

### Esempio 2: Movimento di pattuglia

```
Quando si clicca sulla bandiera verde
Vai a x: [-100] y: [0]
Per sempre
  Punta in direzione [90] gradi
  Ripeti fino a quando <(x position) > [100]>
    Fai [5] passi
  Fine
  Punta in direzione [-90] gradi
  Ripeti fino a quando <(x position) < [-100]>
    Fai [5] passi
  Fine
Fine
```

### Esempio 3: Conto alla rovescia

```
Quando si clicca sulla bandiera verde
Imposta [tempo] a [10]
Ripeti fino a quando <(tempo) = [0]>
  Dire [Tempo rimanente: ] unito a (tempo) per [1] secondi
  Cambia [tempo] di [-1]
Fine
Dire [Tempo scaduto!] per [2] secondi
```

## Cicli annidati

I cicli possono essere inseriti uno dentro l'altro, creando cicli annidati. Questo è utile per operazioni più complesse, come la creazione di pattern o l'elaborazione di dati multidimensionali.

Esempio: Disegnare una griglia
```
Quando si clicca sulla bandiera verde
Cancella tutto
Alza penna
Vai a x: [-150] y: [150]
Ripeti [6] volte
  Abbassa penna
  Ripeti [6] volte
    Fai [50] passi
    Alza penna
    Fai [50] passi
    Abbassa penna
  Fine
  Alza penna
  Vai a x: [-150] y: [(y position) - 50]
Fine
```

## Applicazione nel progetto Frogger

Nel gioco Frogger, utilizzeremo i cicli per:

- **Movimento continuo degli ostacoli**: Utilizzare cicli "Per sempre" per far muovere continuamente i veicoli e altri ostacoli
- **Animazione della rana**: Utilizzare cicli "Ripeti" per animare il salto della rana
- **Controllo del gioco**: Utilizzare cicli "Ripeti fino a quando" per controllare il tempo di gioco o il passaggio al livello successivo
- **Generazione di ostacoli**: Utilizzare cicli per generare sequenze di ostacoli con pattern diversi

## Esercizi pratici

1. **Disegno geometrico**: Crea uno script che disegni una spirale utilizzando un ciclo che aumenta gradualmente la lunghezza di ogni segmento.

2. **Generatore di pattern**: Crea uno script che generi un pattern visivo ripetitivo utilizzando cicli annidati.

3. **Simulazione di traffico**: Crea una semplice simulazione di traffico con più veicoli che si muovono in direzioni diverse utilizzando cicli.

## Concetti avanzati

### Cicli controllati da eventi

In Scratch, i cicli possono essere controllati anche da eventi esterni, come input dell'utente o messaggi da altri sprite. Questo permette di creare cicli che si adattano dinamicamente alle azioni dell'utente o ad altri eventi nel programma.

Esempio:
```
Quando si clicca sulla bandiera verde
Per sempre
  Se <tasto [spazio] premuto> allora
    Ripeti [10] volte
      Cambia effetto [colore] di [10]
      Attendi [0.1] secondi
    Fine
  Fine
Fine
```

### Ottimizzazione dei cicli

Quando si utilizzano i cicli, è importante considerare l'efficienza del codice. Alcuni suggerimenti:

- Evitare cicli infiniti che non hanno una via d'uscita
- Limitare l'uso di cicli annidati profondi, che possono rallentare il programma
- Utilizzare variabili per controllare dinamicamente il numero di iterazioni
- Considerare se un'operazione deve essere veramente ripetuta o può essere eseguita una sola volta

## Navigazione del Corso
- [📑 Indice del modulo](./README.md)
- [⬅️ Condizioni e Operatori Logici](./02-CondizioniEOperatoriLogici.md)
- [➡️ Funzioni e Procedure](./04-FunzioniEProcedure.md)