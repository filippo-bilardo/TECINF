# 03 — Cicli e Animazione

> **Concetto chiave:** ripetizione automatica e movimento continuo degli ostacoli
> **Durata stimata:** 45–60 minuti
> **Prerequisiti:** Unità 2 completata — la rana si muove con le frecce e resta dentro il campo di gioco

---

## Obiettivi dell'unità

Al termine di questa unità lo studente sarà in grado di:

- Spiegare la differenza tra un ciclo `per sempre` e un ciclo `ripeti`
- Usare i cicli per animare uno sprite in modo automatico
- Creare una prima automobile che attraversa la strada in loop
- Regolare la velocità di un ostacolo modificando passi e attese

---

## 3.1 — Cos'è un ciclo?

### 📖 Introduzione teorica

Un **ciclo** è una struttura che permette al computer di ripetere automaticamente una o più istruzioni.

In Scratch i due blocchi più importanti per i cicli sono:

| Blocco | Cosa fa |
|--------|---------|
| `per sempre` | Ripete le istruzioni senza fermarsi mai, finché il progetto è attivo |
| `ripeti (N)` | Ripete le istruzioni un numero preciso di volte |

### Un esempio semplice

Se vuoi che un'auto continui a muoversi finché il gioco è acceso, userai:

```text
quando si clicca su 🚩
└── per sempre
      cambia x di (-5)
```

Se invece vuoi fare un'animazione breve della rana, ad esempio un piccolo salto visivo, puoi usare:

```text
quando si preme il tasto [freccia su]
└── ripeti (2)
      prossimo costume
```

> 💡 **Idea chiave:** `per sempre` serve per il comportamento continuo del gioco. `ripeti` serve per azioni brevi, contate e controllate.

---

## 3.2 — Animare la rana durante il movimento

### 📖 Introduzione teorica

Nelle unità precedenti la rana si spostava, ma il suo aspetto restava quasi sempre uguale. Possiamo renderla più viva cambiando il costume quando si muove.

L'idea è semplice:

1. premi una freccia
2. la rana cambia costume
3. si muove
4. torna al costume normale

Non è ancora una vera animazione complessa, ma basta per dare l'idea del salto.

### 🛠️ Passaggi guidati

**Passo 1 — Controlla i costumi della rana**

Vai nello sprite **Rana** e apri la scheda **Costumi**.

Hai due possibilità:

- Se hai già costumi diversi per le direzioni, usali
- Se hai un solo costume, duplicalo e rinominalo ad esempio:
  - `ferma`
  - `salto`

Anche una differenza minima va bene: zampe più aperte, corpo leggermente inclinato, oppure la rana un po' più schiacciata.

---

**Passo 2 — Modifica uno script di movimento**

Prendiamo come esempio la freccia su. Lo script può diventare così:

```text
quando si preme il tasto [freccia su]
se <(y) < (140)> allora
  passa al costume [salto]
  cambia y di (40)
  attendi (0.1) secondi
  passa al costume [ferma]
```

Questa piccola attesa permette all'occhio di notare il cambio di costume.

---

**Passo 3 — Adatta gli altri tre script**

Ripeti la stessa idea anche per:

- freccia giù
- freccia destra
- freccia sinistra

Se hai costumi direzionali, puoi usare nomi come:

- `su`
- `giu`
- `destra`
- `sinistra`

In quel caso, dopo il movimento puoi tornare al costume della direzione corretta invece di usare sempre `ferma`.

---

**Passo 4 — Prova l'effetto**

Premi le frecce più volte e osserva la rana.

Se l'animazione è troppo veloce:
- aumenta l'attesa da `0.1` a `0.2`

Se è troppo lenta:
- riduci l'attesa

> Non serve esagerare: in Frogger il movimento deve restare rapido e preciso.

---

## 3.3 — Creare la prima automobile che attraversa lo schermo

### 📖 Introduzione teorica

