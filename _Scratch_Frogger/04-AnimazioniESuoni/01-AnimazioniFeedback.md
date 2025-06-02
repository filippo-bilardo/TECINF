# Animazioni e feedback visivo

In questa guida, esploreremo come implementare animazioni e feedback visivo nel nostro gioco Frogger. Questi elementi sono fondamentali per creare un'esperienza di gioco coinvolgente e reattiva, fornendo informazioni visive immediate al giocatore sulle sue azioni e sugli eventi di gioco.

## Importanza delle animazioni nei videogiochi

Le animazioni nei videogiochi servono a diversi scopi:

1. **Feedback visivo**: Comunicano al giocatore che le sue azioni hanno avuto effetto
2. **Miglioramento dell'immersione**: Rendono il mondo di gioco più vivo e credibile
3. **Guida dell'attenzione**: Dirigono l'attenzione del giocatore verso elementi importanti
4. **Comunicazione di informazioni**: Trasmettono informazioni sullo stato del gioco

## Tipi di animazioni in Scratch

Scratch offre diverse tecniche per creare animazioni:

### 1. Animazioni basate sui costumi

Questa è la tecnica più comune in Scratch, dove si alternano diversi costumi di uno sprite per creare l'illusione del movimento.

```
quando si clicca sulla bandiera verde
ripeti sempre
  passa al costume seguente
  attendi (0.1) secondi
fine
```

### 2. Animazioni basate sul movimento

Queste animazioni spostano lo sprite sullo schermo per creare l'effetto di movimento.

```
quando si clicca sulla bandiera verde
ripeti sempre
  scivola in (1) secondi a x: (posizione x casuale) y: (posizione y casuale)
fine
```

### 3. Animazioni basate sugli effetti grafici

Scratch offre vari effetti grafici che possono essere applicati agli sprite per creare effetti visivi interessanti.

```
quando si clicca sulla bandiera verde
ripeti sempre
  cambia effetto [colore v] di (25)
  attendi (0.2) secondi
fine
```

### 4. Animazioni basate sulla rotazione

La rotazione degli sprite può creare effetti visivi interessanti.

```
quando si clicca sulla bandiera verde
ripeti sempre
  ruota di (15) gradi
  attendi (0.1) secondi
fine
```

## Implementazione delle animazioni in Frogger

### Animazione della rana

#### 1. Animazione del salto

Per rendere più realistico il movimento della rana, possiamo animare il salto quando il giocatore preme un tasto direzionale:

```
definiamo [salta verso l'alto]
porta [direzione v] a [90]
porta [in movimento v] a [vero]
pass al costume [rana salto v]
attendi (0.1) secondi
cambia y di (10)
attendi (0.1) secondi
cambia y di (10)
pass al costume [rana normale v]
porta [in movimento v] a [falso]
```

Possiamo creare script simili per le altre direzioni.

#### 2. Animazione della collisione

Quando la rana collide con un ostacolo, possiamo creare un'animazione per comunicare visivamente l'evento:

```
definiamo [animazione collisione]
effetto [fantasma v] per (0.3) secondi
effetto [mosaico v] per (0.3) secondi
pass al costume [rana schiacciata v]
attendi (0.5) secondi
pass al costume [rana normale v]
```

#### 3. Animazione dell'arrivo

Quando la rana raggiunge una ninfea, possiamo creare un'animazione celebrativa:

```
definiamo [animazione arrivo]
ripeti (5)
  effetto [luminosità v] per (0.2) secondi
  effetto [colore v] per (0.2) secondi
fine
```

### Animazione degli ostacoli

#### 1. Animazione dei veicoli

I veicoli possono avere animazioni semplici come il movimento delle ruote o effetti di luce:

```
// Per un camion
quando si clicca sulla bandiera verde
ripeti sempre
  se <(velocità) > (0)> allora
    passa al costume seguente
    attendi (0.2) secondi
  fine
fine
```

#### 2. Animazione delle tartarughe

Le tartarughe nel fiume possono immergersi periodicamente:

```
quando si clicca sulla bandiera verde
porta [immersa v] a [falso]
ripeti sempre
  attendi (5) secondi
  // Inizio immersione
  porta [immersa v] a [vero]
  pass al costume [tartaruga semi-immersa v]
  attendi (0.5) secondi
  pass al costume [tartaruga immersa v]
  attendi (1) secondi
  // Riemersione
  pass al costume [tartaruga semi-immersa v]
  attendi (0.5) secondi
  pass al costume [tartaruga normale v]
  porta [immersa v] a [falso]
fine
```

