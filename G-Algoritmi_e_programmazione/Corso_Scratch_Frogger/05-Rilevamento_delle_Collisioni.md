# 05 — Rilevamento delle Collisioni

> **Concetto chiave:** condizioni e interazione tra sprite
> **Durata stimata:** 45–60 minuti
> **Prerequisiti:** Unità 4 completata — il traffico è composto da più automobili generate con i cloni

---

## Obiettivi dell'unità

Al termine di questa unità lo studente sarà in grado di:

- Spiegare cos'è una condizione in Scratch
- Usare il blocco `se ... allora` per controllare una situazione di pericolo
- Rilevare quando la rana tocca un'automobile
- Gestire una collisione con effetto visivo e ritorno alla posizione di partenza
- Distinguere tra bordo come limite del campo e ostacolo come pericolo attivo

---

## 5.1 — Cos'è una condizione?

### 📖 Introduzione teorica

Finora abbiamo fatto muovere rana e automobili. Ma il gioco non "capisce" ancora quando succede qualcosa di importante.

Per far reagire il programma serve una **condizione**: una domanda a cui il computer può rispondere con **vero** o **falso**.

Esempi di condizioni:

- la rana sta toccando un'auto?
- la rana è arrivata al bordo?
- la rana è dentro il fiume?

In Scratch la struttura più comune è:

```text
se <condizione> allora
  esegui queste istruzioni
```

Per esempio:

```text
se <sta toccando [Auto v] ?> allora
  vai a x: (0) y: (-150)
```

> 💡 **Idea chiave:** i giochi non reagiscono "da soli". Reagiscono quando una condizione diventa vera.

---

## 5.2 — Il blocco `sta toccando [sprite]?`

### 📖 Introduzione teorica

Scratch mette a disposizione un blocco molto utile nella categoria **Sensori**:

```text
sta toccando [sprite]?
```

Questo blocco controlla se uno sprite è in contatto con un altro.

Nel nostro caso lo useremo nello sprite **Rana** per controllare se tocca lo sprite **Auto**.

### Attenzione con i cloni

Anche se le automobili visibili sono **cloni**, Scratch le riconosce comunque come parte dello sprite **Auto**. Quindi il blocco:

```text
sta toccando [Auto]?
```

funziona sia con lo sprite originale sia con tutti i suoi cloni.

Questa è una grande comodità: non dobbiamo controllare ogni automobile una per una.

---

## 5.3 — Cosa succede quando la rana viene investita

### 📖 Introduzione teorica

Quando la rana tocca un'auto, il gioco deve dare un **feedback chiaro** al giocatore.

Le azioni minime sono:

1. mostrare che c'è stata una collisione
2. aspettare un attimo
3. riportare la rana alla posizione di partenza

Più avanti aggiungeremo vite, punteggio e suoni. In questa unità ci concentriamo sul comportamento base.

### 🛠️ Passaggi guidati

**Passo 1 — Aggiungi un controllo continuo nella Rana**

Nello sprite **Rana**, crea questo script:

```text
quando si clicca su 🚩
per sempre
  se <sta toccando [Auto v] ?> allora
    vai a x: (0) y: (-150)
```

Questo è il sistema più semplice possibile: appena la rana tocca un'auto, torna al punto di partenza.

---

**Passo 2 — Aggiungi un piccolo effetto visivo**

Il reset immediato funziona, ma è un po' brusco. Miglioriamolo.

Puoi sostituire lo script con questa versione:

```text
quando si clicca su 🚩
per sempre
  se <sta toccando [Auto v] ?> allora
    effetto fantasma a (50)
    attendi (0.2) secondi
    azzera effetti grafici
    vai a x: (0) y: (-150)
```

### Cosa fa questo script

- rende la rana semitrasparente per un attimo
- aspetta un breve istante
- toglie l'effetto grafico
- la riporta alla partenza

Se preferisci, puoi anche usare:

- `dire [Ahi!] per (0.5) secondi`
- un cambio rapido di costume
- un piccolo suono di collisione

---

**Passo 3 — Evita collisioni ripetute nello stesso istante**

A volte, se la rana viene rimessa troppo vicino alla corsia o se l'effetto dura troppo poco, può sembrare che il gioco reagisca più volte di seguito.

Per rendere il comportamento più pulito, puoi usare questa variante:

```text
quando si clicca su 🚩
per sempre
  se <sta toccando [Auto v] ?> allora
    nascondi
    attendi (0.2) secondi
    vai a x: (0) y: (-150)
    mostra
```

Nascondendo la rana per un attimo, il giocatore percepisce meglio il "colpo" e il reset.

> Scegli una sola versione dell'effetto: fantasma oppure nascondi/mostra. Non serve usarle entrambe.

---

## 5.4 — Collisione con i bordi dello schermo

### 📖 Introduzione teorica

I **bordi** e le **automobili** non sono la stessa cosa.

| Elemento | Ruolo nel gioco |
|----------|-----------------|
| Bordo dello schermo | Limite del campo |
| Automobile | Ostacolo che fa perdere la posizione |

Nelle unità precedenti abbiamo già fatto in modo che la rana non uscisse dal campo. Questo significa che, sulla strada, il bordo si comporta come un **muro invisibile**.

