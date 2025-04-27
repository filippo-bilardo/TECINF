# Eventi e input da tastiera

Gli eventi e l'input da tastiera sono elementi fondamentali per creare progetti interattivi in Scratch. Gli eventi permettono al programma di rispondere a specifiche azioni o condizioni, mentre l'input da tastiera consente all'utente di controllare e interagire con gli sprite. Questi concetti sono particolarmente importanti per il nostro progetto Frogger, dove il giocatore dovrà controllare la rana utilizzando i tasti direzionali.

## Eventi in Scratch

### Cosa sono gli eventi

Gli eventi sono occorrenze specifiche che possono innescare l'esecuzione di uno script. Rappresentano il concetto di "quando accade qualcosa, fai qualcos'altro". In Scratch, gli eventi sono rappresentati dai blocchi cappello di colore giallo nella categoria "Eventi".

### Tipi di eventi

Scratch offre diversi tipi di eventi che possono avviare l'esecuzione di uno script:

1. **Eventi di avvio**:
   - `quando si clicca sulla bandiera verde`: Avvia lo script quando si clicca sul pulsante di avvio
   - `quando si clicca su questo sprite`: Avvia lo script quando lo sprite viene cliccato
   - `quando si clicca sullo stage`: Avvia lo script quando si clicca sullo sfondo

2. **Eventi da tastiera**:
   - `quando si preme il tasto ()`: Avvia lo script quando viene premuto un tasto specifico
   - `quando la chiave () viene premuta?`: Verifica se un tasto è premuto (usato in condizioni)

3. **Eventi di comunicazione**:
   - `quando ricevo ()`: Avvia lo script quando viene ricevuto un messaggio specifico
   - `invia a tutti ()`: Invia un messaggio a tutti gli sprite

4. **Eventi temporali**:
   - `quando lo sfondo passa a ()`: Avvia lo script quando lo sfondo cambia
   - `quando il volume è > ()`: Avvia lo script quando il volume supera una soglia

5. **Eventi di clonazione**:
   - `quando vengo clonato`: Avvia lo script quando viene creato un clone dello sprite

### Programmazione event-driven

La programmazione basata su eventi (event-driven) è un paradigma in cui l'esecuzione del programma è determinata dal verificarsi di eventi esterni. Questo approccio:

- Rende il programma reattivo all'interazione dell'utente
- Permette di gestire più processi in parallelo
- Semplifica la struttura del codice dividendolo in sezioni che rispondono a eventi specifici

## Input da tastiera

### Rilevamento dei tasti

In Scratch, ci sono due modi principali per rilevare l'input da tastiera:

1. **Eventi da tastiera**: Utilizzando il blocco `quando si preme il tasto ()`, puoi avviare uno script specifico ogni volta che un determinato tasto viene premuto

2. **Sensori di tastiera**: Utilizzando il blocco `tasto () premuto?`, puoi verificare continuamente se un tasto è premuto, utile all'interno di cicli o condizioni

### Tasti disponibili

Scratch permette di rilevare diversi tipi di tasti:

- **Tasti freccia**: Su, giù, destra, sinistra
- **Tasti alfanumerici**: Lettere (a-z) e numeri (0-9)
- **Tasti speciali**: Spazio, Invio, Shift, ecc.

### Gestione dell'input continuo vs. discreto

Esistono due approcci principali per gestire l'input da tastiera:

1. **Input discreto**: Lo script viene eseguito una volta quando il tasto viene premuto
   ```
   quando si preme il tasto [freccia su]
   cambia y di (10)
   ```

2. **Input continuo**: Lo script verifica continuamente se un tasto è premuto
   ```
   quando si clicca sulla bandiera verde
   ripeti all'infinito
     se <tasto [freccia su] premuto?> allora
       cambia y di (1)
     fine
   fine
   ```

## Tecniche avanzate

### Gestione di input multipli

Per gestire più tasti contemporaneamente, puoi utilizzare script paralleli o condizioni multiple:

```
quando si clicca sulla bandiera verde
ripeti all'infinito
  se <tasto [freccia su] premuto?> allora
    cambia y di (1)
  fine
  se <tasto [freccia destra] premuto?> allora
    cambia x di (1)
  fine
fine
```

### Prevenzione del rimbalzo dei tasti

A volte, quando un tasto viene premuto, può generare più eventi di pressione in rapida successione. Per evitare questo "rimbalzo", puoi utilizzare variabili di stato o brevi attese:

```
quando si preme il tasto [spazio]
se <(può sparare) = [vero]> allora
  porta [può sparare] a [falso]
  crea clone di [proiettile]
  attendi (0.2) secondi
  porta [può sparare] a [vero]
fine
```

### Personalizzazione dei controlli

Puoi permettere al giocatore di personalizzare i controlli utilizzando variabili per memorizzare i tasti assegnati:

```
quando si clicca sulla bandiera verde
chiedi [Quale tasto vuoi usare per muoverti in alto?] e attendi
porta [tasto su] a (risposta)
```

## Applicazione al progetto Frogger

Nel nostro progetto Frogger, utilizzeremo eventi e input da tastiera per implementare il controllo della rana:

1. **Movimento a salti**: La rana si muoverà a scatti quando vengono premuti i tasti freccia
   ```
   quando si preme il tasto [freccia su]
   punta in direzione (0)
   passa al costume [rana su]
   cambia y di (30)
   ```

2. **Rotazione della rana**: La rana cambierà direzione in base al tasto premuto
   ```
   quando si preme il tasto [freccia destra]
   punta in direzione (90)
   passa al costume [rana destra]
   cambia x di (30)
   ```

3. **Limiti di movimento**: Impediremo alla rana di uscire dallo schermo
   ```
   quando si preme il tasto [freccia su]
   se <(posizione y) < (180)> allora
     punta in direzione (0)
     passa al costume [rana su]
     cambia y di (30)
   fine
   ```

4. **Riavvio del gioco**: Utilizzeremo un tasto specifico per riavviare il gioco dopo una partita
   ```
   quando si preme il tasto [r]
   invia a tutti [riavvia gioco]
   ```

Questi concetti di eventi e input da tastiera sono fondamentali per creare un'esperienza di gioco reattiva e coinvolgente. Nel nostro progetto Frogger, permetteranno al giocatore di controllare la rana in modo intuitivo e preciso.

Ora che abbiamo esplorato tutti i concetti teorici fondamentali, siamo pronti per iniziare a implementare il nostro gioco Frogger, partendo dalla creazione della rana e dal suo movimento base.

## Navigazione del Corso
- [📑 Indice](../README.md)
- [⬅️ Blocchi e script](./04-BlocchiEScript.md)
- [➡️ Movimento e controllo](../02-MovimentoEControllo/README.md)