# Rilevamento delle collisioni

In questa guida, esploreremo le tecniche per implementare il rilevamento delle collisioni nel nostro gioco Frogger. Il rilevamento delle collisioni è un elemento fondamentale che permette di identificare quando la rana interagisce con gli ostacoli o altri elementi del gioco.

## Principi del rilevamento delle collisioni

Il rilevamento delle collisioni è il processo che determina quando due o più oggetti nel gioco si sovrappongono o entrano in contatto. In Frogger, abbiamo principalmente due tipi di collisioni da gestire:

### 1. Collisioni negative (ostacoli)

Queste sono collisioni che causano la perdita di una vita o il reset della posizione della rana:
- Collisioni con veicoli sulla strada
- Caduta nell'acqua (quando non si è su un tronco o una tartaruga)

### 2. Collisioni positive (piattaforme e obiettivi)

Queste sono collisioni che aiutano il giocatore o rappresentano obiettivi:
- Salire su tronchi o tartarughe
- Raggiungere le zone sicure (ninfee) alla fine del livello

## Tecniche di rilevamento delle collisioni in Scratch

Scratch offre diversi metodi per rilevare le collisioni, ognuno con i propri vantaggi e limitazioni.

### 1. Rilevamento basato sugli sprite

Il metodo più semplice utilizza il blocco "sta toccando":

```
se <sta toccando [nome dello sprite v]?> allora
  [azioni da eseguire in caso di collisione]
fine
```

Questo metodo funziona bene per oggetti con forme semplici, ma può essere impreciso per forme complesse o trasparenti.

### 2. Rilevamento basato sui colori

Un metodo più preciso utilizza il rilevamento dei colori:

```
se <sta toccando il colore [#FF0000]?> allora
  [azioni da eseguire in caso di collisione]
fine
```

Questo approccio richiede che gli elementi con cui vogliamo rilevare le collisioni abbiano colori specifici e riconoscibili.

### 3. Rilevamento basato sulla distanza

Per oggetti circolari o quando è necessaria maggiore precisione, possiamo calcolare la distanza tra gli sprite:

```
se <((distanza da [altro sprite v]) < (soglia))> allora
  [azioni da eseguire in caso di collisione]
fine
```

Dove la distanza può essere calcolata con la formula:

```
√((x1 - x2)² + (y1 - y2)²)
```

In Scratch, possiamo utilizzare la variabile "distanza da" che calcola automaticamente questa formula.

## Implementazione delle collisioni in Frogger

### Collisioni con i veicoli

Per rilevare quando la rana viene colpita da un veicolo:

```
// Nello script della rana
ripeti sempre
  per ogni [veicolo v] in [lista di veicoli v]
    se <sta toccando [veicolo v]?> allora
      [gestisci collisione]
    fine
  fine
fine
```

Oppure, in modo più efficiente:

```
// Nello script di ogni veicolo
ripeti sempre
  se <sta toccando [Rana v]?> allora
    invia a tutti [collisione v]
  fine
fine

// Nello script della rana
quando ricevo [collisione v]
[gestisci collisione]
```

### Collisioni con l'acqua

Per rilevare quando la rana cade nell'acqua:

```
ripeti sempre
  se <(y position) < (150) e (y position) > (50)> allora
    se <non <(sta toccando [Tronco v]?) o (sta toccando [Tartaruga v]?)>> allora
      [gestisci caduta nell'acqua]
    fine
  fine
fine
```

Un approccio alternativo è utilizzare un colore specifico per l'acqua e rilevare quando la rana lo tocca senza essere su una piattaforma.

### Movimento sulle piattaforme

Quando la rana sale su un tronco o una tartaruga, deve muoversi insieme ad essi:

```
ripeti sempre
  se <sta toccando [Tronco v]?> allora
    cambia x di (velocità del tronco)
  fine
fine
```

Per le tartarughe che si immergono:

```
ripeti sempre
  se <sta toccando [Tartaruga v]?> allora
    se <(solido) di [Tartaruga v] = [1]> allora
      cambia x di (velocità della tartaruga)
    altrimenti
      [gestisci caduta nell'acqua]
    fine
  fine
fine
```

