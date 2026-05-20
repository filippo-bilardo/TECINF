# 13 — Nemici Avanzati, Bordi Mobili e Bonus Mosche

> **Concetto chiave:** interazioni complesse e operatori logici
> **Durata stimata:** 45–60 minuti
> **Prerequisiti:** Unità 12 completata — il gioco include già supporti dinamici e nemici con stati nel fiume

---

## Obiettivi dell'unità

Al termine di questa unità lo studente sarà in grado di:

- Aggiungere nuovi pericoli in zone prima considerate sicure
- Usare operatori logici come `e`, `o`, `non`
- Gestire casi complessi come la caduta oltre il bordo mentre la rana è su un tronco
- Inserire bonus facoltativi che aumentano il punteggio
- Combinare più regole diverse senza confondere la logica del gioco

---

## 13.1 — Serpenti nell'area sicura centrale

### 📖 Introduzione teorica

Finora l'area sicura centrale era un posto tranquillo. Ma nei giochi avanzati anche le zone di respiro possono nascondere un pericolo.

Un **serpente** è perfetto per questo scopo:

- si muove nell'erba o nell'area centrale
- non è sempre presente
- se tocca la rana, fa perdere una vita

### 🛠️ Passaggi guidati

**Passo 1 — Crea lo sprite Serpente**

1. Aggiungi uno sprite serpente
2. Rinominalo **Serpente**
3. Posizionalo nell'area sicura centrale

---

**Passo 2 — Dagli un movimento semplice**

Puoi usare:

```text
quando si clicca su 🚩
vai a x: (-180) y: (20)
per sempre
  cambia x di (4)
  se <(x posizione) > (220)> allora
    vai a x: (-220) y: (20)
```

oppure un movimento casuale se vuoi maggiore varietà.

---

**Passo 3 — Gestisci la collisione**

Nella Rana aggiungi:

```text
se <sta toccando [Serpente v] ?> allora
  cambia [vite v] di (-1)
  vai a x: (0) y: (-150)
```

Adesso una zona prima sicura diventa più interessante.

---

## 13.2 — Coccodrillo nei nidi

### 📖 Introduzione teorica

Un nido conquistato potrebbe non restare sicuro per sempre. In una versione avanzata, un **coccodrillo nei nidi** può trasformare di nuovo un obiettivo in una trappola.

Questo introduce una logica molto interessante:

- il nido sembra disponibile o occupato
- ma in alcuni momenti può essere pericoloso

### 🛠️ Idea di implementazione

Puoi creare uno sprite **CoccodrilloNido** che:

1. compare a intervalli casuali sopra un nido
2. resta visibile per pochi secondi
3. se la rana lo tocca, perde una vita

Script base:

```text
quando si clicca su 🚩
nascondi
per sempre
  attendi (numero a caso da 4 a 8) secondi
  vai a x: (...) y: (...)
  mostra
  attendi (2) secondi
  nascondi
```

Nella Rana:

```text
se <sta toccando [CoccodrilloNido v] ?> allora
  cambia [vite v] di (-1)
  vai a x: (0) y: (-150)
```

> Per una prima versione, va benissimo far apparire il coccodrillo sempre nello stesso nido.

---

## 13.3 — Caduta dal bordo su un tronco

### 📖 Introduzione teorica

Finora il bordo del fiume non era ancora trattato nel modo più realistico. In realtà, se un tronco trascina la rana oltre il bordo, la rana non dovrebbe fermarsi contro un muro invisibile: dovrebbe **cadere fuori dal campo**.

Questa è una logica più avanzata perché combina due fatti:

1. la rana è su un supporto
2. il supporto la porta in una zona non valida

### Operatori logici utili

In Scratch puoi usare:

- `e`
- `o`
- `non`

Per esempio:

```text
se <<tocca [Tronco]> e <(x posizione) > (230)>> allora
```

### 🛠️ Passaggi guidati

**Passo 1 — Controlla i bordi nel fiume**

Nella Rana puoi aggiungere:

```text
se <<<y posizione> > (50)> e <<(x posizione) > (235)> o <(x posizione) < (-235)>>> allora
  cambia [vite v] di (-1)
  vai a x: (0) y: (-150)
```

Questa logica dice:

- se la rana è nella zona alta del fiume
- e oltrepassa il bordo sinistro o destro
- allora perde una vita

---

**Passo 2 — Capisci perché è diverso dalla strada**

Nella strada il bordo fermava il personaggio.
Nel fiume, invece, il bordo può diventare una **caduta nel vuoto**.

Questo cambia la sensazione di gioco e rende il fiume più pericoloso.

---

## 13.4 — Mosche bonus

### 📖 Introduzione teorica

Non tutti i nuovi elementi devono essere negativi. Una **mosca bonus** è una ricompensa:

- compare in certe aree
- dura poco
- se la rana la raccoglie, ottiene punti extra

### 🛠️ Passaggi guidati

