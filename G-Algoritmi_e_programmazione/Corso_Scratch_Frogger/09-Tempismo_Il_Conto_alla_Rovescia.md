# 09 — Tempismo: Il Conto alla Rovescia

> **Concetto chiave:** timer e variabili di tempo
> **Durata stimata:** 45–60 minuti
> **Prerequisiti:** Unità 8 completata — il gioco ha vite, punteggio e Game Over

---

## Obiettivi dell'unità

Al termine di questa unità lo studente sarà in grado di:

- Spiegare perché un timer rende il gioco più intenso
- Usare una variabile `tempo rimasto` come conto alla rovescia
- Far ripartire il timer quando la rana torna al via
- Ridurre le vite quando il tempo finisce
- Bilanciare la difficoltà modificando la durata del conto alla rovescia

---

## 9.1 — Perché aggiungere un timer?

### 📖 Introduzione teorica

Senza limite di tempo, il giocatore può aspettare quanto vuole prima di attraversare la strada o il fiume.

Con un **conto alla rovescia**, invece:

- il gioco diventa più teso
- il giocatore deve decidere in fretta
- il punteggio può premiare chi arriva prima

In Frogger il tempo è una parte fondamentale della difficoltà.

> 💡 **Idea chiave:** il timer non cambia solo la velocità del gioco; cambia il modo in cui il giocatore prende decisioni.

---

## 9.2 — Il blocco `timer` o una variabile manuale?

### 📖 Introduzione teorica

Scratch offre un blocco già pronto chiamato `timer`, ma per un corso base spesso è più comodo usare una **variabile manuale**:

```text
tempo rimasto
```

Perché?

| Soluzione | Vantaggio |
|-----------|-----------|
| `timer` di Scratch | È già disponibile |
| variabile `tempo rimasto` | È più facile da mostrare, modificare e usare nel punteggio |

In questa unità useremo la seconda soluzione.

### 🛠️ Passaggi guidati

**Passo 1 — Crea la variabile**

Vai in **Variabili** e crea:

- `tempo rimasto`

Deve essere una variabile globale.

---

**Passo 2 — Imposta il valore iniziale**

Nello **Stage** oppure nella **Rana**, aggiungi:

```text
quando si clicca su 🚩
porta [tempo rimasto v] a (20)
```

`20` secondi è un valore comodo per iniziare. Più avanti potrai cambiarlo.

---

**Passo 3 — Crea il conto alla rovescia**

Nello Stage puoi costruire:

```text
quando si clicca su 🚩
per sempre
  attendi (1) secondi
  cambia [tempo rimasto v] di (-1)
```

Questo fa scendere il contatore di 1 ogni secondo.

> Prima di continuare, controlla sullo schermo che il numero scenda davvero: 20, 19, 18, 17...

---

## 9.3 — Cosa succede allo scadere del tempo?

### 📖 Introduzione teorica

Quando il tempo arriva a 0, il gioco deve trattarlo come un errore:

1. la rana perde una vita
2. torna alla partenza
3. il timer riparte

Questa è una nuova causa di sconfitta, diversa da auto e acqua ma gestita in modo simile.

### 🛠️ Passaggi guidati

**Passo 1 — Controlla la scadenza**

Nello Stage oppure nella Rana, aggiungi:

```text
quando si clicca su 🚩
per sempre
  se <(tempo rimasto) < (1)> allora
    cambia [vite v] di (-1)
    porta [tempo rimasto v] a (20)
    invia messaggio [reset-rana v]
```

---

**Passo 2 — Fai tornare la rana alla partenza**

Nello sprite **Rana**, aggiungi:

```text
quando ricevo [reset-rana v]
vai a x: (0) y: (-150)
```

Se vuoi, puoi anche aggiungere:

```text
dire [Tempo scaduto!] per (0.5) secondi
```

---

**Passo 3 — Evita che il timer continui sotto zero**

Se vuoi un comportamento più pulito, puoi migliorare il ciclo del timer:

```text
quando si clicca su 🚩
per sempre
  attendi (1) secondi
  se <(tempo rimasto) > (0)> allora
    cambia [tempo rimasto v] di (-1)
```

Così il timer non continua a scendere inutilmente mentre il reset è in corso.

---

## 9.4 — Far ripartire il timer nei momenti giusti

### 📖 Introduzione teorica

Il timer non deve ripartire solo quando scade. Deve anche essere **azzurato** quando la rana ricomincia un nuovo tentativo.

Esempi:

- all'avvio del gioco
- dopo una collisione
- dopo una caduta in acqua
- dopo aver raggiunto un nido

### 🛠️ Passaggi guidati

**Passo 1 — Resetta il timer sui principali eventi**

Nei punti del codice in cui la rana torna alla partenza, aggiungi:

```text
porta [tempo rimasto v] a (20)
```

Per esempio:

- dopo collisione con auto
- dopo acqua
- dopo tempo scaduto
- dopo nido conquistato

Questo mantiene il comportamento coerente: ogni tentativo parte con tempo pieno.

