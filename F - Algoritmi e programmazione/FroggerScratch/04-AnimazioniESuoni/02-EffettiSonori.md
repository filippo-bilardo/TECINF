# Effetti sonori e musica

In questa guida, esploreremo come implementare effetti sonori e musica di sottofondo nel nostro gioco Frogger. L'audio è un elemento fondamentale per creare un'esperienza di gioco immersiva e coinvolgente, fornendo feedback immediato sulle azioni del giocatore e contribuendo all'atmosfera generale del gioco.

## Importanza dell'audio nei videogiochi

L'audio nei videogiochi serve a diversi scopi:

1. **Feedback sonoro**: Comunica al giocatore che le sue azioni hanno avuto effetto
2. **Immersione**: Contribuisce a creare l'atmosfera e l'ambientazione del gioco
3. **Informazioni**: Fornisce indizi su eventi o pericoli imminenti
4. **Emozione**: Intensifica le reazioni emotive del giocatore
5. **Ritmo**: Scandisce il ritmo del gameplay

## Tipi di audio in Scratch

Scratch offre due principali categorie di audio:

### 1. Suoni

I suoni sono brevi clip audio utilizzate principalmente per effetti sonori. Possono essere riprodotti in risposta ad azioni specifiche o eventi di gioco.

### 2. Musica

La musica è costituita da tracce audio più lunghe utilizzate come sottofondo. Può essere riprodotta in loop per creare un'atmosfera continua.

## Gestione dell'audio in Scratch

### Importazione di suoni

Scratch offre diverse opzioni per aggiungere suoni al progetto:

1. **Libreria di suoni**: Scratch include una vasta libreria di suoni predefiniti
2. **Registrazione**: È possibile registrare suoni direttamente in Scratch
3. **Caricamento**: È possibile caricare file audio dal computer

Per accedere a queste opzioni, fare clic sulla scheda "Suoni" nella parte superiore dell'editor Scratch, quindi utilizzare i pulsanti nella parte inferiore della scheda.

### Riproduzione di suoni

Scratch offre diversi blocchi per la riproduzione dei suoni:

```
suona suono [nome del suono v]
```
Riproduce il suono specificato e passa immediatamente al blocco successivo.

```
suona suono [nome del suono v] e attendi
```
Riproduce il suono specificato e attende che finisca prima di passare al blocco successivo.

```
ferma tutti i suoni
```
Interrompe tutti i suoni in riproduzione.

### Modifica dei suoni

Scratch include un editor di suoni che permette di modificare i suoni importati o registrati. È possibile tagliare, copiare, incollare, invertire e applicare effetti come eco, robot e più alto/più basso.

## Implementazione degli effetti sonori in Frogger

### 1. Suoni per le azioni del giocatore

#### Movimento della rana

```
definiamo [salta]
suona suono [salto v]
pass al costume [rana salto v]
attendi (0.1) secondi
cambia y di (10)
attendi (0.1) secondi
cambia y di (10)
pass al costume [rana normale v]
```

#### Collisione con ostacoli

```
definiamo [collisione]
suona suono [splat v]
effetto [fantasma v] per (0.3) secondi
effetto [mosaico v] per (0.3) secondi
pass al costume [rana schiacciata v]
attendi (0.5) secondi
pass al costume [rana normale v]
```

#### Caduta nell'acqua

```
definiamo [caduta acqua]
suona suono [splash v]
effetto [onda v] per (0.5) secondi
pass al costume [rana che nuota v]
attendi (0.5) secondi
pass al costume [rana normale v]
```

#### Raggiungimento di una ninfea

```
definiamo [arrivo]
suona suono [vittoria v]
ripeti (5)
  effetto [luminosità v] per (0.2) secondi
  effetto [colore v] per (0.2) secondi
fine
```

### 2. Suoni ambientali

#### Suoni dei veicoli

```
// Nello script di un camion
quando si clicca sulla bandiera verde
ripeti sempre
  se <(distanza da [Rana v]) < (150)> allora
    porta volume a ((100 - (distanza da [Rana v])) / 2)%
    se <non (suono in riproduzione?)> allora
      suona suono [motore v]
    fine
  altrimenti
    ferma tutti i suoni
  fine
fine
```

#### Suoni dell'acqua

```
// Nello script dello sfondo del fiume
quando si clicca sulla bandiera verde
ripeti sempre
  se <(y della [Rana v]) > (50) e (y della [Rana v]) < (150)> allora
    porta volume a (50)%
    se <non (suono in riproduzione?)> allora
      suona suono [fiume v]
    fine
  altrimenti
    porta volume a (20)%
  fine
fine
```

### 3. Suoni di sistema

#### Perdita di una vita

```
definiamo [perdi vita]
suona suono [perdita vita v]
cambia [vite v] di (-1)
effetto [fantasma v] per (0.5) secondi
se <(vite) > (0)> allora
  vai a x: (0) y: (-180)  // Posizione iniziale
altrimenti
  invia a tutti [game over v]
fine
```

#### Game over

```
quando ricevo [game over v]
ferma tutti i suoni
suona suono [game over v]
nascondi  // Nascondi la rana
ferma [tutti gli altri script v]
```

#### Completamento del livello