La vera minaccia qui sono le automobili.

Più avanti, quando costruiremo il fiume, dovremo ricordare una cosa importante: **sull'acqua il bordo non sarà più solo un muro**, ma potrà diventare parte del pericolo.

### 🛠️ Verifica guidata

Controlla questi due aspetti:

1. Se premi le frecce verso il bordo, la rana non esce dal campo
2. Se la rana tocca un'auto, il controllo collisione si attiva

Questo ti mostra che stai già usando due logiche diverse:

- una logica di **limite**
- una logica di **interazione**

Sono entrambe fondamentali nei videogiochi.

---

## 🎯 Mini Esercizio dell'Unità

> **Obiettivo:** La rana riconosce il pericolo e torna alla partenza quando viene colpita da un'auto.

**Cosa deve funzionare alla fine:**

1. Il traffico continua a muoversi in almeno tre corsie
2. La rana si muove ancora con le frecce
3. Quando la rana tocca un'auto, si vede un piccolo effetto
4. Dopo l'effetto, la rana torna alla posizione iniziale
5. Il bordo continua a bloccare il movimento senza sostituire la collisione

**Verifica il tuo lavoro:**

- [ ] Lo sprite **Rana** contiene un ciclo `per sempre`
- [ ] Dentro il ciclo c'è `se <sta toccando [Auto] ?> allora`
- [ ] La rana viene riposizionata con `vai a x: ... y: ...`
- [ ] C'è almeno un piccolo feedback visivo o testuale

---

## 💡 Domande di Riflessione

---

**Domanda 1**
Che cos'è una condizione in Scratch?

a) Un tipo di sprite  
b) Una domanda che può risultare vera o falsa  
c) Un effetto grafico  
d) Un modo per cambiare sfondo

> *Risposta corretta: **b)** — Una condizione è un controllo logico che produce vero o falso.*

---

**Domanda 2**
Quale blocco serve per controllare se la rana è in contatto con le automobili?

a) `quando vengo clonato`  
b) `dire [ciao]`  
c) `sta toccando [Auto]?`  
d) `porta in primo piano`

> *Risposta corretta: **c)** — È il blocco dei sensori che rileva il contatto con uno sprite o con i suoi cloni.*

---

**Domanda 3**
Perché il controllo collisione va messo dentro un ciclo `per sempre`?

a) Perché la collisione va controllata continuamente durante il gioco  
b) Perché Scratch non permette di usare `se ... allora` da solo  
c) Perché serve per far comparire nuovi cloni  
d) Perché le frecce della tastiera funzionano solo nei cicli

> *Risposta corretta: **a)** — Il gioco deve verificare in continuazione se la rana tocca un'auto.*

---

**Domanda 4** *(riflessione aperta)*
Secondo te è meglio far tornare la rana subito alla partenza o mostrare prima un piccolo effetto di collisione? Quale soluzione comunica meglio al giocatore che ha sbagliato?

---

**Domanda 5** *(sfida)*
Prova a cambiare l'effetto di collisione: invece di usare l'effetto fantasma, usa `dire [Crash!]`, un cambio costume o una breve vibrazione del personaggio. Quale ti sembra più chiaro?

---

## 🔧 Tip & Tricks

> **Tip 1 — Controllo nella Rana, non nell'Auto**
> È più semplice mettere il controllo collisione nello sprite Rana: così hai un solo punto in cui gestire l'effetto e il reset.

> **Tip 2 — Evita attese troppo lunghe**
> Se l'attesa dopo la collisione è troppo lunga, il gioco sembrerà bloccarsi. Valori come `0.2` o `0.3` secondi sono spesso sufficienti.

> **Tip 3 — Mantieni sempre la stessa posizione di reset**
> Usa gli stessi valori di partenza già scelti nelle unità precedenti, così il comportamento resta coerente.

> **Tip 4 — I cloni contano come Auto**
> Se il blocco `sta toccando [Auto]?` non sembra funzionare, controlla che i cloni siano davvero generati dallo sprite giusto e che la rana tocchi l'area visibile dell'auto.

---

## 📋 Riepilogo dell'Unità

| Concetto | Cosa abbiamo imparato |
|----------|-----------------------|
| Condizione | Controllo logico vero/falso usato per far reagire il gioco |
| `se ... allora` | Esegue un'azione solo quando una situazione è vera |
| `sta toccando [sprite]?` | Rileva il contatto con uno sprite e con i suoi cloni |
| Collisione | Evento di contatto che attiva effetto e reset |
| Feedback | Aiuta il giocatore a capire che è successo qualcosa di importante |
| Bordo vs ostacolo | Il bordo limita il movimento, l'ostacolo genera una conseguenza |

**Verifica rapida:**
- [ ] Sai spiegare cos'è una condizione
- [ ] Hai usato `sta toccando [Auto]?`
- [ ] La rana torna alla partenza dopo una collisione
- [ ] Hai aggiunto un piccolo effetto visivo o testuale

---

## ➡️ Prossimo passo

Nella **Unità 6** porteremo la rana nel fiume: costruiremo i tronchi, il moto relativo e la regola più importante di Frogger sull'acqua.

---

*Mini Corso: Programmiamo con Scratch — Costruiamo Frogger! | Unità 5 di 11*
