# Blocchi e script

I blocchi e gli script sono il cuore della programmazione in Scratch. Rappresentano le istruzioni che determinano come gli sprite si comportano, interagiscono e rispondono agli eventi. Comprendere come utilizzare efficacemente i blocchi e organizzarli in script è fondamentale per creare progetti funzionali e ben strutturati.

## I blocchi: gli elementi base del codice

### Cosa sono i blocchi

I blocchi sono elementi visivi che rappresentano istruzioni o comandi. Ogni blocco ha una forma specifica e un colore che ne indica la categoria di appartenenza. I blocchi sono progettati per incastrarsi solo in modi sintatticamente corretti, riducendo la possibilità di errori.

### Categorie di blocchi

Scratch organizza i blocchi in diverse categorie, ognuna con un colore distintivo:

1. **Movimento** (blu): Per controllare la posizione e l'orientamento degli sprite
   - `vai a x: () y: ()`
   - `fai () passi`
   - `ruota di () gradi`

2. **Aspetto** (viola): Per modificare l'apparenza degli sprite
   - `passa al costume ()`
   - `dire () per () secondi`
   - `cambia effetto () di ()`

3. **Suono** (rosa): Per riprodurre e controllare suoni
   - `riproduci suono ()`
   - `ferma tutti i suoni`
   - `cambia volume di ()`

4. **Eventi** (giallo): Per rilevare eventi e avviare script
   - `quando si clicca sulla bandiera verde`
   - `quando si preme il tasto ()`
   - `quando questo sprite viene cliccato`

5. **Controllo** (arancione): Per gestire il flusso di esecuzione
   - `ripeti () volte`
   - `se () allora`
   - `attendi () secondi`

6. **Sensori** (azzurro): Per rilevare interazioni e condizioni
   - `sta toccando ()?`
   - `chiedi () e attendi`
   - `distanza da ()`

7. **Operatori** (verde): Per eseguire operazioni matematiche e logiche
   - `() + ()`
   - `() < ()`
   - `unione di () e ()`

8. **Variabili** (rosso): Per creare e manipolare variabili e liste
   - `porta () a ()`
   - `cambia () di ()`
   - `aggiungi () a (lista)`

### Tipi di blocchi

In base alla loro forma e funzione, i blocchi possono essere classificati in:

1. **Blocchi cappello**: Hanno la parte superiore arrotondata e servono per avviare uno script in risposta a un evento
2. **Blocchi impilabili**: Hanno tacche sopra e sotto per collegarsi ad altri blocchi in sequenza
3. **Blocchi reporter**: Hanno forma ovale o esagonale e restituiscono un valore
4. **Blocchi booleani**: Hanno forma esagonale e restituiscono un valore vero/falso
5. **Blocchi C**: Hanno una forma a C e contengono altri blocchi (come i cicli e le condizioni)
6. **Blocchi finali**: Hanno una tacca solo nella parte superiore e terminano una sequenza

## Gli script: sequenze di istruzioni

### Cosa sono gli script

Gli script sono sequenze di blocchi collegati che definiscono il comportamento di uno sprite. Ogni script inizia tipicamente con un blocco cappello che determina quando lo script deve essere eseguito.

### Principi di organizzazione degli script

Per creare script efficaci e leggibili:

1. **Inizia sempre con un blocco cappello**: Definisce chiaramente quando lo script viene eseguito
2. **Organizza in sequenze logiche**: Disponi i blocchi in un ordine che riflette la logica del programma
3. **Usa commenti**: Aggiungi commenti (clic destro su un'area vuota) per spiegare parti complesse
4. **Dividi in script più piccoli**: Invece di creare un unico script complesso, dividi la logica in script più piccoli e specifici
5. **Mantieni l'area di lavoro ordinata**: Disponi gli script in modo organizzato nell'area di lavoro

### Esecuzione parallela

Una caratteristica potente di Scratch è la possibilità di eseguire più script contemporaneamente. Questo permette di:

- Gestire diversi aspetti del comportamento di uno sprite simultaneamente
- Creare interazioni complesse tra diversi elementi del progetto
- Implementare sistemi reattivi che rispondono a più eventi

## Tecniche avanzate

### Comunicazione tra sprite

Gli sprite possono comunicare tra loro utilizzando:

1. **Messaggi**: Un sprite può inviare un messaggio che altri sprite possono ricevere e rispondere
   ```
   invia a tutti (messaggio)
   quando ricevo (messaggio)
   ```

2. **Variabili globali**: Variabili accessibili da tutti gli sprite

3. **Sensori**: Rilevare quando uno sprite tocca un altro o la distanza tra sprite

### Ricorsione e iterazione

Scratch supporta diverse forme di ripetizione:

1. **Cicli definiti**: Ripetere un'azione un numero specifico di volte
   ```
   ripeti (10) volte
     ...
   fine
   ```

2. **Cicli indefiniti**: Ripetere un'azione continuamente
   ```
   ripeti all'infinito
     ...
   fine
   ```

3. **Cicli condizionali**: Ripetere finché una condizione è vera
   ```
   ripeti fino a quando <condizione>
     ...
   fine
   ```

### Creazione di funzioni personalizzate

Puoi creare blocchi personalizzati (simili a funzioni) utilizzando l'opzione "Crea un blocco" nella categoria "I miei blocchi". Questo permette di:

- Riutilizzare codice
- Semplificare script complessi
- Creare astrazioni di alto livello

## Applicazione al progetto Frogger

Nel nostro progetto Frogger, utilizzeremo blocchi e script per implementare:

1. **Movimento della rana**: Script che rilevano la pressione dei tasti e muovono la rana di conseguenza
   ```
   quando si preme il tasto [freccia su]
   punta in direzione (0)
   fai (10) passi
   ```

2. **Comportamento degli ostacoli**: Script che fanno muovere auto e tronchi attraverso lo schermo
   ```
   quando si clicca sulla bandiera verde
   ripeti all'infinito
     vai a x: (240) y: ()
     scivola in () secondi a x: (-240) y: ()
   fine
   ```

3. **Rilevamento delle collisioni**: Script che verificano se la rana tocca un ostacolo o raggiunge l'obiettivo
   ```
   ripeti all'infinito
     se <sta toccando (auto)> allora
       invia a tutti (game over)
     fine
   fine
   ```

Nel prossimo argomento, approfondiremo gli eventi e l'input da tastiera, elementi cruciali per rendere il nostro gioco interattivo e reattivo ai comandi del giocatore.

## Navigazione del Corso
- [📑 Indice](../README.md)
- [⬅️ Sprite e costumi](./03-SpriteECostumi.md)
- [➡️ Eventi e input da tastiera](./05-EventiEInput.md)