# Progettazione dei livelli

In questa guida, esploreremo come progettare livelli efficaci per il nostro gioco Frogger in Scratch, un elemento cruciale per creare un'esperienza di gioco coinvolgente e progressivamente sfidante.

## Principi di design dei livelli

Un buon design dei livelli bilancia sfida e divertimento, mantenendo il giocatore impegnato senza frustrarlo eccessivamente.

### Curva di difficoltà

La difficoltà dovrebbe aumentare gradualmente per permettere al giocatore di migliorare le proprie abilità:

- **Livello 1**: Introduzione alle meccaniche di base, pochi ostacoli e movimento lento
- **Livelli intermedi**: Aumento progressivo della velocità e del numero di ostacoli
- **Livelli avanzati**: Configurazioni complesse, timing preciso richiesto, bonus difficili da raggiungere

### Varietà e ritmo

Per mantenere l'interesse del giocatore, è importante variare gli elementi di gioco:

- Alternare sezioni facili e difficili
- Introdurre nuovi tipi di ostacoli o piattaforme
- Creare momenti di tensione seguiti da brevi pause

## Struttura di un livello in Frogger

Un livello tipico di Frogger è composto da diverse zone con caratteristiche specifiche.

### Zona di partenza

L'area sicura da cui la rana inizia il suo percorso:

```
quando si clicca su bandiera verde
vai a x: (0) y: (-150)
```

### Zona stradale

L'area con veicoli in movimento che la rana deve attraversare:

```
# Per un veicolo
quando si clicca su bandiera verde
vai a x: (-240) y: (-100)
porta [velocità] a (3)
ripeti sempre
  cambia x di (velocità)
  se <(x) > (240)> allora
    vai a x: (-240)
  fine
fine
```

Per creare più corsie con traffico, possiamo duplicare questo script modificando la posizione y e la velocità (positiva per movimento verso destra, negativa per movimento verso sinistra).

### Zona fluviale

L'area con acqua e piattaforme galleggianti:

```
# Per un tronco
quando si clicca su bandiera verde
vai a x: (240) y: (50)
porta [velocità] a (-2)
ripeti sempre
  cambia x di (velocità)
  se <(x) < (-240)> allora
    vai a x: (240)
  fine
fine
```

Anche qui, possiamo creare più corsie con tronchi e tartarughe a diverse velocità.

### Zona di arrivo

Le destinazioni sicure che la rana deve raggiungere:

```
# Per una destinazione
quando si clicca su bandiera verde
vai a x: (posizione x) y: (150)
ripeti sempre
  se <sta toccando [rana v]?> allora
    invia a tutti [punto segnato v]
    cambia costume in [destinazione_raggiunta v]
  fine
fine
```

## Implementazione di livelli multipli

### Utilizzo di sfondi diversi

Possiamo utilizzare sfondi diversi per rappresentare i vari livelli:

```
quando ricevo [nuovo livello v]
cambia sfondo in (unione [livello] (livello))
```

### Configurazione dinamica degli ostacoli

Possiamo modificare la configurazione degli ostacoli in base al livello:

```
quando ricevo [nuovo livello v]
se <(livello) = 2> allora
  porta [velocità] a (4)
  porta [frequenza_spawn] a (50)
altrimenti se <(livello) = 3> allora
  porta [velocità] a (5)
  porta [frequenza_spawn] a (30)
fine
```

### Liste per la configurazione dei livelli

Per una gestione più flessibile, possiamo utilizzare liste per memorizzare le configurazioni dei livelli:

```
# Inizializzazione delle liste
quando si clicca su bandiera verde
cancella [velocità_veicoli v]
aggiungi (2) a [velocità_veicoli v]
aggiungi (3) a [velocità_veicoli v]
aggiungi (4) a [velocità_veicoli v]

# Applicazione della configurazione
quando ricevo [nuovo livello v]
porta [velocità] a (elemento (livello) di [velocità_veicoli v])
```

