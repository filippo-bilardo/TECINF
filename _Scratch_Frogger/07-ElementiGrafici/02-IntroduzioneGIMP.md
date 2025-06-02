# Introduzione a GIMP

In questa guida, esploreremo GIMP (GNU Image Manipulation Program), un potente software di editing grafico open source che utilizzeremo per creare gli elementi visivi del nostro gioco Frogger. GIMP offre una vasta gamma di strumenti e funzionalità che ci permetteranno di realizzare sprite, sfondi e altri elementi grafici di alta qualità.

## Installazione e configurazione di GIMP

### Download e installazione

Per iniziare a utilizzare GIMP, è necessario scaricarlo e installarlo sul proprio computer:

1. **Visita il sito ufficiale**: [www.gimp.org](https://www.gimp.org/downloads/)
2. **Scarica la versione appropriata** per il tuo sistema operativo (Windows, macOS o Linux)
3. **Segui le istruzioni di installazione** specifiche per il tuo sistema

### Configurazione iniziale

Al primo avvio di GIMP, potrebbe essere utile configurare alcune impostazioni per ottimizzare il flusso di lavoro per la creazione di grafica per videogiochi:

1. **Modalità finestra singola**: Vai su `Modifica > Preferenze > Interfaccia > Modalità` e seleziona "Modalità finestra singola" per un'interfaccia più compatta
2. **Griglia**: Configura una griglia predefinita andando su `Modifica > Preferenze > Griglia predefinita`
3. **Dimensione predefinita**: Imposta una dimensione predefinita per i nuovi documenti adatta agli sprite di Frogger (ad esempio, 32x32 pixel)

## Panoramica dell'interfaccia

L'interfaccia di GIMP è composta da diverse aree principali:

### 1. Barra dei menu

Situata nella parte superiore della finestra, contiene tutte le funzioni e i comandi organizzati in menu a tendina:

- **File**: Operazioni di base come aprire, salvare, esportare
- **Modifica**: Funzioni di copia, incolla, preferenze
- **Visualizza**: Opzioni di zoom, griglie, guide
- **Immagine**: Trasformazioni e modifiche all'intera immagine
- **Livello**: Gestione dei livelli
- **Colori**: Correzioni e modifiche del colore
- **Strumenti**: Accesso rapido agli strumenti di disegno e modifica
- **Filtri**: Effetti speciali e filtri

### 2. Barra degli strumenti

Solitamente posizionata sul lato sinistro, contiene gli strumenti principali per disegnare, selezionare e modificare l'immagine:

- **Strumenti di selezione**: Rettangolare, ellittica, a mano libera
- **Strumenti di pittura**: Pennello, matita, aerografo
- **Strumenti di trasformazione**: Sposta, ridimensiona, ruota
- **Altri strumenti**: Testo, riempimento, sfumatura

### 3. Pannello delle opzioni degli strumenti

Situato sotto la barra dei menu, mostra le opzioni specifiche per lo strumento attualmente selezionato.

### 4. Pannelli laterali

Solitamente posizionati sul lato destro, includono:

- **Pannello dei livelli**: Gestione dei livelli dell'immagine
- **Pannello dei canali**: Gestione dei canali di colore e delle maschere
- **Pannello dei percorsi**: Creazione e modifica di percorsi vettoriali

### 5. Area di lavoro

L'area centrale dove viene visualizzata e modificata l'immagine.

## Strumenti principali e loro utilizzo

### Strumenti di selezione

1. **Selezione rettangolare** ![Icona](https://docs.gimp.org/2.10/it/images/toolbox/stock-tool-rect-select-22.png)
   - Perfetta per selezionare aree rettangolari
   - Utile per creare sprite con forme geometriche
   - Tieni premuto Shift per creare selezioni quadrate

2. **Selezione ellittica** ![Icona](https://docs.gimp.org/2.10/it/images/toolbox/stock-tool-ellipse-select-22.png)
   - Ideale per forme circolari o ovali
   - Utile per elementi come le teste dei personaggi o oggetti rotondi
   - Tieni premuto Shift per creare cerchi perfetti

3. **Selezione a mano libera** ![Icona](https://docs.gimp.org/2.10/it/images/toolbox/stock-tool-free-select-22.png)
   - Permette di creare selezioni con forme personalizzate
   - Utile per contorni irregolari

4. **Selezione per colore** ![Icona](https://docs.gimp.org/2.10/it/images/toolbox/stock-tool-by-color-select-22.png)
   - Seleziona aree di colore simile
   - Utile per modificare rapidamente aree specifiche di colore

### Strumenti di pittura

1. **Pennello** ![Icona](https://docs.gimp.org/2.10/it/images/toolbox/stock-tool-paintbrush-22.png)
   - Lo strumento principale per dipingere
   - Offre bordi morbidi e varie opzioni di pennello
   - Ideale per dettagli e texture

2. **Matita** ![Icona](https://docs.gimp.org/2.10/it/images/toolbox/stock-tool-pencil-22.png)
   - Crea linee con bordi netti
   - Perfetta per pixel art e contorni definiti
   - Essenziale per la creazione di sprite in stile pixel art

3. **Secchiello** ![Icona](https://docs.gimp.org/2.10/it/images/toolbox/stock-tool-bucket-fill-22.png)
   - Riempie aree con un colore o un pattern
   - Utile per colorare rapidamente grandi aree

4. **Sfumatura** ![Icona](https://docs.gimp.org/2.10/it/images/toolbox/stock-tool-gradient-22.png)
   - Crea transizioni graduali tra colori
   - Utile per sfondi o effetti di luce

### Strumenti di modifica

1. **Sposta** ![Icona](https://docs.gimp.org/2.10/it/images/toolbox/stock-tool-move-22.png)
   - Sposta livelli o selezioni
   - Essenziale per posizionare elementi nell'immagine

2. **Ridimensiona** ![Icona](https://docs.gimp.org/2.10/it/images/toolbox/stock-tool-scale-22.png)
   - Modifica le dimensioni di livelli o selezioni
   - Utile per adattare gli elementi alle dimensioni desiderate

3. **Ruota** ![Icona](https://docs.gimp.org/2.10/it/images/toolbox/stock-tool-rotate-22.png)
   - Ruota livelli o selezioni
   - Utile per creare varianti di uno stesso elemento

4. **Taglia** ![Icona](https://docs.gimp.org/2.10/it/images/toolbox/stock-tool-crop-22.png)
   - Ritaglia l'immagine alle dimensioni desiderate
   - Fondamentale per definire le dimensioni finali degli sprite

### Altri strumenti utili

1. **Testo** ![Icona](https://docs.gimp.org/2.10/it/images/toolbox/stock-tool-text-22.png)
   - Aggiunge testo all'immagine
   - Utile per elementi dell'interfaccia utente

2. **Clona** ![Icona](https://docs.gimp.org/2.10/it/images/toolbox/stock-tool-clone-22.png)
   - Copia parti dell'immagine in altre aree
   - Utile per duplicare elementi o correggere imperfezioni

3. **Gomma** ![Icona](https://docs.gimp.org/2.10/it/images/toolbox/stock-tool-eraser-22.png)
   - Cancella parti dell'immagine
   - Utile per creare trasparenza o correggere errori

## Livelli e trasparenza

I livelli sono uno degli aspetti più potenti di GIMP, permettendo di lavorare su elementi separati dell'immagine senza modificare gli altri.

### Concetto di livelli

I livelli funzionano come fogli trasparenti sovrapposti, ognuno contenente una parte dell'immagine finale:

- **Organizzazione**: I livelli superiori nascondono quelli inferiori
- **Modifica non distruttiva**: Puoi modificare un livello senza influenzare gli altri
- **Flessibilità**: Puoi riorganizzare, nascondere o modificare i livelli in qualsiasi momento

### Pannello dei livelli

Il pannello dei livelli mostra tutti i livelli presenti nell'immagine e permette di:

- **Creare nuovi livelli**: Pulsante "Nuovo livello"
- **Eliminare livelli**: Pulsante "Elimina livello"
- **Riordinare livelli**: Trascinando i livelli su e giù
- **Modificare la visibilità**: Cliccando sull'icona dell'occhio
- **Modificare l'opacità**: Usando il cursore di opacità
- **Cambiare la modalità di fusione**: Usando il menu a tendina delle modalità

### Strategie di organizzazione dei livelli per sprite di gioco

Per creare sprite efficaci per Frogger, è consigliabile organizzare i livelli in questo modo:

1. **Livello di base**: Contiene la forma principale dell'oggetto
2. **Livello dei dettagli**: Contiene dettagli come occhi, bocca, ecc.
3. **Livello delle ombre**: Contiene ombre e profondità
4. **Livello delle luci**: Contiene punti luce e riflessi

Questa organizzazione permette di modificare facilmente ogni aspetto dello sprite senza dover ricominciare da capo.

### Trasparenza e canale alfa

La trasparenza è fondamentale per gli sprite di gioco, permettendo di vedere lo sfondo attraverso parti dell'immagine:

- **Canale alfa**: Controlla la trasparenza di ogni pixel (0% = completamente trasparente, 100% = completamente opaco)
- **Scacchiera grigia e bianca**: Rappresenta le aree trasparenti nell'interfaccia di GIMP
- **Esportazione con trasparenza**: Assicurati di utilizzare formati che supportano la trasparenza (PNG, GIF) quando esporti

## Creazione di un documento per pixel art

Per creare un nuovo documento ottimizzato per pixel art in GIMP:

1. Vai su `File > Nuovo`
2. Imposta le dimensioni appropriate (ad esempio, 32x32 pixel per uno sprite di piccole dimensioni)
3. Assicurati che la risoluzione sia impostata a 72 o 96 PPI (pixel per pollice)
4. Seleziona "RGB" come spazio colore e assicurati che "Aggiungi canale alfa" sia selezionato
5. Clicca su "OK" per creare il nuovo documento

### Configurazione della griglia

Per lavorare con precisione nella pixel art:

1. Vai su `Visualizza > Mostra griglia` per attivare la griglia
2. Vai su `Immagine > Configura griglia` per impostare la spaziatura della griglia (generalmente 1 pixel per la pixel art)
3. Attiva `Visualizza > Aggancia alla griglia` per far sì che gli strumenti si allineino automaticamente alla griglia

## Tecniche base per la creazione di sprite

### 1. Creazione di una silhouette

Iniziate sempre creando una silhouette chiara e riconoscibile:

1. Crea un nuovo livello
2. Usa lo strumento matita con un colore scuro per disegnare il contorno dell'oggetto
3. Riempi la forma con lo strumento secchiello
4. Verifica che la silhouette sia riconoscibile anche senza dettagli

### 2. Aggiunta di dettagli base

1. Crea un nuovo livello sopra la silhouette
2. Aggiungi i dettagli principali (occhi, bocca, caratteristiche distintive)
3. Mantieni i dettagli semplici e leggibili

### 3. Colorazione

1. Crea un nuovo livello sotto i dettagli
2. Usa lo strumento secchiello per riempire le aree con i colori base
3. Utilizza una palette limitata (8-16 colori) per mantenere uno stile coerente

### 4. Ombreggiatura e illuminazione

1. Crea un nuovo livello sopra i colori base
2. Usa colori più scuri per le ombre e più chiari per le luci
3. Imposta la modalità del livello su "Moltiplica" per le ombre o "Sovrapponi" per le luci
4. Usa l'opacità del livello per controllare l'intensità dell'effetto

## Esercizio pratico: Creazione di un semplice sprite

Proviamo a creare un semplice sprite di una moneta che potrebbe essere utilizzato come elemento di gioco:

1. **Crea un nuovo documento** di 16x16 pixel
2. **Attiva la griglia** con spaziatura di 1 pixel
3. **Crea la silhouette**:
   - Usa lo strumento selezione ellittica per creare un cerchio
   - Riempi con un colore giallo oro (#FFD700)
4. **Aggiungi dettagli**:
   - Usa un giallo più scuro (#DAA520) per creare un bordo interno
   - Aggiungi un simbolo semplice al centro (ad esempio, una stella o una lettera)
5. **Aggiungi ombre e luci**:
   - Usa un giallo chiaro (#FFEB3B) per i punti luce
   - Usa un marrone dorato (#B8860B) per le ombre
6. **Esporta lo sprite**:
   - Vai su `File > Esporta come`
   - Salva come PNG per mantenere la trasparenza

## Conclusione

GIMP è uno strumento potente e versatile per la creazione di grafica per videogiochi. Con la pratica, diventerai sempre più abile nell'utilizzare i suoi strumenti per creare sprite accattivanti e professionali per il tuo gioco Frogger.

Nella prossima guida, ci concentreremo sulla creazione degli sprite principali del gioco, a partire dalla rana protagonista.

## Navigazione del Corso
- [📑 Indice](../README.md)
- [⬅️ Introduzione alla grafica per videogiochi](./01-IntroduzioneGrafica.md)
- [➡️ Creazione degli sprite principali](./03-CreazioneSprite.md)