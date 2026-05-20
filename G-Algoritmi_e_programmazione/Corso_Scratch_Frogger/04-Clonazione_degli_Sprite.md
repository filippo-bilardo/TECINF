# 04 — Clonazione degli Sprite

> **Concetto chiave:** creare molte automobili con un solo sprite
> **Durata stimata:** 45–60 minuti
> **Prerequisiti:** Unità 3 completata — esiste almeno un'automobile che attraversa una corsia della strada in loop

---

## Obiettivi dell'unità

Al termine di questa unità lo studente sarà in grado di:

- Spiegare perché i cloni sono utili in un videogioco
- Usare il blocco `crea clone di me stesso`
- Distinguere tra sprite originale e clone
- Costruire più corsie di traffico usando un solo sprite-auto

---

## 4.1 — Perché non creare 10 sprite separati?

### 📖 Introduzione teorica

Se volessimo costruire tre corsie di traffico copiando manualmente lo sprite **Auto**, potremmo farlo. Ma ci sarebbe un problema: dovremmo duplicare anche il codice.

Questo porta a tre svantaggi:

1. **Più lavoro** — bisogna modificare molti sprite invece di uno solo
2. **Più errori** — magari una macchina ha uno script leggermente diverso dalle altre
3. **Meno flessibilità** — ogni cambiamento richiede più tempo

La soluzione è usare i **cloni**.

Un **clone** è una copia temporanea di uno sprite che nasce mentre il gioco è in esecuzione. Ha lo stesso aspetto dello sprite originale, ma può muoversi in modo indipendente.

> 💡 **Idea chiave:** invece di avere 10 sprite-auto diversi, avrai 1 sprite-auto "madre" che genera tutte le altre automobili.

---

## 4.2 — Il blocco `crea clone di me stesso`

### 📖 Introduzione teorica

I blocchi principali della clonazione si trovano nella categoria **Controllo**:

| Blocco | Funzione |
|--------|----------|
| `crea clone di [me stesso]` | genera una copia dello sprite |
| `quando vengo clonato` | avvia il codice del clone appena nato |
| `elimina questo clone` | rimuove il clone quando non serve più |

Il flusso è questo:

```text
sprite originale → crea clone → il clone nasce → esegue il suo script
```

### Differenza tra originale e cloni

- Lo **sprite originale** resta nel progetto anche prima di avviare il gioco
- I **cloni** esistono solo mentre il progetto è in esecuzione
- Quando fermi il progetto, i cloni spariscono automaticamente

---

## 4.3 — Gestire un clone: nascita, movimento ed eliminazione

### 🛠️ Passaggi guidati

Useremo lo sprite **Auto** creato nell'unità precedente.

**Passo 1 — Trasforma l'auto originale in "generatore"**

Nello sprite **Auto**, crea questo script:

```text
quando si clicca su 🚩
nascondi
```

Perché lo nascondiamo? Perché l'auto originale non deve attraversare la strada: deve solo creare cloni.

---

**Passo 2 — Aggiungi lo script del clone**

Sempre nello sprite **Auto**, crea questo secondo script:

```text
quando vengo clonato
mostra
per sempre
  cambia x di (-5)
  se <(x posizione) < (-260)> allora
    elimina questo clone
```

### Cosa succede

- il clone appare
- si muove verso sinistra
- quando esce completamente dallo schermo, si elimina

Questo è importante: se non elimini i cloni, il progetto accumula oggetti invisibili e diventa più difficile da gestire.

---

**Passo 3 — Crea un primo clone manuale**

Aggiungi questo terzo script:

```text
quando si clicca su 🚩
vai a x: (260) y: (-40)
crea clone di [me stesso]
```

Adesso, cliccando la bandiera verde:

1. l'originale si nasconde
2. si sposta nella corsia scelta
3. crea un clone
4. il clone parte e attraversa la strada

Hai quindi ottenuto la stessa auto dell'unità precedente, ma ora è un clone.

---

## 4.4 — Creare tre corsie di automobili con un solo sprite

### 📖 Introduzione teorica

Ora facciamo il vero salto di qualità: usare lo stesso sprite per generare automobili in **più corsie**.

Per restare semplici, in questa unità tutte le auto avranno:

- stessa direzione
- stessa velocità
- stesso aspetto

Più avanti potrai differenziarle.

### 🛠️ Passaggi guidati

**Passo 1 — Crea tre script generatori**

Mantieni lo script `quando vengo clonato` già creato.

Poi aggiungi tre script separati, uno per ogni corsia.

**Corsia 1**

```text
quando si clicca su 🚩
per sempre
  vai a x: (260) y: (-40)
  crea clone di [me stesso]
  attendi (2) secondi
```

**Corsia 2**

```text
quando si clicca su 🚩
attendi (0.7) secondi
per sempre
  vai a x: (260) y: (0)
  crea clone di [me stesso]
  attendi (2) secondi
```

**Corsia 3**

```text
quando si clicca su 🚩
attendi (1.4) secondi
per sempre
  vai a x: (260) y: (40)
  crea clone di [me stesso]
  attendi (2) secondi
```

### Perché usare attese diverse?

Se tutte le corsie creassero il clone nello stesso istante, le auto apparirebbero perfettamente allineate e il traffico sembrerebbe artificiale.

Con piccole attese iniziali diverse:

- il traffico appare più naturale
- le corsie non sono sincronizzate
- il gioco diventa più interessante

---

**Passo 2 — Adatta le coordinate alle tue corsie**

I valori `-40`, `0` e `40` sono solo esempi.

Controlla il tuo sfondo e scegli tre valori `y` che corrispondano davvero alle corsie grigie della strada.

