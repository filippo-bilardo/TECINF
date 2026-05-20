# 02 — Input da Tastiera e Movimento

> **Concetto chiave:** eventi e controllo del personaggio
> **Durata stimata:** 45–60 minuti
> **Prerequisiti:** Unità 1 completata — lo sprite della rana e il campo di gioco sono già presenti nel progetto

---

## Obiettivi dell'unità

Al termine di questa unità lo studente sarà in grado di:

- Spiegare cos'è un **evento** e come funziona in Scratch
- Usare i blocchi di controllo per muovere uno sprite con i tasti freccia
- Distinguere tra **movimento continuo** e **movimento a scatti**
- Impedire alla rana di uscire dai bordi dello schermo

---

## 2.1 — Cos'è un evento?

### 📖 Introduzione teorica

Quando giochi con un videogioco, premi un tasto e il personaggio si muove. Ma com'è possibile? Il segreto sta in un meccanismo chiamato **evento**.

Un **evento** è qualcosa che succede mentre il programma è in esecuzione: un tasto premuto, un clic del mouse, un messaggio ricevuto. Quando si verifica un evento, il programma si "sveglia" e risponde eseguendo una serie di istruzioni.

In Scratch, gli eventi si riconoscono facilmente: hanno la forma di un **cappello arrotondato** nella parte superiore e si trovano nella categoria gialla **"Situazioni"** (o "Events" se usi Scratch in inglese).

```
┌─────────────────────────────┐
│  Quando si preme il tasto ▼ │   ← blocco evento (ha il "cappello")
└──────────────┬──────────────┘
               │
┌──────────────▼──────────────┐
│   vai a x: 0  y: -150       │   ← istruzioni da eseguire
└─────────────────────────────┘
```

> 💡 **Analogia:** Gli eventi funzionano come un campanello alla porta. Il programma non controlla continuamente se qualcuno è arrivato — aspetta in silenzio, e quando suona il campanello (evento), va ad aprire (esegue le istruzioni).

### Blocchi evento principali usati in questo corso

| Blocco | Quando si attiva |
|--------|-----------------|
| `quando si clicca su 🚩` | All'avvio del progetto |
| `quando si preme il tasto [freccia su]` | Quando si preme la freccia su |
| `quando si preme il tasto [freccia giù]` | Quando si preme la freccia giù |
| `quando si preme il tasto [freccia sinistra]` | Quando si preme la freccia sinistra |
| `quando si preme il tasto [freccia destra]` | Quando si preme la freccia destra |

---

## 2.2 — Muovere la rana con i tasti freccia

### 📖 Introduzione teorica

In Scratch, la posizione di ogni sprite è definita da due coordinate: **x** (orizzontale) e **y** (verticale). Il centro dello schermo è il punto (0, 0).

```
         y = 180 (alto)
              ▲
              │
  x = -240 ◄──┼──► x = 240
              │
         y = -180 (basso)
```

Per muovere la rana, dobbiamo **cambiare il valore di x o y** di una quantità fissa a ogni pressione del tasto:

- **Freccia su** → aumenta y (la rana sale)
- **Freccia giù** → diminuisce y (la rana scende)
- **Freccia destra** → aumenta x (la rana va a destra)
- **Freccia sinistra** → diminuisce x (la rana va a sinistra)

Il blocco da usare è **`cambia y di [valore]`** oppure **`cambia x di [valore]`**, che si trova nella categoria **"Moto"** (azzurra).

### 🛠️ Passaggi guidati

**Passo 1 — Seleziona lo sprite della rana**

Clicca sulla rana nell'area degli sprite in basso. Assicurati che sia selezionata (bordo azzurro attorno).

---

**Passo 2 — Aggiungi il movimento verso l'alto**

1. Vai nella categoria **"Situazioni"** (gialla) e trascina il blocco:
   ```
   quando si preme il tasto [freccia su]
   ```
2. Vai nella categoria **"Moto"** (azzurra) e trascina sotto:
   ```
   cambia y di (40)
   ```
3. Aggancia i due blocchi insieme.

> Il valore `40` corrisponde a un "salto" della rana. Puoi modificarlo in base alle dimensioni del tuo campo di gioco.

---

**Passo 3 — Aggiungi i movimenti nelle altre direzioni**

Ripeti l'operazione per le altre tre frecce, usando i valori seguenti:

| Tasto | Blocco da usare | Valore |
|-------|----------------|--------|
| Freccia giù | `cambia y di` | `-40` |
| Freccia destra | `cambia x di` | `40` |
| Freccia sinistra | `cambia x di` | `-40` |

Alla fine dovresti avere **quattro script** separati, ognuno con il suo blocco evento.

---

**Passo 4 — Testa il movimento**

Clicca sulla bandiera verde 🚩 e premi le frecce. La rana si muove!

> ⚠️ **Problema comune:** Se la rana ruota invece di muoversi, vai nelle proprietà dello sprite e imposta **"stile di rotazione"** su **non ruotare** (il simbolo del punto fisso).

---

## 2.3 — Movimento a scatti vs. movimento continuo

### 📖 Introduzione teorica

