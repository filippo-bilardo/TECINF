# Sistema di punteggio

In questa guida, esploreremo come implementare un sistema di punteggio nel nostro gioco Frogger. Un sistema di punteggio ben progettato è fondamentale per motivare i giocatori, fornire un senso di progressione e aumentare la rigiocabilità del gioco.

## Importanza del sistema di punteggio

Un sistema di punteggio serve a diversi scopi:

1. **Feedback sulle prestazioni**: Comunica al giocatore quanto sta facendo bene
2. **Motivazione**: Incoraggia il giocatore a migliorare e superare i propri record
3. **Obiettivi**: Fornisce obiettivi chiari da raggiungere
4. **Competizione**: Permette ai giocatori di confrontare i propri risultati
5. **Progressione**: Può essere utilizzato per sbloccare nuovi contenuti o livelli

## Elementi di un sistema di punteggio

### 1. Azioni che assegnano punti

In Frogger, possiamo assegnare punti per diverse azioni:

- **Movimento in avanti**: Premiare il progresso verso l'obiettivo
- **Raggiungimento di una ninfea**: Premiare il completamento di un obiettivo principale
- **Completamento del livello**: Premiare il completamento di tutti gli obiettivi
- **Tempo rimanente**: Premiare la velocità di completamento
- **Bonus speciali**: Premiare azioni o achievement particolari

### 2. Visualizzazione del punteggio

Il punteggio deve essere chiaramente visibile al giocatore in ogni momento:

```
quando si clicca sulla bandiera verde
porta [punteggio v] a [0]
ripeti sempre
  dire unione di [Punteggio: ] e (punteggio)
fine
```

### 3. Salvataggio del record

Per aumentare la rigiocabilità, è importante salvare e visualizzare il record del giocatore:

```
quando si clicca sulla bandiera verde
se <(record) = [0]> allora  // Se è la prima volta che si gioca
  porta [record v] a [0]
fine
ripeti sempre
  se <(punteggio) > (record)> allora
    porta [record v] a (punteggio)
  fine
fine
```

## Implementazione del sistema di punteggio in Frogger

### 1. Inizializzazione del punteggio

```
quando si clicca sulla bandiera verde
porta [punteggio v] a [0]
porta [moltiplicatore v] a [1]  // Opzionale: per punteggi bonus
```

### 2. Assegnazione dei punti per il movimento

```
definiamo [muovi in avanti]
se <(y) > (y precedente)> allora  // Se la rana si è mossa in avanti
  cambia [punteggio v] di (10 * (moltiplicatore))
  porta [y precedente v] a (y)
fine
```

### 3. Assegnazione dei punti per il raggiungimento di una ninfea

```
definiamo [raggiungi ninfea]
cambia [punteggio v] di (50 * (moltiplicatore))
suona suono [vittoria v]
ripeti (5)
  effetto [luminosità v] per (0.2) secondi
  effetto [colore v] per (0.2) secondi
fine
porta [ninfee raggiunte v] a ((ninfee raggiunte) + (1))
se <(ninfee raggiunte) = (5)> allora  // Se tutte le ninfee sono state raggiunte
  invia a tutti [livello completato v]
fine
```

### 4. Bonus di tempo

```
quando ricevo [livello completato v]
cambia [punteggio v] di ((tempo rimanente) * (2))  // 2 punti per ogni secondo rimanente
suona suono [bonus v]
dici unione di [Bonus tempo: ] e ((tempo rimanente) * (2)) per (2) secondi
```

### 5. Moltiplicatore di punteggio

Per rendere il sistema di punteggio più interessante, possiamo implementare un moltiplicatore che aumenta in base alle prestazioni del giocatore:

```
definiamo [aggiorna moltiplicatore]
se <(rane salvate consecutive) > (2)> allora
  porta [moltiplicatore v] a [2]
fine
se <(rane salvate consecutive) > (4)> allora
  porta [moltiplicatore v] a [3]
fine
```

### 6. Visualizzazione del punteggio e del record

```
// Nello sprite "Punteggio"
quando si clicca sulla bandiera verde
porta a x: (200) y: (170)
ripeti sempre
  dire unione di [Punteggio: ] e (punteggio) unione di [ Record: ] e (record)
fine
```

### 7. Animazione del punteggio

Per rendere più gratificante l'ottenimento di punti, possiamo aggiungere un'animazione:

