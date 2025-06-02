# Ottimizzazione del codice

In questa guida, esploreremo le tecniche di ottimizzazione del codice per migliorare le prestazioni e la manutenibilità del nostro gioco Frogger. Un codice ben ottimizzato non solo garantisce un'esperienza di gioco fluida, ma facilita anche future modifiche e aggiornamenti.

## Importanza dell'ottimizzazione del codice

L'ottimizzazione del codice è un aspetto fondamentale dello sviluppo di giochi, in quanto:

1. **Prestazioni migliori**: Riduce il carico di elaborazione e garantisce un gameplay fluido
2. **Manutenibilità**: Facilita la comprensione e la modifica del codice in futuro
3. **Scalabilità**: Permette di aggiungere nuove funzionalità senza compromettere le prestazioni
4. **Debugging più semplice**: Un codice pulito e ben organizzato è più facile da debuggare
5. **Riutilizzo del codice**: Favorisce la creazione di componenti riutilizzabili in altri progetti

## Tecniche di ottimizzazione

### 1. Rifattorizzazione degli script

La rifattorizzazione consiste nel migliorare la struttura del codice senza modificarne il comportamento esterno:

```
// Prima della rifattorizzazione
quando si clicca sulla bandiera verde
ripeti sempre
  se <tocca [Veicolo v]?> allora
    invia a tutti [rana colpita v]
  fine
  se <tocca [Acqua v]?> e <non <tocca [Tronco v]?> e non <tocca [Tartaruga v]?>>> allora
    invia a tutti [rana annegata v]
  fine
  se <tocca [Serpente v]?> allora
    invia a tutti [rana colpita v]
  fine
fine

// Dopo la rifattorizzazione
quando si clicca sulla bandiera verde
ripeti sempre
  se <(stato) = [in gioco]> allora
    controlla collisioni
  fine
fine

definiamo [controlla collisioni]
se <tocca [Veicolo v]?> o <tocca [Serpente v]?> allora
  invia a tutti [rana colpita v]
altrimenti
  se <tocca [Acqua v]?> e <non <tocca [Tronco v]?> e non <tocca [Tartaruga v]?>>> allora
    invia a tutti [rana annegata v]
  fine
fine
```

### 2. Utilizzo di procedure personalizzate

Le procedure personalizzate (blocchi "definisci") permettono di organizzare il codice in unità logiche e riutilizzabili:

```
definiamo [inizializza livello v]
porta [ninfee raggiunte v] a [0]
porta [tempo rimanente v] a (tempo limite)
porta [stato gioco v] a [in gioco]
posiziona rana
crea ostacoli

definiamo [posiziona rana]
porta a x: (0) y: (-180)
porta [direzione v] a (90)
porta [stato v] a [normale]
mostra

definiamo [crea ostacoli]
elimina tutti gli sprite del gruppo [Ostacoli v]
ripeti (numero ostacoli)
  crea clone di [Ostacolo v]
fine
```

### 3. Ottimizzazione delle condizioni

Semplificare le condizioni complesse può migliorare significativamente le prestazioni:

```
// Prima dell'ottimizzazione
se <tocca [Acqua v]?> e <non <tocca [Tronco v]?> e non <tocca [Tartaruga v]?> e non <tocca [Ninfea v]?>>> allora
  invia a tutti [rana annegata v]
fine

// Dopo l'ottimizzazione
se <tocca [Acqua v]?> allora
  se <non <tocca [Piattaforma v]?>> allora
    invia a tutti [rana annegata v]
  fine
fine
```

### 4. Gestione efficiente degli sprite

Una gestione ottimizzata degli sprite può ridurre significativamente il carico di elaborazione:

```
// Nello sprite Ostacolo
quando si clicca sulla bandiera verde
nascondi

quando ricevo [crea ostacoli v]
se <(numero di cloni) < (numero massimo ostacoli)> allora
  crea clone di [me stesso v]
fine

quando vengo clonato
mostra
porta a x: (posizione iniziale x) y: (posizione iniziale y)
ripeti fino a <(stato gioco) = [game over]>
  se <(stato gioco) = [in gioco]> allora
    cambia x di (velocità)
    se <(x) > (240)> allora
      porta a x: (-240)
    fine
    se <(x) < (-240)> allora
      porta a x: (240)
    fine
  fine
  attendi (0.05) secondi
fine
elimina questo clone
```

