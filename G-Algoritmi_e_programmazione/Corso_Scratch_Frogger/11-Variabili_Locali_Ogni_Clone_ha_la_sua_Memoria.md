# 11 — Variabili Locali: Ogni Clone ha la sua Memoria

> **Concetto chiave:** scope delle variabili (globale vs. locale)
> **Durata stimata:** 45–60 minuti
> **Prerequisiti:** Unità 10 completata — il gioco base è funzionante e rifinito con suoni, schermate e feedback

---

## Obiettivi dell'unità

Al termine di questa unità lo studente sarà in grado di:

- Distinguere tra variabili **globali** e variabili **locali**
- Capire perché i cloni non possono condividere sempre gli stessi valori
- Creare variabili locali come `velocità`, `corsia` e `direzione`
- Assegnare valori diversi ai cloni quando nascono
- Costruire traffico e tronchi con movimenti indipendenti

---

## 11.1 — Il limite delle variabili globali

### 📖 Introduzione teorica

Finora molte automobili e tronchi potevano usare lo stesso codice e la stessa velocità. Ma appena vuoi creare corsie diverse, nasce un problema.

Immagina di avere una sola variabile globale:

```text
velocità
```

Se la cambi in uno script, cambia per tutti. Quindi:

- tutte le auto diventano più veloci insieme
- tutti i tronchi si muovono allo stesso modo
- non puoi avere cloni davvero indipendenti

Per risolvere questo problema servono le **variabili locali**, cioè variabili create **per questo sprite solo**.

> 💡 **Idea chiave:** una variabile globale descrive lo stato del gioco intero; una variabile locale descrive lo stato di uno specifico sprite o clone.

### Esempio

| Tipo di variabile | Esempio | Uso |
|-------------------|---------|-----|
| Globale | `vite`, `punteggio` | Vale per tutto il gioco |
| Locale | `velocità`, `direzione` | Vale per quel clone specifico |

---

## 11.2 — Creare variabili locali: `velocità`, `corsia`, `direzione`

### 🛠️ Passaggi guidati

**Passo 1 — Crea le variabili locali nello sprite Auto**

Seleziona lo sprite **Auto** e crea queste variabili scegliendo **per questo sprite solo**:

- `velocità`
- `corsia`
- `direzione`

Queste variabili saranno presenti anche nei cloni dell'Auto, ma ogni clone avrà i propri valori.

---

**Passo 2 — Cosa rappresentano**

Puoi usare questi significati:

- `velocità` → quanti passi fa il clone a ogni ciclo
- `corsia` → in quale riga del traffico si trova
- `direzione` → `1` per destra, `-1` per sinistra

> Usare numeri è spesso più pratico di usare parole come `destra` o `sinistra`.

---

**Passo 3 — Ripeti l'idea nello sprite Tronco**

Anche nello sprite **Tronco** puoi creare variabili locali simili:

- `velocità`
- `corsia`
- `direzione`

Così auto e tronchi potranno avere comportamenti diversi senza interferire tra loro.

---

## 11.3 — Assegnare valori diversi a ogni clone

### 📖 Introduzione teorica

Quando un clone nasce, copia lo stato corrente dello sprite originale, comprese le sue variabili locali. Questo significa che puoi:

1. impostare i valori nello sprite originale
2. creare il clone
3. lasciare che il clone usi quei valori come propria memoria iniziale

### 🛠️ Passaggi guidati

**Passo 1 — Generatore con valori diversi**

Nello sprite **Auto**, uno script generatore può diventare così:

```text
quando si clicca su 🚩
per sempre
  porta [corsia v] a (-60)
  porta [velocità v] a (4)
  porta [direzione v] a (-1)
  vai a x: (260) y: (corsia)
  crea clone di [me stesso v]
  attendi (2) secondi
```

Un secondo generatore può usare:

```text
quando si clicca su 🚩
attendi (0.8) secondi
per sempre
  porta [corsia v] a (-20)
  porta [velocità v] a (6)
  porta [direzione v] a (1)
  vai a x: (-260) y: (corsia)
  crea clone di [me stesso v]
  attendi (1.6) secondi
```

In questo modo i cloni nascono già con velocità e direzione diverse.

---

**Passo 2 — Leggi le variabili nel clone**

Lo script del clone può diventare:

```text
quando vengo clonato
mostra
per sempre
  cambia x di ((velocità) * (direzione))
  se <<(direzione) = (1)> e <(x posizione) > (260)>> allora
    elimina questo clone
  se <<(direzione) = (-1)> e <(x posizione) < (-260)>> allora
    elimina questo clone
```

Ora ogni clone si comporta in base ai suoi valori locali.

---

**Passo 3 — Applica la stessa logica ai tronchi**

Puoi fare lo stesso per lo sprite **Tronco**:

- una corsia lenta verso destra
- una corsia veloce verso sinistra
- una corsia intermedia

Questo renderà il fiume molto più simile a quello del gioco originale.

