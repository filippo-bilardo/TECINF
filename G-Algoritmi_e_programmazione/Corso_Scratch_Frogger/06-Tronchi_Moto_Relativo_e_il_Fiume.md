# 06 — Tronchi, Moto Relativo e il Fiume

> **Concetto chiave:** coordinate, piattaforme mobili e pericolo dell'acqua
> **Durata stimata:** 45–60 minuti
> **Prerequisiti:** Unità 5 completata — la rana riconosce le automobili come ostacoli e torna alla partenza quando viene colpita

---

## Obiettivi dell'unità

Al termine di questa unità lo studente sarà in grado di:

- Spiegare perché il fiume è una zona di pericolo
- Creare tronchi che scorrono sull'acqua
- Capire il concetto di **moto relativo**
- Far "trasportare" la rana da un tronco mentre lo sta toccando
- Gestire la caduta in acqua quando non c'è un tronco sotto la rana

---

## 6.1 — Il fiume: una zona di pericolo

### 📖 Introduzione teorica

Nella parte alta di Frogger c'è il **fiume**. A differenza della strada, qui il problema non è solo evitare un ostacolo: bisogna anche **restare su qualcosa che galleggia**.

Se la rana entra nella zona blu del fiume senza essere sopra un tronco, deve perdere il turno e tornare alla partenza.

Questa idea introduce una nuova logica:

- sulla strada il pericolo è **toccare qualcosa**
- nel fiume il pericolo può essere anche **non toccare niente di sicuro**

> 💡 **Idea chiave:** a volte in un gioco non conta solo evitare il nemico; conta anche trovare il supporto giusto.

---

## 6.2 — Creare i tronchi che scorrono sull'acqua

### 📖 Introduzione teorica

I tronchi si comportano in modo simile alle automobili:

- compaiono in una corsia
- si muovono orizzontalmente
- escono da un lato
- ricompaiono

Possiamo quindi riutilizzare molte idee dell'unità sulla clonazione.

### 🛠️ Passaggi guidati

**Passo 1 — Aggiungi uno sprite Tronco**

1. Clicca su **Scegli uno sprite**
2. Cerca `log`, `wood`, `barrel` oppure scegli un oggetto allungato che possa funzionare come tronco
3. Rinomina lo sprite in **Tronco**
4. Ridimensionalo in modo che sia chiaramente più lungo della rana

Se non trovi uno sprite adatto, puoi disegnarne uno semplice con un rettangolo marrone.

---

**Passo 2 — Trasforma il tronco originale in generatore**

Nello sprite **Tronco**, crea questo script:

```text
quando si clicca su 🚩
nascondi
```

Come per le automobili, il tronco originale resta nascosto e genera i cloni.

---

**Passo 3 — Crea lo script del clone**

Sempre nello sprite **Tronco**, aggiungi:

```text
quando vengo clonato
mostra
per sempre
  cambia x di (3)
  se <(x posizione) > (260)> allora
    elimina questo clone
```

In questo esempio i tronchi si muovono verso destra.

---

**Passo 4 — Genera almeno due corsie di tronchi**

Puoi partire con due corsie semplici:

**Corsia 1**

```text
quando si clicca su 🚩
per sempre
  vai a x: (-260) y: (80)
  crea clone di [me stesso]
  attendi (2.2) secondi
```

**Corsia 2**

```text
quando si clicca su 🚩
attendi (1.1) secondi
per sempre
  vai a x: (-260) y: (120)
  crea clone di [me stesso]
  attendi (2.2) secondi
```

Adatta i valori `y` alle fasce blu del tuo sfondo.

> Per ora vanno bene due corsie. Potrai aggiungerne una terza quando il sistema funzionerà bene.

---

## 6.3 — La rana sale sul tronco: il moto relativo

### 📖 Introduzione teorica

Ora arriva il concetto più importante dell'unità: il **moto relativo**.

Se la rana è ferma rispetto al tronco ma il tronco si muove, allora anche la rana deve spostarsi insieme a lui. Dal punto di vista del palcoscenico, la rana non è davvero ferma: viene trasportata.

In pratica:

- se la rana tocca un tronco
- e il tronco si muove verso destra
- allora anche la rana deve fare un piccolo `cambia x di (3)`

