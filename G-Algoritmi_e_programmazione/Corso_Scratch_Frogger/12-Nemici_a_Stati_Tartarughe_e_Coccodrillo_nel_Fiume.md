# 12 — Nemici a Stati: Tartarughe e Coccodrillo nel Fiume

> **Concetto chiave:** macchina a stati finita
> **Durata stimata:** 45–60 minuti
> **Prerequisiti:** Unità 11 completata — i cloni possono avere velocità e direzioni indipendenti

---

## Obiettivi dell'unità

Al termine di questa unità lo studente sarà in grado di:

- Capire che uno sprite può cambiare comportamento nel tempo
- Usare una variabile `stato` per descrivere il comportamento di un nemico
- Creare tartarughe che alternano emersa, immersione e sott'acqua
- Gestire il caso in cui la rana cada se una piattaforma scompare
- Aggiungere un coccodrillo con comportamento pericoloso nel fiume

---

## 12.1 — Oltre allo scorrimento: nemici che reagiscono

### 📖 Introduzione teorica

Finora auto, tronchi e altri ostacoli si muovevano sempre nello stesso modo. Ma molti nemici nei videogiochi cambiano comportamento nel tempo.

Per descrivere questo comportamento usiamo una **macchina a stati**:

- lo sprite si trova in uno stato
- ogni stato ha un comportamento preciso
- dopo un evento o un certo tempo, lo sprite passa a un altro stato

### Esempio semplice

Una tartaruga può essere:

1. `emersa`
2. `immersione`
3. `sottacqua`

Quando è emersa, la rana può usarla come piattaforma. Quando è sott'acqua, non è più sicura.

> 💡 **Idea chiave:** invece di chiederti "cosa fa questo sprite?", chiediti "in che stato si trova adesso?".

---

## 12.2 — La variabile `stato`

### 🛠️ Passaggi guidati

**Passo 1 — Crea lo sprite Tartaruga**

1. Aggiungi uno sprite tartaruga
2. Rinominalo **Tartaruga**
3. Se serve, crea più costumi:
   - `emersa`
   - `immersione`
   - `sottacqua`

Se non hai costumi perfetti, puoi simularli così:

- `emersa` → costume normale
- `immersione` → effetto fantasma leggero
- `sottacqua` → quasi invisibile o costume molto piccolo

---

**Passo 2 — Crea la variabile locale**

Nello sprite **Tartaruga** crea una variabile **per questo sprite solo**:

- `stato`

Così ogni clone di tartaruga potrà avere il proprio stato.

---

**Passo 3 — Imposta uno script di movimento**

Puoi riutilizzare la logica dei tronchi:

```text
quando vengo clonato
mostra
porta [stato v] a [emersa]
per sempre
  cambia x di (3)
```

Poi aggiungeremo la parte che cambia lo stato nel tempo.

---

## 12.3 — Le tartarughe che affondano

### 📖 Introduzione teorica

Le tartarughe sono interessanti perché sono piattaforme **non affidabili**. A volte aiutano la rana, a volte la fanno cadere.

La sequenza più semplice è:

1. emersa per 2 secondi
2. immersione per 1 secondo
3. sott'acqua per 1 secondo
4. ritorno a emersa

### 🛠️ Passaggi guidati

**Passo 1 — Crea il ciclo degli stati**

Nello sprite **Tartaruga**, nello script del clone, aggiungi in parallelo un controllo tipo:

```text
quando vengo clonato
mostra
porta [stato v] a [emersa]
per sempre
  passa al costume [emersa v]
  porta [stato v] a [emersa]
  attendi (2) secondi
  passa al costume [immersione v]
  porta [stato v] a [immersione]
  attendi (1) secondi
  passa al costume [sottacqua v]
  porta [stato v] a [sottacqua]
  attendi (1) secondi
```

Questo fa alternare automaticamente i tre stati.

---

**Passo 2 — Gestisci la sicurezza della piattaforma**

Nella **Rana**, dove già controlli tronchi o supporti del fiume, aggiungi una logica del tipo:

```text
se <sta toccando [Tartaruga v] ?> allora
  cambia x di (3)
```

ma solo quando la tartaruga non è sott'acqua.

In Scratch non è facile leggere direttamente la variabile locale di un altro clone. Per un corso base hai due strade:

1. usare il **costume visibile** della tartaruga come indicatore
2. considerare sicura la tartaruga solo quando è visibile

Quindi puoi ragionare così:

- se la rana tocca una tartaruga visibile, viene trasportata
- se la tartaruga sparisce o diventa sott'acqua, la rana cade

---

**Passo 3 — Crea la caduta**

Se la rana è nel fiume e non tocca:

- un tronco
- una tartaruga emersa

allora deve perdere una vita.

La tua logica del fiume può diventare mentalmente così:

```text
se la rana tocca un supporto sicuro
  allora sopravvive
altrimenti se tocca l'acqua
  allora cade
```

> Questa unità ti obbliga a pensare in termini di "supporti sicuri", non solo di singoli sprite.

---

## 12.4 — Il coccodrillo nel fiume

### 📖 Introduzione teorica

Il coccodrillo è un nemico più ambiguo:

- a volte si vede e fa paura
- a volte scompare
- in alcune versioni può sembrare una piattaforma, ma in realtà è pericoloso

Anche qui il concetto utile è lo **stato**.

### Stati suggeriti

