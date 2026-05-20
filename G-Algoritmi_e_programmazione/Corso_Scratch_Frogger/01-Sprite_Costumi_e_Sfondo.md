# 01 — Sprite, Costumi e Sfondo

> **Concetto chiave:** oggetti grafici e ambienti visivi
> **Durata stimata:** 45–60 minuti
> **Prerequisiti:** Unità 0 completata — il progetto Frogger è stato creato e salvato

---

## Obiettivi dell'unità

Al termine di questa unità lo studente sarà in grado di:

- Spiegare cos'è uno **sprite** e qual è la differenza tra sprite e sfondo
- Importare o disegnare lo sprite della rana protagonista
- Creare un campo di gioco con strada, fiume e aree sicure
- Aggiungere **costumi** diversi per simulare il movimento della rana
- Posizionare correttamente lo sprite sulla posizione di partenza

---

## 1.1 — Cos'è uno sprite? Differenza tra sprite e sfondo

### 📖 Introduzione teorica

In Scratch, tutto ciò che si muove, cambia aspetto o interagisce è uno **sprite**. Uno sprite è un oggetto grafico a cui si può associare del codice.

Lo **sfondo** (o "stage background") invece è l'immagine di sottofondo che non si muove e non ha un proprio codice (anche se lo stage stesso può avere script per gestire eventi globali).

**Confronto sprite vs. sfondo:**

| Caratteristica | Sprite | Sfondo |
|----------------|--------|--------|
| Si può muovere | ✅ Sì | ❌ No |
| Ha codice associato | ✅ Sì | ⚠️ Solo lo stage, non i singoli sfondi |
| Può cambiare costume | ✅ Sì | ✅ Sì (cambio di sfondo) |
| Può toccare altri sprite | ✅ Sì | ❌ No |
| Esempi | Personaggi, nemici, oggetti | Paesaggi, sfondi menu, sfondi livelli |

> 💡 **Analogia teatrale:** Pensa al palcoscenico come a un teatro. Lo **sfondo** è la scenografia dipinta sul fondale (montagne, città, interno di una casa). Gli **sprite** sono gli attori che si muovono davanti alla scenografia ed eseguono le azioni.

### Sprite multipli

Un progetto Scratch può avere **molti sprite** contemporaneamente. Nel nostro Frogger avremo:
- La rana (protagonista)
- Le automobili (nemici)
- I tronchi (piattaforme mobili)

Ogni sprite ha il suo codice separato, ma gli sprite possono interagire tra loro (ad esempio: "la rana tocca un'auto?" → Game Over).

---

## 1.2 — Importare o disegnare la rana protagonista

### 📖 Introduzione teorica

Ci sono tre modi per ottenere uno sprite in Scratch:

1. **Scegliere dalla libreria** — Scratch ha centinaia di sprite pronti
2. **Disegnare** — Usare l'editor integrato per creare sprite personalizzati
3. **Caricare da file** — Importare immagini dal computer

Per questo corso useremo il modo più semplice: **scegliere dalla libreria**. Se ti piace disegnare, nella sezione finale ti mostrerò come personalizzare la rana!

### 🛠️ Passaggi guidati

**Passo 1 — Apri il selettore di sprite**

1. Assicurati di essere nel progetto "Frogger - Corso"
2. In basso a destra, nell'area degli sprite, clicca sull'icona **Scegli uno sprite** (il gatto con il simbolo +)
3. Si aprirà una finestra con la libreria degli sprite

---

**Passo 2 — Cerca la rana**

1. Nella barra di ricerca in alto, digita **"frog"** (o "rana" se usi la versione italiana)
2. Dovresti vedere almeno uno sprite che rappresenta una rana
3. Se non trovi una rana che ti piace, puoi cercare anche "amphibian" o semplicemente scorri tra gli animali

> Se Scratch non ha una rana nella tua versione, puoi usare temporaneamente un altro sprite (come una tartaruga o un altro animale) e sostituirlo in seguito.

---

**Passo 3 — Seleziona lo sprite**

1. Clicca sulla rana che ti piace
2. Lo sprite appare nel palcoscenico e nella lista degli sprite in basso
3. Noterai che lo sprite è selezionato (bordo blu intorno alla miniatura)

---

