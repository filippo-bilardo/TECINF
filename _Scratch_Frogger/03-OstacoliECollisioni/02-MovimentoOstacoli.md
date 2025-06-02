# Algoritmi di movimento per gli ostacoli

In questa guida, esploreremo gli algoritmi di movimento che possiamo implementare per gli ostacoli nel nostro gioco Frogger. Il movimento degli ostacoli è un elemento cruciale che determina la difficoltà e la dinamica del gameplay.

## Principi di base del movimento degli ostacoli

Nel gioco Frogger, gli ostacoli seguono alcuni pattern di movimento fondamentali:

### 1. Movimento lineare

La maggior parte degli ostacoli in Frogger si muove in linea retta, orizzontalmente attraverso lo schermo:

- I veicoli si muovono da sinistra a destra o da destra a sinistra sulla strada
- I tronchi e le tartarughe si muovono orizzontalmente nel fiume

### 2. Velocità variabili

Diversi tipi di ostacoli si muovono a velocità diverse:

- Le auto piccole tendono a muoversi più velocemente dei camion
- I tronchi lunghi generalmente si muovono più lentamente di quelli corti
- Le corsie alternate spesso hanno velocità diverse per aumentare la sfida

### 3. Direzioni alternate

Per aumentare la difficoltà, le corsie adiacenti hanno spesso direzioni di movimento opposte:

- Una corsia di traffico va da sinistra a destra, quella successiva da destra a sinistra
- Lo stesso principio si applica alle corsie del fiume con tronchi e tartarughe

## Implementazione del movimento in Scratch

### Movimento base con blocchi di posizione

Il modo più semplice per implementare il movimento orizzontale è utilizzare i blocchi di posizione:

```
quando si clicca su ⚑
ripeti sempre
  cambia x di (velocità)
  se <(x position) > (bordo destro)> allora
    vai a x: (bordo sinistro) y: (y position)
  fine
fine
```

Per il movimento da destra a sinistra, basta utilizzare una velocità negativa e invertire i controlli dei bordi.

### Gestione del riavvolgimento (wrapping)

Quando un ostacolo esce dallo schermo, deve riapparire dal lato opposto. Questo è chiamato "wrapping" o "riavvolgimento":

```
quando si clicca su ⚑
ripeti sempre
  cambia x di (velocità)
  se <(x position) > (290)> allora
    vai a x: (-290) y: (y position)
  fine
fine
```

Per gli ostacoli che si muovono da destra a sinistra:

```
quando si clicca su ⚑
ripeti sempre
  cambia x di (-velocità)
  se <(x position) < (-290)> allora
    vai a x: (290) y: (y position)
  fine
fine
```

### Creazione di pattern di traffico

Per creare un flusso realistico di ostacoli, possiamo utilizzare la clonazione con tempistiche diverse:

```
quando si clicca su ⚑
nascondi
ripeti sempre
  crea clone di [me stesso v]
  attendi (intervallo) secondi
fine
```

E per ogni clone:

```
quando vengo clonato
mostra
vai a x: (-290) y: (y position)
ripeti fino a quando <(x position) > (290)>
  cambia x di (velocità)
fine
elimina questo clone
```

## Algoritmi avanzati di movimento

### Movimento con accelerazione

Per alcuni ostacoli, potremmo voler implementare un'accelerazione graduale invece di una velocità costante:

```
quando vengo clonato
mostra
vai a x: (-290) y: (y position)
porta velocità attuale a [0]
ripeti fino a quando <(x position) > (290)>
  porta velocità attuale a ((velocità attuale) + (accelerazione))
  se <(velocità attuale) > (velocità massima)> allora
    porta velocità attuale a (velocità massima)
  fine
  cambia x di (velocità attuale)
fine
elimina questo clone
```

### Movimento con variazioni casuali

Per rendere il gioco meno prevedibile, possiamo introdurre elementi casuali:

```
quando vengo clonato
mostra
vai a x: (-290) y: (y position)
porta velocità base a (velocità)
ripeti fino a quando <(x position) > (290)>
  porta velocità casuale a ((velocità base) + (numero a caso da (-0.5) a (0.5)))
  cambia x di (velocità casuale)
fine
elimina questo clone
```

