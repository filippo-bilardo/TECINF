# Progressione dei livelli

In questa guida, esploreremo come implementare un sistema di progressione dei livelli nel nostro gioco Frogger. Un sistema di livelli ben progettato è fondamentale per mantenere alta l'attenzione del giocatore, aumentare gradualmente la difficoltà e fornire un senso di avanzamento nell'esperienza di gioco.

## Importanza della progressione dei livelli

Un sistema di progressione dei livelli serve a diversi scopi:

1. **Curva di apprendimento**: Introduce gradualmente meccaniche e sfide più complesse
2. **Senso di avanzamento**: Fornisce al giocatore un chiaro senso di progressione
3. **Varietà**: Mantiene il gameplay fresco e interessante
4. **Sfida bilanciata**: Aumenta la difficoltà in modo proporzionale alle abilità acquisite dal giocatore
5. **Rigiocabilità**: Incentiva i giocatori a migliorare le proprie prestazioni su livelli già completati

## Elementi di un sistema di livelli

### 1. Struttura dei livelli

In Frogger, possiamo strutturare i livelli in diversi modi:

- **Livelli sequenziali**: Il giocatore progredisce da un livello all'altro in ordine
- **Livelli a difficoltà crescente**: Ogni livello è più difficile del precedente
- **Livelli con nuove meccaniche**: Ogni livello introduce nuovi elementi di gameplay

### 2. Transizione tra livelli

La transizione tra un livello e l'altro deve essere chiara e gratificante:

```
quando ricevo [livello completato v]
ferma tutti i suoni
suona suono [livello completato v] e attendi
mostra [Livello completato!] per (2) secondi
mostra unione di [Punteggio: ] e (punteggio) per (2) secondi
mostra [Preparati per il prossimo livello...] per (2) secondi
invia a tutti [prossimo livello v]
```

### 3. Indicatori di livello

È importante che il giocatore sappia sempre a quale livello sta giocando:

```
// Nello sprite "Indicatore Livello"
quando si clicca sulla bandiera verde
porta a x: (-200) y: (170)
ripeti sempre
  dire unione di [Livello: ] e (livello attuale)
fine
```

## Implementazione della progressione dei livelli in Frogger

### 1. Inizializzazione del livello

```
quando si clicca sulla bandiera verde
porta [livello attuale v] a [1]
porta [ninfee raggiunte v] a [0]
porta [tempo limite v] a [60]
porta [velocità ostacoli v] a [2]
invia a tutti [inizializza livello v]
```

### 2. Configurazione del livello

```
quando ricevo [inizializza livello v]
// Configura gli ostacoli in base al livello
se <(livello attuale) = [1]> allora
  porta [numero veicoli v] a [5]
  porta [numero tronchi v] a [4]
  porta [numero tartarughe v] a [3]
fine
se <(livello attuale) = [2]> allora
  porta [numero veicoli v] a [6]
  porta [numero tronchi v] a [3]
  porta [numero tartarughe v] a [4]
  porta [velocità ostacoli v] a [3]
fine
// E così via per i livelli successivi

// Crea gli ostacoli
ripeti (numero veicoli)
  crea clone di [Veicolo v]
fine
ripeti (numero tronchi)
  crea clone di [Tronco v]
fine
ripeti (numero tartarughe)
  crea clone di [Tartaruga v]
fine

// Inizializza il timer
porta [tempo rimanente v] a (tempo limite)
invia a tutti [avvia timer v]
```

### 3. Completamento del livello

```
quando ricevo [livello completato v]
// Calcola bonus di fine livello
cambia [punteggio v] di ((tempo rimanente) * (2))  // Bonus per il tempo rimanente
se <(vite) = [3]> allora  // Bonus per non aver perso vite
  cambia [punteggio v] di (100)
  mostra [Bonus vite intatte: 100] per (2) secondi
fine

// Prepara il prossimo livello
cambia [livello attuale v] di (1)
porta [ninfee raggiunte v] a [0]
porta [tempo limite v] a ((tempo limite) - (5))  // Riduce il tempo disponibile
porta [velocità ostacoli v] a ((velocità ostacoli) * (1.2))  // Aumenta la velocità

// Transizione al prossimo livello
mostra [Livello completato!] per (2) secondi
mostra unione di [Prossimo livello: ] e (livello attuale) per (2) secondi
mostra [Preparati...] per (2) secondi

// Elimina tutti gli ostacoli attuali
invia a tutti [elimina ostacoli v]
// Inizializza il nuovo livello
invia a tutti [inizializza livello v]
```