### 5. Ottimizzazione dei cicli

I cicli inefficienti possono causare rallentamenti significativi:

```
// Prima dell'ottimizzazione
quando si clicca sulla bandiera verde
ripeti sempre
  aggiorna posizione
  controlla collisioni
  aggiorna punteggio
  aggiorna timer
  aggiorna animazioni
fine

// Dopo l'ottimizzazione
quando si clicca sulla bandiera verde
ripeti sempre
  se <(stato gioco) = [in gioco]> allora
    aggiorna gioco
  fine
fine

definiamo [aggiorna gioco]
aggiorna posizione
controlla collisioni
aggiorna punteggio
aggiorna timer
```

## Tecniche avanzate di ottimizzazione

### 1. Gestione degli eventi

Un sistema di eventi ben progettato può migliorare significativamente le prestazioni:

```
// Nello sprite Controller
quando si clicca sulla bandiera verde
invia a tutti [inizializza gioco v]

quando ricevo [inizializza gioco v]
porta [stato gioco v] a [menu]
mostra menu

quando ricevo [inizia gioco v]
porta [stato gioco v] a [in gioco]
nascondi menu
invia a tutti [inizializza livello v]

quando ricevo [pausa gioco v]
se <(stato gioco) = [in gioco]> allora
  porta [stato gioco precedente v] a [in gioco]
  porta [stato gioco v] a [pausa]
  mostra menu pausa
altrimenti
  se <(stato gioco) = [pausa]> allora
    porta [stato gioco v] a (stato gioco precedente)
    nascondi menu pausa
  fine
fine
```

### 2. Caching dei valori

Il caching dei valori calcolati frequentemente può ridurre il carico di elaborazione:

```
// Prima dell'ottimizzazione
quando si clicca sulla bandiera verde
ripeti sempre
  porta [distanza dal bordo v] a (sqrt((x) * (x) + (y) * (y)))
  se <(distanza dal bordo) > (200)> allora
    // Azioni quando la rana è vicina al bordo
  fine
fine

// Dopo l'ottimizzazione
quando si clicca sulla bandiera verde
porta [ultimo x v] a (x)
porta [ultimo y v] a (y)
porta [distanza dal bordo v] a (sqrt((x) * (x) + (y) * (y)))
ripeti sempre
  se <non <(x) = (ultimo x) o (y) = (ultimo y)>> allora
    porta [ultimo x v] a (x)
    porta [ultimo y v] a (y)
    porta [distanza dal bordo v] a (sqrt((x) * (x) + (y) * (y)))
  fine
  se <(distanza dal bordo) > (200)> allora
    // Azioni quando la rana è vicina al bordo
  fine
fine
```

### 3. Ottimizzazione delle animazioni

Le animazioni possono essere ottimizzate per ridurre il carico di elaborazione:

```
// Prima dell'ottimizzazione
quando ricevo [rana colpita v]
ripeti (10)
  cambia effetto [fantasma v] di (10)
  attendi (0.05) secondi
fine
ripeti (10)
  cambia effetto [fantasma v] di (-10)
  attendi (0.05) secondi
fine

// Dopo l'ottimizzazione
quando ricevo [rana colpita v]
porta [effetto fantasma v] a [0]
porta [direzione effetto v] a [1]
ripeti (20)
  cambia effetto [fantasma v] di ((direzione effetto) * (10))
  se <(effetto fantasma) > (100)> allora
    porta [direzione effetto v] a [-1]
  fine
  attendi (0.05) secondi
fine
porta effetto [fantasma v] a [0]
```

## Ottimizzazione della struttura del progetto

### 1. Organizzazione degli sprite

Una buona organizzazione degli sprite facilita la manutenzione e l'ottimizzazione:

```
// Struttura consigliata
- Personaggio (Rana)
- Ostacoli
  - Veicoli
  - Serpenti
- Piattaforme
  - Tronchi
  - Tartarughe
  - Ninfee
- Ambiente
  - Acqua
  - Strada
  - Sfondo
- Interfaccia
  - Punteggio
  - Vite
  - Timer
  - Menu
- Controller (gestione del gioco)
```

