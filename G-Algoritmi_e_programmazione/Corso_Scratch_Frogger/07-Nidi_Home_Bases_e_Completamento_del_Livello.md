# 07 — Nidi (Home Bases) e Completamento del Livello

> **Concetto chiave:** obiettivi multipli, stati e avanzamento del livello
> **Durata stimata:** 45–60 minuti
> **Prerequisiti:** Unità 6 completata — la rana attraversa strada e fiume, usa i tronchi e torna alla partenza se cade in acqua

---

## Obiettivi dell'unità

Al termine di questa unità lo studente sarà in grado di:

- Creare i **5 nidi** in cima al campo di gioco
- Usare sprite-sensore o sprite-obiettivo per riconoscere l'arrivo della rana
- Gestire il cambio di stato di un nido da **vuoto** a **pieno**
- Tenere il conto dei nidi conquistati
- Rilevare quando il livello è stato completato

---

## 7.1 — I 5 nidi in cima al campo

### 📖 Introduzione teorica

Nel Frogger classico l'obiettivo non è arrivare una sola volta in cima allo schermo: bisogna riempire **tutti i nidi**.

Ogni nido può avere due stati:

| Stato | Significato |
|-------|-------------|
| Vuoto | La rana può entrarci |
| Pieno | Il nido è già stato conquistato |

Per costruirli in Scratch hai due possibilità:

1. usare **5 sprite separati** (`Nido1`, `Nido2`, `Nido3`, `Nido4`, `Nido5`)
2. usare un solo sprite duplicato più volte

Per questa unità la soluzione più chiara è la prima: uno sprite per ogni nido.

### 🛠️ Passaggi guidati

**Passo 1 — Crea il primo nido**

1. Aggiungi uno sprite semplice oppure disegnane uno
2. Dagli un aspetto chiaro, ad esempio un cerchio verde o una piccola tana
3. Rinominalo **Nido1**
4. Posizionalo nella fascia alta del campo

---

**Passo 2 — Duplica fino ad arrivare a cinque**

Duplica lo sprite quattro volte e rinomina le copie:

- `Nido2`
- `Nido3`
- `Nido4`
- `Nido5`

Disponili in modo regolare nella parte superiore del prato.

> Se vuoi, puoi lasciare un piccolo spazio tra un nido e l'altro per rendere il gioco più leggibile.

---

## 7.2 — Raggiungere un nido

### 📖 Introduzione teorica

Quando la rana tocca un nido libero, deve succedere qualcosa di importante:

1. il nido viene segnato come occupato
2. la rana scompare oppure torna alla partenza
3. il gioco registra il progresso

Per farlo, ogni nido può avere **due costumi**:

- `vuoto`
- `pieno`

Il costume `pieno` può mostrare una piccola rana seduta o un simbolo di obiettivo completato.

### 🛠️ Passaggi guidati

**Passo 1 — Aggiungi due costumi a un nido**

Apri **Nido1** e crea:

- un costume `vuoto`
- un costume `pieno`

Il primo deve essere visibile ma libero. Il secondo deve mostrare chiaramente che quel posto è già occupato.

Poi ripeti la stessa cosa per gli altri quattro nidi.

---

**Passo 2 — Crea il controllo nello sprite Rana**

Per iniziare, lavora con un solo nido. Nello sprite **Rana**, aggiungi dentro un ciclo `per sempre` una logica di questo tipo:

```text
se <sta toccando [Nido1 v] ?> allora
  invia messaggio [nido1-preso v]
  vai a x: (0) y: (-150)
```

Questo messaggio serve per lasciare al nido il compito di cambiare stato.

---

**Passo 3 — Fai reagire il nido**

Nello sprite **Nido1**, crea:

```text
quando ricevo [nido1-preso v]
passa al costume [pieno v]
```

Ora, quando la rana raggiunge il nido, il nido cambia aspetto.

> Usare un messaggio è utile perché separa bene i compiti: la Rana rileva l'arrivo, il Nido gestisce il proprio stato.

---

## 7.3 — Tenere il conto: la variabile `nidi pieni`

### 📖 Introduzione teorica

Se vogliamo sapere quando il livello è finito, dobbiamo contare quanti nidi sono già stati riempiti.

Creiamo quindi una variabile globale:

```text
nidi pieni
```

Ogni volta che un nuovo nido viene conquistato, la variabile aumenta di 1.

### 🛠️ Passaggi guidati

**Passo 1 — Crea la variabile**

Vai in **Variabili** e crea:

- `nidi pieni` per tutti gli sprite

Poi aggiungi nello stage o nella Rana uno script di inizializzazione:

```text
quando si clicca su 🚩
porta [nidi pieni v] a (0)
```

---

**Passo 2 — Aggiorna il conteggio**

Nel messaggio del nido, aggiungi:

```text
quando ricevo [nido1-preso v]
passa al costume [pieno v]
cambia [nidi pieni v] di (1)
```

Ripeti lo stesso schema per `Nido2`, `Nido3`, `Nido4`, `Nido5`.

---

**Passo 3 — Evita che un nido già pieno conti due volte**

Se la rana torna su un nido già occupato, non vogliamo aumentare di nuovo il contatore.

Nel singolo nido puoi usare una condizione:

```text
quando ricevo [nido1-preso v]
se <costume [nome v] = [vuoto]> allora
  passa al costume [pieno v]
  cambia [nidi pieni v] di (1)
```

Se questa forma ti sembra complicata, puoi usare una soluzione più semplice:

- quando il nido diventa pieno, non deve più reagire
- oppure la rana non deve più poterci entrare

Per un corso base va bene anche trattare il nido già pieno come "proibito" e rimandare la rana alla partenza.

---

## 7.4 — Livello superato

### 📖 Introduzione teorica

Quando `nidi pieni = 5`, il livello è stato completato.

Questo è un esempio perfetto di **stato globale del gioco**: il programma osserva una variabile e decide quando mostrare una nuova situazione.

### 🛠️ Passaggi guidati

**Passo 1 — Controlla la fine del livello**

Nello **Stage** oppure nella **Rana**, crea:

```text
quando si clicca su 🚩
per sempre
  se <(nidi pieni) = (5)> allora
    dire [LIVELLO COMPLETATO] per (2) secondi
    ferma [tutti v]
```

Questa è la versione più semplice.

---

**Passo 2 — Migliora il feedback**

Se vuoi rendere il momento più bello, puoi aggiungere:

- un suono di vittoria
- un cambio di sfondo
- una scritta grande nello stage

Per esempio:

```text
quando si clicca su 🚩
per sempre
  se <(nidi pieni) = (5)> allora
    trasmetti [livello-completato v]
    ferma [questo script v]
```

Poi nello Stage:

```text
quando ricevo [livello-completato v]
dire [LIVELLO COMPLETATO] per (2) secondi
```

---

## 🎯 Mini Esercizio dell'Unità

> **Obiettivo:** Riempire tutti e 5 i nidi; quando l'ultimo viene conquistato, appare il messaggio di livello completato.

**Cosa deve funzionare alla fine:**

1. Esistono 5 nidi nella parte alta del campo
2. Ogni nido può passare da vuoto a pieno
3. La rana può attivare i nidi quando li raggiunge
4. La variabile `nidi pieni` conta i nidi conquistati
5. Quando il contatore arriva a 5, compare `LIVELLO COMPLETATO`

**Verifica il tuo lavoro:**

- [ ] Hai creato la variabile `nidi pieni`
- [ ] Ogni nido ha almeno due stati visivi
- [ ] La rana riconosce almeno un nido con `sta toccando [Nido]?`
- [ ] Il gioco mostra un messaggio finale quando tutti i nidi sono pieni

---

## 💡 Domande di Riflessione

---

**Domanda 1**
Perché i nidi sono importanti in Frogger?

a) Perché sostituiscono le automobili  
b) Perché rappresentano gli obiettivi finali del livello  
c) Perché servono solo per decorazione  
d) Perché fanno muovere la rana più velocemente

> *Risposta corretta: **b)** — I nidi sono i punti da conquistare per completare il livello.*

---

**Domanda 2**
Cosa rappresenta la variabile `nidi pieni`?

a) Il numero di vite rimaste  
b) Il numero di tronchi presenti nel fiume  
c) Quanti obiettivi sono già stati conquistati  
d) La velocità delle auto

> *Risposta corretta: **c)** — Serve a tenere il conto dei nidi occupati.*

---

**Domanda 3**
Perché è utile usare un messaggio come `nido1-preso`?

a) Per cambiare lingua a Scratch  
b) Per far collaborare rana e nido senza mescolare troppo il codice  
c) Per far sparire le automobili  
d) Per creare un clone

> *Risposta corretta: **b)** — I messaggi aiutano a separare i compiti dei diversi sprite.*

---

**Domanda 4** *(riflessione aperta)*
Se la rana entra in un nido già pieno, secondo te è meglio bloccarla, farla rimbalzare o farle perdere il turno? Quale soluzione ti sembra più chiara per il giocatore?

---

**Domanda 5** *(sfida)*
Prova a fare in modo che ogni nido mostri una piccola rana seduta quando viene conquistato. Quale costume aggiungeresti?

---

## 🔧 Tip & Tricks

> **Tip 1 — Inizia da un solo nido**
> Fai funzionare bene `Nido1`, poi copia la logica sugli altri quattro.

> **Tip 2 — Dai nomi chiari ai messaggi**
> Usa messaggi come `nido1-preso`, `nido2-preso` e `livello-completato`: sono facili da leggere.

> **Tip 3 — Tieni visibile `nidi pieni`**
> Durante i test è utile vedere il contatore sullo schermo.

> **Tip 4 — Separa la logica**
> La Rana rileva l'arrivo; il Nido cambia costume; lo Stage può gestire il messaggio finale. Questa divisione rende il progetto più ordinato.

---

## 📋 Riepilogo dell'Unità

| Concetto | Cosa abbiamo imparato |
|----------|-----------------------|
| Nido | Obiettivo finale da conquistare |
| Stato vuoto/pieno | Rappresenta se il nido è disponibile oppure occupato |
| Variabile `nidi pieni` | Conta i progressi del livello |
| Messaggi | Fanno collaborare rana, nidi e stage |
| Livello completato | Si attiva quando tutti i nidi sono occupati |

**Verifica rapida:**
- [ ] Hai creato 5 nidi
- [ ] Almeno un nido cambia stato correttamente
- [ ] La variabile `nidi pieni` si aggiorna
- [ ] Compare un messaggio quando tutti i nidi sono pieni

---

## ➡️ Prossimo passo

Nella **Unità 8** aggiungeremo le variabili più importanti del gioco: **vite**, **punteggio** e i primi **bonus**.

---

*Mini Corso: Programmiamo con Scratch — Costruiamo Frogger! | Unità 7 di 11*
