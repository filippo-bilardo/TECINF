# Gestione del punteggio e delle vite

In questa guida, esploreremo come implementare un sistema di punteggio e gestire le vite del giocatore in Scratch, elementi essenziali per rendere il nostro gioco Frogger completo e coinvolgente.

## Sistema di punteggio in Frogger

Un buon sistema di punteggio rende il gioco più gratificante e stimola i giocatori a migliorare le proprie prestazioni.

### Variabili per il punteggio

Per implementare un sistema di punteggio, dobbiamo prima creare una variabile:

```
variabile [punteggio] = 0
```

Questa variabile terrà traccia dei punti accumulati dal giocatore durante la partita.

### Assegnazione dei punti

In Frogger, i punti possono essere assegnati in diversi modi:

1. **Raggiungimento di una destinazione**:
   ```
   quando ricevo [punto segnato v]
   cambia [punteggio] di (100)
   ```

2. **Avanzamento verso l'alto**:
   ```
   quando si preme tasto [freccia su v]
   cambia y di (30)
   se <(y) > (y precedente)> allora
     cambia [punteggio] di (10)
   fine
   porta [y precedente] a (y)
   ```

3. **Bonus per il tempo**:
   ```
   variabile [tempo rimanente] = 30
   
   quando si clicca su bandiera verde
   porta [tempo rimanente] a (30)
   ripeti fino a <(tempo rimanente) = 0>
     attendi (1) secondi
     cambia [tempo rimanente] di (-1)
   fine
   
   quando ricevo [punto segnato v]
   cambia [punteggio] di ((tempo rimanente) * 2)
   ```

### Visualizzazione del punteggio

È importante che il punteggio sia sempre visibile al giocatore:

```
quando si clicca su bandiera verde
porta [punteggio] a (0)
mostra variabile [punteggio]
```

Possiamo anche creare un sprite dedicato per visualizzare il punteggio in modo più accattivante:

```
quando si clicca su bandiera verde
ripeti sempre
  dire unione [Punteggio: ] (punteggio)
fine
```

## Gestione delle vite

La gestione delle vite è fondamentale per dare al giocatore più possibilità di completare il gioco.

### Variabili per le vite

Come per il punteggio, dobbiamo creare una variabile per le vite:

```
variabile [vite] = 3
```

### Perdita di una vita

Quando la rana collide con un ostacolo o cade in acqua, il giocatore perde una vita:

```
quando ricevo [game over v]
cambia [vite] di (-1)
se <(vite) = 0> allora
  invia a tutti [fine gioco v]
  ferma [tutti v]
altrimenti
  vai a x: (0) y: (-150)
fine
```

### Visualizzazione delle vite

Possiamo visualizzare le vite rimanenti in diversi modi:

1. **Visualizzazione numerica**:
   ```
   quando si clicca su bandiera verde
   mostra variabile [vite]
   ```

2. **Visualizzazione grafica**:
   ```
   quando si clicca su bandiera verde
   nascondi
   porta [vite visualizzate] a (0)
   ripeti fino a <(vite visualizzate) = (vite)>
     crea clone di [me stesso v]
     cambia [vite visualizzate] di (1)
   fine
   
   quando vengo clonato
   mostra
   vai a x: ((-200) + ((vite visualizzate) * 30)) y: (160)
   ```

### Guadagnare vite extra

Per rendere il gioco più interessante, possiamo permettere al giocatore di guadagnare vite extra:

```
quando ricevo [punto segnato v]
se <(punteggio) > (1000)> allora
  cambia [vite] di (1)
  porta [punteggio] a ((punteggio) - (1000))
  riproduci suono [vita extra v]
fine
```

## Implementazione di un sistema di livelli

Un sistema di livelli può rendere il gioco progressivamente più difficile e gratificante.

### Variabile per il livello

```
variabile [livello] = 1
```

### Avanzamento di livello

Quando tutte le destinazioni sono state raggiunte, il giocatore avanza al livello successivo:

```
variabile [destinazioni raggiunte] = 0

quando ricevo [punto segnato v]
cambia [destinazioni raggiunte] di (1)
se <(destinazioni raggiunte) = (5)> allora
  cambia [livello] di (1)
  porta [destinazioni raggiunte] a (0)
  invia a tutti [nuovo livello v]
fine
```

### Aumento della difficoltà

Con l'avanzare dei livelli, possiamo aumentare la difficoltà del gioco:

```
quando ricevo [nuovo livello v]
porta [velocità veicoli] a ((velocità veicoli) * (1.2))
porta [tempo rimanente] a ((tempo rimanente) - (5))
```

## Salvataggio dei punteggi migliori

Per incentivare i giocatori a migliorarsi, possiamo salvare e visualizzare i punteggi migliori.

### Variabile per il punteggio migliore

```
variabile [punteggio migliore] = 0
```

### Aggiornamento del punteggio migliore

```
quando ricevo [fine gioco v]
se <(punteggio) > (punteggio migliore)> allora
  porta [punteggio migliore] a (punteggio)
  salva [punteggio migliore] nel cloud
fine
```

### Visualizzazione dei punteggi migliori

```
quando si clicca su bandiera verde
dire unione [Punteggio migliore: ] (punteggio migliore) per (2) secondi
```

## Feedback visivo e sonoro

Per rendere l'esperienza più coinvolgente, è importante fornire feedback quando il giocatore guadagna punti o perde vite.

### Feedback per i punti

```
quando ricevo [punto segnato v]
cambia effetto [colore v] di (25)
riproduci suono [punto v]
attendi (0.2) secondi
rimuovi effetti grafici
```

### Feedback per la perdita di vite

```
quando ricevo [game over v]
cambia effetto [fantasma v] di (50)
riproduci suono [perdita v]
attendi (0.5) secondi
rimuovi effetti grafici
```

## Conclusione

Un sistema ben progettato di punteggio e vite è essenziale per creare un'esperienza di gioco coinvolgente e gratificante. Implementando questi elementi nel nostro gioco Frogger, possiamo motivare i giocatori a migliorare le proprie prestazioni e a continuare a giocare.

## Esercizi pratici

1. Implementa un sistema di punteggio che assegna punti in base alla velocità con cui il giocatore completa il livello
2. Crea un sistema di vite con visualizzazione grafica
3. Aggiungi un sistema di livelli con difficoltà crescente
4. Implementa un sistema di punteggi migliori con visualizzazione a fine partita

## Risorse aggiuntive

- [Documentazione ufficiale di Scratch sulle variabili](https://en.scratch-wiki.info/wiki/Variables_Blocks)
- [Tutorial su sistemi di punteggio avanzati in Scratch](https://scratch.mit.edu/studios/1672493/)

---

[◀ Collisioni e interazioni](./04-CollisioniEInterazioni.md) | [Progettazione dei livelli ▶](./06-ProgettazioneLivelli.md)