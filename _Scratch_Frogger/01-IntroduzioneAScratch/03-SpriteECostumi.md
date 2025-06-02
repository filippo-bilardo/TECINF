# Sprite e costumi

In Scratch, gli sprite sono gli oggetti che animano i tuoi progetti. Possono essere personaggi, oggetti, elementi decorativi o qualsiasi cosa tu voglia far apparire e interagire nel tuo programma. I costumi, invece, rappresentano i diversi aspetti grafici che uno sprite può assumere. Comprendere come gestire sprite e costumi è fondamentale per creare progetti interattivi e visivamente accattivanti.

## Sprite: gli attori del tuo progetto

### Cosa sono gli sprite

Gli sprite sono oggetti indipendenti che possono muoversi ed interagire all'interno dello stage. Ogni sprite:

- Ha una propria posizione sullo stage (coordinate x, y)
- Può avere uno o più costumi (aspetti grafici)
- Possiede i propri script (codice) che ne determinano il comportamento
- Può avere i propri suoni
- Mantiene le proprie variabili e proprietà

### Tipi di sprite

In Scratch puoi utilizzare diversi tipi di sprite:

1. **Sprite dalla libreria**: Scratch offre una vasta libreria di sprite predefiniti
2. **Sprite disegnati**: Puoi creare i tuoi sprite utilizzando l'editor di disegno integrato
3. **Sprite caricati**: Puoi caricare immagini dal tuo computer
4. **Sprite fotografati**: Puoi utilizzare la webcam per catturare immagini e trasformarle in sprite
5. **Sprite casuali**: Scratch può generare sprite con forme casuali

### Proprietà degli sprite

Ogni sprite ha diverse proprietà che puoi controllare tramite i blocchi di codice:

- **Posizione**: Coordinate x e y sullo stage
- **Direzione**: L'angolo verso cui è orientato lo sprite (0-359 gradi)
- **Dimensione**: La scala dello sprite rispetto alla dimensione originale
- **Visibilità**: Puoi rendere uno sprite visibile o invisibile
- **Effetti grafici**: Come trasparenza, colore, luminosità, ecc.
- **Livello**: Determina quali sprite appaiono davanti o dietro ad altri

## Costumi: l'aspetto degli sprite

### Cosa sono i costumi

I costumi sono le diverse rappresentazioni grafiche che uno sprite può assumere. Cambiare costume permette di:

- Creare animazioni
- Mostrare diverse espressioni o stati
- Rappresentare diverse azioni (camminare, saltare, ecc.)
- Indicare visivamente cambiamenti nel gioco

### Editor dei costumi

L'editor dei costumi in Scratch offre strumenti per creare e modificare l'aspetto grafico degli sprite:

- **Strumenti di disegno**: Pennello, linea, rettangolo, ellisse, ecc.
- **Strumenti di modifica**: Seleziona, riempi, cancella, ecc.
- **Modalità vettoriale e bitmap**: Puoi scegliere tra grafica vettoriale (scalabile) o bitmap (a pixel)
- **Trasformazioni**: Ruota, capovolgi, ridimensiona
- **Livelli**: Per progetti più complessi

### Gestione dei costumi

Per gestire efficacemente i costumi:

1. **Rinomina i costumi** con nomi descrittivi per identificarli facilmente
2. **Organizza l'ordine** dei costumi per facilitare le animazioni
3. **Mantieni un punto di riferimento** coerente tra i diversi costumi per evitare "salti" durante le animazioni
4. **Usa il centro di rotazione** per definire il punto attorno al quale ruota lo sprite

## Tecniche avanzate

### Animazioni

Puoi creare animazioni cambiando sequenzialmente i costumi di uno sprite:

```
quando si clicca sulla bandiera verde
ripeti all'infinito
  passa al costume seguente
  attendi (0.1) secondi
fine
```

### Cloni

I cloni sono copie temporanee di uno sprite che possono essere create durante l'esecuzione del programma. Sono utili per:

- Creare molti oggetti simili (come proiettili, nemici, ostacoli)
- Risparmiare risorse rispetto alla creazione di molti sprite separati
- Implementare effetti particellari

### Sprite compositi

Puoi creare sprite complessi combinando più sprite semplici o utilizzando costumi con parti separate che si muovono indipendentemente.

## Applicazione al progetto Frogger

Nel nostro progetto Frogger, utilizzeremo sprite e costumi in diversi modi:

1. **Sprite della rana**: Il protagonista del gioco, con costumi che mostrano la rana nelle diverse direzioni
2. **Sprite degli ostacoli**: Auto, tronchi e altri elementi con cui la rana interagisce
3. **Sprite dell'ambiente**: Elementi dello sfondo come l'acqua e la strada

Per la rana protagonista, creeremo diversi costumi per rappresentare:
- La rana che guarda in alto
- La rana che guarda a destra
- La rana che guarda in basso
- La rana che guarda a sinistra

Questi costumi ci permetteranno di mostrare visivamente la direzione in cui si sta muovendo la rana, migliorando l'esperienza di gioco.

Nel prossimo argomento, esploreremo i blocchi e gli script, che ci permetteranno di dare vita ai nostri sprite e implementare la logica del gioco.

## Navigazione del Corso
- [📑 Indice](../README.md)
- [⬅️ L'interfaccia di Scratch](./02-InterfacciaScratch.md)
- [➡️ Blocchi e script](./04-BlocchiEScript.md)