### Raggiungimento degli obiettivi

Per rilevare quando la rana raggiunge una zona sicura:

```
ripeti sempre
  se <sta toccando [Ninfea v]?> allora
    se <non ([ninfea occupata]?)> allora
      [gestisci raggiungimento obiettivo]
      porta [ninfea occupata] a [vero]
    fine
  fine
fine
```

## Gestione delle collisioni

Una volta rilevata una collisione, dobbiamo gestirla appropriatamente:

### Gestione delle collisioni negative

```
definiamo [gestisci collisione]
  cambia [vite v] di (-1)
  se <(vite) > (0)> allora
    [effetto sonoro collisione]
    [effetto visivo]
    vai a x: (0) y: (-180)  // Posizione iniziale
  altrimenti
    invia a tutti [game over v]
  fine
fine
```

### Gestione del movimento sulle piattaforme

```
definiamo [aggiorna posizione su piattaforma]
  se <sta toccando [Tronco v]?> allora
    porta [piattaforma attuale] a [Tronco v]
    porta [velocità piattaforma] a (velocità del tronco)
  altrimenti se <sta toccando [Tartaruga v]?> allora
    se <(solido) di [Tartaruga v] = [1]> allora
      porta [piattaforma attuale] a [Tartaruga v]
      porta [velocità piattaforma] a (velocità della tartaruga)
    altrimenti
      [gestisci caduta nell'acqua]
    fine
  altrimenti
    porta [piattaforma attuale] a [nessuna]
    porta [velocità piattaforma] a [0]
  fine
  
  se <non <(piattaforma attuale) = [nessuna]>> allora
    cambia x di (velocità piattaforma)
  fine
fine
```

## Ottimizzazione del rilevamento delle collisioni

### Riduzione del carico di elaborazione

Il rilevamento delle collisioni può essere intensivo in termini di risorse, specialmente con molti oggetti. Alcune strategie per ottimizzare:

1. **Controllo della distanza preliminare**: Prima di utilizzare rilevamenti più precisi, verifica se gli oggetti sono abbastanza vicini

```
se <((distanza da [veicolo v]) < (50))> allora
  se <sta toccando [veicolo v]?> allora
    [gestisci collisione]
  fine
fine
```

2. **Limitazione dell'area di controllo**: Controlla le collisioni solo nelle aree rilevanti

```
se <(y position) > (0) e (y position) < (100)> allora
  [controlla collisioni con veicoli]
altrimenti se <(y position) > (100) e (y position) < (200)> allora
  [controlla collisioni con elementi del fiume]
fine
```

3. **Riduzione della frequenza dei controlli**: Non è sempre necessario controllare le collisioni ad ogni frame

```
se <(timer) mod (0.1) < (0.01)> allora
  [controlla collisioni]
fine
```

### Hitbox personalizzate

Per collisioni più precise, possiamo creare hitbox personalizzate:

1. Utilizza sprite invisibili più piccoli come "sensori" di collisione
2. Posiziona questi sensori nelle parti critiche degli sprite principali
3. Utilizza questi sensori per il rilevamento delle collisioni invece degli sprite completi

## Debugging del rilevamento delle collisioni

Il rilevamento delle collisioni può essere difficile da debuggare. Alcuni suggerimenti:

1. **Visualizzazione delle hitbox**: Temporaneamente, rendi visibili le aree di collisione
2. **Logging**: Utilizza la funzione "dire" per visualizzare quando vengono rilevate le collisioni
3. **Rallentamento**: Temporaneamente, rallenta il gioco per osservare meglio le collisioni

## Conclusione

Il rilevamento delle collisioni è un elemento cruciale del nostro gioco Frogger. Implementando correttamente queste tecniche, possiamo creare un'esperienza di gioco reattiva e intuitiva. Nella prossima guida, esploreremo come implementare un sistema di vite e la logica di game over per gestire le conseguenze delle collisioni.

## Navigazione del Corso
- [📑 Indice](../README.md)
- [⬅️ Algoritmi di movimento per gli ostacoli](./02-MovimentoOstacoli.md)
- [➡️ Sistema di vite e game over](./04-SistemaVite.md)