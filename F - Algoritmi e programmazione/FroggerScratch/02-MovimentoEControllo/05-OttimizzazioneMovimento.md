# Ottimizzazione del movimento

## Perché ottimizzare il movimento?

L'ottimizzazione del movimento è un aspetto fondamentale nello sviluppo di videogiochi, anche in un ambiente di programmazione visuale come Scratch. Un movimento ben ottimizzato rende il gioco più fluido, reattivo e piacevole da giocare. In questa sezione, esploreremo diverse tecniche per ottimizzare il movimento della nostra rana in Frogger.

## Tecniche di ottimizzazione in Scratch

### 1. Riduzione del carico computazionale

In Scratch, è importante ridurre il numero di blocchi e la complessità degli script per garantire prestazioni ottimali. Ecco alcuni suggerimenti:

- Utilizza il minor numero possibile di cicli "per sempre"
- Evita di nidificare troppi blocchi condizionali
- Utilizza variabili locali anziché globali quando possibile

### 2. Gestione efficiente degli eventi

Invece di controllare continuamente se un tasto è premuto all'interno di un ciclo "per sempre", è più efficiente utilizzare gli eventi "quando si preme [tasto]":

```
# Approccio meno efficiente
Quando si preme bandiera verde
Per sempre
  Se <tasto [freccia su] premuto?> allora
    # Azioni per il movimento verso l'alto
  Fine
  # Altri controlli per le altre direzioni
Fine

# Approccio più efficiente
Quando si preme [freccia su]
# Azioni per il movimento verso l'alto
```

L'approccio basato sugli eventi riduce il carico computazionale perché il codice viene eseguito solo quando l'evento si verifica, anziché essere controllato continuamente.

### 3. Prevenzione del "rimbalzo" dei tasti

Un problema comune nei giochi è il "rimbalzo" dei tasti, che si verifica quando un singolo tasto premuto viene registrato più volte. In Scratch, possiamo prevenire questo problema utilizzando una variabile di stato:

```
Quando si preme bandiera verde
Imposta [tasto_premuto v] a [falso]

Quando si preme [freccia su]
Se <(tasto_premuto) = [falso]> allora
  Imposta [tasto_premuto v] a [vero]
  # Azioni per il movimento verso l'alto
  Imposta [tasto_premuto v] a [falso]
Fine
```

### 4. Ottimizzazione delle animazioni

Le animazioni possono rallentare il gioco se non sono ottimizzate. Ecco alcuni suggerimenti:

- Utilizza il minor numero possibile di costumi
- Riduci la complessità grafica dei costumi
- Utilizza effetti grafici solo quando necessario

```
Quando si preme [freccia su]
Punta in direzione (0)
# Animazione semplificata
Cambia costume in [rana-salto]
Cambia y di (30)
Cambia costume in [rana-normale]
```

## Ottimizzazione specifica per Frogger

### 1. Movimento a griglia ottimizzato

Per Frogger, il movimento a griglia è essenziale. Possiamo ottimizzarlo definendo una dimensione fissa per la griglia e utilizzando questa dimensione per tutti i movimenti:

```
Quando si preme bandiera verde
Imposta [dimensione_griglia v] a [30]

Quando si preme [freccia su]
Punta in direzione (0)
Cambia y di (dimensione_griglia)
```

Questo approccio rende più facile modificare la dimensione della griglia in futuro, poiché dobbiamo cambiare solo il valore della variabile `dimensione_griglia`.

### 2. Gestione delle collisioni ottimizzata

Le collisioni sono una parte importante di Frogger. Possiamo ottimizzare il rilevamento delle collisioni utilizzando la funzione "sta toccando [sprite]?" solo quando necessario:

```
Quando si preme [freccia su]
Punta in direzione (0)
Cambia y di (30)
# Controlla le collisioni solo dopo il movimento
Se <sta toccando [auto v]?> allora
  # Gestione della collisione
Fine
```

### 3. Utilizzo di cloni per gli ostacoli

In Frogger, ci sono molti ostacoli simili (auto, tronchi, ecc.). Invece di creare molti sprite separati, possiamo utilizzare i cloni per ridurre il carico computazionale:

```
Quando si preme bandiera verde
Nascondi
Per sempre
  Crea clone di [me stesso v]
  Attendi (2) secondi
Fine

Quando vengo clonato
Vai a x: (-240) y: (-100)
Mostra
Per sempre
  Cambia x di (5)
  Se <(x position) > [240]> allora
    Elimina questo clone
  Fine
Fine
```

## Esercizio pratico

Implementa alcune delle tecniche di ottimizzazione discusse nel tuo progetto Frogger. In particolare:

1. Utilizza l'approccio basato sugli eventi per il movimento della rana
2. Implementa una variabile `dimensione_griglia` per il movimento a griglia
3. Ottimizza le animazioni della rana

## Sfida aggiuntiva

Implementa un sistema di "buffer di input" che permetta al giocatore di premere il tasto successivo prima che l'animazione corrente sia completata. Questo renderà il gioco più reattivo e fluido.

```
Quando si preme bandiera verde
Imposta [buffer_input v] a [nessuno]
Imposta [in_movimento v] a [falso]

Quando si preme [freccia su]
Se <(in_movimento) = [vero]> allora
  Imposta [buffer_input v] a [su]
Altrimenti
  Imposta [in_movimento v] a [vero]
  Punta in direzione (0)
  Cambia costume in [rana-salto]
  Cambia y di (30)
  Cambia costume in [rana-normale]
  Imposta [in_movimento v] a [falso]
  Se <(buffer_input) = [su]> allora
    Imposta [buffer_input v] a [nessuno]
    # Esegui nuovamente il movimento verso l'alto
  Fine
Fine
```

Questo codice permette al giocatore di "accodare" un movimento mentre la rana sta ancora eseguendo il movimento precedente, rendendo il controllo più fluido e reattivo.