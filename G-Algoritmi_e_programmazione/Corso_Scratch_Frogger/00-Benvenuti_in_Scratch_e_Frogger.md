# 00 — Benvenuti in Scratch e nel mondo di Frogger

> **Concetto chiave:** orientamento nell'ambiente di sviluppo e comprensione del progetto
> **Durata stimata:** 30–45 minuti
> **Prerequisiti:** Nessuno — questa è la prima unità del corso

---

## Obiettivi dell'unità

Al termine di questa unità lo studente sarà in grado di:

- Riconoscere le principali aree dell'interfaccia di Scratch
- Spiegare le regole e l'obiettivo del gioco Frogger
- Identificare gli elementi principali del gioco (personaggio, ostacoli, obiettivo)
- Creare e salvare il primo progetto Scratch

---

## 0.1 — Cos'è Scratch? L'interfaccia in cinque minuti

### 📖 Introduzione teorica

**Scratch** è un linguaggio di programmazione visuale creato dal MIT per insegnare a programmare in modo intuitivo. Invece di scrivere codice con parole, si assemblano **blocchi colorati** come fossero mattoncini LEGO.

Ogni blocco rappresenta un comando: muovere un personaggio, emettere un suono, aspettare un certo tempo. I blocchi si incastrano tra loro, e il programma risultante viene eseguito dal computer.

Scratch è usato da milioni di studenti in tutto il mondo ed è completamente gratuito.

### Come accedere a Scratch

Hai due opzioni:

1. **Online** → Vai su [scratch.mit.edu](https://scratch.mit.edu) e clicca su "Crea" (serve una connessione internet)
2. **Offline** → Scarica l'editor da [scratch.mit.edu/download](https://scratch.mit.edu/download) (funziona senza internet)

Per questo corso andrà bene entrambe le soluzioni. Se sei a scuola e la connessione è lenta, l'editor offline è consigliato.

### L'interfaccia di Scratch in 5 aree

Quando apri Scratch, vedrai una schermata divisa in cinque zone principali:

```
┌─────────────────────────────────────────────────────────────┐
│  ① Barra degli strumenti (File, Modifica, Tutorial...)      │
├──────────────┬──────────────────────────┬───────────────────┤
│              │                          │                   │
│  ② Palcoscenico                         │  ③ Area degli     │
│     (qui si vede                        │     sprite        │
│      il gioco)                          │     (personaggi)  │
│              │                          │                   │
├──────────────┴──────────────────────────┤                   │
│  ④ Blocchi di codice                    │                   │
│     (divisi per categoria)              │                   │
│                                         │                   │
├─────────────────────────────────────────┤                   │
│  ⑤ Area degli script                    │                   │
│     (qui si assembla il codice)         │                   │
│                                         │                   │
└─────────────────────────────────────────┴───────────────────┘
```

**① Barra degli strumenti**
Serve per salvare, caricare, condividere il progetto.

**② Palcoscenico**
È lo "schermo" del gioco. Qui vedrai muoversi i personaggi e succedere le azioni. La bandierina verde 🚩 avvia il programma, lo stop ⏹ lo ferma.

**③ Area degli sprite**
Mostra tutti i personaggi e oggetti del progetto. Ogni sprite ha il suo codice separato.

**④ Blocchi di codice**
I mattoncini disponibili, organizzati per **categoria** (Movimento, Aspetto, Suono, Controllo...). I colori aiutano a riconoscerli rapidamente.

**⑤ Area degli script**
Qui si trascinano e si collegano i blocchi per creare il programma. Ogni sprite ha la sua area degli script.

### 🛠️ Esercizio pratico (5 minuti)

1. Apri Scratch (online o offline)
2. Nota il gatto arancione al centro del palcoscenico — è lo sprite predefinito
3. Clicca su **"Movimento"** (azzurro) nell'area dei blocchi
4. Trascina il blocco `fai 10 passi` nell'area degli script
5. Fai clic sul blocco — il gatto si muove!
6. Trascina il blocco `ruota di 15 gradi ↻` e fai clic — il gatto ruota!

Congratulazioni, hai appena eseguito il tuo primo codice in Scratch! 🎉

---

## 0.2 — Cos'è Frogger? Analisi del gioco

### 📖 Introduzione teorica

**Frogger** è un videogioco arcade del 1981. L'obiettivo è semplice ma sfidante: guidare una rana attraverso una strada trafficata e un fiume pericoloso per raggiungere la salvezza dall'altra parte.

Il gioco è uno dei classici della storia dei videogiochi ed è perfetto per imparare a programmare, perché combina molti concetti fondamentali in un formato divertente e accessibile.

### Le regole del gioco

**Obiettivo:** Portare la rana dalla parte bassa dello schermo alla zona sicura in alto, evitando le automobili sulla strada e salendo sui tronchi nel fiume.

**Ostacoli:**
- **Strada:** Automobili che si muovono orizzontalmente a velocità diverse
- **Fiume:** Tronchi che scorrono; la rana deve saltare su un tronco per non annegare

**Controlli:**
- Frecce direzionali (su, giù, sinistra, destra)
- La rana si muove "a scatti", una casella alla volta

**Vite e punteggio:**
- Si inizia con 3 vite
- Si perde una vita se:
  - La rana viene investita da un'auto
  - La rana cade in acqua (non è su un tronco)
  - Il tempo scade prima di raggiungere la meta
- Si guadagna punteggio ogni volta che la rana raggiunge la zona sicura

### Perché Frogger è perfetto per imparare a programmare?

| Elemento del gioco | Concetto di programmazione |
|--------------------|---------------------------|
| Movimento della rana | Eventi da tastiera |
| Automobili che attraversano | Cicli e clonazione |
| Collisione con le auto | Condizioni e rilevamento |
| Tronchi sul fiume | Movimento relativo |
| Vite e punteggio | Variabili |
| Timer | Gestione del tempo |

Ogni elemento del gioco è una piccola "lezione" su un concetto fondamentale della programmazione. Alla fine del corso avrai costruito un gioco completo e avrai imparato a programmare!

---

## 0.3 — Pianificare prima di scrivere codice

### 📖 Introduzione teorica

Prima di iniziare a programmare, è importante **pianificare**. I programmatori professionisti non si buttano subito a scrivere codice — prima si fanno uno schema di ciò che devono costruire.

Per il nostro Frogger, identifichiamo gli **elementi essenziali**:

### Schema del gioco

```
┌───────────────────────────────────────┐
│     🏁 ZONA SICURA (meta)             │
├───────────────────────────────────────┤
│  🪵 ← ← ← ← ← ← ← ← ←  Tronchi        │
│  🪵 → → → → → → → → →  Tronchi        │
│  🪵 ← ← ← ← ← ← ← ← ←  Tronchi        │
├───────────────────────────────────────┤
│     💚 AREA SICURA                    │
├───────────────────────────────────────┤
│  🚗 → → → → → → → → →  Auto veloci    │
│  🚙 ← ← ← ← ← ← ← ← ←  Auto medie     │
│  🚕 → → → → → → → → →  Auto lente     │
├───────────────────────────────────────┤
│            🐸 PARTENZA                │
└───────────────────────────────────────┘
```

### Elementi da creare

**Sprite necessari:**
1. **Rana** — il personaggio controllato dal giocatore
2. **Auto** — gli ostacoli sulla strada (diversi tipi a diverse velocità)
3. **Tronchi** — le piattaforme galleggianti sul fiume

**Sfondo:**
- Strada (asfalto grigio)
- Fiume (acqua blu)
- Zone sicure (erba verde)

**Variabili:**
- Vite
- Punteggio
- Timer (opzionale, per aumentare la difficoltà)

### Lista delle funzionalità (in ordine di sviluppo)

Durante il corso costruiremo il gioco passo per passo, in questo ordine:

1. ✅ Creare la rana e il campo di gioco
2. ✅ Muovere la rana con i tasti freccia
3. ✅ Animare le automobili che attraversano lo schermo
4. ✅ Creare più auto usando i cloni
5. ✅ Rilevare le collisioni (rana investita)
6. ✅ Aggiungere i tronchi sul fiume
7. ✅ Gestire vite e punteggio
8. ✅ Aggiungere il timer
9. ✅ Suoni ed effetti grafici
10. ✅ Livelli di difficoltà crescente

Questa lista è la nostra **roadmap** — torneremo a consultarla spesso per vedere a che punto siamo.

---

## 0.4 — Creare il primo progetto e salvarlo

### 🛠️ Passaggi guidati

**Passo 1 — Crea un nuovo progetto**

Se hai appena aperto Scratch, hai già un progetto vuoto pronto.

Se invece stavi lavorando a qualcos'altro:
1. Clicca su **File** → **Nuovo** nella barra degli strumenti
2. Se hai modifiche non salvate, Scratch ti chiederà se vuoi salvare — rispondi in base alle tue esigenze

---

**Passo 2 — Salva il progetto**

È importante salvare subito il progetto con un nome riconoscibile.

**Se usi Scratch online:**
1. Clicca su **File** → **Salva ora**
2. Scratch ti chiederà di fare login o creare un account (è gratuito)
3. Dai al progetto un nome come "Frogger - Corso"
4. Il progetto viene salvato automaticamente ogni pochi secondi

**Se usi Scratch offline:**
1. Clicca su **File** → **Salva nel computer**
2. Scegli dove salvare il file (ad esempio nella cartella "Documenti")
3. Dai al progetto un nome come "Frogger_Corso"
4. Il file verrà salvato con estensione `.sb3`

> ⚠️ **Importante:** Ricordati di salvare spesso! Se usi l'editor offline, premi Ctrl+S (Windows/Linux) o Cmd+S (Mac) ogni volta che completi un passo importante.

---

**Passo 3 — Elimina il gatto**

Lo sprite predefinito è un gatto, ma noi costruiremo Frogger — non ci serve!

1. Nell'area degli sprite in basso a destra, posiziona il cursore sopra il gatto
2. Clicca sull'icona del **cestino** 🗑 che appare in alto a destra dello sprite
3. Il gatto sparisce — il palcoscenico è vuoto

Non preoccuparti: nella prossima unità aggiungeremo la rana!

---

**Passo 4 — Aggiungi uno sfondo temporaneo (opzionale)**

Per dare un'idea di "campo di gioco", puoi aggiungere uno sfondo semplice.

1. In basso a destra, sotto l'area degli sprite, c'è l'icona **Sfondo** (rettangolo bianco)
2. Passa sopra con il mouse e clicca sull'icona **Scegli uno sfondo** (paesaggio con montagna)
3. Cerca "grass" o "strada" e scegline uno che ti piace
4. Oppure clicca su **Dipingi** per creare uno sfondo personalizzato (lo faremo in dettaglio nell'Unità 1)

Per ora va bene anche lasciare lo sfondo bianco — è solo un segnaposto.

---

**Passo 5 — Verifica il salvataggio**

1. Chiudi Scratch
2. Riaprilo
3. Vai su **File** → **Carica dal computer** (offline) oppure controlla **I miei progetti** (online)
4. Apri il progetto "Frogger - Corso"
5. Lo sfondo dovrebbe essere quello che hai scelto (o bianco se non ne hai scelto uno)

Se tutto funziona, sei pronto per la prossima unità! 🎉

---

## 💡 Domande di Riflessione

Rispondi a queste domande per consolidare ciò che hai imparato.

---

**Domanda 1**
Quali sono le cinque aree principali dell'interfaccia di Scratch?

a) Menù, Palcoscenico, Sprite, Codice, Variabili
b) File, Stage, Blocchi, Script, Costumi
c) Barra strumenti, Palcoscenico, Area sprite, Blocchi, Area script
d) Editor, Esecuzione, Debug, Condivisione, Help

