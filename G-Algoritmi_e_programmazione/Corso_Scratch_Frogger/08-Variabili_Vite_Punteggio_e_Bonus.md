# 08 — Variabili: Vite, Punteggio e Bonus

> **Concetto chiave:** variabili e stato del gioco
> **Durata stimata:** 45–60 minuti
> **Prerequisiti:** Unità 7 completata — i nidi esistono e il livello si conclude quando tutti gli obiettivi sono pieni

---

## Obiettivi dell'unità

Al termine di questa unità lo studente sarà in grado di:

- Spiegare cos'è una **variabile**
- Creare e visualizzare `vite` e `punteggio`
- Aggiornare il punteggio quando la rana raggiunge un nido
- Ridurre le vite quando la rana viene colpita o cade in acqua
- Gestire una semplice schermata o messaggio di **Game Over**

---

## 8.1 — Cos'è una variabile?

### 📖 Introduzione teorica

Una **variabile** è un contenitore con un nome, dentro cui il programma conserva un valore che può cambiare.

Nel nostro Frogger alcune informazioni devono restare in memoria:

- quante vite restano
- quanti punti ha fatto il giocatore
- quanti nidi sono già pieni

Queste informazioni non appartengono a un singolo costume o a un singolo blocco: fanno parte dello **stato del gioco**.

> 💡 **Idea chiave:** senza variabili, il gioco non potrebbe "ricordare" nulla da un momento all'altro.

### Esempi

| Variabile | Significato |
|-----------|-------------|
| `vite` | Quanti tentativi restano |
| `punteggio` | Quanti punti ha ottenuto il giocatore |
| `nidi pieni` | Quanti obiettivi sono già stati completati |

---

## 8.2 — Creare e visualizzare `vite` e `punteggio`

### 🛠️ Passaggi guidati

**Passo 1 — Crea le variabili**

Vai nella categoria **Variabili** e crea:

- `vite`
- `punteggio`

Entrambe devono essere **per tutti gli sprite**.

---

**Passo 2 — Inizializza i valori**

Nello **Stage** oppure nella **Rana**, crea:

```text
quando si clicca su 🚩
porta [vite v] a (3)
porta [punteggio v] a (0)
```

Questo significa:

- il giocatore parte con 3 vite
- il punteggio iniziale è 0

---

**Passo 3 — Mostra le variabili**

Assicurati che `vite` e `punteggio` siano visibili sullo schermo.

Durante il test è molto utile vedere i valori cambiare in tempo reale.

> Più avanti potrai spostare i riquadri in un angolo ordinato dello schermo.

---

## 8.3 — Aumentare il punteggio: nidi e bonus

### 📖 Introduzione teorica

Il punteggio serve a premiare le azioni corrette del giocatore.

Per ora useremo questa regola base:

- ogni nido conquistato vale punti

Poi aggiungeremo due idee bonus:

- **bonus tempo** quando avrai introdotto il timer nell'unità successiva
- **bonus mosca** come estensione facoltativa

### 🛠️ Passaggi guidati

**Passo 1 — Assegna punti ai nidi**

Quando un nido viene conquistato, aggiungi:

```text
cambia [punteggio v] di (100)
```

Puoi metterlo nello script del nido, insieme al cambio di costume e all'aumento di `nidi pieni`.

Per esempio:

```text
quando ricevo [nido1-preso v]
se <costume [nome v] = [vuoto]> allora
  passa al costume [pieno v]
  cambia [nidi pieni v] di (1)
  cambia [punteggio v] di (100)
```

---

**Passo 2 — Prepara il bonus tempo**

Nell'unità 9 creerai la variabile `tempo rimasto`. Quando esisterà, potrai aggiungere:

```text
cambia [punteggio v] di (tempo rimasto)
```

oppure un bonus più controllato, ad esempio:

```text
cambia [punteggio v] di ((tempo rimasto) * (2))
```

Per ora ti basta sapere che il punteggio può dipendere anche dalla velocità con cui completi il percorso.

---

**Passo 3 — Bonus mosca (opzionale)**

Se vuoi una piccola estensione, puoi creare uno sprite **Mosca** che compare vicino a un nido.

Regola semplice:

- se la rana tocca la mosca
- aggiungi `200` punti
- nascondi la mosca

Script base della mosca:

```text
quando si clicca su 🚩
mostra
vai a x: (...) y: (...)
```

e nella Rana:

```text
se <sta toccando [Mosca v] ?> allora
  cambia [punteggio v] di (200)
```

> Questo bonus è facoltativo. La parte obbligatoria dell'unità è far funzionare vite e punteggio.

---

## 8.4 — Diminuire le vite e gestire il Game Over

### 📖 Introduzione teorica

Il giocatore non deve poter sbagliare all'infinito. Le **vite** servono proprio a questo: ogni errore grave riduce il numero di tentativi rimasti.

Nel nostro progetto, per ora gli errori principali sono:

