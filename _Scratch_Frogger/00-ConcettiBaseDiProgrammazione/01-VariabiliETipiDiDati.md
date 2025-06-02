# Variabili e Tipi di Dati

## Cosa sono le variabili?

Le variabili sono come contenitori che permettono di memorizzare informazioni all'interno di un programma. Puoi immaginare una variabile come una scatola etichettata: l'etichetta è il nome della variabile, mentre il contenuto della scatola è il valore memorizzato.

## Perché sono importanti?

Le variabili sono fondamentali nella programmazione perché permettono di:

- Memorizzare dati che cambiano durante l'esecuzione del programma
- Riutilizzare valori in diverse parti del codice
- Tenere traccia dello stato del programma (ad esempio, il punteggio in un gioco)
- Rendere il codice più leggibile e manutenibile

## Tipi di dati in Scratch

Anche se Scratch non richiede di dichiarare esplicitamente il tipo di una variabile, è importante comprendere i diversi tipi di dati che possono essere memorizzati:

### Numeri

I numeri possono essere interi (come 1, 42, -5) o decimali (come 3.14, 0.5). In Scratch, puoi utilizzare i numeri per:

- Contare (vite, punteggio, livello)
- Misurare (posizione, dimensione, velocità)
- Calcolare (operazioni matematiche)

### Testo (Stringhe)

Il testo, chiamato anche "stringa" in programmazione, è una sequenza di caratteri. In Scratch, puoi utilizzare il testo per:

- Mostrare messaggi all'utente
- Memorizzare nomi o altre informazioni testuali
- Combinare testo con altri valori (concatenazione)

### Booleani

I valori booleani possono essere solo vero (true) o falso (false). In Scratch, sono utilizzati principalmente nelle condizioni per prendere decisioni. Esempi di utilizzo:

- Verificare se il giocatore ha perso una vita
- Controllare se due sprite si stanno toccando
- Attivare o disattivare funzionalità del gioco

## Come creare e utilizzare variabili in Scratch

### Creazione di una variabile

1. Vai alla categoria "Variabili" nella palette dei blocchi
2. Clicca su "Crea una Variabile"
3. Assegna un nome significativo alla variabile
4. Scegli se la variabile deve essere disponibile per tutti gli sprite o solo per uno specifico

### Utilizzo delle variabili

Una volta creata una variabile, puoi:

- Assegnare un valore iniziale
- Modificare il valore durante l'esecuzione
- Utilizzare il valore in calcoli o condizioni
- Visualizzare il valore sullo stage

## Esempi pratici in Scratch

### Esempio 1: Contatore di punteggio

```
Quando si clicca sulla bandiera verde
Imposta [punteggio] a [0]
Per sempre
  Se <tocca [oggetto da raccogliere]> allora
    Cambia [punteggio] di [10]
  Fine
Fine
```

### Esempio 2: Nome del giocatore

```
Quando si clicca sulla bandiera verde
Chiedi [Come ti chiami?] e attendi
Imposta [nome giocatore] a (risposta)
Dici [Ciao, ] unito a (nome giocatore) per [2] secondi
```

### Esempio 3: Stato del gioco

```
Quando si clicca sulla bandiera verde
Imposta [gioco in corso] a [vero]
Per sempre
  Se <(vite) = [0]> allora
    Imposta [gioco in corso] a [falso]
    Ferma [tutti]
  Fine
Fine
```

## Applicazione nel progetto Frogger

Nel gioco Frogger che svilupperemo, utilizzeremo diverse variabili:

- **vite**: per tenere traccia delle vite rimanenti della rana
- **punteggio**: per calcolare e visualizzare il punteggio del giocatore
- **livello**: per gestire la progressione della difficoltà
- **velocità_ostacoli**: per controllare quanto velocemente si muovono i veicoli

## Esercizi pratici

1. **Crea un contatore semplice**: Crea uno sprite che aumenta una variabile "contatore" ogni volta che ci clicchi sopra.

2. **Cronometro**: Crea una variabile "tempo" che aumenta di 1 ogni secondo e si ferma quando raggiunge 60.

3. **Calcolatrice**: Crea due variabili "numero1" e "numero2", chiedi all'utente di inserire due numeri e poi mostra la somma, la differenza, il prodotto e il quoziente.

## Concetti avanzati

### Liste (Array)

In Scratch, le liste sono collezioni ordinate di elementi che possono essere numeri o testo. Sono simili alle variabili, ma possono contenere più valori. Le liste sono utili quando devi gestire gruppi di dati correlati, come un elenco di punteggi o i nomi dei giocatori.

### Variabili locali vs globali

Quando crei una variabile in Scratch, puoi scegliere se renderla disponibile per tutti gli sprite (globale) o solo per uno specifico sprite (locale). Questa distinzione è importante per organizzare il tuo codice e prevenire conflitti tra variabili.

## Navigazione del Corso
- [📑 Indice del modulo](./README.md)
- [➡️ Condizioni e Operatori Logici](./02-CondizioniEOperatoriLogici.md)