### 4. Gestione del timer

```
quando ricevo [avvia timer v]
porta [tempo rimanente v] a (tempo limite)
ripeti fino a <(tempo rimanente) = [0]>
  attendi (1) secondi
  cambia [tempo rimanente v] di (-1)
  se <(tempo rimanente) < [10]> allora  // Avviso quando il tempo sta per scadere
    suona suono [tick v]
  fine
fine
se <(tempo rimanente) = [0]> allora  // Se il tempo è scaduto
  invia a tutti [tempo scaduto v]
fine
```

### 5. Gestione del game over per tempo scaduto

```
quando ricevo [tempo scaduto v]
suona suono [tempo scaduto v]
mostra [Tempo scaduto!] per (2) secondi
cambia [vite v] di (-1)
se <(vite) > (0)> allora
  // Riavvia il livello attuale
  porta [ninfee raggiunte v] a [0]
  invia a tutti [elimina ostacoli v]
  invia a tutti [inizializza livello v]
altrimenti
  invia a tutti [game over v]
fine
```

## Variazione della difficoltà

Per mantenere il gioco interessante, è importante variare la difficoltà in modi diversi:

### 1. Aumento della velocità

```
definiamo [aggiorna velocità ostacoli]
porta [velocità ostacoli v] a ((livello attuale) * (0.5) + (1.5))  // Formula per aumentare gradualmente la velocità
```

### 2. Aumento del numero di ostacoli

```
definiamo [aggiorna numero ostacoli]
porta [numero veicoli v] a ((livello attuale) + (4))  // Più veicoli nei livelli avanzati
porta [numero tronchi v] a (4)  // Il numero di tronchi rimane costante
porta [numero tartarughe v] a ((livello attuale) / (2) + (2))  // Più tartarughe nei livelli avanzati
```

### 3. Riduzione del tempo disponibile

```
definisome [aggiorna tempo limite]
porta [tempo limite v] a (60 - ((livello attuale) - (1)) * (5))  // Riduce di 5 secondi per livello
se <(tempo limite) < (30)> allora  // Imposta un limite minimo
  porta [tempo limite v] a (30)
fine
```

### 4. Introduzione di nuove meccaniche

Nei livelli più avanzati, possiamo introdurre nuove meccaniche di gioco:

```
quando ricevo [inizializza livello v]
// Configura meccaniche speciali in base al livello
se <(livello attuale) > (3)> allora  // Dal livello 4 in poi
  porta [tartarughe immergibili v] a [vero]  // Le tartarughe possono immergersi
fine
se <(livello attuale) > (5)> allora  // Dal livello 6 in poi
  porta [serpenti v] a [vero]  // Aggiunge serpenti che si muovono sulle ninfee
fine
se <(livello attuale) > (7)> allora  // Dal livello 8 in poi
  porta [tempo variabile v] a [vero]  // Il tempo scorre più velocemente in alcune aree
fine
```

## Bilanciamento della difficoltà

Un buon sistema di livelli deve essere bilanciato per essere sfidante ma non frustrante:

### 1. Curva di difficoltà graduale

La difficoltà deve aumentare gradualmente per dare al giocatore il tempo di adattarsi:

```
definisome [calcola difficoltà]
porta [difficoltà base v] a (livello attuale)
se <(difficoltà base) > (10)> allora  // Limita la difficoltà massima
  porta [difficoltà base v] a (10)
fine
porta [velocità ostacoli v] a ((difficoltà base) * (0.3) + (1.5))
porta [frequenza ostacoli v] a ((difficoltà base) * (0.1) + (0.5))
porta [tempo limite v] a (60 - ((difficoltà base) - (1)) * (3))
```

### 2. Adattamento dinamico della difficoltà (opzionale)

