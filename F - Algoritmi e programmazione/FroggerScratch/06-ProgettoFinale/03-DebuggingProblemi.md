# Debugging e risoluzione dei problemi

## Importanza del debugging

Il debugging è una fase fondamentale nello sviluppo di qualsiasi software, inclusi i giochi creati con Scratch. Consiste nell'identificare, analizzare e risolvere gli errori (bug) che impediscono al programma di funzionare correttamente. Un buon processo di debugging non solo risolve i problemi attuali, ma aiuta anche a prevenire problemi futuri. In questa sezione, esploreremo le tecniche di debugging e risoluzione dei problemi specifiche per il nostro gioco Frogger in Scratch.

## Tecniche di debugging in Scratch

### 1. Utilizzo dei blocchi "dire"

Uno dei metodi più semplici per il debugging in Scratch è l'utilizzo dei blocchi "dire" per visualizzare il valore delle variabili o lo stato del programma in punti specifici:

```
Quando si preme bandiera verde
Per sempre
  # Visualizza il valore delle variabili importanti
  Dire unione [x: ] (x position) unione [, y: ] (y position) unione [, vite: ] (vite) per (0.5) secondi
Fine
```

### 2. Modalità passo-passo

Scratch permette di eseguire il codice passo-passo, cliccando sui blocchi uno alla volta. Questo è utile per identificare esattamente dove si verifica un problema:

1. Ferma tutti gli script in esecuzione
2. Clicca direttamente sul blocco da cui vuoi iniziare l'esecuzione
3. Osserva attentamente cosa succede dopo ogni passo

### 3. Semplificazione del codice

Quando si verifica un problema complesso, può essere utile semplificare temporaneamente il codice per isolare la causa:

1. Commenta o disattiva parti del codice non essenziali
2. Testa il codice semplificato
3. Aggiungi gradualmente le parti commentate, testando dopo ogni aggiunta

```
# Versione semplificata per il debugging
Quando si preme bandiera verde
# Disattiva temporaneamente la generazione degli ostacoli
# Ripeti (10)
#   Crea clone di [ostacolo v]
#   Attendi (1) secondi
# Fine
# Testa solo il movimento della rana
Per sempre
  Se <tasto [freccia su] premuto?> allora
    Cambia y di (30)
  Fine
  # ...
Fine
```

## Problemi comuni in Frogger e soluzioni

### 1. Problemi di collisione

**Problema**: Le collisioni non vengono rilevate correttamente o vengono rilevate quando non dovrebbero.

**Soluzioni**:

- Verifica che i costumi degli sprite abbiano dimensioni appropriate
- Utilizza il blocco "sta toccando il colore" invece di "sta toccando lo sprite" per collisioni più precise
- Assicurati che il punto di controllo degli sprite sia posizionato correttamente

```
# Debugging delle collisioni
Quando si preme bandiera verde
Per sempre
  Se <sta toccando [auto v]?> allora
    # Visualizza un messaggio di debug
    Dire [Collisione rilevata!] per (1) secondi
    # Evidenzia visivamente la collisione
    Cambia effetto [fantasma v] di (50)
    Attendi (0.5) secondi
    Azzera effetti grafici
  Fine
Fine
```

### 2. Problemi di movimento

**Problema**: La rana non si muove correttamente o si muove in direzioni inaspettate.

**Soluzioni**:

- Verifica che i blocchi di movimento utilizzino i valori corretti
- Controlla che non ci siano conflitti tra diversi script di movimento
- Assicurati che i limiti dell'area di gioco siano definiti correttamente

```
# Debugging del movimento
Quando si preme bandiera verde
Per sempre
  # Visualizza la posizione e la direzione
  Dire unione [x: ] (x position) unione [, y: ] (y position) unione [, direzione: ] (direzione) per (0.5) secondi
  # Evidenzia visivamente i limiti dell'area di gioco
  Penna giù
  Vai a x: (-240) y: (-180)
  Vai a x: (240) y: (-180)
  Vai a x: (240) y: (180)
  Vai a x: (-240) y: (180)
  Vai a x: (-240) y: (-180)
  Penna su
Fine
```

### 3. Problemi di sincronizzazione

**Problema**: Gli eventi non si verificano nel momento giusto o si verificano in ordine errato.

**Soluzioni**:

- Utilizza i messaggi per sincronizzare gli eventi tra diversi sprite
- Aggiungi blocchi "attendi" per controllare il timing
- Utilizza variabili di stato per tracciare lo stato del gioco

```
# Debugging della sincronizzazione
Quando si preme bandiera verde
Imposta [stato_gioco v] a [inizializzazione]
Dire unione [Stato: ] (stato_gioco) per (1) secondi
Imposta [stato_gioco v] a [gioco]
Dire unione [Stato: ] (stato_gioco) per (1) secondi
# ...

Quando ricevo [fine_livello v]
# Verifica che il messaggio venga ricevuto
Dire [Messaggio 'fine_livello' ricevuto] per (1) secondi
Imposta [stato_gioco v] a [transizione]
Dire unione [Stato: ] (stato_gioco) per (1) secondi
```

## Strumenti avanzati di debugging

### 1. Logging strutturato

Possiamo implementare un sistema di logging strutturato che registra eventi importanti durante l'esecuzione del gioco:

```
Quando si preme bandiera verde
# Inizializza il log
Cancella [log v]

Quando ricevo [log_evento v]
# Aggiungi l'evento al log con timestamp
Aggiungi unione (timer) unione [: ] (evento) a [log v]
```

### 2. Modalità di debug

Possiamo implementare una modalità di debug che può essere attivata/disattivata durante il gioco:

```
Quando si preme [d]
# Attiva/disattiva la modalità debug
Se <(debug_mode) = [falso]> allora
  Imposta [debug_mode v] a [vero]
  Dire [Modalità debug attivata] per (1) secondi
Altrimenti
  Imposta [debug_mode v] a [falso]
  Dire [Modalità debug disattivata] per (1) secondi
Fine

Quando si preme bandiera verde
Per sempre
  Se <(debug_mode) = [vero]> allora
    # Visualizza informazioni di debug
    Dire unione [FPS: ] (1 / (timer - (ultimo_frame))) unione [\nSprite: ] (numero di sprite) per (0.1) secondi
    Imposta [ultimo_frame v] a (timer)
  Fine
Fine
```

### 3. Visualizzazione delle hitbox

Per debugging avanzato delle collisioni, possiamo visualizzare le hitbox degli sprite:

```
Quando si preme bandiera verde
Per sempre
  Se <(debug_mode) = [vero]> allora
    # Visualizza la hitbox della rana
    Vai a x: (x position di [rana v]) y: (y position di [rana v])
    Penna giù
    Ripeti (4)
      Fai (30) passi
      Gira a destra di (90) gradi
    Fine
    Penna su
  Fine
Fine
```

## Approccio sistematico al debugging

### 1. Identificazione del problema

Il primo passo è identificare chiaramente il problema:

- Cosa sta succedendo?
- Quando si verifica?
- È riproducibile?

### 2. Isolamento del problema

Una volta identificato il problema, cerca di isolarlo:

- Quali parti del codice sono coinvolte?
- Quali sprite sono coinvolti?
- Quali variabili sono coinvolte?

### 3. Formulazione di ipotesi

Formula ipotesi sulle possibili cause del problema:

- Potrebbe essere un problema di timing?
- Potrebbe essere un problema di collisione?
- Potrebbe essere un problema di logica?

### 4. Test delle ipotesi

Testa le tue ipotesi una alla volta:

- Modifica il codice in base all'ipotesi
- Osserva se il problema persiste
- Se il problema persiste, prova un'altra ipotesi

### 5. Implementazione della soluzione

Una volta identificata la causa del problema, implementa una soluzione:

- Modifica il codice per risolvere il problema
- Assicurati che la soluzione non causi altri problemi
- Documenta la soluzione per riferimento futuro

## Esercizio pratico

Implementa un sistema di debugging per il tuo gioco Frogger che includa:

1. Una modalità di debug che può essere attivata/disattivata premendo il tasto "D"
2. Visualizzazione delle informazioni di debug (posizione, direzione, stato) quando la modalità debug è attiva
3. Logging degli eventi importanti (collisioni, cambi di livello, ecc.)

## Sfida aggiuntiva

Implementa un sistema di "replay" che registra le azioni del giocatore e permette di riprodurle automaticamente. Questo può essere estremamente utile per il debugging, poiché permette di riprodurre esattamente le condizioni in cui si è verificato un problema.