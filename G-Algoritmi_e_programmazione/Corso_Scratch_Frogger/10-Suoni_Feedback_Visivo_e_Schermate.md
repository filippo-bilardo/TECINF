# 10 — Suoni, Feedback Visivo e Schermate

> **Concetto chiave:** feedback multimediale
> **Durata stimata:** 45–60 minuti
> **Prerequisiti:** Unità 9 completata — il gioco ha traffico, fiume, nidi, vite, punteggio e timer

---

## Obiettivi dell'unità

Al termine di questa unità lo studente sarà in grado di:

- Importare o registrare suoni in Scratch
- Associare suoni alle azioni principali del gioco
- Usare effetti grafici e messaggi visivi per migliorare il feedback
- Creare una semplice schermata iniziale
- Mostrare una schermata di Game Over con punteggio finale

---

## 10.1 — Importare o registrare suoni in Scratch

### 📖 Introduzione teorica

Un buon videogioco non comunica solo con immagini e movimento. Usa anche:

- **suoni**
- **messaggi visivi**
- **piccoli effetti grafici**

Questi elementi aiutano il giocatore a capire subito cosa sta succedendo:

- salto riuscito
- collisione
- arrivo a un nido
- fine della partita

Scratch permette due strade molto semplici:

1. usare suoni già presenti nella libreria
2. registrare un suono con il microfono

### 🛠️ Passaggi guidati

**Passo 1 — Apri la scheda Suoni**

Seleziona uno sprite, ad esempio **Rana**, poi clicca sulla scheda **Suoni**.

---

**Passo 2 — Aggiungi un suono**

Puoi:

1. cliccare su **Scegli un suono**
2. cercare un effetto breve
3. aggiungerlo allo sprite

Per la rana vanno bene suoni come:

- pop
- jump
- boing

Per il Game Over possono funzionare:

- lose
- buzz
- down note

---

**Passo 3 — Registra un suono personalizzato (opzionale)**

Se vuoi personalizzare il progetto:

1. clicca su **Registra**
2. pronuncia una parola breve come `via!`, `goal!` o `game over`
3. rifila il suono se serve

> I suoni brevi funzionano meglio dei suoni lunghi: non rallentano il gioco e sono più chiari.

---

## 10.2 — Suoni per salto, collisione, goal e Game Over

### 📖 Introduzione teorica

In un gioco non serve mettere un suono ovunque. Conviene scegliere i momenti davvero importanti.

I quattro casi più utili sono:

| Evento | Feedback suggerito |
|--------|--------------------|
| Salto della rana | Suono rapido e leggero |
| Collisione con auto / acqua | Suono corto e netto |
| Nido conquistato | Suono positivo |
| Game Over | Suono finale riconoscibile |

### 🛠️ Passaggi guidati

**Passo 1 — Suono del salto**

Nello sprite **Rana**, nel punto in cui gestisci il movimento con le frecce, aggiungi:

```text
avvia il suono [jump v]
```

Mettilo poco prima o poco dopo il movimento.

Per esempio:

```text
quando si preme il tasto [freccia su]
avvia il suono [jump v]
cambia y di (40)
```

---

**Passo 2 — Suono della collisione**

Nel blocco che gestisce auto o acqua, aggiungi:

```text
avvia il suono [crash v]
```

Esempio:

```text
se <sta toccando [Auto v] ?> allora
  avvia il suono [crash v]
  cambia [vite v] di (-1)
  vai a x: (0) y: (-150)
```

---

**Passo 3 — Suono del nido conquistato**

Nel punto in cui la rana conquista un nido o invia il messaggio corrispondente, aggiungi:

```text
avvia il suono [goal v]
```

Questo aiuta il giocatore a percepire il successo.

---

**Passo 4 — Suono del Game Over**

Nel controllo finale puoi usare:

```text
quando ricevo [game-over v]
avvia il suono [game over v]
```

Se non hai ancora un messaggio dedicato, puoi aggiungerlo:

```text
se <(vite) < (1)> allora
  trasmetti [game-over v]
  ferma [tutti v]
```

> Se usi `ferma [tutti]`, fai partire il suono appena prima oppure gestiscilo nello Stage.

---

## 10.3 — Effetti grafici e pop-up messaggi

### 📖 Introduzione teorica

Il suono da solo non basta. Un buon feedback usa anche segnali visivi.

In Scratch puoi lavorare con:

- `dire [messaggio] per (...) secondi`
- `cambia effetto [fantasma]`
- `cambia effetto [colore]`
- `mostra` / `nascondi`

### 🛠️ Passaggi guidati

**Passo 1 — Effetto di danno**

Nella collisione puoi usare:

```text
effetto fantasma a (70)
attendi (0.2) secondi
azzera effetti grafici
```

Questo rende visivamente chiaro che la rana ha subito un colpo.

---

**Passo 2 — Messaggio per il tempo scaduto**

Quando il timer arriva a zero, puoi aggiungere:

```text
dire [Tempo scaduto!] per (0.5) secondi
```

---

**Passo 3 — Messaggio di successo**

Quando la rana conquista un nido:

```text
dire [Goal!] per (0.4) secondi
```

oppure, se preferisci non far parlare la rana, puoi mostrare un piccolo sprite testo nello Stage.

---

**Passo 4 — Effetto visivo per la vittoria**

Quando `nidi pieni = 5`, puoi usare nello Stage:

```text
dire [LIVELLO COMPLETATO] per (2) secondi
```

oppure un effetto più ricco:

```text
cambia effetto [colore v] di (25)
attendi (0.2) secondi
azzera effetti grafici
```

> Gli effetti devono essere brevi. Se durano troppo, rallentano il ritmo del gioco.

---

## 10.4 — Schermata iniziale e schermata di Game Over