#### 3. Animazione dei tronchi

I tronchi possono avere un'animazione semplice di ondeggiamento sull'acqua:

```
quando si clicca sulla bandiera verde
ripeti sempre
  cambia y di (1)
  attendi (0.5) secondi
  cambia y di (-1)
  attendi (0.5) secondi
fine
```

## Feedback visivo per eventi di gioco

### 1. Feedback per la perdita di una vita

```
definiamo [feedback perdita vita]
effetto [fantasma v] per (0.5) secondi
effetto [colore v] per (0.3) secondi
invia a tutti [lampeggia vite v]
```

### 2. Feedback per il guadagno di punti

```
definiamo [feedback punti]
crea clone di [indicatore punti v]

// Nello sprite "indicatore punti"
quando vengo clonato
porta a x: (x della rana) y: (y della rana)
dici unione di [+] e (punti guadagnati) per (1) secondi
scivola in (1) secondi a x: (x) y: (y + 50)
elimina questo clone
```

### 3. Feedback per il completamento del livello

```
definiamo [feedback livello completato]
ripeti (10)
  effetto [colore v] di (25)
  attendi (0.1) secondi
fine
ripristina effetti grafici
```

## Transizioni di scena

Le transizioni tra livelli o stati di gioco possono migliorare significativamente l'esperienza utente.

### 1. Transizione di inizio livello

```
definiamo [transizione inizio livello]
porta [transizione v] a [0]
mostra
ripeti fino a <(transizione) = (100)>
  cambia [transizione v] di (5)
  porta effetto [fantasma v] a (transizione)
  attendi (0.05) secondi
fine
nascondi
ripristina effetti grafici
```

### 2. Transizione di game over

```
definiamo [transizione game over]
mostra
porta in primo piano
porta effetto [mosaico v] a (0)
ripeti fino a <(effetto [mosaico v]) = (100)>
  cambia effetto [mosaico v] di (5)
  attendi (0.05) secondi
fine
```

## Ottimizzazione delle animazioni

### 1. Gestione delle prestazioni

Troppe animazioni contemporaneamente possono rallentare il gioco. Alcune strategie per ottimizzare:

- Limitare il numero di sprite animati contemporaneamente
- Utilizzare animazioni più semplici per oggetti distanti o meno importanti
- Disattivare le animazioni quando non sono visibili sullo schermo

```
ripeti sempre
  se <([bordo sinistro dello stage] - (50)) < (x) e (x) < ([bordo destro dello stage] + (50))> allora
    porta [animazione attiva v] a [vero]
  altrimenti
    porta [animazione attiva v] a [falso]
  fine
fine
```

### 2. Sincronizzazione delle animazioni

Per sincronizzare diverse animazioni, possiamo utilizzare i messaggi broadcast:

```
quando ricevo [sincronizza animazioni v]
porta [contatore animazione v] a [0]
```

## Tecniche avanzate di animazione

### 1. Animazioni procedurali

Invece di utilizzare costumi predefiniti, possiamo generare animazioni proceduralmente:

```
quando si clicca sulla bandiera verde
cancella tutto
porta dimensione penna a (5)
ripeti sempre
  penna giù
  cambia effetto [colore v] di (5)
  vai a x: (20 * [sin v] di (timer * 360)) y: (20 * [cos v] di (timer * 360))
  attendi (0.01) secondi
fine
```

### 2. Animazioni basate sulla fisica

Possiamo simulare comportamenti fisici per animazioni più realistiche:

```
quando si clicca sulla bandiera verde
porta [velocità y v] a [0]
porta [gravità v] a [-0.5]
ripeti sempre
  cambia [velocità y v] di (gravità)
  cambia y di (velocità y)
  se <(y) < (-180)> allora
    porta [velocità y v] a [10]
  fine
  attendi (0.01) secondi
fine
```

## Conclusione

Le animazioni e il feedback visivo sono elementi cruciali per creare un'esperienza di gioco coinvolgente e reattiva. Implementando queste tecniche nel nostro gioco Frogger, possiamo migliorare significativamente la qualità percepita del gioco e fornire al giocatore informazioni immediate sulle sue azioni e sugli eventi di gioco.

Nella prossima guida, esploreremo come implementare effetti sonori e musica di sottofondo per completare l'esperienza audiovisiva del nostro gioco.

## Navigazione del Corso
- [📑 Indice](../README.md)
- [⬅️ Sistema di vite e game over](../03-OstacoliECollisioni/04-SistemaVite.md)
- [➡️ Effetti sonori e musica](./02-EffettiSonori.md)