Per esempio potresti usare:

- `y = -100`
- `y = -60`
- `y = -20`

L'importante è che ogni corsia sia ben visibile e separata dalle altre.

---

**Passo 3 — Regola la distanza tra le auto**

La riga:

```text
attendi (2) secondi
```

decide ogni quanto compare una nuova auto in quella corsia.

Prova tre possibilità:

| Attesa | Effetto |
|--------|---------|
| `3` secondi | Poche auto, traffico facile |
| `2` secondi | Traffico medio |
| `1` secondo | Traffico intenso |

> In questa unità mantieni la stessa attesa in tutte le corsie: così il sistema resta semplice e facile da capire.

---

**Passo 4 — Controlla il risultato**

Premi la bandiera verde e osserva:

- compaiono auto in tre corsie diverse
- tutte si muovono nella stessa direzione
- le auto spariscono quando escono a sinistra
- nuove auto continuano a nascere a intervalli regolari

Hai costruito il primo sistema di traffico multi-corsia di Frogger.

---

## 🎯 Mini Esercizio dell'Unità

> **Obiettivo:** Tre corsie di automobili generate da cloni di un solo sprite.

**Cosa deve funzionare alla fine:**

1. Lo sprite originale **Auto** è nascosto
2. Le automobili visibili sono cloni
3. Le auto nascono in almeno tre corsie diverse
4. Tutte si muovono con la stessa velocità
5. I cloni vengono eliminati quando escono dallo schermo

**Verifica il tuo lavoro:**

- [ ] Esiste un blocco `quando vengo clonato`
- [ ] Lo script del clone contiene `elimina questo clone`
- [ ] Esistono almeno 3 script generatori con `crea clone di [me stesso]`
- [ ] Il traffico continua senza dover premere altri tasti

---

## 💡 Domande di Riflessione

---

**Domanda 1**
Perché i cloni sono utili in un gioco come Frogger?

a) Perché rendono i file `.sb3` più colorati  
b) Perché permettono di creare molte copie di uno sprite senza duplicare tutto il codice  
c) Perché sostituiscono gli sfondi  
d) Perché funzionano solo con le automobili

> *Risposta corretta: **b)** — I cloni servono a riutilizzare uno stesso sprite e uno stesso insieme di script per creare molte istanze.*

---

**Domanda 2**
Cosa succede se dimentichi di usare `elimina questo clone`?

a) Nulla, Scratch elimina sempre i cloni al posto tuo durante il gioco  
b) Le auto cambiano colore automaticamente  
c) I cloni possono accumularsi e il progetto diventa più difficile da gestire  
d) La rana smette di muoversi

> *Risposta corretta: **c)** — Anche se i cloni spariscono quando si ferma il progetto, durante il gioco è importante rimuoverli quando non servono più.*

---

**Domanda 3**
Quale script viene eseguito dal clone appena creato?

a) `quando si clicca su 🚩`  
b) `quando vengo clonato`  
c) `quando questo sprite viene cliccato`  
d) `ripeti (10)`

> *Risposta corretta: **b)** — Ogni clone inizia eseguendo il codice collegato a `quando vengo clonato`.*

---

**Domanda 4** *(riflessione aperta)*
Se volessi rendere una corsia più difficile senza usare ancora variabili locali, quale parametro potresti cambiare: la velocità delle auto o il tempo tra un clone e il successivo? Quale scelta ti sembra più chiara da gestire?

---

**Domanda 5** *(sfida)*
Prova ad aggiungere una quarta corsia. Quale nuovo script generatore dovresti scrivere? Quale valore `y` sceglieresti?

---

## 🔧 Tip & Tricks

> **Tip 1 — Nascondi sempre il generatore**
> Se dimentichi `nascondi`, vedrai anche lo sprite originale sullo schermo oltre ai cloni. In questo caso il traffico sembrerà "sbagliato".

> **Tip 2 — Sfalsa la partenza delle corsie**
> Piccole attese iniziali diverse rendono il traffico molto più naturale.

> **Tip 3 — Tieni ordinati gli script**
> Metti in alto lo script `quando si clicca su 🚩` che nasconde l'originale, al centro lo script `quando vengo clonato`, e di lato i tre script generatori. Così capirai subito cosa fa ogni blocco.

> **Tip 4 — Una modifica, tante auto**
> Se cambi il costume o la dimensione dello sprite **Auto**, tutte le future copie useranno subito quell'aspetto. È uno dei grandi vantaggi dei cloni.

---

## 📋 Riepilogo dell'Unità

| Concetto | Cosa abbiamo imparato |
|----------|-----------------------|
| Clone | Copia temporanea di uno sprite creata durante il gioco |
| Sprite originale | Fa da generatore e spesso resta nascosto |
| `quando vengo clonato` | Avvia il comportamento del clone |
| `elimina questo clone` | Rimuove i cloni quando non servono più |
| Generatori multipli | Permettono di creare corsie diverse con lo stesso sprite |
| Intervallo di creazione | Controlla la distanza temporale tra le auto |

**Verifica rapida:**
- [ ] Sai spiegare la differenza tra sprite originale e clone
- [ ] Hai nascosto lo sprite Auto originale
- [ ] Hai creato almeno tre corsie con cloni
- [ ] I cloni vengono eliminati quando escono dallo schermo

---

## ➡️ Prossimo passo

Nella **Unità 5** faremo in modo che la rana riconosca il pericolo: se tocca un'automobile, perderà una vita e tornerà alla posizione di partenza.

---

*Mini Corso: Programmiamo con Scratch — Costruiamo Frogger! | Unità 4 di 11*