**Passo 4 — Rinomina lo sprite**

È buona pratica dare nomi significativi agli sprite, soprattutto quando ne hai molti.

1. Sopra l'area dei blocchi c'è un campo di testo con il nome dello sprite (ad esempio "Frog1")
2. Cancella il nome e scrivi **"Rana"**
3. Premi Invio

Ora il tuo sprite si chiama "Rana" — molto più chiaro quando dovrai scriverci il codice!

---

**Passo 5 — Imposta la dimensione**

La rana potrebbe essere troppo grande o troppo piccola rispetto al campo di gioco. Regoliamo le dimensioni.

1. Sotto il campo del nome dello sprite c'è un campo **"Dimensione"** con un numero (di default è 100, che significa 100% della dimensione originale)
2. Prova a impostare **60** (60% dell'originale)
3. Guarda il palcoscenico — se la rana è ancora troppo grande o troppo piccola, aggiusta il valore

> Il valore giusto dipende dalla dimensione dello sfondo che creerai. Per ora 60 è un buon punto di partenza — potrai modificarlo in seguito.

---

## 1.3 — Creare il campo di gioco: strada, fiume, area sicura

### 📖 Introduzione teorica

Il campo di gioco di Frogger è diviso in **fasce orizzontali**:

```
┌─────────────────────────────────────────┐
│  🏁  Zona sicura (meta) — verde         │ ← fascia superiore
├─────────────────────────────────────────┤
│  🌊  Fiume — blu                        │ ← 3 fasce (tronchi)
│  🌊  Fiume — blu                        │
│  🌊  Fiume — blu                        │
├─────────────────────────────────────────┤
│  💚  Area sicura — verde                │ ← fascia centrale
├─────────────────────────────────────────┤
│  🛣️  Strada — grigio                    │ ← 3 fasce (auto)
│  🛣️  Strada — grigio                    │
│  🛣️  Strada — grigio                    │
├─────────────────────────────────────────┤
│  🌱  Partenza — verde chiaro            │ ← fascia inferiore
└─────────────────────────────────────────┘
```

Creeremo questo sfondo usando l'**editor grafico integrato** di Scratch. È semplice: basta disegnare rettangoli colorati!

### 🛠️ Passaggi guidati

**Passo 1 — Apri l'editor degli sfondi**

1. In basso a destra, clicca sull'icona **Sfondi** (il rettangolo bianco accanto agli sprite)
2. Se c'è già uno sfondo, clicca sul pulsante **Dipingi** (icona del pennello) in alto a sinistra per crearne uno nuovo
3. Si apre l'editor grafico

L'editor ha due modalità:
- **Bitmap** — disegno a pixel (come Paint)
- **Vettoriale** — disegno con forme geometriche (consigliato)

Assicurati di essere in modalità **Vettoriale** (se vedi scritto "Converti in vettoriale" in basso, cliccaci sopra).

---

**Passo 2 — Prepara gli strumenti**

1. Nella barra degli strumenti a sinistra, seleziona lo strumento **Rettangolo** (icona del quadrato)
2. In alto seleziona:
   - **Riempimento:** attivato (icona del secchiello piena)
   - **Contorno:** disattivato (icona del bordo con una barra sopra)

Ora sei pronto per disegnare!

---

**Passo 3 — Disegna lo sfondo fascia per fascia**

Disegneremo il campo dall'alto verso il basso, una fascia alla volta.

**Fascia 1 — Zona sicura superiore (meta)**

1. Scegli un colore **verde scuro** dalla palette
2. Disegna un rettangolo che copre tutta la larghezza del canvas e circa 1/8 dell'altezza, partendo dall'alto
3. Non preoccuparti della precisione — puoi regolare in seguito

**Fascia 2-4 — Fiume (3 corsie)**

1. Scegli un colore **blu** (tipo acqua)
2. Disegna un grande rettangolo che copre circa 3/8 dell'altezza, subito sotto la fascia verde
3. Opzionale: per distinguere le corsie, disegna sottili linee orizzontali azzurre più chiare all'interno

**Fascia 5 — Area sicura centrale**

1. Scegli un colore **verde medio**
2. Disegna un rettangolo che copre circa 1/8 dell'altezza, sotto il fiume

**Fascia 6-8 — Strada (3 corsie)**

1. Scegli un colore **grigio scuro** (asfalto)
2. Disegna un rettangolo che copre circa 3/8 dell'altezza, sotto l'area verde
3. Opzionale: disegna linee tratteggiate bianche o gialle per simulare le corsie

**Fascia 9 — Partenza**

1. Scegli un colore **verde chiaro**
2. Disegna l'ultimo rettangolo che copre la parte inferiore rimasta

---

**Passo 4 — Regola e perfeziona**

1. Usa lo strumento **Selezione** (freccia) per spostare o ridimensionare i rettangoli
2. Assicurati che non ci siano spazi bianchi tra le fasce
3. Se serve, usa lo strumento **Riempi** (secchiello) per colorare eventuali buchi

> Non serve che sia perfetto! L'importante è che si distinguano chiaramente le zone: fiume (blu), strada (grigio), aree sicure (verde).

---

**Passo 5 — Salva e nomina lo sfondo**

1. In alto a sinistra, nel campo di testo, scrivi il nome **"Campo di gioco"**
2. Il tuo sfondo è salvato automaticamente

Torna al palcoscenico: dovresti vedere il campo di gioco completo con la rana sopra!

---

## 1.4 — Aggiungere costumi per simulare il movimento della rana

### 📖 Introduzione teorica

I **costumi** sono le diverse "versioni grafiche" di uno sprite. Cambiando costume, si crea l'illusione del movimento (come nei cartoni animati).

Per la rana, vogliamo almeno **4 costumi** che rappresentano le quattro direzioni:
- Rana vista dall'alto (rivolta verso l'alto)
- Rana vista dal basso (rivolta verso il basso)
- Rana vista da sinistra
- Rana vista da destra