Hai notato che la rana si muove con piccoli salti ogni volta che premi un tasto? Questo si chiama **movimento a scatti** (o discreto): la rana si sposta di una quantità fissa e poi si ferma.

Esiste anche il **movimento continuo**: se tieni premuto il tasto, lo sprite si muove senza interruzioni. Quale stile scegliere dipende dal gioco.

**Confronto tra i due stili:**

| | Movimento a scatti | Movimento continuo |
|---|---|---|
| **Come funziona** | Un tasto = un salto | Tasto tenuto premuto = moto costante |
| **Blocco Scratch** | `quando si preme il tasto` | `per sempre` + `se tasto premuto?` |
| **Adatto a** | Frogger, giochi a griglia | Giochi platform, racing |
| **Precisione** | Alta (posizioni fisse) | Bassa (posizione variabile) |

Per **Frogger**, il movimento a scatti è la scelta corretta: la rana deve occupare posizioni precise sulla griglia del campo di gioco.

> 💡 **Curiosità:** Il Frogger originale del 1981 usava esattamente questo sistema. Ogni pressione del tasto spostava la rana di una casella precisa.

### Movimento continuo (opzionale — per chi ha finito prima)

Se vuoi sperimentare il movimento continuo, ecco come si costruisce:

```
quando si clicca su 🚩
│
└── per sempre
      │
      ├── se <tasto [freccia su] premuto?> allora
      │       cambia y di (5)
      ├── se <tasto [freccia giù] premuto?> allora
      │       cambia y di (-5)
      ├── se <tasto [freccia destra] premuto?> allora
      │       cambia x di (5)
      └── se <tasto [freccia sinistra] premuto?> allora
              cambia x di (-5)
```

Prova a costruirlo e confronta la sensazione di gioco con la versione a scatti.

---

## 2.4 — Limitare il movimento ai bordi del campo

### 📖 Introduzione teorica

In questo momento, se premi ripetutamente un tasto freccia, la rana esce dallo schermo. Dobbiamo **aggiungere un controllo** che blocchi il movimento quando la rana raggiungerebbe una posizione fuori dal campo.

Il blocco da usare è la **struttura condizionale `se … allora`**, che esegue un'istruzione solo se una certa condizione è vera. Lo trovate nella categoria **"Controllo"** (arancione).

La logica è questa:

```
se (la posizione y NON supererebbe il bordo superiore) allora
    cambia y di (40)
```

Oppure, in modo equivalente, possiamo spostare la rana e poi **correggerla** se è uscita:

```
cambia y di (40)
se (y > 160) allora
    cambia y di (-40)   ← torna indietro
```

### 🛠️ Passaggi guidati

**Passo 1 — Identifica i limiti del campo**

Lo schermo di Scratch misura 480 × 360 pixel. I valori limite sono:

| Bordo | Valore |
|-------|--------|
| Alto | y = 180 |
| Basso | y = -180 |
| Destra | x = 240 |
| Sinistra | x = -240 |

Se il campo di gioco non occupa tutto lo schermo, i tuoi limiti potrebbero essere più stretti — adattali al tuo sfondo.

---

**Passo 2 — Modifica lo script "freccia su"**

Sostituisci il blocco semplice `cambia y di (40)` con questa struttura:

```
quando si preme il tasto [freccia su]
│
└── se <(y) < (140)> allora
        cambia y di (40)
```

Il controllo `y < 140` garantisce che la rana si muova verso l'alto solo se non ha già raggiunto il limite superiore del campo.

---

**Passo 3 — Applica lo stesso controllo alle altre tre direzioni**

Aggiorna gli altri tre script seguendo la stessa logica:

| Script | Condizione da aggiungere |
|--------|-------------------------|
| Freccia giù | `se (y) > (-160) allora` |
| Freccia destra | `se (x) < (200) allora` |
| Freccia sinistra | `se (x) > (-200) allora` |

> I valori esatti dipendono dal tuo campo di gioco. Aggiustali finché la rana si ferma esattamente ai bordi dell'area di gioco.

---

**Passo 4 — Aggiungi la posizione di partenza**

È buona pratica definire dove appare la rana all'inizio del gioco. Aggiungi questo script:

```
quando si clicca su 🚩
│
└── vai a x: (0) y: (-150)
```

Ora ogni volta che clicchi la bandiera verde, la rana torna alla posizione di partenza.

---

**Passo 5 — Test finale**

Prova a spingere la rana contro ogni bordo. Verifica che:

- [ ] La rana non esca dallo schermo in nessuna direzione
- [ ] Il movimento sia fluido e reattivo
- [ ] La rana torni in posizione di partenza alla pressione della bandiera verde

---

## 🎯 Mini Esercizio dell'Unità

> **Obiettivo:** La rana si muove con le quattro frecce e non esce dal campo di gioco.

**Cosa deve funzionare alla fine:**

1. La rana parte dal centro-basso del campo alla pressione di 🚩
2. I tasti freccia spostano la rana in modo preciso, a scatti
3. La rana si blocca ai bordi del campo senza "sparire"
4. Il movimento è a griglia: ogni pressione sposta la rana di una casella fissa