### Movimento sincronizzato

Per creare pattern più complessi, possiamo sincronizzare il movimento di più ostacoli:

```
quando si clicca su ⚑
invia a tutti [inizia movimento v]
porta [fase] a [0]
ripeti sempre
  cambia [fase] di [1]
  attendi (0.1) secondi
fine
```

E per gli ostacoli:

```
quando ricevo [inizia movimento v]
ripeti sempre
  vai a x: ((-290) + ((fase) * (velocità))) y: (y position)
  se <(x position) > (290)> allora
    vai a x: (-290) y: (y position)
  fine
fine
```

## Ottimizzazione del movimento

### Gestione efficiente dei cloni

Per evitare di sovraccaricare il gioco con troppi cloni:

1. Limita il numero massimo di cloni attivi contemporaneamente
2. Elimina i cloni non appena escono dallo schermo
3. Utilizza una variabile per tenere traccia del numero di cloni attivi

### Movimento basato su timer

Per un movimento più fluido e meno dipendente dalle prestazioni del computer:

```
quando si clicca su ⚑
porta [ultimo tempo] a [timer]
ripeti sempre
  porta [delta tempo] a ((timer) - (ultimo tempo))
  porta [ultimo tempo] a [timer]
  cambia x di ((velocità) * (delta tempo))
  se <(x position) > (290)> allora
    vai a x: (-290) y: (y position)
  fine
fine
```

## Implementazione pratica

### Esempio: Traffico a più corsie

Per implementare il traffico su più corsie con direzioni alternate:

1. Crea uno sprite "controller" che gestisce la creazione degli ostacoli
2. Per ogni corsia, definisci:
   - La posizione y
   - La direzione (positiva o negativa)
   - La velocità base
   - L'intervallo di generazione
3. Il controller crea i cloni appropriati per ogni corsia

### Esempio: Movimento delle tartarughe

Le tartarughe nel gioco Frogger hanno un comportamento speciale: si immergono periodicamente, rendendo impossibile per la rana stare sopra di loro in quel momento:

```
quando vengo clonato
mostra
vai a x: (-290) y: (y position)
ripeti fino a quando <(x position) > (290)>
  cambia x di (velocità)
  se <(timer) mod (10) < (3)> allora
    passa al costume [immerso v]
    porta [solido] a [0]
  altrimenti
    passa al costume [normale v]
    porta [solido] a [1]
  fine
fine
elimina questo clone
```

## Sfide e soluzioni

### Gestione delle collisioni durante il movimento

Quando implementiamo il movimento degli ostacoli, dobbiamo considerare come gestire le collisioni con la rana:

1. Possiamo controllare le collisioni all'interno dello script di movimento di ogni ostacolo
2. Oppure possiamo centralizzare il controllo delle collisioni nello script della rana

La seconda opzione è generalmente più efficiente, soprattutto con molti ostacoli.

### Sincronizzazione del movimento con il gameplay

Per garantire che il gioco sia giocabile e bilanciato:

1. Adatta le velocità e gli intervalli in base al livello di difficoltà
2. Assicurati che ci siano sempre spazi sufficienti tra gli ostacoli per permettere il passaggio
3. Considera di creare "pattern" riconoscibili che i giocatori possano imparare

## Conclusione

Gli algoritmi di movimento per gli ostacoli sono fondamentali per creare un'esperienza di gioco Frogger coinvolgente e sfidante. Sperimentando con diverse velocità, pattern e comportamenti, puoi creare un gioco che sia sia impegnativo che divertente. Nella prossima guida, esploreremo come implementare il rilevamento delle collisioni tra la rana e questi ostacoli in movimento.

## Navigazione del Corso
- [📑 Indice](../README.md)
- [⬅️ Creazione e gestione degli sprite ostacoli](./01-CreazioneOstacoli.md)
- [➡️ Rilevamento delle collisioni](./03-RilevamentoCollisioni.md)