Ora costruiamo il primo vero ostacolo del gioco: un'**automobile** che si muove in modo continuo lungo una corsia della strada.

Per questo useremo un ciclo `per sempre`, perché l'auto deve:

1. partire da un lato dello schermo
2. attraversarlo
3. riapparire dal lato opposto
4. ricominciare all'infinito

### 🛠️ Passaggi guidati

**Passo 1 — Aggiungi uno sprite automobile**

1. Clicca su **Scegli uno sprite**
2. Cerca `car`, `auto` oppure un veicolo simile
3. Aggiungilo al progetto
4. Rinomina lo sprite in **Auto**

Se serve, ridimensionala per adattarla alla corsia della strada.

---

**Passo 2 — Posiziona l'auto in una corsia**

Trascina l'auto su una delle fasce grigie della strada.

Per esempio puoi usare una posizione iniziale come:

- x = 220
- y = -40

Non è obbligatorio usare questi valori precisi: scegli quelli che si adattano meglio al tuo sfondo.

---

**Passo 3 — Crea lo script di movimento**

Nello sprite **Auto**, costruisci questo script:

```text
quando si clicca su 🚩
vai a x: (220) y: (-40)
per sempre
  cambia x di (-5)
  se <(x posizione) < (-260)> allora
    vai a x: (260) y: (-40)
```

### Come funziona

- `cambia x di (-5)` sposta l'auto verso sinistra
- quando l'auto supera il bordo sinistro, viene riportata a destra
- il ciclo ricomincia subito

Il risultato è un movimento continuo.

---

**Passo 4 — Rendi il movimento più fluido**

Se l'auto sembra troppo veloce, prova una di queste modifiche:

```text
cambia x di (-3)
```

oppure:

```text
cambia x di (-5)
attendi (0.02) secondi
```

Le due scelte producono effetti diversi:

| Strategia | Effetto |
|-----------|---------|
| Passi più piccoli | Movimento più preciso |
| Piccola attesa | Movimento più lento e leggibile |

---

## 3.4 — Controllare la velocità degli ostacoli

### 📖 Introduzione teorica

La **velocità** di uno sprite in Scratch dipende soprattutto da due fattori:

1. **quanto si sposta a ogni ciclo**
2. **quanto tempo aspetta tra uno spostamento e il successivo**

Più aumenta il primo valore, più l'oggetto corre.
Più aumenta il secondo valore, più l'oggetto rallenta.

### Esempi a confronto

| Script | Risultato |
|--------|-----------|
| `cambia x di (-8)` | Auto molto veloce |
| `cambia x di (-3)` | Auto più lenta |
| `cambia x di (-5)` + `attendi (0.05)` | Auto regolare e leggibile |

### 🛠️ Esperimento guidato

Prova tre versioni della stessa auto:

1. **Lenta** → `cambia x di (-2)`
2. **Media** → `cambia x di (-4)`
3. **Veloce** → `cambia x di (-7)`

Osserva come cambia la difficoltà del gioco.

> 💡 In un buon videogioco non basta che qualcosa "si muova": deve muoversi alla velocità giusta per essere divertente.

---

## 🎯 Mini Esercizio dell'Unità

> **Obiettivo:** Un'automobile attraversa una corsia della strada in loop continuo.

**Cosa deve funzionare alla fine:**

1. La rana continua a muoversi correttamente con le frecce
2. Lo sprite **Auto** parte da un lato della strada
3. L'auto attraversa lo schermo automaticamente
4. Quando esce da un lato, riappare dall'altro
5. La velocità è leggibile e adatta al gioco

**Verifica il tuo lavoro:**

- [ ] Esiste uno sprite chiamato `Auto`
- [ ] L'auto ha almeno uno script con `quando si clicca su 🚩`
- [ ] Lo script contiene un ciclo `per sempre`
- [ ] La rana si anima o cambia costume durante il movimento

---

## 💡 Domande di Riflessione

---

**Domanda 1**
Qual è la differenza principale tra `per sempre` e `ripeti (10)`?