> *Risposta corretta: **c)** — Barra degli strumenti, Palcoscenico (stage), Area degli sprite, Blocchi di codice, Area degli script.*

---

**Domanda 2**
Nel gioco Frogger, quando si perde una vita?

a) Solo quando la rana viene investita da un'auto
b) Solo quando la rana cade in acqua
c) Quando la rana esce dallo schermo
d) Quando la rana viene investita, cade in acqua, o il tempo scade

> *Risposta corretta: **d)** — Tutte e tre le condizioni fanno perdere una vita.*

---

**Domanda 3**
Perché è importante pianificare prima di programmare?

a) Perché altrimenti Scratch non funziona
b) Per avere un'idea chiara di cosa costruire e in che ordine
c) Perché lo fanno tutti i programmatori e bisogna imitarli
d) Per fare bella figura con l'insegnante

> *Risposta corretta: **b)** — Pianificare aiuta a organizzare il lavoro, identificare i problemi in anticipo e lavorare in modo più efficiente.*

---

**Domanda 4** *(riflessione aperta)*
Pensa a un videogioco che conosci bene. Quali sono i tre elementi principali che lo compongono (personaggio, obiettivo, ostacoli)?

> *Non c'è una risposta unica — l'importante è identificare chiaramente i componenti fondamentali del gioco scelto.*

---

## 🔧 Tip & Tricks

> **Tip 1 — Cambia la lingua**
> Se Scratch è in inglese e preferisci l'italiano, clicca sull'icona del mappamondo 🌍 in alto e seleziona "Italiano". L'interfaccia e i nomi dei blocchi cambieranno subito.

> **Tip 2 — Tutorial integrati**
> Scratch ha tutorial incorporati molto utili. Clicca sull'icona dei **Tutorial** in alto (icona con punto interrogativo) per accedere a guide rapide su vari argomenti.

> **Tip 3 — Modalità schermo intero**
> Puoi ingrandire il palcoscenico cliccando sull'icona delle quattro frecce in alto a destra del palcoscenico. Utile per vedere meglio il gioco durante il test.

> **Tip 4 — Backup dei progetti**
> Se usi Scratch online, i progetti sono salvati nel cloud. Ma è sempre buona pratica scaricare una copia locale: vai su **File** → **Salva nel computer** ogni tanto, per sicurezza.

---

## 📋 Riepilogo dell'Unità

| Argomento | Cosa abbiamo imparato |
|-----------|-----------------------|
| Interfaccia Scratch | Le cinque aree principali: barra strumenti, palcoscenico, sprite, blocchi, script |
| Frogger | Obiettivo, regole, ostacoli e meccaniche di gioco |
| Pianificazione | Importanza di identificare gli elementi prima di programmare |
| Progetto | Come creare, nominare e salvare un progetto Scratch |

**Verifica rapida:**
- [ ] Hai aperto Scratch e riconosci le cinque aree dell'interfaccia
- [ ] Sai spiegare l'obiettivo di Frogger a un compagno
- [ ] Hai creato un progetto chiamato "Frogger - Corso" e lo hai salvato
- [ ] Hai eliminato il gatto predefinito e (opzionalmente) aggiunto uno sfondo

---

## ➡️ Prossimo passo

Nella **Unità 1** creeremo finalmente la rana protagonista e disegneremo il campo di gioco con strada, fiume e zone sicure. Daremo vita al mondo di Frogger!

---

*Mini Corso: Programmiamo con Scratch — Costruiamo Frogger! | Unità 0 di 11*
