# 14 — Procedure Personalizzate (I Miei Blocchi)

> **Concetto chiave:** astrazione e riutilizzo del codice
> **Durata stimata:** 45–60 minuti
> **Prerequisiti:** Unità 13 completata — il progetto include ormai molte regole, eccezioni e comportamenti differenti

---

## Obiettivi dell'unità

Al termine di questa unità lo studente sarà in grado di:

- Riconoscere codice ripetuto nel progetto
- Creare blocchi personalizzati in Scratch
- Riunire più istruzioni in procedure come `resetta rana` o `game over`
- Passare parametri ai blocchi personalizzati
- Preparare il progetto a una gestione più modulare dei livelli

---

## 14.1 — Perché il codice si ripete?

### 📖 Introduzione teorica

Dopo molte unità, il progetto è più ricco ma anche più difficile da leggere. Probabilmente hai scritto più volte blocchi molto simili:

- riportare la rana alla partenza
- togliere una vita
- resettare il timer
- mostrare un messaggio finale

Questo è il classico problema della **copia e incolla**.

Gli svantaggi sono:

1. se cambi una regola, devi ricordarti di aggiornarla ovunque
2. aumentano gli errori
3. il progetto diventa lungo e dispersivo

La soluzione è creare **blocchi personalizzati** nella categoria **I miei blocchi**.

> 💡 **Idea chiave:** un blocco personalizzato trasforma una sequenza di istruzioni ricorrenti in un comando con un nome chiaro.

---

## 14.2 — Creare blocchi come `resetta rana`, `controlla collisione`, `game over`

### 🛠️ Passaggi guidati

**Passo 1 — Crea il blocco `resetta rana`**

Nello sprite **Rana**, vai in **I miei blocchi** e clicca **Crea un blocco**.

Nome consigliato:

- `resetta rana`

Dentro il blocco puoi mettere:

```text
definisci resetta rana
vai a x: (0) y: (-150)
porta [tempo rimasto v] a (20)
mostra
azzera effetti grafici
```

Adesso, invece di riscrivere questi blocchi in più punti, puoi richiamare direttamente:

```text
resetta rana
```

---

**Passo 2 — Crea il blocco `perdi una vita`**

Puoi creare un altro blocco:

```text
definisci perdi una vita
cambia [vite v] di (-1)
resetta rana
```

E poi usarlo in:

- collisione con auto
- caduta in acqua
- tempo scaduto
- serpente
- coccodrillo

In questo modo il progetto diventa molto più ordinato.

---

**Passo 3 — Crea il blocco `game over`**

Per esempio nello Stage:

```text
definisci game over
passa allo sfondo [game over v]
dire (unisci [Punti finali: ] (punteggio)) per (3) secondi
```

Poi, nel controllo delle vite:

```text
se <(vite) < (1)> allora
  game over
  ferma [tutti v]
```

---

## 14.3 — Blocchi con parametri

### 📖 Introduzione teorica

Un blocco personalizzato diventa ancora più potente quando accetta **parametri**, cioè valori da inserire ogni volta in modo diverso.

Esempio:

- `crea auto (corsia) (velocità) (direzione)`
- `crea tronco (y) (velocità)`

Così non serve avere uno script separato per ogni corsia.

### 🛠️ Passaggi guidati

**Passo 1 — Crea un blocco per generare auto**

Nello sprite **Auto**, crea un blocco personalizzato:

- `crea auto (y) (velocita) (direzione)`

Dentro puoi scrivere:

```text
definisci crea auto (y) (velocita) (direzione)
porta [corsia v] a (y)
porta [velocità v] a (velocita)
porta [direzione v] a (direzione)
se <(direzione) = (1)> allora
  vai a x: (-260) y: (y)
altrimenti
  vai a x: (260) y: (y)
crea clone di [me stesso v]
```

---

**Passo 2 — Richiama il blocco più volte**

Ora, invece di scrivere tre generatori quasi uguali, puoi fare:

```text
quando si clicca su 🚩
per sempre
  crea auto (-60) (4) (-1)
  attendi (2) secondi
```

e in un altro script:

```text
quando si clicca su 🚩
attendi (0.8) secondi
per sempre
  crea auto (-20) (6) (1)
  attendi (1.5) secondi
```

Il codice resta più corto e più leggibile.

---

**Passo 3 — Crea un blocco simile per i tronchi**

Per esempio:

- `crea tronco (y) (velocita) (direzione)`

Il principio è lo stesso.

> Una volta imparato questo schema, puoi riusarlo per quasi tutti gli elementi ripetuti del gioco.

---

## 14.4 — Il vantaggio dello "schermo disabilitato"

### 📖 Introduzione teorica

Quando crei un blocco personalizzato in Scratch, puoi attivare l'opzione:

- **esegui senza aggiornamento schermo**

In alcune traduzioni o spiegazioni viene chiamata anche **schermo disabilitato**.