### 🛠️ Passaggi guidati

**Passo 1 — Aggiungi un controllo continuo nella Rana**

Nello sprite **Rana**, crea o amplia un ciclo `per sempre` con questo controllo:

```text
quando si clicca su 🚩
per sempre
  se <sta toccando [Tronco v] ?> allora
    cambia x di (3)
```

Questo fa "scivolare" la rana insieme al tronco.

### Perché funziona?

Perché il blocco controlla continuamente se la rana è sopra un clone dello sprite **Tronco**. Se sì, la sposta nella stessa direzione e con la stessa velocità del tronco.

---

**Passo 2 — Allinea la velocità**

Se nel clone del tronco hai usato:

```text
cambia x di (3)
```

allora anche nella rana devi usare `cambia x di (3)`.

Se i due valori non coincidono:

- la rana scivolerà via dal tronco
- oppure sembrerà muoversi troppo velocemente

> Il moto relativo funziona bene solo se i due spostamenti sono coerenti.

---

**Passo 3 — Prova il trasporto**

Avvia il progetto e porta la rana sopra un tronco.

Dovresti osservare questo comportamento:

1. la rana resta sopra il tronco
2. si sposta con lui verso destra
3. se salta giù, smette di essere trasportata

Questo è uno dei meccanismi più caratteristici di Frogger.

---

## 6.4 — Cadere in acqua

### 📖 Introduzione teorica

Ora il gioco deve distinguere due situazioni diverse nel fiume:

| Situazione | Conseguenza |
|------------|-------------|
| Rana nel fiume e sopra un tronco | Sopravvive |
| Rana nel fiume ma non sopra un tronco | Cade in acqua |

Per fare questo possiamo usare il colore dello sfondo oppure una zona del palcoscenico riconoscibile come acqua.

Il controllo più semplice è:

```text
se <sta toccando il colore [blu acqua]> allora
```

Ma attenzione: se la rana tocca anche un tronco, non deve morire. Quindi serve combinare i controlli con attenzione.

### 🛠️ Passaggi guidati

**Passo 1 — Individua il blu del fiume**

Vai nello sfondo e controlla quale tonalità di blu hai usato nelle corsie del fiume.

Nello sprite **Rana**, scegli quel colore nel blocco:

```text
sta toccando il colore [ ]
```

---

**Passo 2 — Aggiungi il controllo acqua**

Nel ciclo della Rana, inserisci questa logica:

```text
quando si clicca su 🚩
per sempre
  se <sta toccando [Tronco v] ?> allora
    cambia x di (3)
  se <<sta toccando il colore [blu acqua] ?> e <non <sta toccando [Tronco v] ?>>> allora
    vai a x: (0) y: (-150)
```

### Cosa significa

- se la rana è sul tronco, viene trasportata
- se la rana tocca l'acqua **e non** tocca il tronco, allora cade

Questa è una condizione composta, un po' più avanzata delle precedenti.

---

**Passo 3 — Aggiungi un effetto di caduta**

Come per la collisione con le auto, anche qui è utile far capire al giocatore cosa è successo.

Puoi usare una versione come questa:

```text
se <<sta toccando il colore [blu acqua] ?> e <non <sta toccando [Tronco v] ?>>> allora
  effetto fantasma a (70)
  attendi (0.2) secondi
  azzera effetti grafici
  vai a x: (0) y: (-150)
```

Se preferisci, puoi usare un messaggio come:

```text
dire [Splash!] per (0.3) secondi
```

---

**Passo 4 — Controlla il bordo del fiume**

Se il tronco porta la rana molto vicino al bordo destro, osserva cosa succede.

Per questa unità puoi mantenere una regola semplice:

- la rana si muove insieme al tronco
- se scende dal tronco e tocca l'acqua, perde

Il caso in cui il tronco trascina la rana oltre il bordo verrà raffinato più avanti. Per ora l'obiettivo è far funzionare bene il fiume.

---

## 🎯 Mini Esercizio dell'Unità

> **Obiettivo:** La rana galleggia sui tronchi e cade in acqua se non è appoggiata a un tronco.

**Cosa deve funzionare alla fine:**

