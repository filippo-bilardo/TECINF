# Coordinate e sistema di posizionamento

In questa guida, esploreremo il sistema di coordinate e posizionamento in Scratch, un concetto fondamentale per controllare con precisione il movimento della nostra rana nel gioco Frogger.

## Il sistema di coordinate in Scratch

Scratch utilizza un sistema di coordinate cartesiane per posizionare gli sprite sullo stage:

### Struttura del sistema di coordinate

- **Origine (0,0)**: Il centro dello stage è il punto (0,0)
- **Asse X**: Si estende orizzontalmente, con valori positivi verso destra e negativi verso sinistra
- **Asse Y**: Si estende verticalmente, con valori positivi verso l'alto e negativi verso il basso
- **Limiti**: Lo stage standard ha dimensioni 480x360 pixel, quindi i limiti sono:
  - X: da -240 a +240
  - Y: da -180 a +180

### Visualizzazione delle coordinate

Scratch offre strumenti per visualizzare le coordinate:

1. **Posizione del mouse**: Sotto lo stage, Scratch mostra le coordinate del puntatore del mouse
2. **Posizione dello sprite**: Nelle proprietà dello sprite, puoi vedere le sue coordinate x e y
3. **Griglia**: Puoi attivare una griglia di riferimento sullo stage per visualizzare meglio le coordinate

## Posizionamento degli sprite

### Blocchi di posizionamento

Scratch offre diversi blocchi per controllare la posizione degli sprite:

- **Vai a x: () y: ()**: Sposta immediatamente lo sprite alle coordinate specificate
- **Scivola in () secondi a x: () y: ()**: Muove gradualmente lo sprite verso le coordinate specificate
- **Cambia x di ()**: Modifica la coordinata x dello sprite del valore specificato
- **Cambia y di ()**: Modifica la coordinata y dello sprite del valore specificato
- **Vai a [sprite v]**: Sposta lo sprite nella posizione di un altro sprite

### Posizionamento relativo vs. assoluto

- **Posizionamento assoluto**: Utilizzando coordinate specifiche (vai a x: 100 y: 50)
- **Posizionamento relativo**: Modificando la posizione corrente (cambia x di 10)

## Applicazione al gioco Frogger

### Griglia di movimento

In Frogger, il movimento della rana è tipicamente organizzato in una griglia:

1. **Dimensione della cella**: Determina quanto la rana si muove ad ogni salto
2. **Allineamento alla griglia**: Assicura che la rana si posizioni sempre correttamente nelle corsie

### Esempio di implementazione

Per implementare un movimento a griglia in Frogger, possiamo definire:

```
variabile [dimensione_cella] = 30

quando si preme tasto [freccia su v]
se <(y position) < (180 - dimensione_cella)> allora
  cambia y di (dimensione_cella)
fine
```

Questo codice fa muovere la rana verso l'alto di una cella alla volta, fermandosi prima del bordo superiore.

### Limitazione dell'area di gioco

Per limitare il movimento della rana all'area di gioco, utilizziamo le coordinate per definire i confini:

```
quando si preme tasto [freccia destra v]
se <(x position) < (240 - dimensione_cella)> allora
  cambia x di (dimensione_cella)
fine
```

## Tecniche avanzate

### Movimento fluido con interpolazione

Per un movimento più fluido, possiamo utilizzare l'interpolazione tra posizioni:

```
quando si preme tasto [freccia su v]
se <(y position) < (180 - dimensione_cella)> allora
  scivola in (0.1) secondi a x: (x position) y: ((y position) + (dimensione_cella))
fine
```

### Posizionamento basato sulla fisica

Per movimenti più realistici, possiamo implementare semplici principi fisici:

```
variabile [velocita_y] = 0
variabile [gravita] = -1

quando si clicca su ⚑
ripeti sempre
  cambia y di (velocita_y)
  cambia [velocita_y] di (gravita)
  se <(y position) < (-180)> allora
    porta [velocita_y] a (0)
    vai a y: (-180)
  fine
fine
```

## Conclusione

Comprendere il sistema di coordinate e posizionamento in Scratch è fondamentale per implementare un controllo preciso della rana nel nostro gioco Frogger. Utilizzando i blocchi di posizionamento in modo efficace, possiamo creare movimenti fluidi e realistici, limitare l'area di gioco e implementare meccaniche di gioco più complesse.

## Esercizi pratici

1. Crea uno script che faccia muovere la rana in diagonale quando si premono contemporaneamente due tasti freccia
2. Implementa un sistema che impedisca alla rana di uscire dai bordi dello stage
3. Crea un effetto di "rimbalzo" quando la rana raggiunge i bordi dello stage

## Risorse aggiuntive

- [Documentazione ufficiale di Scratch sul sistema di coordinate](https://en.scratch-wiki.info/wiki/Coordinate_System)
- [Tutorial su movimenti avanzati in Scratch](https://scratch.mit.edu/studios/475476/)

---

[◀ Torna all'indice](./README.md) | [Gestione avanzata degli input ▶](./02-GestioneInput.md)