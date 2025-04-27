# Collisioni e interazioni

In questa guida, esploreremo come gestire le collisioni e le interazioni tra gli sprite in Scratch, elementi fondamentali per il nostro gioco Frogger dove la rana deve interagire con vari oggetti nell'ambiente.

## Rilevamento delle collisioni in Scratch

Scratch offre diversi metodi per rilevare quando gli sprite entrano in contatto tra loro:

### Blocco "sta toccando?"

Il blocco più semplice per rilevare le collisioni è il blocco "sta toccando?":

```
se <sta toccando [nome dello sprite v]?> allora
  [azioni da eseguire]
fine
```

Questo blocco verifica se lo sprite corrente sta toccando un altro sprite specifico, un colore o il bordo dello stage.

### Blocco "sta toccando il colore?"

Per collisioni più precise, possiamo utilizzare il rilevamento basato sul colore:

```
se <sta toccando il colore [#FF0000]?> allora
  [azioni da eseguire]
fine
```

Questo è utile quando vogliamo rilevare il contatto con parti specifiche di altri sprite o dello sfondo.

### Blocco "colore sta toccando?"

Per una precisione ancora maggiore, possiamo verificare se un colore specifico dello sprite sta toccando un altro colore:

```
se <colore [#00FF00] sta toccando [#0000FF]?> allora
  [azioni da eseguire]
fine
```

## Implementazione delle collisioni in Frogger

### Collisioni con ostacoli

In Frogger, la rana deve evitare vari ostacoli come le auto. Possiamo implementare questa logica così:

```
ripeti sempre
  se <sta toccando [auto v]?> allora
    invia a tutti [game over v]
    ferma [questo script v]
  fine
fine
```

Per gestire più tipi di veicoli, possiamo utilizzare una lista di sprite o verificare ciascuno separatamente:

```
ripeti sempre
  se <<sta toccando [auto1 v]?> o <sta toccando [auto2 v]?>> allora
    invia a tutti [game over v]
    ferma [questo script v]
  fine
fine
```

### Collisioni con l'acqua

Nel gioco Frogger, la rana non può nuotare e deve utilizzare i tronchi o le tartarughe per attraversare il fiume. Possiamo implementare questa meccanica utilizzando il rilevamento del colore:

```
ripeti sempre
  se <<sta toccando il colore [#0000FF]?> e <non <sta toccando [tronco v]?>>> allora
    invia a tutti [game over v]
    ferma [questo script v]
  fine
fine
```

### Raggiungimento della destinazione

Per rilevare quando la rana raggiunge una delle destinazioni sicure, possiamo utilizzare:

```
ripeti sempre
  se <sta toccando [destinazione v]?> allora
    invia a tutti [punto segnato v]
    vai a x: (0) y: (-150)
  fine
fine
```

## Interazioni avanzate

### Movimento sui tronchi galleggianti

Una delle meccaniche più interessanti di Frogger è che la rana si muove insieme ai tronchi quando ci salta sopra. Possiamo implementare questa interazione così:

```
ripeti sempre
  se <sta toccando [tronco v]?> allora
    cambia x di (velocità del tronco)
  fine
fine
```

Dove "velocità del tronco" è una variabile che contiene la velocità di movimento del tronco.

### Interazione con le tartarughe che si immergono

In alcune versioni di Frogger, le tartarughe si immergono periodicamente, facendo cadere la rana in acqua se si trova sopra di esse. Possiamo implementare questa meccanica così:

```
quando si clicca su bandiera verde
ripeti sempre
  attendi (5) secondi
  cambia effetto [fantasma v] di (10)
  ripeti (10)
    cambia effetto [fantasma v] di (10)
    attendi (0.1) secondi
  fine
  porta effetto [fantasma v] a (0)
fine
```

E nello script della rana:

```
ripeti sempre
  se <<sta toccando [tartaruga v]?> e <(effetto [fantasma v] di [tartaruga v]) > (50)>> allora
    invia a tutti [game over v]
    ferma [questo script v]
  fine
fine
```

## Ottimizzazione delle collisioni

### Uso di hitbox semplificate

Per migliorare le prestazioni e la precisione delle collisioni, possiamo utilizzare hitbox semplificate:

```
quando si clicca su bandiera verde
nascondi
crea clone di [me stesso v]

quando vengo clonato
cambia costume in [hitbox v]
nascondi
ripeti sempre
  vai a x: (x di [rana v]) y: (y di [rana v])
  se <sta toccando [ostacolo v]?> allora
    invia a tutti [collisione v]
  fine
fine
```

### Ottimizzazione con variabili di stato

Per evitare di controllare continuamente le collisioni, possiamo utilizzare variabili di stato:

```
variabile [in_acqua] = falso

quando si clicca su bandiera verde
ripeti sempre
  se <sta toccando il colore [#0000FF]?> allora
    porta [in_acqua] a [vero]
  altrimenti
    porta [in_acqua] a [falso]
  fine
  
  se <<(in_acqua) = [vero]> e <non <sta toccando [tronco v]?>>> allora
    invia a tutti [game over v]
    ferma [questo script v]
  fine
fine
```

## Feedback visivo e sonoro

Per migliorare l'esperienza di gioco, è importante fornire feedback quando avvengono collisioni o interazioni:

```
quando ricevo [collisione v]
cambia effetto [colore v] di (25)
riproduci suono [collisione v]
attendi (0.2) secondi
rimuovi effetti grafici
```

## Conclusione

Le collisioni e le interazioni sono elementi fondamentali per creare un gioco Frogger coinvolgente. Implementando correttamente il rilevamento delle collisioni con ostacoli, acqua e destinazioni, e aggiungendo interazioni speciali come il movimento sui tronchi, possiamo creare un'esperienza di gioco autentica e divertente.

## Esercizi pratici

1. Implementa un sistema di collisioni per la rana con diversi tipi di veicoli
2. Crea un meccanismo per il movimento della rana sui tronchi galleggianti
3. Aggiungi tartarughe che si immergono periodicamente
4. Implementa un feedback visivo e sonoro per diversi tipi di collisioni

## Risorse aggiuntive

- [Documentazione ufficiale di Scratch sui blocchi di rilevamento](https://en.scratch-wiki.info/wiki/Sensing_Blocks)
- [Tutorial su collisioni avanzate in Scratch](https://scratch.mit.edu/studios/3159697/)

---

[◀ Algoritmi di movimento](./03-AlgoritmiMovimento.md) | [Gestione del punteggio e delle vite ▶](./05-PunteggioEVite.md)