Per un'esperienza più personalizzata, possiamo implementare un sistema che adatta la difficoltà in base alle prestazioni del giocatore:

```
definisome [adatta difficoltà]
se <(vite perse nel livello) > (2)> allora  // Se il giocatore sta avendo difficoltà
  cambia [fattore difficoltà v] di (-0.1)  // Riduce leggermente la difficoltà
fine
se <(tempo completamento) < (tempo limite / 2)> allora  // Se il giocatore è molto veloce
  cambia [fattore difficoltà v] di (0.1)  // Aumenta leggermente la difficoltà
fine
```

## Estensioni del sistema di livelli

### 1. Livelli bonus

Possiamo implementare livelli bonus speciali che appaiono dopo aver completato determinati livelli:

```
quando ricevo [livello completato v]
se <(livello attuale) mod (3) = (0)> allora  // Ogni 3 livelli
  invia a tutti [livello bonus v]
altrimenti
  invia a tutti [prossimo livello v]
fine
```

### 2. Selezione del livello (modalità pratica)

Per permettere ai giocatori di esercitarsi su livelli specifici:

```
quando si clicca su questo sprite  // Sprite "Selezione Livello"
chiedi [Seleziona un livello (1-10):] e attendi
se <(risposta) > (0) e (risposta) < (11)> allora
  porta [livello attuale v] a (risposta)
  invia a tutti [inizializza livello v]
fine
```

### 3. Modalità infinita

Per i giocatori che vogliono una sfida senza fine:

```
quando si clicca su questo sprite  // Sprite "Modalità Infinita"
porta [modalità infinita v] a [vero]
porta [livello attuale v] a [1]
invia a tutti [inizializza livello v]

// Nel codice di completamento del livello
quando ricevo [livello completato v]
se <(modalità infinita)> allora
  cambia [livello attuale v] di (1)  // Continua all'infinito
  // La difficoltà continua ad aumentare
fine
```

## Feedback visivo per la progressione

È importante fornire feedback visivo chiaro sulla progressione del giocatore:

### 1. Indicatore di livello

```
// Nello sprite "Indicatore Livello"
quando si clicca sulla bandiera verde
porta a x: (-200) y: (170)
ripeti sempre
  dire unione di [Livello: ] e (livello attuale)
fine
```

### 2. Mappa dei livelli

Per giochi con molti livelli, può essere utile una mappa che mostra la progressione:

```
quando si clicca su questo sprite  // Sprite "Mappa"
mostra
porta in primo piano
ripeti (numero totale livelli)
  se <(livello) <= (livello massimo sbloccato)> allora
    passa al costume (unione di [livello_sbloccato_] e (livello))
  altrimenti
    passa al costume (unione di [livello_bloccato_] e (livello))
  fine
  attendi (0.5) secondi
fine
attendi fino a <tasto qualsiasi premuto?>
nascondi
```

### 3. Animazione di transizione

```
definisome [transizione livello]
mostra
porta in primo piano
porta effetto [mosaico v] a (100)
ripeti fino a <(effetto [mosaico v]) = (0)>
  cambia effetto [mosaico v] di (-5)
  attendi (0.05) secondi
fine
mostra [Livello completato!] per (2) secondi
mostra unione di [Prossimo livello: ] e (livello attuale) per (2) secondi
ripeti fino a <(effetto [mosaico v]) = (100)>
  cambia effetto [mosaico v] di (5)
  attendi (0.05) secondi
fine
nascondi
ripristina effetti grafici
```

## Conclusione

Un sistema di progressione dei livelli ben progettato è fondamentale per creare un'esperienza di gioco coinvolgente e duratura. Implementando queste tecniche nel nostro gioco Frogger, possiamo creare una curva di difficoltà bilanciata che mantiene alta l'attenzione del giocatore e fornisce un chiaro senso di avanzamento.

Nella prossima guida, esploreremo come integrare tutti gli elementi che abbiamo imparato per creare un progetto finale completo e funzionale.

## Navigazione del Corso
- [📑 Indice](../README.md)
- [⬅️ Sistema di punteggio](./01-SistemaPunteggio.md)
- [➡️ Progetto finale](../06-ProgettoFinale/README.md)