**Passo 1 — Crea lo sprite Mosca**

1. Aggiungi uno sprite mosca
2. Rinominalo **Mosca**
3. Nascondilo all'avvio

---

**Passo 2 — Falla comparire a intervalli**

Uno script semplice:

```text
quando si clicca su 🚩
nascondi
per sempre
  attendi (numero a caso da 5 a 10) secondi
  vai a x: (...) y: (...)
  mostra
  attendi (2) secondi
  nascondi
```

Puoi farla comparire:

- in un nido vuoto
- nell'area sicura centrale

---

**Passo 3 — Gestisci la raccolta**

Nella Rana:

```text
se <sta toccando [Mosca v] ?> allora
  cambia [punteggio v] di (200)
```

Per evitare raccolte multiple nella stessa comparsa, aggiungi anche:

```text
trasmetti [mosca-raccolta v]
```

e nello sprite Mosca:

```text
quando ricevo [mosca-raccolta v]
nascondi
```

---

## 🎯 Mini Esercizio dell'Unità

> **Obiettivo:** Implementare almeno 2 meccaniche avanzate, ad esempio serpenti + caduta dal bordo, oppure mosche + coccodrillo nei nidi.

**Cosa deve funzionare alla fine:**

1. È presente almeno un nuovo pericolo o bonus
2. La rana reagisce correttamente alle nuove regole
3. Hai usato almeno un operatore logico complesso
4. Il progetto resta leggibile e ordinato

**Verifica il tuo lavoro:**

- [ ] Hai aggiunto almeno 2 nuove meccaniche
- [ ] Almeno una usa `e`, `o` oppure `non`
- [ ] Almeno una modifica vite o punteggio
- [ ] Il comportamento è coerente con la zona del gioco

---

## 💡 Domande di Riflessione

---

**Domanda 1**
Perché un serpente nell'area sicura centrale rende il gioco più interessante?

a) Perché elimina le automobili  
b) Perché rompe una regola che il giocatore aveva dato per scontata  
c) Perché cambia il timer  
d) Perché sostituisce i tronchi

> *Risposta corretta: **b)** — Una zona non più completamente sicura obbliga il giocatore a restare attento.*

---

**Domanda 2**
Quale operatore logico è utile per controllare se la rana è nel fiume **e** oltre il bordo?

a) `non` da solo  
b) `e`  
c) `dire`  
d) `mostra`

> *Risposta corretta: **b)** — `e` combina due condizioni che devono essere vere insieme.*

---

**Domanda 3**
A cosa serve una mosca bonus?

a) A far perdere una vita  
b) A creare un obiettivo facoltativo che aumenta il punteggio  
c) A cambiare lo sfondo  
d) A sostituire i nidi

> *Risposta corretta: **b)** — È una ricompensa extra che arricchisce il gameplay.*

---

**Domanda 4** *(riflessione aperta)*
Tra serpenti, coccodrilli nei nidi e mosche bonus, quale meccanica aggiunge più tensione? Quale aggiunge più varietà?

---

**Domanda 5** *(sfida)*
Prova a far comparire la mosca solo in un nido vuoto e mai in un nido pieno. Quale informazione del gioco devi controllare?

---

## 🔧 Tip & Tricks

> **Tip 1 — Aggiungi una meccanica alla volta**
> Se ne aggiungi troppe insieme, diventa difficile capire quale blocco causa un problema.

> **Tip 2 — Usa messaggi per gli eventi speciali**
> `mosca-raccolta`, `game-over`, `livello-completato` aiutano a tenere ordinato il progetto.

> **Tip 3 — Tratta ogni zona in modo diverso**
> Strada, area sicura e fiume non devono seguire sempre le stesse regole.

> **Tip 4 — Gli operatori logici leggono meglio se pensi a voce alta**
> Prima formula la frase: "Se la rana è nel fiume e supera il bordo, allora perde". Poi trasformala in blocchi.

---

## 📋 Riepilogo dell'Unità

| Concetto | Cosa abbiamo imparato |
|----------|-----------------------|
| Serpente | Pericolo in una zona prima tranquilla |
| Coccodrillo nei nidi | Obiettivo che può tornare pericoloso |
| Bordi mobili del fiume | Caso avanzato di caduta oltre il campo |
| Mosca bonus | Ricompensa temporanea |
| Operatori logici | Combinano condizioni più complesse |

**Verifica rapida:**
- [ ] Hai aggiunto almeno due meccaniche avanzate
- [ ] Hai usato operatori logici
- [ ] Hai modificato vite o punteggio con le nuove regole
- [ ] Il gioco è più ricco senza diventare confuso

---

## ➡️ Prossimo passo

Nella **Unità 14** cominceremo a ripulire il progetto con i **blocchi personalizzati**, così il codice diventerà più riutilizzabile e più facile da mantenere.

---

*Mini Corso: Programmiamo con Scratch — Costruiamo Frogger! | Unità 13 di 19*