Questa opzione è utile quando vuoi:

- preparare molti oggetti in un solo istante
- evitare piccoli lampeggiamenti
- costruire un livello in modo "invisibile", prima di mostrarlo

### 🛠️ Passaggi guidati

**Passo 1 — Crea il blocco `prepara livello`**

Nello Stage oppure in uno sprite organizzatore, crea:

- `prepara livello`

Se disponibile, attiva **esegui senza aggiornamento schermo**.

Dentro puoi mettere:

```text
definisci prepara livello
porta [tempo rimasto v] a (20)
porta [nidi pieni v] a (0)
resetta rana
```

e poi richiamare blocchi di generazione:

```text
crea auto ...
crea auto ...
crea tronco ...
crea tronco ...
```

---

**Passo 2 — Usalo all'avvio**

Per esempio:

```text
quando si clicca su 🚩
prepara livello
```

Questo trasforma l'avvio del gioco in un unico comando chiaro.

---

## 🎯 Mini Esercizio dell'Unità

> **Obiettivo:** Creare un blocco `prepara livello` che posiziona la rana, azzera il timer e avvia la generazione di auto e tronchi con un solo comando.

**Cosa deve funzionare alla fine:**

1. Hai creato almeno 2 blocchi personalizzati utili
2. Uno dei blocchi evita davvero una ripetizione di codice
3. Hai almeno un blocco con parametri
4. L'avvio del livello è più ordinato e leggibile

**Verifica il tuo lavoro:**

- [ ] Hai creato `resetta rana` oppure un blocco equivalente
- [ ] Hai creato un blocco che genera auto o tronchi con parametri
- [ ] Hai ridotto il numero di script quasi identici
- [ ] Il progetto resta funzionante dopo il refactoring

---

## 💡 Domande di Riflessione

---

**Domanda 1**
Perché i blocchi personalizzati sono utili?

a) Perché cambiano il colore dei costumi  
b) Perché permettono di riusare codice e dare nomi chiari a sequenze di azioni  
c) Perché sostituiscono tutte le variabili  
d) Perché eliminano i cloni

> *Risposta corretta: **b)** — I blocchi personalizzati rendono il progetto più ordinato e meno ripetitivo.*

---

**Domanda 2**
Che cos'è un parametro in un blocco personalizzato?

a) Un effetto grafico  
b) Un valore che il blocco riceve per lavorare in modi diversi  
c) Un tipo di sfondo  
d) Un messaggio automatico

> *Risposta corretta: **b)** — Un parametro rende il blocco flessibile e riutilizzabile.*

---

**Domanda 3**
Quale di questi è un buon candidato per un blocco personalizzato?

a) `resetta rana`  
b) `perdi una vita`  
c) `crea auto (y) (velocita) (direzione)`  
d) Tutti i precedenti

> *Risposta corretta: **d)** — Sono tutti esempi ottimi di logiche riutilizzabili.*

---

**Domanda 4** *(riflessione aperta)*
Nel tuo progetto quale parte del codice si ripete più spesso? Quale blocco personalizzato potrebbe renderla più chiara?

---

**Domanda 5** *(sfida)*
Prova a trasformare tutta la preparazione iniziale del gioco in due o tre blocchi ben nominati. Quali sceglieresti?

---

## 🔧 Tip & Tricks

> **Tip 1 — Dai nomi concreti ai blocchi**
> `resetta rana` è molto meglio di `blocco1`.

> **Tip 2 — Non creare blocchi troppo grandi**
> Un blocco deve rappresentare un'idea chiara, non fare "tutto".

> **Tip 3 — Refactoring graduale**
> Prendi prima un pezzo ripetuto e trasformalo in blocco. Poi passa al successivo.

> **Tip 4 — Parametri ben scelti**
> Se un blocco crea auto, i parametri più naturali sono corsia, velocità e direzione.

---

## 📋 Riepilogo dell'Unità

| Concetto | Cosa abbiamo imparato |
|----------|-----------------------|
| Blocco personalizzato | Procedura riutilizzabile con un nome chiaro |
| Astrazione | Trasformare dettagli ripetuti in un comando più generale |
| Parametri | Rendono i blocchi più flessibili |
| Refactoring | Riorganizzare il codice senza cambiare il comportamento |
| `prepara livello` | Esempio di blocco che organizza l'avvio del gioco |

**Verifica rapida:**
- [ ] Hai creato blocchi personalizzati
- [ ] Hai eliminato almeno una ripetizione inutile
- [ ] Hai usato almeno un blocco con parametri
- [ ] Il progetto è più leggibile di prima

---

## ➡️ Prossimo passo

Nella **Unità 15** useremo numeri casuali e regole di bilanciamento per generare livelli sempre diversi ma ancora giocabili.

---

*Mini Corso: Programmiamo con Scratch — Costruiamo Frogger! | Unità 14 di 19*