---

**Passo 2 — Collega il bonus tempo al punteggio**

Ora che `tempo rimasto` esiste davvero, puoi completare l'idea dell'unità 8.

Quando la rana conquista un nido, aggiungi un bonus come:

```text
cambia [punteggio v] di (tempo rimasto)
```

oppure:

```text
cambia [punteggio v] di ((tempo rimasto) * (2))
```

In questo modo chi arriva prima guadagna più punti.

---

**Passo 3 — Bilancia la difficoltà**

Puoi cambiare il valore iniziale del timer:

| Tempo iniziale | Effetto |
|----------------|---------|
| `30` | Facile |
| `20` | Equilibrato |
| `12` | Difficile |

Anche il tipo di traffico e la velocità dei tronchi influenzano la difficoltà. Il timer deve essere scelto in modo da rendere il gioco teso, ma non frustrante.

---

## 🎯 Mini Esercizio dell'Unità

> **Obiettivo:** Aggiungere un timer visibile; quando arriva a zero, la rana perde una vita e torna al via.

**Cosa deve funzionare alla fine:**

1. Il gioco mostra `tempo rimasto`
2. Il valore scende di 1 ogni secondo
3. Quando arriva a zero, le vite diminuiscono
4. La rana torna alla partenza
5. Il timer riparte da capo per il nuovo tentativo

**Verifica il tuo lavoro:**

- [ ] Hai creato la variabile `tempo rimasto`
- [ ] Il timer scende correttamente ogni secondo
- [ ] A zero si perde una vita
- [ ] La Rana riceve un messaggio di reset oppure viene riportata al via
- [ ] Il timer viene riportato al valore iniziale

---

## 💡 Domande di Riflessione

---

**Domanda 1**
Perché il timer rende Frogger più interessante?

a) Perché cambia il colore dello sfondo  
b) Perché obbliga il giocatore a decidere e muoversi più rapidamente  
c) Perché sostituisce i tronchi  
d) Perché elimina il bisogno di usare le vite

> *Risposta corretta: **b)** — Il tempo aggiunge pressione e cambia il ritmo delle decisioni.*

---

**Domanda 2**
Perché in questa unità usiamo la variabile `tempo rimasto` invece del blocco `timer`?

a) Perché il blocco `timer` non esiste  
b) Perché una variabile è più facile da mostrare e da collegare al punteggio  
c) Perché le variabili funzionano solo nello Stage  
d) Perché il blocco `timer` serve per i suoni

> *Risposta corretta: **b)** — Una variabile manuale è più flessibile per un progetto didattico come questo.*

---

**Domanda 3**
Cosa deve succedere quando `tempo rimasto` arriva a zero?

a) La rana vince automaticamente  
b) Il punteggio raddoppia  
c) Il giocatore perde una vita e la rana riparte dal via  
d) Tutti i nidi si svuotano

> *Risposta corretta: **c)** — Il tempo scaduto è una penalità come gli altri errori principali.*

---

**Domanda 4** *(riflessione aperta)*
Per il tuo gioco preferisci un timer generoso che lascia pensare oppure un timer stretto che crea tensione? Che effetto ha sulla sensazione di gioco?

---

**Domanda 5** *(sfida)*
Prova a usare `tempo rimasto` come bonus sul punteggio quando conquisti un nido. Quale formula ti sembra più equilibrata?

---

## 🔧 Tip & Tricks

> **Tip 1 — Usa un solo punto di reset**
> Se possibile, raggruppa i reset del timer in pochi punti chiari del codice.

> **Tip 2 — Parti da un valore comodo**
> Meglio testare con 20 o 30 secondi. Solo dopo puoi abbassare il tempo.

> **Tip 3 — Tieni visibile il timer**
> Se il giocatore non vede bene il tempo, non sentirà la tensione del conto alla rovescia.

> **Tip 4 — Collega tempo e punteggio**
> Un buon timer non serve solo a far perdere: può anche premiare chi gioca bene.

---

## 📋 Riepilogo dell'Unità

| Concetto | Cosa abbiamo imparato |
|----------|-----------------------|
| Timer | Limite di tempo che aumenta la tensione |
| `tempo rimasto` | Variabile che controlla il conto alla rovescia |
| Scadenza | Evento che fa perdere una vita |
| Reset del timer | Riporta il tempo al valore iniziale per un nuovo tentativo |
| Bilanciamento | Scelta del tempo giusto in base alla difficoltà del gioco |

**Verifica rapida:**
- [ ] Hai creato un conto alla rovescia visibile
- [ ] Il timer fa perdere una vita quando scade
- [ ] La rana torna alla partenza
- [ ] Il tempo riparte correttamente a ogni nuovo tentativo

---

## ➡️ Prossimo passo

Nella **Unità 10** aggiungeremo suoni, effetti visivi e schermate per dare al gioco un feedback più ricco e più vicino a un vero arcade.

---

*Mini Corso: Programmiamo con Scratch — Costruiamo Frogger! | Unità 9 di 11*