Se lo sprite che hai scelto ha già questi costumi, puoi saltare questa sezione. Altrimenti, ecco come crearli!

### 🛠️ Passaggi guidati

**Passo 1 — Controlla i costumi esistenti**

1. Assicurati che lo sprite "Rana" sia selezionato
2. In alto al centro, clicca sulla scheda **Costumi** (accanto a "Codice" e "Suoni")
3. Vedrai una lista dei costumi disponibili per questo sprite

Se lo sprite ha già 4 costumi che rappresentano le quattro direzioni, sei fortunato — passa direttamente al punto 1.5!

Altrimenti, continua con i passi seguenti.

---

**Passo 2 — Duplica il costume base**

Partiremo dal costume esistente e lo modificheremo.

1. Fai clic destro sul costume nella lista
2. Seleziona **Duplica**
3. Ripeti 3 volte — ora hai 4 copie del costume

---

**Passo 3 — Ruota i costumi**

Per ogni costume, ruoteremo la rana in una direzione diversa.

1. Seleziona il secondo costume
2. Usa lo strumento **Ruota** (icona di rotazione circolare) o manualmente seleziona tutto e ruota di 90° verso sinistra
3. Ripeti per il terzo costume (180°) e il quarto (270°)

Ora hai quattro costumi della rana, ognuno rivolto in una direzione!

> Se il tuo sprite non si presta bene alla rotazione (ad esempio ha già una direzione fissa), puoi usare l'editor per ridisegnare manualmente gli occhi o le zampe in modo che sembrino guardare nelle diverse direzioni.

---

**Passo 4 — Rinomina i costumi (opzionale ma consigliato)**