## Tecniche avanzate di design

### Pattern di ostacoli

Per creare sfide interessanti, possiamo progettare pattern specifici di ostacoli:

```
# Spawn sincronizzato di veicoli
quando si clicca su bandiera verde
ripeti sempre
  crea clone di [auto1 v]
  attendi (2) secondi
  crea clone di [auto2 v]
  attendi (1) secondi
fine
```

### Eventi casuali

Per aggiungere varietà, possiamo introdurre eventi casuali:

```
quando si clicca su bandiera verde
ripeti sempre
  attendi (numero a caso da (5) a (15)) secondi
  invia a tutti [evento_casuale v]
fine

quando ricevo [evento_casuale v]
se <(numero a caso da (1) a (3)) = 1> allora
  # Evento 1: Pioggia che aumenta la velocità dell'acqua
  cambia [velocità_tronchi] di (1)
  attendi (10) secondi
  cambia [velocità_tronchi] di (-1)
altrimenti se <(numero a caso da (1) a (3)) = 2> allora
  # Evento 2: Traffico intenso
  porta [frequenza_spawn] a ((frequenza_spawn) / 2)
  attendi (8) secondi
  porta [frequenza_spawn] a ((frequenza_spawn) * 2)
fine
```

### Checkpoint

Per livelli più lunghi, possiamo implementare checkpoint:

```
quando si clicca su bandiera verde
porta [checkpoint_attivo] a (falso)
porta [checkpoint_x] a (0)
porta [checkpoint_y] a (0)

quando ricevo [checkpoint_raggiunto v]
porta [checkpoint_attivo] a (vero)
porta [checkpoint_x] a (x)
porta [checkpoint_y] a (y)

quando ricevo [game over v]
se <(checkpoint_attivo) = (vero)> allora
  vai a x: (checkpoint_x) y: (checkpoint_y)
altrimenti
  vai a x: (0) y: (-150)
fine
```

## Test e bilanciamento

Il test è fondamentale per garantire che i livelli siano divertenti e ben bilanciati.

### Raccolta di feedback

Possiamo implementare un sistema per raccogliere dati durante il test:

```
variabile [tentativi_livello1] = 0
variabile [tempo_livello1] = 0

quando ricevo [game over v]
se <(livello) = 1> allora
  cambia [tentativi_livello1] di (1)
fine

quando ricevo [livello_completato v]
se <(livello) = 1> allora
  porta [tempo_livello1] a (timer)
fine
```

### Aggiustamenti in base ai dati

In base ai dati raccolti, possiamo apportare modifiche:

- Se un livello ha un numero di tentativi troppo alto, potrebbe essere troppo difficile
- Se un livello viene completato troppo velocemente, potrebbe essere troppo facile
- Se i giocatori perdono sempre nello stesso punto, potrebbe essere necessario modificare quel pattern specifico

## Conclusione

Un buon design dei livelli è essenziale per creare un'esperienza di gioco coinvolgente in Frogger. Bilanciando la difficoltà, variando gli elementi di gioco e testando accuratamente, possiamo creare livelli che sfidano e divertono i giocatori, mantenendo alto il loro interesse.

## Esercizi pratici

1. Progetta un livello introduttivo che insegni gradualmente le meccaniche di gioco
2. Crea un sistema di livelli con difficoltà crescente basato su liste di configurazione
3. Implementa eventi casuali che modificano temporaneamente le condizioni di gioco
4. Sviluppa un sistema di checkpoint per livelli più complessi

## Risorse aggiuntive

- [Principi di game design](https://en.scratch-wiki.info/wiki/Game_Design)
- [Tutorial su design dei livelli in Scratch](https://scratch.mit.edu/studios/5941283/)

---

[◀ Gestione del punteggio e delle vite](./05-PunteggioEVite.md) | [Effetti sonori e visivi ▶](./07-EffettiSonoriVisivi.md)