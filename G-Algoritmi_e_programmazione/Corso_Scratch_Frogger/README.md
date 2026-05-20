# Mini Corso: Programmiamo con Scratch — Costruiamo Frogger!

**Edizione Completa: dal Prototipo al Gioco Arcade**
> **Livello:** Scuola secondaria di primo e secondo grado (11–16 anni)
> **Durata stimata:** 8–10 sessioni da 45–60 minuti
> **Strumento:** [Scratch 3.0](https://scratch.mit.edu) (online o offline)
> **Prerequisiti:** Nessuno — il corso è pensato per principianti assoluti

## Consegna dei lavori

Per **ogni esercitazione / unità** lo studente deve preparare una **versione dedicata della consegna** usando un **Documento Google**.

### Cosa consegnare per ogni esercitazione

Creare un Documento Google con queste sezioni:

1. **Obiettivo da raggiungere**  
   Scrivere in modo sintetico qual era il traguardo dell'unità o del mini esercizio.

2. **Screenshot del lavoro**  
   Inserire uno o più screenshot del progetto Scratch che mostrino:
   - il palcoscenico
   - gli sprite principali
   - eventuali blocchi di codice importanti

3. **Descrizione dei risultati ottenuti**  
   Spiegare cosa funziona nel progetto realizzato, quali parti sono state completate e se ci sono eventuali difficoltà o parti da migliorare.

4. **Risposte alle domande**  
   Riportare le risposte alle domande di riflessione presenti nella guida dell'unità.

5. **Link al lavoro**  
   Inserire il link al progetto Scratch online oppure, se il lavoro è stato svolto offline, indicare chiaramente dove si trova il file `.sb3` consegnato.

### Suggerimento di struttura del documento

Puoi usare questo modello:

```text
Titolo: Frogger - Unità X

1. Obiettivo da raggiungere
2. Screenshot del lavoro
3. Descrizione dei risultati ottenuti
4. Risposte alle domande
5. Link al progetto / file consegnato
```

---

Il corso guida gli studenti nella realizzazione completa del classico videogioco **Frogger** usando Scratch. Ogni unità introduce un concetto di programmazione attraverso un mini esercizio autonomo e funzionante, che si integra progressivamente nel gioco finale.

Ogni unità è strutturata in:
- 📖 **Introduzione teorica** — il concetto chiave spiegato con esempi
- 🛠️ **Passaggi guidati** — le istruzioni passo-passo da seguire in Scratch
- 💡 **Domande di riflessione** — per consolidare la comprensione


## Introduzione al corso

Questo corso guida gli studenti alla realizzazione **completa e fedele** del classico *Frogger* di Konami.  
È strutturato in **due fasi distinte**:

1. **Fase 1 — Le Fondamenta** (Unità 0→10): si costruisce un gioco giocabile e riconoscibile, introducendo i concetti base della programmazione visiva.
2. **Fase 2 — Perfezionamento** (Unità 11→19): si aggiungono le meccaniche avanzate dell’arcade originale (nidi, tartarughe, nemici a stati, generazione procedurale, classifica) e si affrontano concetti di programmazione strutturata.

Ogni unità mantiene la struttura collaudata:
- 📖 **Introduzione teorica**
- 🛠️ **Passaggi guidati**
- 💡 **Domande di riflessione**

E produce sempre un **mini esercizio autonomo e funzionante**.

---

## FASE 1 — LE FONDAMENTA  
*Obiettivo: avere un Frogger giocabile con strada, fiume, vite, punteggio e livelli.*

---

### 🐸 Unità 0 — Benvenuti in Scratch e nel mondo di Frogger
> *Prima di programmare, capiamo cosa programmeremo*

- **0.1** Cos'è Scratch? L'interfaccia in cinque minuti: stage, sprite, blocchi, aree di script.
- **0.2** Cos'è Frogger? Analisi del gioco originale: la rana deve attraversare strada e fiume per raggiungere i **nidi** in cima allo schermo, evitando auto, treni, serpenti e cadendo in acqua.
- **0.3** Pianificare prima di scrivere codice: lo schema del gioco su carta (griglia, corsie, aree sicure).
- **0.4** Creare il primo progetto, salvarlo e condividerlo con il docente.

---

### 🎬 Unità 1 — Sprite, Costumi, Sfondo e la Griglia di Gioco
> *Concetto chiave: oggetti grafici e il sistema a scatti*

- **1.1** Sprite vs. Sfondo: chi si muove e chi resta fermo.
- **1.2** Disegnare la rana protagonista: almeno due costumi (ferma, in salto) per simulare l’animazione.
- **1.3** Creare il campo di gioco: strada, fiume, area sicura centrale, **prato superiore** (dove ospiteremo i nidi). Usare la griglia di Scratch per allineare gli elementi.
- **1.4** Perché Frogger si muove a scatti? Introduzione al concetto di **griglia logica**: ogni cella corrisponde a un salto fisso (es. 40×35 pixel).

**Mini esercizio:** Crea la rana e il campo di gioco completo; posiziona la rana nella cella di partenza in basso al centro.

---

### ⌨️ Unità 2 — Input da Tastiera e Movimento a Griglia
> *Concetto chiave: eventi e controllo rigido del personaggio*

- **2.1** Cos'è un evento? Il blocco `quando si preme il tasto`.
- **2.2** Movimento a scatti: usare `cambia x di [passo]` e `cambia y di [passo]` con valori fissi (es. ±40 per x, ±35 per y), mai coordinate libere.
- **2.3** Movimento continuo vs. a scatti: perché in Frogger serve il secondo.
- **2.4** Limitare il movimento ai bordi del campo: `se <tocca il bordo> allora` o controlli sulle coordinate x/y, in modo che la rana non esca dalla griglia di gioco.

**Mini esercizio:** La rana si muove con le frecce a scatti di una cella alla volta e non esce dal campo.

---

### 🔄 Unità 3 — Cicli e Animazione
> *Concetto chiave: ripetizione e loop*

- **3.1** Cos'è un ciclo? `per sempre` vs. `ripeti N volte`.
- **3.2** Animare la rana: cambiare costume a ogni passo per simulare il salto, poi tornare alla posa normale.
- **3.3** Creare il movimento ciclico delle automobili: un’auto attraversa lo schermo e riappare dall’altro lato.
- **3.4** Velocità e parametri: come rendere un ostacolo più veloce riducendo l’attesa o aumentando i passi.

**Mini esercizio:** Un’automobile attraversa lo schermo in loop da destra a sinistra.

---

### 🚗 Unità 4 — Clonazione degli Sprite
> *Concetto chiave: cloni e istanze multiple*

- **4.1** Perché non creare 10 sprite separati? Il problema della duplicazione del codice.
- **4.2** Il blocco `crea clone di me stesso`.
- **4.3** Gestire i cloni: posizione iniziale, direzione, eliminazione quando escono dallo schermo.
- **4.4** Creare tre corsie di automobili usando un solo sprite-auto e cloni che partono in momenti diversi.

**Mini esercizio:** Tre corsie di automobili con cloni che si muovono a velocità identica.

---

### 💥 Unità 5 — Rilevamento delle Collisioni
> *Concetto chiave: condizioni e interazione tra sprite*

- **5.1** Cos'è una condizione? Il blocco `se … allora`.
- **5.2** Il blocco `sta toccando [sprite]?`.
- **5.3** Cosa succede quando la rana viene investita: effetto visivo (lampeggio, fantasma), suono e reset alla posizione di partenza.
- **5.4** Collisione con i bordi dello schermo: in strada è un muro, ma ricorderemo che in fiume il bordo è pericoloso (lo vedremo in Unità 13).

**Mini esercizio:** La rana viene colpita da un’auto → torna alla posizione di partenza con un effetto visivo.

---

### 🪵 Unità 6 — Tronchi, Moto Relativo e il Fiume
> *Concetto chiave: coordinate e moto relativo*

- **6.1** Il fiume: zona di pericolo dove la rana muore se tocca il colore dell’acqua.
- **6.2** Creare i tronchi che scorrono sull’acqua (cloni in loop).
- **6.3** La rana “sale” sul tronco: usando `cambia x di` insieme al tronco oppure seguendo la `posizione x di [tronco]`.
- **6.4** Cadere in acqua: `se sta toccando il colore [acqua] allora` perdi una vita / reset.

**Mini esercizio:** La rana galleggia sul tronco e cade in acqua (muore) se non c’è un tronco sotto di lei.

---

### 🏠 Unità 7 — Nidi (Home Bases) e Completamento del Livello
> *Concetto chiave: stati multipli e raggruppamento logico*

- **7.1** I 5 nidi in cima: sprite-sensori (invisibili o con costume “vuoto”) che rappresentano gli obiettivi.
- **7.2** Raggiungere un nido: `se tocca nido` → cambia il costume del nido in “rana seduta”, nascondi la rana protagonista, emetti suono di successo.
- **7.3** Tenere il conto: variabile `nidi pieni` che aumenta di 1 ogni volta che si conquista un nido nuovo. Se il nido è già pieno, la rana non può entrare (rimbalzo o morte).
- **7.4** Livello superato: quando `nidi pieni = 5`, mostra messaggio, suona fanfara, passa al livello successivo.

**Mini esercizio:** Riesci a riempire tutti e 5 i nidi; quando l’ultimo si riempie, appare la scritta “LIVELLO COMPLETATO”.

---

### 🏆 Unità 8 — Variabili: Vite, Punteggio e Bonus
> *Concetto chiave: variabili e stato del gioco*

- **8.1** Cos'è una variabile? A cosa serve nel gioco?
- **8.2** Creare e visualizzare le variabili globali `vite` e `punteggio`.
- **8.3** Incrementare il punteggio: per ogni nido raggiunto, per il **tempo residuo** (più veloce = più punti), per le **mosche** che appaiono nei nidi (bonus).
- **8.4** Decrementare le vite (investita, acqua, tempo scaduto) e gestire il Game Over.

**Mini esercizio:** Il gioco tiene traccia di vite e punteggio e mostra “Game Over” quando le vite finiscono.

---

### ⏱️ Unità 9 — Tempismo: Il Conto alla Rovescia
> *Concetto chiave: timer e variabili di tempo*

- **9.1** Aggiungere tensione: il timer per attraversare prima che scada il tempo.
- **9.2** Usare il blocco `timer` di Scratch o una variabile manuale `tempo rimasto`.
- **9.3** Cosa succede allo scadere del tempo? Perdi una vita, reset rana, il timer riparte.
- **9.4** Bilanciare la difficoltà: tempo, velocità, numero di ostacoli.

**Mini esercizio:** Un timer a conto alla rovescia visibile; allo scadere si perde una vita e la rana torna al via.

---

### 🎵 Unità 10 — Suoni, Feedback Visivo e Schermate
> *Concetto chiave: feedback multimediale*

- **10.1** Importare o registrare suoni in Scratch.
- **10.2** Suono per il salto, la collisione, il Goal, il Game Over.
- **10.3** Effetti grafici: cambiare colore, effetto fantasma, pop-up messaggi.
- **10.4** Schermata di inizio (titolo, istruzioni, “clca spazio per iniziare”) e schermata di Game Over con punteggio finale.

**Mini esercizio:** Il gioco ha suoni per le azioni principali, una schermata di benvenuto e una di Game Over.

---

## FASE 2 — PERFEZIONAMENTO E CONCETTI AVANZATI  
*Obiettivo: trasformare il prototipo in un gioco arcade completo, introducendo programmazione strutturata.*

---

### 🧩 Unità 11 — Variabili Locali: Ogni Clone ha la sua Memoria
> *Concetto chiave: scope delle variabili (globale vs. locale)*

- **11.1** Il limite delle variabili globali: perché tutte le auto cambiano velocità insieme?
- **11.2** Creare una variabile `per questo sprite solo`: `velocità`, `corsia`, `direzione`.
- **11.3** Assegnare valori diversi a ogni clone nel momento della nascita.
- **11.4** Usare la variabile locale dentro il ciclo di movimento: corsie a velocità diverse, auto che vanno a sinistra e a destra.

**Mini esercizio:** Tre corsie di automobili e tronchi con cloni che si muovono a velocità e direzioni indipendenti.

---

### 🐊 Unità 12 — Nemici a Stati: Tartarughe e Coccodrillo nel Fiume
> *Concetto chiave: macchina a stati finita*

- **12.1** Oltre allo scorrimento: nemici che *reagiscono* e cambiano comportamento.
- **12.2** La variabile `stato`: valori come `"emersa"`, `"immersione"`, `"sott'acqua"`.
- **12.3** Le tartarughe: piattaforme mobili che affondano ciclicamente. Se la rana è sopra mentre lo stato è `"sott'acqua"`, cade in acqua.
- **12.4** Coccodrillo nel fiume: se visibile e toccato = perdi vita; se sott’acqua = la rana può nuotare/attraversare (come piattaforma fantasma).

**Mini esercizio:** Una tartaruga che alterna emersa/sott’acqua ogni 3 secondi; la rana cade se non scappa in tempo.

---

### 🧱 Unità 13 — Nemici Avanzati, Bordi Mobili e Bonus Mosche
> *Concetto chiave: interazioni complesse e operatori logici*

- **13.1** Serpenti nell’area sicura centrale: sprite nemico a movimento lineare o casuale che uccide la rana.
- **13.2** Coccodrillo nei nidi: a volte un nido già conquistato viene occupato da un coccodrillo, rendendolo di nuovo pericoloso.
- **13.3** Caduta dal bordo su tronco: se un tronco esce dallo schermo portando la rana oltre il bordo, la rana perde una vita (il bordo in fiume non è un muro, è un vuoto).
- **13.4** Mosche bonus: sprite che appaiono a caso nei nidi vuoti o nell’area sicura; raccolte per 200 punti extra.

**Mini esercizio:** Implementa almeno 2 di queste meccaniche (es. serpenti + caduta dal bordo).

---

### 🛠️ Unità 14 — Procedure Personalizzate (I Miei Blocchi)
> *Concetto chiave: astrazione e riutilizzo del codice*

- **14.1** Perché il codice si ripete? Il problema della “copia e incolla”.
- **14.2** Creare un blocco personalizzato: `resetta rana`, `controlla collisione`, `game over`.
- **14.3** Passare parametri: `crea auto [corsia] [velocità] [direzione]`, `crea tronco [y] [velocità]`.
- **14.4** Il vantaggio dello “schermo disabilitato”: generare interi livelli istantaneamente richiamando i propri blocchi.

**Mini esercizio:** Un singolo blocco `prepara livello` che, al suo interno, posiziona la rana, crea cloni di auto/tronchi e azzera il timer con un solo click.

---

### 🎲 Unità 15 — Generazione Procedurale del Livello
> *Concetto chiave: randomicità controllata e riproducibilità*

- **15.1** Perché i livelli prefatti diventano prevedibili?
- **15.2** Usare `numero a caso` per velocità, direzione, distanza tra ostacoli e numero di corsie.
- **15.3** Regole di bilanciamento: impostare minimo e massimo assoluti per non rendere il livello impossibile (es. auto mai più veloci di 8 passi).
- **15.4** Pattern e seed: come generare lo “stesso” livello casuale per sfidare un amico (usare una variabile `seed` che influenza le scelte).

**Mini esercizio:** Ogni volta che si preme “Inizia”, il gioco genera 5 corsie con velocità e direzione casuali ma sempre giocabili.

---

### 🏅 Unità 16 — Liste e Classifica (Hall of Fame)
> *Concetto chiave: strutture dati e persistenza temporanea*

- **16.1** Dalle variabili alle liste: memorizzare più valori in ordine.
- **16.2** Creare le liste `nomi` e `punteggi`; aggiungere un nuovo risultato a fine partita.
- **16.3** Trovare il punteggio massimo e ordinare la classifica (algoritmo semplice: scorrere e confrontare).
- **16.4** Mostrare/nascondere la lista solo alla fine della partita.

**Mini esercizio:** Schermata “Hall of Fame” che mostra i 5 migliori punteggi della sessione.

---

### 🎤 Unità 17 — Input Fisico: Webcam e Microfono
> *Concetto chiave: sensori e interazione multimodale*

- **17.1** Scratch 3.0 vede e sente: blocchi `volume` e `direzione movimento webcam`.
- **17.2** Controllare la rana con il movimento: sinistra/destra inclinando il corpo davanti alla webcam.
- **17.3** “Salta” quando si batte le mani: soglia del volume come evento alternativo.
- **17.4** Calibrare la sensibilità per ambienti rumorosi o poco illuminati.

**Mini esercizio:** Modalità alternativa in cui la rana si muove con le frecce, ma il salto si attiva con un forte suono (es. battito di mani).

---

### 🐞 Unità 18 — Laboratorio di Debug
> *Concetto chiave: pensiero computazionale e risoluzione sistematica di errori*

- **18.1** I bug non sono sbagliati: sono ipotesi da verificare.
- **18.2** Tecnica del “dire” per tracciare variabili: far parlare lo sprite per capire cosa succede.
- **18.3** Isolare il problema: disattivare gli script uno alla volta per trovare il colpevole.
- **18.4** Bug hunt: 3 errori comuni inseriti di proposito in un progetto Frogger precompilato (rana che attraversa i muri, cloni che non si eliminano, punteggio che non aumenta).

**Mini esercizio:** Gli studenti ricevono un file `.sb3` con bug; devono trovarli e correggerli usando `dire` e lo stop dei singoli script.

---

### 🌟 Unità 19 — Livelli di Difficoltà, Rifinitura e Pubblicazione
> *Concetto chiave: scalabilità, messaggi e chiusura del progetto*

- **19.1** Come aumentare la difficoltà a ogni livello superato: più auto, più veloci, meno tempo.
- **19.2** Usare i messaggi (`invia messaggio`) per gestire le transizioni tra schermate, livelli e Game Over in modo pulito.
- **19.3** Aggiungere elementi personalizzati: nuovi nemici, power-up, sfondo notturno, skin della rana.
- **19.4** Test e debug finali, revisione del codice (ordine, commenti tramite blocchi `dire` o descrizioni), pubblicazione su Scratch e presentazione agli altri studenti.

**Progetto finale:** Versione completa e personalizzata di Frogger, con almeno una meccanica avanzata scelta dallo studente, pubblicata e presentata.

---

## Appendice

### A — Tabella riepilogativa dei concetti

| Unità | Concetto principale | Blocchi / Strumenti Scratch coinvolti |
|-------|--------------------|---------------------------------------|
| 1 | Sprite, sfondi, griglia | Costumi, Sfondo, Griglia |
| 2 | Eventi e input | `quando si preme il tasto`, `cambia x/y di` |
| 3 | Cicli e animazione | `per sempre`, `ripeti`, `prossimo costume` |
| 4 | Clonazione base | `crea clone`, `quando vengo clonato` |
| 5 | Condizioni e collisioni | `se … allora`, `sta toccando?` |
| 6 | Coordinate e moto relativo | `cambia x di`, `posizione x di [sprite]` |
| 7 | Stati di gioco e nidi | `se … allora`, variabili, costumi |
| 8 | Variabili globali | `imposta [var] a`, `cambia [var] di` |
| 9 | Timer | `timer`, `azzera timer` |
| 10 | Suoni ed effetti | `suona`, `imposta effetto`, `mostra/nascondi` |
| 11 | Scope (variabili locali) | Variabili `per questo sprite solo` |
| 12 | Macchina a stati | Variabili + condizioni nidificate |
| 13 | Interazioni complesse | Operatori logici, `e`, `o`, `non` |
| 14 | Astrazione (funzioni) | `Crea un blocco`, parametri |
| 15 | Random seed e balancing | `numero a caso`, operatori matematici |
| 16 | Array / strutture dati | `lista`, `aggiungi a`, `elemento di` |
| 17 | Sensori | `volume`, `direzione movimento webcam` |
| 18 | Debug sistematico | `dire`, `ferma [questo script]` |
| 19 | Messaggi e scalabilità | `invia messaggio`, `quando ricevo` |

### B — Glossario dei termini chiave

- **Sprite** — Un personaggio o oggetto grafico nel progetto.
- **Costume** — Una variante visiva di uno sprite.
- **Script** — Un insieme di blocchi collegati che formano un programma.
- **Evento** — Un’azione che avvia l’esecuzione di uno script.
- **Variabile** — Un contenitore per memorizzare un valore (globale o locale).
- **Clone** — Una copia temporanea di uno sprite generata durante l’esecuzione.
- **Collisione** — Il contatto tra due sprite rilevato dal programma.
- **Griglia** — Sistema di celle discrete che vincola il movimento (tipico di Frogger).
- **Stato** — Valore di una variabile che determina il comportamento di un sprite (es. “emersa”/“sott’acqua”).
- **Procedura / Blocco personalizzato** — Uno script riutilizzabile creato dallo studente.
- **Lista** — Una struttura che memorizza una sequenza ordinata di valori.

### C — Meccaniche dell’arcade originali coperte nel corso

| Meccanica originale | Unità che la implementa |
|---------------------|------------------------|
| Movimento a scatti su griglia | 1, 2 |
| Auto su corsie multiple | 3, 4, 11 |
| Tronchi e moto relativo | 6 |
| Nidi (Home Bases) da riempire | 7 |
| Vite, punteggio, bonus tempo | 8 |
| Timer di gioco | 9 |
| Tartarughe che affondano | 12 |
| Coccodrillo nel fiume | 12 |
| Serpenti nell’area sicura | 13 |
| Coccodrillo nei nidi | 13 |
| Caduta dal bordo su tronco | 13 |
| Mosche bonus nei nidi | 8, 13 |
| Livelli di difficoltà crescente | 15, 19 |

### D — Risorse utili

- [Scratch 3.0 online](https://scratch.mit.edu)
- [Scratch offline editor](https://scratch.mit.edu/download)
- [Scratch Wiki (italiano)](https://it.scratch-wiki.info)
- [ScratchEd — risorse per insegnanti](https://scratched.gse.harvard.edu)

---

*Corso progettato per un apprendimento progressivo e autonomo. La Fase 1 garantisce un risultato visibile e funzionante in tempi brevi; la Fase 2 trasforma quel prototipo in un gioco robusto, fedele all’arcade e arricchito di concetti avanzati di programmazione.*