a) Nessuna, fanno esattamente la stessa cosa  
b) `per sempre` si ferma dopo 10 volte, `ripeti` no  
c) `per sempre` continua finché il progetto è attivo, `ripeti` si ferma dopo il numero indicato  
d) `ripeti` può essere usato solo con gli sprite, `per sempre` solo con lo stage

> *Risposta corretta: **c)** — `per sempre` non ha una fine naturale, mentre `ripeti` esegue il blocco un numero preciso di volte.*

---

**Domanda 2**
Se vuoi rallentare un'automobile, quale modifica è corretta?

a) Aumentare `cambia x di (-5)` a `cambia x di (-10)`  
b) Diminuire il numero di passi oppure aggiungere una piccola attesa  
c) Eliminare il ciclo `per sempre`  
d) Spostare l'auto più in alto nello schermo

> *Risposta corretta: **b)** — Per rallentare uno sprite puoi ridurre lo spostamento a ogni ciclo o introdurre una breve pausa.*

---

**Domanda 3**
Perché l'auto deve riapparire dall'altro lato dello schermo?

a) Perché Scratch non permette agli sprite di fermarsi  
b) Per creare un ostacolo continuo tipico di Frogger  
c) Per far sparire l'auto e alleggerire il progetto  
d) Per cambiare automaticamente costume

> *Risposta corretta: **b)** — In Frogger il traffico deve essere continuo: l'auto esce da un lato e rientra dall'altro.*

---

**Domanda 4** *(riflessione aperta)*
Se volessi creare una corsia molto difficile, sarebbe meglio aumentare i passi dell'auto o diminuire il tempo tra una macchina e l'altra? Spiega perché.

---

**Domanda 5** *(sfida)*
Prova a creare una seconda auto che vada da sinistra verso destra. Quali valori di `cambia x di` e di posizione iniziale dovresti modificare?

---

## 🔧 Tip & Tricks

> **Tip 1 — Parti da una sola corsia**
> Non cercare di costruire subito tutto il traffico. Prima fai funzionare bene una sola auto, poi moltiplicherai il sistema nell'unità successiva.

> **Tip 2 — Usa coordinate leggibili**
> Scegli valori rotondi come `-40`, `0`, `40`, `220`, `-220`. Rendono più facile capire in quale corsia si trova uno sprite.

> **Tip 3 — Non esagerare con l'attesa**
> Se l'attesa è troppo alta, l'auto si muoverà "a scatti". Meglio attese molto piccole come `0.02` o `0.05`.

> **Tip 4 — Nascondi i problemi con il reset**
> Quando un'auto ricompare, fai attenzione che rientri appena fuori dal bordo, non già a metà schermo. Così il movimento sembrerà più naturale.

---

## 📋 Riepilogo dell'Unità

| Concetto | Cosa abbiamo imparato |
|----------|-----------------------|
| Ciclo | Una struttura che ripete automaticamente istruzioni |
| `per sempre` | Serve per i comportamenti continui del gioco |
| `ripeti` | Serve per animazioni o azioni da eseguire un numero definito di volte |
| Animazione | Cambio di costume per dare vita al personaggio |
| Velocità | Dipende da passi e attese dentro il ciclo |
| Reset laterale | Un ostacolo che esce da un bordo può rientrare dall'altro |

**Verifica rapida:**
- [ ] Sai spiegare la differenza tra `per sempre` e `ripeti`
- [ ] Hai animato la rana durante almeno un movimento
- [ ] Hai creato una prima auto che attraversa la strada in loop
- [ ] Hai provato a cambiare la velocità dell'ostacolo

---

## ➡️ Prossimo passo

Nella **Unità 4** useremo i **cloni** per evitare di creare tante auto a mano. Con un solo sprite costruiremo più automobili e più corsie di traffico.

---

*Mini Corso: Programmiamo con Scratch — Costruiamo Frogger! | Unità 3 di 11*