### 2. Gestione delle variabili

Una gestione efficiente delle variabili migliora la leggibilità e le prestazioni:

```
// Variabili globali (per tutti gli sprite)
- punteggio
- vite
- livello attuale
- stato gioco
- tempo rimanente

// Variabili locali (per sprite specifici)
- velocità (per ostacoli e piattaforme)
- direzione (per la rana)
- stato (per la rana)
- posizione iniziale (per ostacoli e piattaforme)
```

### 3. Gestione dei messaggi

Un sistema di messaggi ben progettato facilita la comunicazione tra gli sprite:

```
// Messaggi di sistema
- inizializza gioco
- inizializza livello
- avvia livello
- pausa gioco
- riprendi gioco
- game over
- livello completato

// Messaggi di gameplay
- rana colpita
- rana annegata
- ninfea raggiunta
- riposiziona rana
```

## Debugging e profiling

### 1. Tecniche di debugging

Il debugging è essenziale per identificare e risolvere problemi di prestazioni:

```
// Aggiunta di indicatori di debug
quando si clicca sulla bandiera verde
porta [debug mode v] a [falso]
ripeti sempre
  se <tasto [d v] premuto?> allora
    se <(debug mode) = [falso]> allora
      porta [debug mode v] a [vero]
    altrimenti
      porta [debug mode v] a [falso]
    fine
    attendi fino a <non <tasto [d v] premuto?>>
  fine
  
  se <(debug mode) = [vero]> allora
    dire unione di [FPS: ] e (fps)
    dire unione di [Sprite attivi: ] e (numero di sprite attivi)
    dire unione di [Memoria: ] e (utilizzo memoria)
  altrimenti
    dire []
  fine
fine
```

### 2. Profiling delle prestazioni

Il profiling permette di identificare i colli di bottiglia nelle prestazioni:

```
// Misurazione del tempo di esecuzione
definiamo [misura tempo esecuzione %s]
porta [tempo inizio v] a (timer)
esegui %s
porta [tempo fine v] a (timer)
porta [tempo esecuzione v] a ((tempo fine) - (tempo inizio))
dire unione di [Tempo di esecuzione: ] e (tempo esecuzione)
```

## Ottimizzazione per dispositivi mobili

Se il gioco sarà giocato anche su dispositivi mobili, è importante ottimizzarlo di conseguenza:

```
// Rilevamento del dispositivo
quando si clicca sulla bandiera verde
se <(larghezza schermo) < (500)> allora
  porta [dispositivo v] a [mobile]
  adatta interfaccia per mobile
altrimenti
  porta [dispositivo v] a [desktop]
  adatta interfaccia per desktop
fine

definiamo [adatta interfaccia per mobile]
porta [dimensione controlli v] a [grande]
porta [numero ostacoli v] a ((numero ostacoli standard) * (0.7))
porta [dettaglio grafico v] a [basso]

definiamo [adatta interfaccia per desktop]
porta [dimensione controlli v] a [normale]
porta [numero ostacoli v] a (numero ostacoli standard)
porta [dettaglio grafico v] a [alto]
```

## Conclusione

L'ottimizzazione del codice è un processo continuo che richiede attenzione ai dettagli e una buona comprensione delle tecniche di programmazione. Seguendo le tecniche presentate in questa guida, potrai migliorare significativamente le prestazioni e la manutenibilità del tuo gioco Frogger.

Ricorda che l'ottimizzazione dovrebbe essere un equilibrio tra prestazioni e leggibilità del codice. Un codice troppo ottimizzato potrebbe diventare difficile da comprendere e modificare in futuro.

Nella prossima guida, esploreremo le tecniche di debugging e risoluzione dei problemi per garantire che il nostro gioco funzioni correttamente in tutte le situazioni.

## Navigazione del Corso
- [📑 Indice](../README.md)
- [⬅️ Integrazione dei componenti](./01-IntegrazioneComponenti.md)
- [➡️ Debugging e risoluzione dei problemi](./03-DebuggingProblemi.md)