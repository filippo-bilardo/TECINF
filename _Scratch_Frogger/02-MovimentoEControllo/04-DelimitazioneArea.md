# Delimitazione dell'area di gioco

## Importanza della delimitazione

In un videogioco come Frogger, è fondamentale definire chiaramente i limiti dell'area di gioco. Senza questi limiti, il giocatore potrebbe muovere la rana al di fuori dello schermo, rendendo impossibile continuare a giocare. La delimitazione dell'area di gioco è quindi un aspetto cruciale della progettazione del gameplay.

## Implementazione dei limiti in Scratch

In Scratch, possiamo implementare i limiti dell'area di gioco utilizzando condizioni che verificano la posizione dello sprite e impediscono movimenti che lo porterebbero fuori dai confini stabiliti.

### Utilizzo delle coordinate

Scratch utilizza un sistema di coordinate cartesiane dove:
- L'origine (0,0) è al centro dello stage
- L'asse X va da -240 a 240 (larghezza totale: 480 pixel)
- L'asse Y va da -180 a 180 (altezza totale: 360 pixel)

Possiamo utilizzare queste coordinate per definire i limiti dell'area di gioco.

### Esempio di codice per la delimitazione

```
Quando si preme [freccia su]
Punta in direzione (0)
Se <(y position) < [170]> allora
  Cambia y di (30)
Fine

Quando si preme [freccia giù]
Punta in direzione (180)
Se <(y position) > [-170]> allora
  Cambia y di (-30)
Fine

Quando si preme [freccia destra]
Punta in direzione (90)
Se <(x position) < [230]> allora
  Cambia x di (30)
Fine

Quando si preme [freccia sinistra]
Punta in direzione (-90)
Se <(x position) > [-230]> allora
  Cambia x di (-30)
Fine
```

In questo esempio, abbiamo aggiunto condizioni che verificano se la rana si trova già al limite dell'area di gioco. Se la rana è al limite, il movimento in quella direzione viene impedito.

## Approcci alternativi

### Rimbalzo ai bordi

Un approccio alternativo è quello di utilizzare il blocco "rimbalza quando tocchi il bordo" di Scratch:

```
Quando si preme bandiera verde
Per sempre
  Rimbalza quando tocchi il bordo
Fine
```

Tuttavia, questo approccio non è ideale per Frogger, poiché vogliamo semplicemente impedire il movimento oltre i bordi, non far rimbalzare la rana.

### Teletrasporto al bordo opposto

In alcuni giochi, come Pac-Man, quando il personaggio esce da un lato dello schermo, riappare dal lato opposto. Potremmo implementare questa meccanica in Frogger per alcune aree specifiche:

```
Quando si preme bandiera verde
Per sempre
  Se <(x position) > [240]> allora
    Porta x a [-240]
  Fine
  Se <(x position) < [-240]> allora
    Porta x a [240]
  Fine
Fine
```

## Delimitazione specifica per Frogger

Nel gioco Frogger originale, ci sono alcune considerazioni specifiche per la delimitazione dell'area di gioco:

1. La rana non può tornare indietro una volta raggiunta la zona sicura in alto
2. La rana non può uscire dai lati dello schermo
3. La rana non può andare oltre il bordo inferiore dello schermo

Possiamo implementare queste regole specifiche utilizzando condizioni più complesse:

```
Quando si preme [freccia giù]
Punta in direzione (180)
Se <(y position) > [-170] E <non <(y position) > [150]>> allora
  Cambia y di (-30)
Fine
```

Questo codice impedisce alla rana di tornare indietro una volta raggiunta la zona sicura in alto (y > 150).

## Esercizio pratico

Implementa il codice per la delimitazione dell'area di gioco nel tuo progetto Frogger. Assicurati che la rana non possa uscire dai bordi dello schermo e che rispetti le regole specifiche del gioco Frogger.

## Sfida aggiuntiva

Modifica il codice per creare una "zona sicura" in alto, dove la rana non può tornare indietro una volta raggiunta. Aggiungi anche un effetto visivo o sonoro quando la rana tenta di uscire dall'area di gioco.