1. Clicca sul campo di testo sopra ogni costume e rinominali:
   - Costume 1: **"su"** (rivolta verso l'alto)
   - Costume 2: **"destra"**
   - Costume 3: **"giù"**
   - Costume 4: **"sinistra"**

Questo renderà più facile richiamarli dal codice nelle prossime unità.

---

**Versione semplificata (se non vuoi creare 4 costumi)**

Se preferisci concentrarti sulla programmazione e non sulla grafica, puoi anche usare un solo costume e fare ruotare lo sprite dal codice. Lo vedremo nell'Unità 2.

Per ora, anche un solo costume va bene per procedere!

---

## 1.5 — Posizionare la rana nella posizione di partenza

### 📖 Introduzione teorica

In Scratch, ogni sprite ha una **posizione** definita da due coordinate:
- **x**: posizione orizzontale (da -240 a sinistra a +240 a destra)
- **y**: posizione verticale (da -180 in basso a +180 in alto)

Il punto (0, 0) è al centro del palcoscenico.

Per Frogger, la rana deve partire dal centro-basso del campo di gioco, sulla fascia verde di partenza.

### 🛠️ Passaggi guidati

**Passo 1 — Sposta la rana manualmente**

1. Torna alla scheda **Codice** dello sprite Rana
2. Trascina la rana con il mouse sul palcoscenico fino alla posizione di partenza (centro-basso, sulla fascia verde chiara)

Mentre la trascini, nota che nell'area delle proprietà dello sprite (sotto il nome) i valori di **x** e **y** cambiano in tempo reale.

---

**Passo 2 — Annota le coordinate**

Una volta posizionata la rana dove vuoi che inizi, leggi i valori di **x** e **y** dalle proprietà dello sprite.

Esempio:
- x: 0 (centro)
- y: -150 (vicino al bordo inferiore, ma non troppo)

Scrivi questi valori su un foglio o ricordali — li useremo nel prossimo passo.

---

**Passo 3 — Crea lo script di inizializzazione**

Ora faremo in modo che ogni volta che si clicca sulla bandiera verde 🚩, la rana torni in quella posizione.

1. Vai nella categoria **Situazioni** (gialla) e trascina il blocco:
   ```
   quando si clicca su 🚩
   ```
2. Vai nella categoria **Movimento** (azzurra) e trascina sotto:
   ```
   vai a x: (0) y: (-150)
   ```
3. Modifica i valori di x e y con le coordinate che hai annotato
4. Aggancia i due blocchi insieme

Ora hai il tuo primo script funzionante! 🎉

---

**Passo 4 — Testa lo script**

1. Sposta la rana in un punto qualsiasi del palcoscenico trascinandola con il mouse
2. Clicca sulla bandiera verde 🚩 in alto al palcoscenico
3. La rana dovrebbe "saltare" istantaneamente nella posizione di partenza

Se funziona, complimenti — hai appena scritto il primo pezzo di codice del gioco!

---

**Passo 5 (opzionale) — Imposta lo stile di rotazione**

Se hai creato i costumi per le diverse direzioni, non vuoi che la rana **ruoti** quando si muove — vuoi che **cambi costume**.

1. Sotto il nome dello sprite, c'è una sezione **"Direzione"** con un'icona circolare
2. Clicca sull'icona finché non vedi il simbolo che indica **"non ruotare"** (un punto fisso)
3. Ora la rana non ruoterà mai automaticamente — useremo i costumi per cambiare direzione

Se invece hai un solo costume e vuoi che la rana ruoti verso la direzione del movimento, lascia l'impostazione su **"ruota completamente"** o **"ruota sinistra-destra"**.

---

## 🎯 Mini Esercizio dell'Unità

> **Obiettivo:** La rana appare nella posizione di partenza su un campo di gioco chiaramente diviso in zone (strada, fiume, aree sicure).

**Cosa deve funzionare alla fine:**

1. Il campo di gioco ha almeno tre zone visivamente distinte: strada (grigio), fiume (blu), aree verdi
2. Lo sprite della rana è presente e ha dimensioni proporzionate al campo
3. Cliccando la bandiera verde 🚩, la rana si posiziona nella zona di partenza
4. (Opzionale) La rana ha 4 costumi per le 4 direzioni

**Verifica il tuo lavoro:**

Guarda l'area degli sprite:
- [ ] C'è uno sprite chiamato "Rana"
- [ ] La rana ha almeno 1 costume (idealmente 4)

Guarda il palcoscenico:
- [ ] Lo sfondo mostra chiaramente strada, fiume e zone sicure
- [ ] La rana parte dalla fascia verde in basso

Guarda il codice:
- [ ] C'è 1 script che inizia con `quando si clicca su 🚩` e posiziona la rana

---

## 💡 Domande di Riflessione

---

**Domanda 1**
Qual è la differenza principale tra uno sprite e uno sfondo?

a) Lo sprite è colorato, lo sfondo è in bianco e nero
b) Lo sprite può muoversi ed eseguire codice, lo sfondo è fisso
c) Non c'è differenza, sono la stessa cosa
d) Lo sfondo è più grande dello sprite

