# Sistema di vite e game over

In questa guida, esploreremo come implementare un sistema di vite e la logica di game over nel nostro gioco Frogger. Questi elementi sono fondamentali per creare una sfida bilanciata e fornire feedback al giocatore sulle sue prestazioni.

## Sistema di vite

Un sistema di vite ben progettato aggiunge tensione al gameplay e dà al giocatore più opportunità di completare il livello prima di dover ricominciare da capo.

### Implementazione delle vite in Scratch

#### 1. Inizializzazione delle vite

All'inizio del gioco, dobbiamo impostare il numero di vite disponibili:

```
quando si clicca sulla bandiera verde
porta [vite v] a [3]
```

#### 2. Visualizzazione delle vite

Possiamo visualizzare le vite in diversi modi:

**Utilizzo di testo**:

```
ripeti sempre
  dire unione di [Vite: ] e (vite)
fine
```

**Utilizzo di sprite**:

```
quando si clicca sulla bandiera verde
nascondi
porta [vite visualizzate v] a [0]
ripeti sempre
  se <(vite visualizzate) < (vite)> allora
    crea clone di [me stesso v]
    cambia [vite visualizzate v] di (1)
  fine
  se <(vite visualizzate) > (vite)> allora
    porta [vite visualizzate v] a (vite)
    invia a tutti [aggiorna vite v]
  fine
fine

quando vengo clonato
mostra
porta a x: ((-200) + ((vite visualizzate) * (30))) y: (170)
```

#### 3. Perdita di una vita

Quando la rana collide con un ostacolo o cade nell'acqua, dobbiamo decrementare il contatore delle vite:

```
definiamo [perdi vita]
cambia [vite v] di (-1)
[effetto sonoro perdita vita]
effetto [fantasma v] per (0.5) secondi
se <(vite) > (0)> allora
  vai a x: (0) y: (-180)  // Posizione iniziale
altrimenti
  invia a tutti [game over v]
fine
```

#### 4. Guadagnare vite extra (opzionale)

Possiamo premiare il giocatore con vite extra al raggiungimento di determinati obiettivi:

```
se <(punteggio) > (1000) e <non (vita extra guadagnata)>> allora
  cambia [vite v] di (1)
  porta [vita extra guadagnata v] a [vero]
  [effetto sonoro vita extra]
fine
```

## Implementazione del game over

Il game over si verifica quando il giocatore esaurisce tutte le vite disponibili.

### 1. Rilevamento del game over

```
quando ricevo [game over v]
nascondi  // Nascondi la rana
[effetto sonoro game over]
ferma [tutti gli altri script v]
```

### 2. Schermata di game over

Possiamo creare uno sprite specifico per la schermata di game over:

```
// Nello sprite "Schermata Game Over"
quando si clicca sulla bandiera verde
nascondi

quando ricevo [game over v]
mostra
porta in primo piano
porta a x: (0) y: (0)
dici [Game Over!] per (2) secondi
dici unione di [Punteggio finale: ] e (punteggio) per (2) secondi
se <(punteggio) > (record)> allora
  porta [record v] a (punteggio)
  dici [Nuovo record!] per (2) secondi
fine
dici [Clicca sulla bandiera verde per ricominciare] per (2) secondi
```

### 3. Salvataggio del record (opzionale)

Per mantenere il record anche dopo la chiusura del gioco, possiamo utilizzare le variabili persistenti di Scratch:

```
quando si clicca sulla bandiera verde
se <(record) = [0]> allora  // Se è la prima volta che si gioca
  porta [record v] a [0]
fine
```

## Integrazione con il sistema di collisioni

Il sistema di vite deve essere integrato con il sistema di rilevamento delle collisioni che abbiamo implementato in precedenza.

### Esempio di integrazione

```
// Nello script della rana
quando ricevo [collisione v]
perdi vita

// Nello script di ogni veicolo
ripeti sempre
  se <sta toccando [Rana v]?> allora
    invia a tutti [collisione v]
  fine
fine

// Per la caduta nell'acqua
ripeti sempre
  se <(y position) < (150) e (y position) > (50)> allora
    se <non <(sta toccando [Tronco v]?) o (sta toccando [Tartaruga v]?)>> allora
      invia a tutti [collisione v]
    fine
  fine
fine
```

## Feedback visivo e sonoro

Per migliorare l'esperienza di gioco, è importante fornire feedback visivo e sonoro quando il giocatore perde una vita o quando si verifica il game over.

### Feedback visivo

```
definiamo [effetto visivo perdita vita]
effetto [fantasma v] per (0.5) secondi
effetto [colore v] per (0.3) secondi
```

### Feedback sonoro

Possiamo utilizzare suoni diversi per eventi diversi:

- Suono per la perdita di una vita
- Suono per il game over
- Suono per il guadagno di una vita extra

## Bilanciamento della difficoltà

Il numero di vite deve essere bilanciato in base alla difficoltà del gioco:

- **Troppo facile**: Se il giocatore raramente perde tutte le vite, il gioco potrebbe risultare noioso.
- **Troppo difficile**: Se il giocatore perde tutte le vite troppo rapidamente, potrebbe frustrarsi e abbandonare il gioco.

Considerate di testare il gioco con diversi numeri di vite iniziali (3-5 è generalmente un buon punto di partenza) e osservate quanto tempo impiegano i giocatori per completare il livello o perdere tutte le vite.

## Estensioni del sistema

### 1. Sistema di checkpoint

Per livelli più lunghi, potrebbe essere utile implementare un sistema di checkpoint:

```
se <sta toccando [Checkpoint v]?> allora
  porta [checkpoint attuale v] a (posizione attuale)
fine

definiamo [perdi vita]
cambia [vite v] di (-1)
se <(vite) > (0)> allora
  vai a x: (x di (checkpoint attuale)) y: (y di (checkpoint attuale))
altrimenti
  invia a tutti [game over v]
fine
```

### 2. Indicatore di invulnerabilità temporanea

Dopo aver perso una vita, potrebbe essere utile rendere la rana temporaneamente invulnerabile per evitare perdite di vite consecutive:

```
definiamo [perdi vita]
cambia [vite v] di (-1)
porta [invulnerabile v] a [vero]
effetto [fantasma v] per (2) secondi
attendi (2) secondi
porta [invulnerabile v] a [falso]
```

E poi nel rilevamento delle collisioni:

```
se <sta toccando [veicolo v]?> e <non (invulnerabile)>> allora
  perdi vita
fine
```

## Conclusione

Un sistema di vite ben implementato e una logica di game over chiara sono elementi fondamentali per creare un'esperienza di gioco coinvolgente. Questi sistemi forniscono al giocatore feedback immediato sulle sue azioni e aggiungono tensione al gameplay.

Nella prossima guida, esploreremo come implementare animazioni e suoni per rendere il nostro gioco Frogger ancora più coinvolgente e reattivo.

## Navigazione del Corso
- [📑 Indice](../README.md)
- [⬅️ Rilevamento delle collisioni](./03-RilevamentoCollisioni.md)
- [➡️ Animazioni e feedback visivo](../04-AnimazioniESuoni/01-AnimazioniFeedback.md)