### 📖 Introduzione teorica

Ora il progetto può diventare più simile a un vero videogioco completo.

Due schermate molto utili sono:

1. **schermata iniziale**
2. **schermata di Game Over**

La prima spiega come iniziare. La seconda chiude la partita in modo chiaro.

### 🛠️ Passaggi guidati

**Passo 1 — Crea una schermata iniziale**

Nel **palcoscenico**, aggiungi uno sfondo iniziale con:

- titolo del gioco
- istruzioni brevi
- messaggio tipo `premi spazio per iniziare`

Puoi chiamare questo sfondo:

- `titolo`

e lasciare lo sfondo di gioco come:

- `campo di gioco`

---

**Passo 2 — Aspetta il tasto spazio**

Nello Stage puoi costruire:

```text
quando si clicca su 🚩
passa allo sfondo [titolo v]
attendi fino a <tasto [spazio v] premuto?>
passa allo sfondo [campo di gioco v]
```

Se vuoi, mentre aspetti puoi nascondere gli sprite principali e mostrarli solo dopo lo start.

---

**Passo 3 — Crea una schermata di Game Over**

Quando il gioco finisce, puoi passare a uno sfondo finale:

```text
quando ricevo [game-over v]
passa allo sfondo [game over v]
dire (unisci [Punti finali: ] (punteggio)) per (3) secondi
```

Lo sfondo `game over` può contenere:

- scritta grande `GAME OVER`
- istruzione `clicca bandiera verde per ricominciare`

---

**Passo 4 — Rendi chiaro il flusso**

Il giocatore dovrebbe percepire con chiarezza:

1. **inizio**
2. **gioco**
3. **fine**

Se queste tre fasi sono visibili, il progetto sembra molto più rifinito.

---

## 🎯 Mini Esercizio dell'Unità

> **Obiettivo:** Aggiungere suoni per le azioni principali, una schermata di benvenuto e una schermata di Game Over.

**Cosa deve funzionare alla fine:**

1. La rana ha almeno un suono di salto
2. Collisione o acqua hanno un suono dedicato
3. Il nido conquistato o la vittoria hanno un feedback positivo
4. Esiste uno sfondo iniziale con istruzioni
5. Esiste una schermata finale con `GAME OVER`

**Verifica il tuo lavoro:**

- [ ] Hai aggiunto almeno 3 suoni utili
- [ ] Hai usato almeno 1 effetto visivo o messaggio
- [ ] Il gioco mostra una schermata iniziale
- [ ] Il gioco mostra una schermata finale

---

## 💡 Domande di Riflessione

---

**Domanda 1**
Perché suoni ed effetti sono importanti in un videogioco?

a) Perché sostituiscono il codice  
b) Perché aiutano il giocatore a capire subito cosa è successo  
c) Perché fanno aumentare le vite  
d) Perché servono solo nei giochi musicali

> *Risposta corretta: **b)** — Il feedback multimediale rende il gioco più chiaro e coinvolgente.*

---

**Domanda 2**
Quale schermata compare prima dell'inizio della partita?

a) Game Over  
b) Schermata iniziale con titolo e istruzioni  
c) Schermata del fiume  
d) Nessuna schermata

> *Risposta corretta: **b)** — Una schermata iniziale aiuta a presentare il gioco e i controlli.*

---

**Domanda 3**
Quando conviene usare un suono breve invece di uno lungo?

a) Sempre, perché nei giochi d'azione i feedback devono essere rapidi e chiari  
b) Mai  
c) Solo per gli sfondi  
d) Solo nello Stage

> *Risposta corretta: **a)** — Nei giochi come Frogger funzionano meglio suoni rapidi e riconoscibili.*

---

**Domanda 4** *(riflessione aperta)*
Preferisci un feedback molto evidente, con molti suoni e messaggi, oppure uno più discreto? Quale stile si adatta meglio al tuo Frogger?

---

**Domanda 5** *(sfida)*
Prova ad aggiungere una schermata iniziale animata in cui il titolo cambia colore o lampeggia. Quale effetto grafico useresti?

---

## 🔧 Tip & Tricks

> **Tip 1 — Pochi suoni, ma giusti**
> Meglio pochi suoni chiari che molti suoni confusi.

> **Tip 2 — Evita sovrapposizioni inutili**
> Se due eventi possono accadere quasi insieme, scegli quali suoni devono avere priorità.

> **Tip 3 — Lo Stage è ideale per le schermate**
> Titolo, Game Over e messaggi globali stanno meglio nello Stage che negli sprite mobili.

> **Tip 4 — Coerenza prima di tutto**
> Se il verde indica successo e il fantasma indica danno, usa sempre gli stessi segnali lungo tutto il gioco.

---

## 📋 Riepilogo dell'Unità

| Concetto | Cosa abbiamo imparato |
|----------|-----------------------|
| Suono | Rafforza azioni ed eventi importanti |
| Feedback visivo | Comunica colpo, successo, attesa e fine partita |
| Schermata iniziale | Presenta titolo e istruzioni |
| Schermata finale | Mostra chiaramente la fine della partita |
| Coordinazione audio-video | Rende il gioco più chiaro e coinvolgente |

**Verifica rapida:**
- [ ] Hai aggiunto suoni alle azioni principali
- [ ] Hai migliorato il feedback con effetti o messaggi
- [ ] Hai una schermata iniziale
- [ ] Hai una schermata di Game Over

---

## ➡️ Prossimo passo

Nella **Unità 11** inizieremo la fase avanzata del corso: i cloni avranno una loro memoria locale, così corsie e ostacoli potranno comportarsi in modo indipendente.

---

*Mini Corso: Programmiamo con Scratch — Costruiamo Frogger! | Unità 10 di 11*