1. Esiste almeno uno sprite **Tronco** che genera cloni
2. I tronchi scorrono in almeno due corsie del fiume
3. Se la rana tocca un tronco, viene trasportata con lui
4. Se la rana entra nella zona blu senza tronco, torna alla partenza
5. Il comportamento del fiume è diverso da quello della strada

**Verifica il tuo lavoro:**

- [ ] Lo sprite **Tronco** usa `quando vengo clonato`
- [ ] I cloni dei tronchi si muovono orizzontalmente
- [ ] La Rana contiene `se <sta toccando [Tronco] ?> allora`
- [ ] La Rana contiene un controllo su `sta toccando il colore [blu acqua]`
- [ ] La rana sopravvive sul tronco ma non nell'acqua libera

---

## 💡 Domande di Riflessione

---

**Domanda 1**
Perché il fiume è diverso dalla strada?

a) Perché è disegnato in blu  
b) Perché nel fiume non basta evitare un ostacolo: bisogna anche restare su un supporto sicuro  
c) Perché i tronchi non possono usare cloni  
d) Perché la rana non può saltare nel fiume

> *Risposta corretta: **b)** — Nel fiume il pericolo dipende anche dall'assenza di un appoggio sicuro.*

---

**Domanda 2**
Cosa significa **moto relativo** in questa unità?

a) La rana cambia costume mentre nuota  
b) La rana si muove insieme al tronco quando lo sta toccando  
c) I tronchi compaiono in corsie diverse  
d) Le auto si muovono più lentamente

> *Risposta corretta: **b)** — La rana viene trasportata dal tronco e quindi si sposta con lui.*

---

**Domanda 3**
Quando la rana deve cadere in acqua?

a) Sempre quando entra nella parte alta dello schermo  
b) Quando tocca il blu del fiume e non tocca nessun tronco  
c) Solo quando preme la freccia giù  
d) Quando tocca il bordo sinistro

> *Risposta corretta: **b)** — La condizione corretta combina acqua + assenza di tronco.*

---

**Domanda 4** *(riflessione aperta)*
Se un tronco si muove più velocemente, quali parti del codice devi aggiornare perché la rana continui a restare sopra senza scivolare via?

---

**Domanda 5** *(sfida)*
Prova ad aggiungere una terza corsia di tronchi che si muova in direzione opposta. Quali blocchi cambieresti nello script del clone e nello script della Rana?

---

## 🔧 Tip & Tricks

> **Tip 1 — Parti da un solo tipo di tronco**
> Prima fai funzionare bene un tronco semplice. Solo dopo aggiungi corsie extra o velocità diverse.

> **Tip 2 — Scegli con attenzione il blu dell'acqua**
> Se selezioni il colore sbagliato, la rana potrebbe non cadere mai oppure morire anche fuori dal fiume.

> **Tip 3 — Mantieni sincronizzati tronco e rana**
> Se il tronco usa `cambia x di (3)`, anche il trasporto della rana deve usare `3`.

> **Tip 4 — Controlla l'ordine mentale della logica**
> Prima chiediti: "La rana è su un tronco?". Poi: "Sta toccando l'acqua senza supporto?". Pensare nell'ordine giusto aiuta a non confondere le condizioni.

---

## 📋 Riepilogo dell'Unità

| Concetto | Cosa abbiamo imparato |
|----------|-----------------------|
| Fiume | Zona di pericolo in cui serve un supporto sicuro |
| Tronco | Piattaforma mobile che trasporta la rana |
| Moto relativo | La rana si sposta insieme al tronco se lo sta toccando |
| Colore dell'acqua | Serve per riconoscere la zona pericolosa |
| Condizione composta | Unisce più controlli, come acqua + non tronco |
| Caduta in acqua | Avviene quando la rana è nel fiume senza appoggio |

**Verifica rapida:**
- [ ] Hai creato i tronchi con i cloni
- [ ] La rana viene trasportata dai tronchi
- [ ] Hai distinto acqua sicura e acqua pericolosa
- [ ] La rana cade in acqua se non c'è un tronco sotto

---

## ➡️ Prossimo passo

Nella **Unità 7** aggiungeremo i nidi in cima al campo e la logica per completare il livello quando la rana raggiunge tutti gli obiettivi.

---

*Mini Corso: Programmiamo con Scratch — Costruiamo Frogger! | Unità 6 di 11*