**Verifica il tuo lavoro:**

Conta quanti script hai nella scheda dello sprite della rana. Dovresti avere:
- 1 script con `quando si clicca su 🚩`
- 4 script con `quando si preme il tasto [freccia ...]`

In totale: **5 script**.

---

## 💡 Domande di Riflessione

Rispondi a queste domande per consolidare ciò che hai imparato. Puoi scrivere le risposte sul quaderno o discuterle con un compagno.

---

**Domanda 1**
Nel codice seguente, in quale ordine vengono eseguiti i blocchi A, B e C?

```
quando si preme il tasto [freccia su]   ← blocco A
cambia y di (40)                         ← blocco B
cambia costume in [rana-su]              ← blocco C
```

a) C, B, A
b) A, B, C
c) I blocchi vengono eseguiti tutti insieme nello stesso istante
d) L'ordine dipende dalla velocità del computer

> *Risposta corretta: **b)** — I blocchi di uno script vengono sempre eseguiti dall'alto verso il basso, uno alla volta.*

---

**Domanda 2**
Hai impostato `cambia y di (40)` per il tasto freccia su, ma la rana salta troppo in alto. Come potresti risolvere?

a) Cancellare il blocco e ricominciare da zero
b) Cambiare il valore `40` con un numero più piccolo, ad esempio `20`
c) Usare il tasto freccia giù al posto del tasto freccia su
d) Non è possibile modificare il valore di un blocco in Scratch

> *Risposta corretta: **b)** — Il valore all'interno dei blocchi è modificabile: basta fare doppio clic sul numero e digitare il nuovo valore.*

---

**Domanda 3**
Cosa succederebbe se rimuovessi il controllo sui bordi (il blocco `se … allora`) dallo script della freccia su?

a) La rana non si muoverebbe più verso l'alto
b) La rana si muoverebbe verso l'alto senza fermarsi, uscendo dallo schermo
c) Il progetto andrebbe in errore e si bloccherebbe
d) La rana si fermerebbe automaticamente al bordo grazie a Scratch

> *Risposta corretta: **b)** — Senza la condizione di controllo, la rana continuerebbe a spostarsi oltre il bordo dello schermo, diventando invisibile.*

---

**Domanda 4** *(riflessione aperta)*
Nel gioco Frogger originale, la rana non può muoversi all'indietro (verso il basso) una volta che ha attraversato una corsia. Come modificheresti il codice per implementare questa regola?

> *Suggerimento: pensa a come potresti usare una variabile per ricordare la posizione più alta raggiunta dalla rana, e usarla come limite per il movimento verso il basso.*

---

**Domanda 5** *(sfida)*
Hai quattro script separati, uno per ogni freccia. Un compagno ti dice: "Si può fare tutto con un solo script usando il ciclo `per sempre`". Ha ragione? Scrivi o disegna come sarebbe quel script alternativo e spiega quali sono i vantaggi e gli svantaggi rispetto alla versione con quattro script.

---

## 🔧 Tip & Tricks

> **Tip 1 — Griglia di posizionamento**
> Per allineare la rana alle "caselle" del campo, usa valori multipli della stessa quantità. Se la casella è larga 40 pixel, usa sempre multipli di 40: -120, -80, -40, 0, 40, 80, 120. Così la rana sarà sempre perfettamente centrata.

> **Tip 2 — Visualizza le coordinate**
> Spunta la casella accanto ai blocchi `x posizione` e `y posizione` nella categoria "Moto" per vedere in tempo reale le coordinate della rana mentre la muovi. Utilissimo per trovare i valori giusti dei bordi.

> **Tip 3 — Duplicare gli script**
> Puoi duplicare uno script facendo clic destro sul blocco cappello e scegliendo "Duplica". Poi modifica solo i valori che cambiano. Risparmia molto tempo!

> **Tip 4 — Commenta il tuo codice**
> Fai clic destro su un'area vuota della scheda degli script e scegli "Aggiungi commento" per lasciare note esplicative. I commenti non influenzano il funzionamento del programma, ma rendono il codice molto più facile da capire in futuro.

---

## 📋 Riepilogo dell'Unità

| Concetto | Cosa abbiamo imparato |
|----------|-----------------------|
| Evento | Un'azione che avvia l'esecuzione di uno script (`quando si preme il tasto`) |
| Coordinate x, y | Definiscono la posizione di uno sprite nello schermo |
| `cambia x/y di` | Sposta lo sprite di una quantità relativa alla posizione attuale |
| Movimento a scatti | Un tasto = uno spostamento fisso; ideale per giochi a griglia come Frogger |
| `se … allora` | Esegue un blocco solo se una condizione è vera; usato per limitare il movimento |
| Posizione iniziale | `vai a x … y …` con evento `quando si clicca su 🚩` per il reset |

---

## ➡️ Prossimo passo

Nella **Unità 3** costruiremo le automobili che attraversano la strada usando i **cicli** (`per sempre` e `ripeti`), e impareremo a controllare la velocità degli ostacoli.

---

*Mini Corso: Programmiamo con Scratch — Costruiamo Frogger! | Unità 2 di 11*