```
definiamo [mostra punti guadagnati [punti]]
crea clone di [indicatore punti v]

// Nello sprite "indicatore punti"
quando vengo clonato
porta a x: (x della rana) y: (y della rana)
dici unione di [+] e (punti) per (1) secondi
scivola in (1) secondi a x: (x) y: (y + 50)
elimina questo clone
```

## Bilanciamento del sistema di punteggio

Un buon sistema di punteggio deve essere bilanciato per essere gratificante ma non troppo facile o difficile:

### 1. Distribuzione dei punti

I punti devono essere distribuiti in modo che le azioni più difficili o rischiose diano più punti:

- Movimento in avanti: 10 punti
- Raggiungimento di una ninfea: 50 punti
- Completamento del livello: 100 punti
- Bonus di tempo: 2 punti per secondo rimanente
- Bonus per non aver perso vite: 100 punti

### 2. Curva di difficoltà

Il sistema di punteggio può essere utilizzato per creare una curva di difficoltà che aumenta gradualmente:

```
quando ricevo [prossimo livello v]
cambia [livello v] di (1)
porta [velocità ostacoli v] a ((velocità ostacoli) * (1.2))  // Aumenta la difficoltà
porta [tempo limite v] a ((tempo limite) - (5))  // Riduce il tempo disponibile
porta [moltiplicatore punti base v] a ((moltiplicatore punti base) + (0.5))  // Aumenta i punti ottenibili
```

### 3. Ricompense per il rischio

Possiamo incentivare i giocatori a prendere rischi per ottenere più punti:

```
definiamo [raccogli bonus]
cambia [punteggio v] di (30)
suona suono [bonus v]
effetto [luminosità v] per (0.3) secondi
```

## Estensioni del sistema di punteggio

### 1. Tabella dei punteggi

Per progetti più avanzati, possiamo implementare una tabella dei punteggi che salva i migliori risultati:

```
definiamo [aggiorna tabella punteggi]
se <(punteggio) > (elemento (10) di [lista punteggi v])> allora
  aggiungi (punteggio) a [lista punteggi v]
  ordina [lista punteggi v] in ordine decrescente
  elimina elemento (11) di [lista punteggi v]
  chiedi [Inserisci il tuo nome:] e attendi
  porta [nome giocatore v] a (risposta)
  aggiungi (nome giocatore) a [lista nomi v]
  // Riordina la lista nomi in base alla lista punteggi
fine
```

### 2. Achievement

Gli achievement sono obiettivi speciali che i giocatori possono completare per ottenere riconoscimenti:

```
definiamo [controlla achievement]
se <(rane salvate) = (10) e <non (achievement sbloccato [Salvatore di rane])>> allora
  porta [achievement sbloccato [Salvatore di rane] v] a [vero]
  invia a tutti [achievement sbloccato v]
fine
se <(punteggio) > (1000) e <non (achievement sbloccato [Maestro di Frogger])>> allora
  porta [achievement sbloccato [Maestro di Frogger] v] a [vero]
  invia a tutti [achievement sbloccato v]
fine
```

### 3. Sistema di livelli per il giocatore

Possiamo implementare un sistema di livelli per il giocatore basato sul punteggio totale accumulato:

```
definiamo [aggiorna livello giocatore]
se <(punteggio totale) > (1000)> allora
  porta [livello giocatore v] a [2]
fine
se <(punteggio totale) > (3000)> allora
  porta [livello giocatore v] a [3]
fine
// E così via
```

## Debugging del sistema di punteggio

Per assicurarsi che il sistema di punteggio funzioni correttamente:

1. **Logging**: Utilizzare la funzione "dire" per visualizzare quando vengono assegnati punti
2. **Verifica del bilanciamento**: Testare il gioco per assicurarsi che i punti siano bilanciati
3. **Controllo dei bug**: Verificare che non ci siano modi per ottenere punti in modo non intenzionale

## Conclusione

Un sistema di punteggio ben progettato è un elemento fondamentale per creare un'esperienza di gioco coinvolgente e motivante. Implementando queste tecniche nel nostro gioco Frogger, possiamo aumentare significativamente la rigiocabilità e fornire ai giocatori obiettivi chiari da raggiungere.

Nella prossima guida, esploreremo come implementare un sistema di livelli per creare una progressione di gioco che mantenga alta l'attenzione del giocatore.

## Navigazione del Corso
- [📑 Indice](../README.md)
- [⬅️ Effetti sonori e musica](../04-AnimazioniESuoni/02-EffettiSonori.md)
- [➡️ Progressione dei livelli](./02-ProgressioneLivelli.md)