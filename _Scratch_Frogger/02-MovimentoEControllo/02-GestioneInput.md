# Gestione avanzata degli input

In questa guida, esploreremo le tecniche avanzate per gestire gli input da tastiera in Scratch, un aspetto fondamentale per creare controlli reattivi e precisi per la nostra rana nel gioco Frogger.

## Tipi di input in Scratch

Scratch offre diversi metodi per rilevare e gestire gli input dell'utente:

### Input da tastiera

- **Tasti freccia**: Ideali per il movimento direzionale
- **Tasti WASD**: Un'alternativa comune per il movimento
- **Tasti spazio/invio**: Spesso utilizzati per azioni speciali
- **Altri tasti**: Possono essere assegnati a funzioni specifiche

### Input da mouse

- **Clic del mouse**: Per interazioni puntuali
- **Posizione del puntatore**: Per controlli basati sulla posizione
- **Trascinamento**: Per interazioni più complesse

### Altri input

- **Microfono**: Per controlli basati sul volume
- **Webcam**: Per controlli basati sul movimento
- **Sensori esterni**: Se si utilizza Scratch con hardware aggiuntivo

## Gestione avanzata degli input da tastiera

### Rilevamento della pressione dei tasti

Scratch offre due approcci principali per rilevare la pressione dei tasti:

1. **Eventi di pressione dei tasti**:
   ```
   quando si preme tasto [freccia su v]
   [azioni da eseguire]
   ```
   Questo metodo esegue le azioni una volta quando il tasto viene premuto.

2. **Controllo continuo dello stato dei tasti**:
   ```
   ripeti sempre
     se <tasto [freccia su v] premuto?> allora
       [azioni da eseguire]
     fine
   fine
   ```
   Questo metodo controlla continuamente se un tasto è premuto, permettendo azioni ripetute.

### Gestione di input multipli

Per gestire la pressione simultanea di più tasti, possiamo utilizzare condizioni annidate:

```
ripeti sempre
  se <tasto [freccia su v] premuto?> allora
    se <tasto [freccia destra v] premuto?> allora
      [movimento in diagonale verso l'alto a destra]
    altrimenti
      [movimento verso l'alto]
    fine
  fine
fine
```

### Buffer di input

Per creare controlli più reattivi, possiamo implementare un buffer di input che memorizza temporaneamente gli input dell'utente:

```
variabile [ultimo_tasto] = ""

quando si preme tasto [qualsiasi v]
porta [ultimo_tasto] a (tasto premuto)

ripeti sempre
  se <(ultimo_tasto) = [freccia su]> allora
    [movimento verso l'alto]
    porta [ultimo_tasto] a ""
  fine
fine
```

## Applicazione al gioco Frogger

### Movimento a scatti vs. movimento continuo

In Frogger, il movimento della rana è tipicamente a scatti (un salto per ogni pressione del tasto). Possiamo implementarlo in due modi:

1. **Movimento a scatto con eventi**:
   ```
   quando si preme tasto [freccia su v]
   cambia y di (dimensione_cella)
   ```

2. **Movimento a scatto con controllo dello stato e cooldown**:
   ```
   variabile [cooldown] = 0
   
   ripeti sempre
     se <<tasto [freccia su v] premuto?> e <(cooldown) = 0>> allora
       cambia y di (dimensione_cella)
       porta [cooldown] a (10)
     fine
     se <(cooldown) > 0> allora
       cambia [cooldown] di (-1)
     fine
   fine
   ```
   Questo secondo approccio permette di controllare la frequenza dei salti.

### Prevenzione di input indesiderati

Per evitare che la rana si muova in diagonale o in modi non previsti, possiamo implementare un sistema di priorità degli input:

```
variabile [direzione_corrente] = "nessuna"

ripeti sempre
  se <tasto [freccia su v] premuto?> allora
    porta [direzione_corrente] a "su"
  altrimenti se <tasto [freccia giù v] premuto?> allora
    porta [direzione_corrente] a "giù"
  altrimenti se <tasto [freccia sinistra v] premuto?> allora
    porta [direzione_corrente] a "sinistra"
  altrimenti se <tasto [freccia destra v] premuto?> allora
    porta [direzione_corrente] a "destra"
  altrimenti
    porta [direzione_corrente] a "nessuna"
  fine
  
  se <(direzione_corrente) = [su]> allora
    [movimento verso l'alto]
  fine
  se <(direzione_corrente) = [giù]> allora
    [movimento verso il basso]
  fine
  [e così via...]
fine
```

### Feedback visivo per gli input

Per migliorare l'esperienza utente, possiamo aggiungere feedback visivi quando vengono rilevati input:

```
quando si preme tasto [freccia su v]
cambia y di (dimensione_cella)
cambia effetto [colore v] di (25)
attendi (0.1) secondi
rimuovi effetti grafici
```

## Tecniche avanzate

### Controlli personalizzabili

Possiamo implementare controlli personalizzabili permettendo al giocatore di scegliere i tasti:

```
variabile [tasto_su] = "freccia su"
variabile [tasto_giu] = "freccia giù"
[e così via...]

ripeti sempre
  se <tasto ((tasto_su)) premuto?> allora
    [movimento verso l'alto]
  fine
fine
```

### Modalità di controllo alternative

Possiamo offrire diverse modalità di controllo:

1. **Controllo a singolo tasto**: La rana ruota con un tasto e avanza con un altro
2. **Controllo con mouse**: La rana si muove nella direzione del puntatore
3. **Controllo automatico**: La rana avanza automaticamente e il giocatore controlla solo la direzione

## Conclusione

Una gestione avanzata degli input è fondamentale per creare un'esperienza di gioco fluida e reattiva in Frogger. Implementando tecniche come il buffer di input, il sistema di priorità e il feedback visivo, possiamo creare controlli che rispondono esattamente come previsto, migliorando significativamente la giocabilità.

## Esercizi pratici

1. Implementa un sistema di controllo che permetta alla rana di muoversi in diagonale
2. Crea un menu che permetta al giocatore di scegliere tra diverse modalità di controllo
3. Aggiungi feedback visivi e sonori per diversi tipi di input

## Risorse aggiuntive

- [Documentazione ufficiale di Scratch sugli eventi](https://en.scratch-wiki.info/wiki/Events_Blocks)
- [Tutorial su controlli avanzati in Scratch](https://scratch.mit.edu/studios/2045/)

---

[◀ Coordinate e sistema di posizionamento](./01-CoordinateEPosizionamento.md) | [Algoritmi di movimento ▶](./03-AlgoritmiMovimento.md)