---

## 11.4 — Corsi e direzioni indipendenti

### 📖 Introduzione teorica

Le variabili locali permettono di creare un mondo più ricco:

- auto lente e auto veloci
- corsie verso destra e verso sinistra
- tronchi lunghi e tronchi rapidi

Inoltre preparano il terreno per le unità successive, dove useremo anche **stati** e **nemici più complessi**.

### 🛠️ Esperimento guidato

Prova a costruire tre corsie di auto con questi valori:

| Corsia | Velocità | Direzione | Effetto |
|--------|----------|------------|---------|
| 1 | `3` | `1` | lenta verso destra |
| 2 | `5` | `-1` | media verso sinistra |
| 3 | `7` | `1` | veloce verso destra |

Poi crea due corsie di tronchi con valori diversi.

Osserva come il gioco diventa più vario senza dover creare sprite completamente nuovi.

---

## 🎯 Mini Esercizio dell'Unità

> **Obiettivo:** Tre corsie di automobili e due di tronchi con cloni che si muovono a velocità e direzioni indipendenti.

**Cosa deve funzionare alla fine:**

1. Gli sprite **Auto** e **Tronco** hanno variabili locali
2. Cloni diversi possono nascere con valori diversi
3. Almeno due corsie hanno velocità differenti
4. Almeno una corsia si muove in direzione opposta alle altre
5. Il comportamento resta corretto anche con molti cloni in gioco

**Verifica il tuo lavoro:**

- [ ] Hai creato `velocità`, `corsia` o `direzione` come variabili locali
- [ ] I cloni leggono questi valori nel loro script
- [ ] Non tutte le auto si muovono allo stesso modo
- [ ] Non tutti i tronchi si muovono allo stesso modo

---

## 💡 Domande di Riflessione

---

**Domanda 1**
Qual è il vantaggio principale di una variabile locale?

a) Fa apparire nuovi costumi  
b) Permette a ogni clone di avere i propri valori indipendenti  
c) Sostituisce gli sfondi  
d) Elimina i messaggi

> *Risposta corretta: **b)** — Una variabile locale evita che tutti i cloni condividano per forza lo stesso valore.*

---

**Domanda 2**
Quale di queste variabili ha più senso tenere globale?

a) `vite`  
b) `direzione` di una singola auto  
c) `velocità` di un singolo tronco  
d) `corsia` di un clone

> *Risposta corretta: **a)** — `vite` appartiene allo stato generale del gioco.*

---

**Domanda 3**
Quando il clone riceve i valori iniziali delle sue variabili locali?

a) Quando si ferma il gioco  
b) Quando viene creato  
c) Quando si cambia lo sfondo  
d) Quando si clicca sul clone con il mouse

> *Risposta corretta: **b)** — Il clone copia lo stato locale dello sprite al momento della nascita.*

---

**Domanda 4** *(riflessione aperta)*
Nel tuo Frogger preferisci corsie molto diverse tra loro o un traffico più regolare? In che modo cambia la difficoltà?

---

**Domanda 5** *(sfida)*
Prova a usare una sola variabile locale `velocità`, con valori positivi e negativi, invece di separare `velocità` e `direzione`. Quali vantaggi e svantaggi noti?

---

## 🔧 Tip & Tricks

> **Tip 1 — Parti da un solo sprite**
> Prima fai funzionare bene le variabili locali nello sprite Auto, poi copia l'idea sui Tronchi.

> **Tip 2 — Tieni visibili i valori solo durante il test**
> Vedere `velocità` o `direzione` sullo schermo può aiutarti a capire se ogni clone sta ricevendo i valori giusti.

> **Tip 3 — Mantieni chiari i segni**
> Se usi `1` e `-1` per la direzione, ricorda bene quale valore corrisponde a destra e quale a sinistra.

> **Tip 4 — Le variabili globali non spariscono**
> Vite, punteggio e timer restano globali. Non tutto deve diventare locale.

---

## 📋 Riepilogo dell'Unità

| Concetto | Cosa abbiamo imparato |
|----------|-----------------------|
| Variabile globale | Vale per tutto il gioco |
| Variabile locale | Vale per uno sprite e i suoi cloni |
| `velocità`, `corsia`, `direzione` | Permettono comportamenti indipendenti |
| Clone con memoria | Ogni clone può muoversi secondo i propri valori |
| Scope | Indica dove una variabile è valida e utile |

**Verifica rapida:**
- [ ] Sai distinguere globale e locale
- [ ] Hai creato almeno una variabile locale
- [ ] I cloni hanno velocità o direzioni diverse
- [ ] Il traffico e il fiume sono più variati

---

## ➡️ Prossimo passo

Nella **Unità 12** costruiremo nemici a stati: tartarughe che affondano e un coccodrillo che cambia comportamento nel fiume.

---

*Mini Corso: Programmiamo con Scratch — Costruiamo Frogger! | Unità 11 di 19*