- collisione con un'auto
- caduta in acqua
- tempo scaduto (lo collegheremo bene nell'unità 9)

### 🛠️ Passaggi guidati

**Passo 1 — Riduci le vite nella collisione con l'auto**

Nel punto in cui già gestisci la collisione, aggiungi:

```text
cambia [vite v] di (-1)
```

Per esempio:

```text
se <sta toccando [Auto v] ?> allora
  cambia [vite v] di (-1)
  vai a x: (0) y: (-150)
```

---

**Passo 2 — Riduci le vite anche nell'acqua**

Nel controllo del fiume, aggiungi la stessa idea:

```text
se <<sta toccando il colore [blu acqua] ?> e <non <sta toccando [Tronco v] ?>>> allora
  cambia [vite v] di (-1)
  vai a x: (0) y: (-150)
```

---

**Passo 3 — Crea il controllo di Game Over**

Nello **Stage** oppure nella **Rana**, aggiungi:

```text
quando si clicca su 🚩
per sempre
  se <(vite) = (0)> allora
    dire [GAME OVER] per (2) secondi
    ferma [tutti v]
```

Se vuoi essere più prudente, puoi usare:

```text
se <(vite) < (1)> allora
```

così il gioco si ferma anche se per errore il valore scende sotto zero.

---

**Passo 4 — Migliora il feedback finale**

Puoi aggiungere:

- un suono triste
- una schermata finale
- il punteggio mostrato per ultimo

Per esempio:

```text
quando ricevo [game-over v]
dire (unisci [GAME OVER - Punti: ] (punteggio)) per (3) secondi
```

---

## 🎯 Mini Esercizio dell'Unità

> **Obiettivo:** Il gioco tiene traccia di vite e punteggio e mostra `GAME OVER` quando le vite finiscono.

**Cosa deve funzionare alla fine:**

1. Il gioco parte con 3 vite e 0 punti
2. Ogni nido conquistato aumenta il punteggio
3. Collisioni e acqua fanno perdere una vita
4. Le variabili si aggiornano visivamente sullo schermo
5. Quando le vite arrivano a 0, compare il Game Over

**Verifica il tuo lavoro:**

- [ ] Hai creato `vite` e `punteggio`
- [ ] Hai inizializzato le due variabili alla bandiera verde
- [ ] Il punteggio aumenta almeno con i nidi
- [ ] Le vite diminuiscono almeno con auto e acqua
- [ ] Hai un controllo che mostra `GAME OVER`

---

## 💡 Domande di Riflessione

---

**Domanda 1**
Che cos'è una variabile?

a) Un tipo di suono  
b) Un contenitore che conserva un valore modificabile  
c) Un costume dello sprite  
d) Un bordo del palcoscenico

> *Risposta corretta: **b)** — Una variabile memorizza un valore che il gioco può leggere e modificare.*

---

**Domanda 2**
Perché `vite` e `punteggio` devono essere visibili durante il test?

a) Per decorare lo schermo  
b) Per controllare se la logica del gioco sta funzionando correttamente  
c) Per far andare più veloce Scratch  
d) Per creare cloni

> *Risposta corretta: **b)** — Vedere le variabili aiuta a capire subito se aumentano o diminuiscono nel momento giusto.*

---

**Domanda 3**
Quale istruzione riduce le vite di una unità?

a) `porta [vite] a (3)`  
b) `cambia [vite] di (1)`  
c) `cambia [vite] di (-1)`  
d) `nascondi`

> *Risposta corretta: **c)** — Sommare `-1` equivale a sottrarre una vita.*

---

**Domanda 4** *(riflessione aperta)*
Secondo te un nido dovrebbe valere sempre lo stesso numero di punti o dovrebbe dare più punti se viene raggiunto in fretta? Perché?

---

**Domanda 5** *(sfida)*
Prova ad aggiungere un bonus mosca da 200 punti vicino a un nido. Come fai a evitare che venga raccolta più volte?

---

## 🔧 Tip & Tricks

> **Tip 1 — Tieni le variabili semplici**
> All'inizio usa pochi valori chiari: 3 vite, 100 punti per nido, 200 per bonus.

> **Tip 2 — Aggiorna le vite nello stesso punto dell'errore**
> Se la perdita di una vita è scritta vicino alla collisione o alla caduta in acqua, il codice è più facile da leggere.

> **Tip 3 — Usa lo Stage per Game Over**
> Lo Stage è un buon posto per mostrare messaggi globali come `GAME OVER`.

> **Tip 4 — Pensa allo stato del gioco**
> Vite, punteggio e nidi pieni raccontano in ogni momento "come sta andando" la partita.

---

## 📋 Riepilogo dell'Unità

| Concetto | Cosa abbiamo imparato |
|----------|-----------------------|
| Variabile | Memoria del gioco per valori che cambiano |
| `vite` | Numero di tentativi rimasti |
| `punteggio` | Valore accumulato dal giocatore |
| Bonus | Punti extra assegnati per azioni speciali |
| Game Over | Stato finale quando le vite finiscono |

**Verifica rapida:**
- [ ] Hai creato e mostrato `vite` e `punteggio`
- [ ] Le vite diminuiscono quando la rana sbaglia
- [ ] Il punteggio aumenta almeno con i nidi
- [ ] Il gioco mostra `GAME OVER` quando le vite finiscono

---

## ➡️ Prossimo passo

Nella **Unità 9** aggiungeremo il **conto alla rovescia** per aumentare la tensione: se il tempo scade, la rana perderà una vita.

---

*Mini Corso: Programmiamo con Scratch — Costruiamo Frogger! | Unità 8 di 11*
