# Algoritmi di movimento

## Introduzione agli algoritmi di movimento

Gli algoritmi di movimento sono fondamentali nella programmazione di videogiochi. In Scratch, possiamo implementare diversi tipi di movimento per rendere il nostro gioco Frogger più realistico e coinvolgente. In questa sezione, esploreremo i principali algoritmi di movimento che possiamo utilizzare per la nostra rana protagonista.

## Movimento a griglia

Il movimento a griglia è particolarmente adatto per Frogger, poiché il gioco originale utilizza questo tipo di movimento. In questo approccio, la rana si muove di un numero fisso di passi (o pixel) in una direzione specifica, saltando da una posizione all'altra sulla griglia di gioco.

### Implementazione in Scratch

```
Quando si preme [freccia su]
Punta in direzione (0)
Cambia y di (30)
```

Questo codice fa sì che la rana salti verso l'alto di 30 pixel ogni volta che viene premuto il tasto freccia su. Possiamo implementare un codice simile per le altre direzioni:

```
Quando si preme [freccia giù]
Punta in direzione (180)
Cambia y di (-30)

Quando si preme [freccia destra]
Punta in direzione (90)
Cambia x di (30)

Quando si preme [freccia sinistra]
Punta in direzione (-90)
Cambia x di (-30)
```

## Movimento fluido

Per un'esperienza di gioco più moderna, potremmo voler implementare un movimento fluido anziché a scatti. In questo caso, la rana si muoverebbe continuamente finché il tasto direzionale è premuto.

### Implementazione in Scratch

```
Quando si preme bandiera verde
Per sempre
  Se <tasto [freccia su] premuto?> allora
    Punta in direzione (0)
    Fai (5) passi
  Fine
  Se <tasto [freccia giù] premuto?> allora
    Punta in direzione (180)
    Fai (5) passi
  Fine
  Se <tasto [freccia destra] premuto?> allora
    Punta in direzione (90)
    Fai (5) passi
  Fine
  Se <tasto [freccia sinistra] premuto?> allora
    Punta in direzione (-90)
    Fai (5) passi
  Fine
Fine
```

## Movimento con accelerazione

Per un movimento ancora più realistico, potremmo implementare un'accelerazione, dove la rana inizia a muoversi lentamente e poi accelera fino a raggiungere una velocità massima.

### Implementazione in Scratch

```
Quando si preme bandiera verde
Imposta [velocità v] a [0]
Per sempre
  Se <tasto [freccia su] premuto?> allora
    Punta in direzione (0)
    Cambia [velocità v] di [0.5]
    Se <(velocità) > [10]> allora
      Imposta [velocità v] a [10]
    Fine
  Altrimenti
    Imposta [velocità v] a [0]
  Fine
  Fai (velocità) passi
Fine
```

Questo codice implementa un'accelerazione semplice per il movimento verso l'alto. Possiamo estenderlo per includere tutte le direzioni.

## Considerazioni per Frogger

Per il nostro gioco Frogger, il movimento a griglia è probabilmente la scelta migliore, poiché riflette il gameplay del gioco originale. Tuttavia, potremmo voler aggiungere alcune animazioni durante il salto per rendere il movimento più fluido visivamente, pur mantenendo la meccanica di movimento a griglia.

## Esercizio pratico

Prova a implementare il movimento a griglia per la tua rana in Scratch, utilizzando il codice fornito come punto di partenza. Poi, sperimenta con gli altri tipi di movimento per vedere quale preferisci per il tuo gioco.

## Sfida aggiuntiva

Prova a combinare il movimento a griglia con un'animazione di salto. Puoi farlo cambiando il costume della rana durante il movimento per simulare un salto, anche se la posizione effettiva cambia istantaneamente.

```
Quando si preme [freccia su]
Punta in direzione (0)
Cambia costume in [rana-salto]
Attendi (0.1) secondi
Cambia y di (30)
Cambia costume in [rana-normale]
```

Questo codice fa sì che la rana cambi brevemente costume prima di saltare, creando l'illusione di un movimento più fluido pur mantenendo la meccanica di movimento a griglia.