| Stato | Significato |
|-------|-------------|
| `visibile` | Se la rana lo tocca, perde una vita |
| `sottacqua` | Non è pericoloso visivamente, oppure non è attivo |

### 🛠️ Passaggi guidati

**Passo 1 — Crea lo sprite Coccodrillo**

1. Aggiungi uno sprite coccodrillo
2. Crea due costumi:
   - `visibile`
   - `sottacqua`

Puoi usare un effetto fantasma per la fase sott'acqua.

---

**Passo 2 — Crea la variabile locale**

Nello sprite **Coccodrillo**, crea:

- `stato` per questo sprite solo

---

**Passo 3 — Alterna gli stati**

Uno script semplice può essere:

```text
quando si clicca su 🚩
per sempre
  passa al costume [visibile v]
  porta [stato v] a [visibile]
  attendi (3) secondi
  passa al costume [sottacqua v]
  porta [stato v] a [sottacqua]
  attendi (2) secondi
```

---

**Passo 4 — Gestisci il pericolo**

Nella Rana puoi usare la regola semplice:

- se tocca il coccodrillo **visibile**, perde una vita

In pratica:

```text
se <sta toccando [Coccodrillo v] ?> allora
  cambia [vite v] di (-1)
  vai a x: (0) y: (-150)
```

Se il costume sott'acqua è davvero invisibile o non toccabile, questa soluzione è già sufficiente per una prima versione.

---

## 🎯 Mini Esercizio dell'Unità

> **Obiettivo:** Una tartaruga alterna emersa e sott'acqua ogni pochi secondi; la rana cade se resta sopra nel momento sbagliato.

**Cosa deve funzionare alla fine:**

1. Esiste uno sprite **Tartaruga** con stati diversi
2. La tartaruga cambia aspetto nel tempo
3. Quando è emersa, può funzionare come supporto
4. Quando è sott'acqua, la rana non è più al sicuro
5. (Opzionale) Esiste un coccodrillo visibile/sottacqua

**Verifica il tuo lavoro:**

- [ ] Hai creato la variabile locale `stato`
- [ ] La tartaruga alterna almeno 2 stati
- [ ] La rana può usarla come supporto solo in certe fasi
- [ ] Hai aggiunto almeno una logica di pericolo al coccodrillo oppure l'hai progettata

---

## 💡 Domande di Riflessione

---

**Domanda 1**
Che cosa descrive una macchina a stati?

a) La quantità di suoni nel progetto  
b) I possibili comportamenti di uno sprite in momenti diversi  
c) Il numero di sprite sullo schermo  
d) Il colore dello sfondo

> *Risposta corretta: **b)** — Una macchina a stati descrive i diversi modi in cui uno sprite può comportarsi nel tempo.*

---

**Domanda 2**
Perché una tartaruga che affonda è più interessante di un tronco normale?

a) Perché usa meno blocchi  
b) Perché cambia comportamento e obbliga il giocatore a osservare il momento giusto  
c) Perché è sempre invisibile  
d) Perché elimina il timer

> *Risposta corretta: **b)** — Introduce un rischio dinamico, non solo un movimento costante.*

---

**Domanda 3**
Quale variabile locale è più adatta per descrivere i diversi momenti della tartaruga?

a) `vite`  
b) `stato`  
c) `punteggio`  
d) `tempo rimasto`

> *Risposta corretta: **b)** — `stato` è la variabile che descrive il comportamento corrente.*

---

**Domanda 4** *(riflessione aperta)*
Preferisci che le tartarughe restino sott'acqua per poco tempo o per molto? Come cambia la difficoltà del fiume?

---

**Domanda 5** *(sfida)*
Prova a creare due gruppi di tartarughe che si immergono con tempi diversi. Come cambieresti il ciclo degli stati?

---

## 🔧 Tip & Tricks

> **Tip 1 — Parti da due stati**
> Se tre stati sono troppi per iniziare, usa solo `emersa` e `sottacqua`. Poi aggiungi `immersione`.

> **Tip 2 — Il costume può fare da stato visivo**
> Anche quando non leggi direttamente una variabile, il costume dello sprite può comunicare molto bene il suo comportamento.

> **Tip 3 — Non complicare subito il coccodrillo**
> Prima fai funzionare bene le tartarughe. Il coccodrillo può partire come estensione semplice.

> **Tip 4 — Pensa in termini di supporto sicuro**
> Nel fiume la domanda non è solo "cosa sto toccando?", ma soprattutto "questo supporto è sicuro adesso?".

---

## 📋 Riepilogo dell'Unità

| Concetto | Cosa abbiamo imparato |
|----------|-----------------------|
| Stato | Descrive il comportamento corrente di uno sprite |
| Macchina a stati | Sequenza di comportamenti possibili |
| Tartaruga che affonda | Piattaforma che non è sempre sicura |
| Coccodrillo | Nemico con comportamento variabile |
| Supporto sicuro | Oggetto che in un dato momento salva la rana |

**Verifica rapida:**
- [ ] Hai introdotto almeno uno sprite con stati
- [ ] La tartaruga cambia comportamento nel tempo
- [ ] La rana può cadere se il supporto scompare
- [ ] Hai progettato o aggiunto il coccodrillo

---

## ➡️ Prossimo passo

Nella **Unità 13** arricchiremo il gioco con serpenti, mosche bonus, coccodrilli nei nidi e il caso avanzato della caduta oltre il bordo del fiume.

---

*Mini Corso: Programmiamo con Scratch — Costruiamo Frogger! | Unità 12 di 19*