> *Risposta corretta: **b)** — Gli sprite sono oggetti attivi con codice associato; lo sfondo è statico e non ha codice (tranne lo stage stesso).*

---

**Domanda 2**
Quanti costumi può avere uno sprite?

a) Solo 1
b) Massimo 4
c) Illimitati (dipende dalla memoria)
d) Uno per ogni direzione (4 in totale)

> *Risposta corretta: **c)** — Uno sprite può avere un numero illimitato di costumi. Il limite pratico dipende dalla memoria del computer.*

---

**Domanda 3**
Se la rana ha coordinate x: 0 e y: -150, dove si trova?

a) In alto a sinistra
b) Al centro in basso
c) In basso a sinistra
d) Al centro esatto del palcoscenico

> *Risposta corretta: **b)** — x: 0 significa centro orizzontale, y: -150 significa basso (i valori y negativi sono verso il basso).*

---

**Domanda 4** *(riflessione aperta)*
Se dovessi aggiungere un ostacolo aggiuntivo al gioco (ad esempio serpenti nell'erba), creeresti uno **sprite** o lo disegneresti direttamente sullo **sfondo**? Perché?

> *Risposta suggerita: Uno sprite, perché deve muoversi e interagire con la rana (rilevamento collisioni). Gli elementi statici puramente decorativi possono stare nello sfondo.*

---

**Domanda 5** *(sfida)*
Prova a modificare il campo di gioco aggiungendo una quinta corsia di strada o una quarta corsia di fiume. Di quanto dovresti modificare le dimensioni delle altre fasce per mantenere tutto visibile?

---

## 🔧 Tip & Tricks

> **Tip 1 — Copia-incolla gli sprite**
> Se devi creare più sprite simili (ad esempio più auto), puoi duplicare uno sprite esistente: clic destro sullo sprite → Duplica. Poi modifichi solo i dettagli (colore, dimensione, velocità).

> **Tip 2 — Centro del costume**
> Ogni costume ha un "centro" (il puntino + nell'editor). Quando ruoti o posizioni uno sprite, Scratch usa quel punto come riferimento. Se il tuo sprite sembra "saltare" o ruotare male, regola il centro del costume nell'editor.

> **Tip 3 — Livelli degli sprite**
> Gli sprite hanno un ordine di sovrapposizione ("layer"). Se uno sprite passa dietro un altro quando non dovrebbe, usa i blocchi `porta in primo piano` o `vai indietro di 1 livelli` nella categoria "Aspetto".

> **Tip 4 — Sfondo ridimensionato**
> Se il campo di gioco non copre tutto il palcoscenico, puoi ridimensionarlo nell'editor degli sfondi usando lo strumento Selezione e trascinando gli angoli.

> **Tip 5 — Griglia e guide**
> Nell'editor grafico, puoi attivare una griglia per allineare meglio le forme. Non è sempre disponibile in tutte le versioni, ma se vedi l'opzione, usala per rendere le fasce perfettamente uniformi!

---

## 📋 Riepilogo dell'Unità

| Concetto | Cosa abbiamo imparato |
|----------|-----------------------|
| Sprite | Oggetto grafico con codice associato; può muoversi e interagire |
| Sfondo | Immagine di sottofondo statica che definisce l'ambiente |
| Costumi | Varianti grafiche di uno sprite per creare animazioni o direzioni diverse |
| Coordinate x, y | Sistema di riferimento per posizionare sprite nel palcoscenico |
| Script di inizializzazione | Codice con evento `quando si clicca su 🚩` per resettare il gioco |

**Verifica rapida:**
- [ ] Sai spiegare la differenza tra sprite e sfondo
- [ ] Hai creato lo sprite della rana e il campo di gioco
- [ ] La rana ha almeno un costume (idealmente 4 per le direzioni)
- [ ] Cliccando la bandiera verde, la rana va in posizione di partenza

---

## ➡️ Prossimo passo

Nella **Unità 2** daremo vita alla rana! Impareremo a usare gli **eventi** per rispondere ai tasti freccia e faremo muovere la rana in tutte e quattro le direzioni.

---

*Mini Corso: Programmiamo con Scratch — Costruiamo Frogger! | Unità 1 di 11*