```
quando ricevo [livello completato v]
ferma tutti i suoni
suona suono [livello completato v] e attendi
invia a tutti [prossimo livello v]
```

## Implementazione della musica di sottofondo

### 1. Musica di base

```
quando si clicca sulla bandiera verde
ferma tutti i suoni
ripeti sempre
  suona suono [musica sottofondo v] e attendi
fine
```

### 2. Musica adattiva

La musica adattiva cambia in base allo stato del gioco, aumentando l'immersione e l'intensità dell'esperienza.

```
quando si clicca sulla bandiera verde
porta [stato gioco v] a [normale]
ripeti sempre
  se <(stato gioco) = [normale]> allora
    se <non <(suono in riproduzione?) e (suono = [musica normale v])>> allora
      ferma tutti i suoni
      suona suono [musica normale v]
    fine
  fine
  se <(stato gioco) = [pericolo]> allora
    se <non <(suono in riproduzione?) e (suono = [musica pericolo v])>> allora
      ferma tutti i suoni
      suona suono [musica pericolo v]
    fine
  fine
  se <(stato gioco) = [vittoria]> allora
    se <non <(suono in riproduzione?) e (suono = [musica vittoria v])>> allora
      ferma tutti i suoni
      suona suono [musica vittoria v]
    fine
  fine
fine
```

### 3. Transizioni musicali

Per transizioni più fluide tra diverse tracce musicali:

```
definiamo [cambia musica a [nuova musica]]
porta [volume attuale v] a (100)
ripeti fino a <(volume attuale) = (0)>
  cambia [volume attuale v] di (-5)
  porta volume a (volume attuale)%
  attendi (0.05) secondi
fine
ferma tutti i suoni
suona suono (nuova musica)
ripeti fino a <(volume attuale) = (100)>
  cambia [volume attuale v] di (5)
  porta volume a (volume attuale)%
  attendi (0.05) secondi
fine
```

## Ottimizzazione dell'audio

### 1. Gestione del volume

È importante bilanciare i livelli di volume dei diversi elementi audio:

```
quando si clicca sulla bandiera verde
porta [volume musica v] a (30)%  // La musica di sottofondo dovrebbe essere più bassa
porta [volume effetti v] a (80)%  // Gli effetti sonori dovrebbero essere più alti
```

### 2. Prioritizzazione dei suoni

In situazioni con molti suoni contemporanei, è importante prioritizzare quelli più importanti:

```
definiamo [riproduci suono prioritario [nome suono]]
se <(priorità) > (priorità suono attuale)> allora
  ferma tutti i suoni
  suona suono (nome suono)
  porta [priorità suono attuale v] a (priorità)
fine
```

### 3. Distanza spaziale

Per un audio più realistico, il volume può variare in base alla distanza tra la fonte del suono e il giocatore:

```
definiamo [riproduci suono spaziale [nome suono] da [fonte]]
porta [distanza v] a (distanza da (fonte))
se <(distanza) < (200)> allora
  porta [volume calcolato v] a ((100 - (distanza / 2)))%
  porta volume a (volume calcolato)
  suona suono (nome suono)
fine
```

## Considerazioni tecniche

### 1. Formati audio supportati

Scratch supporta i formati audio WAV e MP3. I file WAV offrono una migliore qualità ma occupano più spazio, mentre i file MP3 sono più compressi ma potrebbero avere una qualità leggermente inferiore.

### 2. Dimensione del progetto

I file audio possono aumentare significativamente la dimensione del progetto Scratch. Per ottimizzare:

- Utilizzare file MP3 invece di WAV quando possibile
- Tagliare i suoni per rimuovere parti non necessarie
- Utilizzare una frequenza di campionamento più bassa per suoni meno importanti

### 3. Latenza audio

In alcuni casi, potrebbe esserci un leggero ritardo tra l'azione e il suono corrispondente. Per minimizzare questo problema:

- Utilizzare file audio più piccoli
- Precaricaricare i suoni all'inizio del gioco
- Evitare di riprodurre troppi suoni contemporaneamente

## Risorse audio

Ecco alcune risorse utili per trovare effetti sonori e musica per il vostro gioco Frogger:

1. **Libreria di Scratch**: Contiene molti suoni utili
2. **Freesound.org**: Una vasta libreria di effetti sonori gratuiti
3. **OpenGameArt.org**: Offre musica e suoni con licenze libere
4. **Incompetech.com**: Musica royalty-free di Kevin MacLeod

Ricordate di verificare sempre le licenze dei suoni che utilizzate e di dare credito agli autori quando richiesto.

## Conclusione

Gli effetti sonori e la musica sono elementi fondamentali per creare un'esperienza di gioco coinvolgente e immersiva. Implementando un sistema audio ben progettato nel nostro gioco Frogger, possiamo migliorare significativamente la qualità percepita del gioco e fornire al giocatore un feedback immediato sulle sue azioni.

Nella prossima guida, esploreremo come implementare un sistema di punteggio per tenere traccia dei progressi del giocatore e aumentare la rigiocabilità del nostro gioco.

## Navigazione del Corso
- [📑 Indice](../README.md)
- [⬅️ Animazioni e feedback visivo](./01-AnimazioniFeedback.md)
- [➡️ Sistema di punteggio](../05-PunteggioELivelli/01-SistemaPunteggio.md)