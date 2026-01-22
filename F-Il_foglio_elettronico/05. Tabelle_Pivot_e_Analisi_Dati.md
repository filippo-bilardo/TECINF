# Guida alle Tabelle Pivot e Analisi Dati

**Analisi avanzata con Google Sheets e Microsoft Excel**

---

## Indice

1. [Introduzione alle Tabelle Pivot](#introduzione-alle-tabelle-pivot)
2. [Creare una Tabella Pivot](#creare-una-tabella-pivot)
3. [Struttura e Componenti](#struttura-e-componenti)
4. [Operazioni Base](#operazioni-base)
5. [Funzioni di Aggregazione](#funzioni-di-aggregazione)
6. [Filtri e Segmentazione](#filtri-e-segmentazione)
7. [Raggruppamento Dati](#raggruppamento-dati)
8. [Campi Calcolati](#campi-calcolati)
9. [Grafici Pivot](#grafici-pivot)
10. [Analisi Dati Avanzata](#analisi-dati-avanzata)
11. [Best Practices](#best-practices)
12. [Esempi Pratici](#esempi-pratici)

---

## Introduzione alle Tabelle Pivot

### Cos'è una Tabella Pivot

Una **tabella pivot** (pivot table) è uno strumento che permette di:
- **Riassumere** grandi quantità di dati
- **Riorganizzare** informazioni dinamicamente
- **Analizzare** pattern e trend
- **Aggregare** dati per categorie
- **Creare** report interattivi

### Esempio Trasformazione

**Dati originali (100+ righe):**
```
Data       | Prodotto | Categoria | Regione | Vendite
-----------|----------|-----------|---------|--------
01/01/26   | iPhone   | Telefoni  | Nord    | 1.200
01/01/26   | iPad     | Tablet    | Nord    | 800
02/01/26   | iPhone   | Telefoni  | Sud     | 950
...
```

**Tabella Pivot (riassunto):**
```
Categoria ↓ | Nord   | Sud    | Centro | TOTALE
------------|--------|--------|--------|--------
Telefoni    | 45.600 | 38.200 | 42.100 | 125.900
Tablet      | 28.400 | 22.800 | 25.600 | 76.800
Computer    | 67.200 | 54.300 | 61.800 | 183.300
TOTALE      | 141.200| 115.300| 129.500| 386.000
```

**Da 100+ righe → 3×3 celle con insight immediati!**

---

### Quando Usare le Pivot

✅ **Ideale per:**
- Dataset grandi (100+ righe)
- Analisi multi-dimensionale
- Report ricorrenti
- Confronti per categorie
- Identificare top/bottom performer
- Trend temporali
- Dashboard dinamici

❌ **NON necessario per:**
- Pochi dati (< 20 righe)
- Analisi semplice con SOMMA/MEDIA
- Dati già aggregati
- Dataset non strutturato

---

### Vantaggi Tabelle Pivot

```
✅ Velocità:       Analisi in secondi vs ore di formule
✅ Flessibilità:   Riorganizzazione drag & drop
✅ Interattività:  Filtri e drill-down immediati
✅ No formule:     Aggregazioni automatiche
✅ Aggiornamento:  Un click per riflettere nuovi dati
✅ Visualizzazione: Grafici pivot integrati
```

---

## Creare una Tabella Pivot

### Prerequisiti Dati

#### ✅ Struttura Corretta

```
┌──────────┬──────────┬──────────┬──────────┐
│ Data     │ Prodotto │ Quantità │ Importo  │ ← Intestazioni (1 riga)
├──────────┼──────────┼──────────┼──────────┤
│ 01/01/26 │ iPhone   │    5     │  4.500   │ ← Dati uniformi
│ 01/01/26 │ iPad     │    3     │  1.800   │ ← Una riga = un record
│ 02/01/26 │ MacBook  │    2     │  3.600   │ ← Nessuna riga vuota
└──────────┴──────────┴──────────┴──────────┘
```

**Requisiti:**
- Prima riga: intestazioni chiare e uniche
- Nessuna riga/colonna vuota
- Dati uniformi per colonna (no mix testo/numeri)
- Nessuna cella unita
- Formato tabella/intervallo continuo

#### ❌ Struttura Problematica

```
┌──────────┬──────────┬──────────┬──────────┐
│          │          │ VENDITE GENNAIO    │ ← Celle unite
├──────────┼──────────┼──────────┼──────────┤
│ Data     │ Prod     │ Prod     │ Importo  │ ← Intestazioni duplicate
├──────────┼──────────┼──────────┼──────────┤
│          │          │          │          │ ← Riga vuota
├──────────┼──────────┼──────────┼──────────┤
│ 01/01/26 │ iPhone   │ TOTALE:  │  4.500   │ ← Mix dati/aggregati
└──────────┴──────────┴──────────┴──────────┘
```

---

### Processo Creazione

#### Excel

```
1. Clicca in qualsiasi cella del dataset
2. Inserisci → Tabella pivot
   O Ctrl+Alt+P (scorciatoia personalizzata)
3. Finestra dialogo:
   - Tabella/Intervallo: conferma selezione automatica
   - Posizione: Nuovo foglio o Foglio esistente
4. OK
5. Si apre pannello "Campi tabella pivot" a destra
```

#### Google Sheets

```
1. Seleziona dati (incluse intestazioni)
2. Dati → Tabella pivot
   O Inserisci → Tabella pivot
3. Finestra dialogo:
   - Intervallo dati: conferma
   - Crea in: Nuovo foglio o Foglio esistente
4. Crea
5. Editor tabella pivot si apre a destra
```

---

### Interfaccia Tabella Pivot

#### Layout Excel

```
┌─────────────────────────────────────┐
│  CAMPI TABELLA PIVOT                │
├─────────────────────────────────────┤
│ Cerca campi: [_____________]        │
├─────────────────────────────────────┤
│ □ Data                              │
│ □ Prodotto                          │
│ □ Categoria                         │
│ □ Regione                           │
│ □ Quantità                          │
│ □ Importo                           │
├─────────────────────────────────────┤
│ Trascina campi tra le aree:         │
├─────────────────────────────────────┤
│ FILTRI                              │
│ [________________]                  │
├─────────────────────────────────────┤
│ COLONNE                             │
│ [________________]                  │
├─────────────────────────────────────┤
│ RIGHE                               │
│ [________________]                  │
├─────────────────────────────────────┤
│ VALORI                              │
│ [________________]                  │
└─────────────────────────────────────┘
```

#### Layout Google Sheets

```
┌─────────────────────────────────────┐
│  Editor tabella pivot               │
├─────────────────────────────────────┤
│ Righe                               │
│  [+ Aggiungi]                       │
├─────────────────────────────────────┤
│ Colonne                             │
│  [+ Aggiungi]                       │
├─────────────────────────────────────┤
│ Valori                              │
│  [+ Aggiungi]                       │
├─────────────────────────────────────┤
│ Filtri                              │
│  [+ Aggiungi]                       │
└─────────────────────────────────────┘
```

---

## Struttura e Componenti

### Le 4 Aree

```
        [FILTRI] ← Filtro generale su tutta la tabella
             │
    ┌────────┴────────┐
    │                 │
  RIGHE          COLONNE
    │                 │
    └────────┬────────┘
             │
          VALORI ← Dati aggregati (somma, media, ecc.)
```

---

### 1. RIGHE

Categorie visualizzate verticalmente (asse Y).

**Esempio:**
```
Prodotto ↓   | Vendite
-------------|--------
iPhone       | 45.600
iPad         | 28.400
MacBook      | 67.200
```

**Quando usare:**
- Categorie principali di analisi
- Elenchi (prodotti, clienti, regioni)
- Gerarchie (Anno → Trimestre → Mese)

---

### 2. COLONNE

Categorie visualizzate orizzontalmente (asse X).

**Esempio:**
```
Categoria ↓ | Q1     | Q2     | Q3     | Q4
------------|--------|--------|--------|--------
Telefoni    | 32.100 | 28.600 | 31.400 | 33.800
Tablet      | 18.200 | 19.800 | 19.600 | 19.200
```

**Quando usare:**
- Confronti temporali (mesi, trimestri, anni)
- Categorie secondarie
- Analisi matrice (righe × colonne)

---

### 3. VALORI

Dati numerici da aggregare.

**Funzioni disponibili:**
```
Somma        - SOMMA(campo)
Media        - MEDIA(campo)
Conteggio    - CONTA.VALORI(campo)
Massimo      - MAX(campo)
Minimo       - MIN(campo)
Deviaz.Std   - DEV.ST(campo)
Varianza     - VAR(campo)
Prodotto     - PRODOTTO(campo)
% su totale  - Calcolo percentuale
```

**Esempio:**
```
Regione     | Somma Vendite | Media Vendite | Conta Ordini
------------|---------------|---------------|-------------
Nord        | 141.200       | 2.355         | 60
Centro      | 129.500       | 2.158         | 60
Sud         | 115.300       | 1.922         | 60
```

---

### 4. FILTRI

Filtra l'intera tabella pivot.

**Esempio:**
```
[Filtro: Anno = 2025 ▼]

Prodotto    | Vendite (solo 2025)
------------|--------------------
iPhone      | 45.600
iPad        | 28.400
MacBook     | 67.200
```

**Quando usare:**
- Filtro globale su tutta l'analisi
- Cambio contesto rapido (anno, regione, categoria)
- Report con selezione utente

---

## Operazioni Base

### Aggiungere Campi

#### Excel

```
1. Spunta checkbox nel pannello "Campi tabella pivot"
   - Campo testo → va in RIGHE automaticamente
   - Campo numero → va in VALORI (Somma)
   
2. O trascina campo in area specifica:
   - Prodotto → RIGHE
   - Vendite → VALORI
```

#### Google Sheets

```
1. Clicca "+ Aggiungi" nell'area desiderata
2. Seleziona campo dal menu
3. Configura:
   - Ordina per
   - Mostra totali
   - Funzione aggregazione (per VALORI)
```

---

### Rimuovere Campi

**Excel:**
```
- Deseleziona checkbox
  O
- Trascina campo fuori dall'area
```

**Google Sheets:**
```
- Click su X accanto al campo
```

---

### Riorganizzare Campi

**Drag & Drop:**
```
Prima:
Righe: Prodotto
Colonne: Regione

Dopo:
Righe: Regione
Colonne: Prodotto

→ Pivot si riorganizza automaticamente!
```

**Vantaggi:** Esplorare dati da prospettive diverse senza ricreare tutto.

---

### Esempio Pratico: Prima Pivot

**Dataset vendite:**
```
Data       | Prodotto | Regione | Importo
-----------|----------|---------|--------
01/01/26   | iPhone   | Nord    | 1.200
01/01/26   | iPad     | Sud     | 800
02/01/26   | iPhone   | Nord    | 950
02/01/26   | MacBook  | Centro  | 2.400
...
```

**Obiettivo:** Totale vendite per prodotto

**Step:**
```
1. Crea pivot
2. Trascina "Prodotto" → RIGHE
3. Trascina "Importo" → VALORI (automaticamente Somma)
4. Risultato:

Prodotto    | Somma di Importo
------------|------------------
iPhone      | 45.600
iPad        | 28.400
MacBook     | 67.200
Totale      | 141.200
```

---

## Funzioni di Aggregazione

### Cambiare Funzione

**Excel:**
```
1. Click su campo in VALORI
2. Impostazioni campo valore
3. Scegli funzione:
   - Somma
   - Conteggio
   - Media
   - Max/Min
   - ...
4. OK
```

**Google Sheets:**
```
1. Click su campo in VALORI
2. Menu a discesa "Riassumi per:"
3. Scegli funzione
```

---

### Funzioni Comuni

#### SOMMA (Sum)

```
Vendite per Prodotto:

Prodotto    | Somma Importo
------------|---------------
iPhone      | 45.600
iPad        | 28.400
MacBook     | 67.200
```

**Quando usare:** Totali vendite, ricavi, quantità

---

#### MEDIA (Average)

```
Prezzo medio per Categoria:

Categoria   | Media Prezzo
------------|-------------
Telefoni    | 856
Tablet      | 542
Computer    | 1.823
```

**Quando usare:** Valori medi, ticket medio, rating

---

#### CONTEGGIO (Count)

```
Numero ordini per Cliente:

Cliente     | Conta Ordini
------------|-------------
Rossi S.p.A | 45
Verdi Ltd   | 38
Bianchi Srl | 52
```

**Quando usare:** Frequenza, numero transazioni, occorrenze

---

#### MASSIMO/MINIMO (Max/Min)

```
Range prezzi per Categoria:

Categoria   | Max Prezzo | Min Prezzo
------------|------------|------------
Telefoni    | 1.299      | 399
Tablet      | 899        | 299
Computer    | 2.899      | 799
```

**Quando usare:** Identificare estremi, range

---

#### DEVIAZIONE STANDARD (StdDev)

```
Variabilità vendite:

Prodotto    | Media | Dev.Std
------------|-------|--------
iPhone      | 912   | 145
iPad        | 568   | 89
MacBook     | 1.834 | 312
```

**Quando usare:** Analisi variabilità, consistenza, rischio

---

### Calcoli Personalizzati

#### Mostra Valori Come

**Excel: Impostazioni campo valore → Mostra valori come**

**Opzioni:**

1. **% del totale generale**
```
Prodotto    | Vendite | % Totale
------------|---------|----------
iPhone      | 45.600  | 32,3%
iPad        | 28.400  | 20,1%
MacBook     | 67.200  | 47,6%
TOTALE      | 141.200 | 100,0%
```

2. **% del totale riga**
```
Prodotto  | Q1    | Q2    | Q3    | Q4    | Totale
----------|-------|-------|-------|-------|--------
iPhone    | 28%   | 24%   | 26%   | 22%   | 100%
```

3. **% del totale colonna**
```
          | Nord  | Sud   | Centro
----------|-------|-------|--------
iPhone    | 45%   | 38%   | 42%
iPad      | 28%   | 22%   | 26%
MacBook   | 67%   | 54%   | 62%
Totale    | 100%  | 100%  | 100%
```

4. **Differenza da valore**
```
Mese   | Vendite | Diff da Gen
-------|---------|-------------
Gen    | 12.300  | -
Feb    | 13.100  | +800
Mar    | 11.900  | -400
```

5. **% differenza da valore**
```
Mese   | Vendite | % vs Gen
-------|---------|----------
Gen    | 12.300  | 0%
Feb    | 13.100  | +6,5%
Mar    | 11.900  | -3,3%
```

6. **Totale progressivo**
```
Mese   | Vendite | Progr.
-------|---------|--------
Gen    | 12.300  | 12.300
Feb    | 13.100  | 25.400
Mar    | 11.900  | 37.300
Apr    | 14.200  | 51.500
```

7. **Classifica (Rank)**
```
Prodotto    | Vendite | Rank
------------|---------|------
MacBook     | 67.200  | 1
iPhone      | 45.600  | 2
iPad        | 28.400  | 3
```

---

## Filtri e Segmentazione

### Filtri Etichette

Filtro su categorie (righe/colonne).

**Excel:**
```
Click freccia su etichetta riga/colonna
□ Seleziona tutto
☑ iPhone
☑ iPad
☐ MacBook
```

**Filtri disponibili:**
- Uguale a
- Diverso da
- Inizia con
- Finisce con
- Contiene
- Non contiene
- Maggiore di / Minore di (ordine alfabetico)

---

### Filtri Valori

Filtro basato su dati aggregati.

**Esempio:**
```
Mostra solo prodotti con Vendite > 30.000

Prodotto    | Vendite
------------|--------
iPhone      | 45.600  ← Visibile
MacBook     | 67.200  ← Visibile
(iPad nascosto perché 28.400 < 30.000)
```

**Opzioni:**
- Uguale a
- Maggiore di / Minore di
- Tra
- Primi 10 / Ultimi 10
- Sopra media / Sotto media

---

### Filtri Temporali (Date)

**Opzioni intelligenti:**
```
□ Oggi
□ Ieri
□ Questa settimana
□ Settimana scorsa
□ Questo mese
□ Mese scorso
□ Questo trimestre
□ Trimestre scorso
□ Quest'anno
□ Anno scorso
□ Intervallo personalizzato...
```

**Esempio:**
```
Filtro: Questo trimestre (Q1 2026)

Data       | Vendite
-----------|--------
Gen 2026   | 45.600
Feb 2026   | 42.100
Mar 2026   | 48.300
```

---

### Slicer (Filtro Dati)

Pulsanti visivi per filtrare.

**Excel:**
```
1. Clicca su pivot
2. Analizza tabella pivot → Inserisci filtro dati
3. Seleziona campi
4. Slicer appare come pannello:

┌─────────────────┐
│ REGIONE         │
├─────────────────┤
│ ☑ Nord          │
│ ☑ Centro        │
│ ☑ Sud           │
└─────────────────┘
```

**Vantaggi:**
- Visibile e intuitivo
- Multi-selezione semplice
- Collegabile a più pivot
- Design personalizzabile

**Google Sheets:** Non disponibile nativamente (usare filtri o controlli)

---

### Timeline (Sequenza Temporale)

Filtro visivo per date.

**Excel:**
```
1. Clicca su pivot
2. Analizza tabella pivot → Inserisci sequenza temporale
3. Seleziona campo data
4. Appare barra temporale:

┌──────────────────────────────────┐
│ ANNI   TRIMESTRI   MESI   GIORNI│
├──────────────────────────────────┤
│ [<] 2025 [===============] [>]  │
├──────────────────────────────────┤
│ G F M A M G L A S O N D          │
│ █ █ █ ░ ░ ░ ░ ░ ░ ░ ░ ░  ← Q1   │
└──────────────────────────────────┘
```

**Utilizzo:**
- Trascina per selezionare periodo
- Switch tra Anno/Trimestre/Mese/Giorno
- Chiaro e immediato

---

### Filtri Multipli

Combinare più filtri per analisi precise.

**Esempio:**
```
Filtro Regione: Nord
Filtro Categoria: Telefoni
Filtro Data: Q1 2025
Filtro Valore: Vendite > 5.000

Risultato: Solo vendite telefoni > 5k in Nord durante Q1 2025
```

---

## Raggruppamento Dati

### Raggruppare Date

Aggregare date per periodo.

**Automatico (Excel):**
```
Trascina campo Data in RIGHE
→ Excel raggruppa automaticamente per:
   - Anni
   - Trimestri
   - Mesi
```

**Risultato:**
```
▼ 2024
  ▼ Trim1
    ▶ Gen
    ▶ Feb
    ▶ Mar
  ▼ Trim2
    ▶ Apr
    ▶ Mag
    ▶ Giu
▼ 2025
  ...
```

**Personalizzare:**
```
Click destro su data → Raggruppa
Opzioni:
□ Secondi
□ Minuti
□ Ore
□ Giorni
☑ Mesi
☑ Trimestri
☑ Anni
```

---

### Raggruppare Numeri

Creare intervalli numerici.

**Esempio: Età**
```
Click destro su campo Età → Raggruppa
Inizio: 0
Fine: 100
Incremento: 10

Risultato:
0-10    | 15 persone
10-20   | 234 persone
20-30   | 456 persone
30-40   | 389 persone
...
```

**Esempio: Prezzi**
```
Fascia Prezzo | Conteggio
--------------|----------
0-500         | 120
500-1000      | 89
1000-1500     | 45
1500-2000     | 23
>2000         | 12
```

---

### Raggruppare Manualmente

Creare gruppi personalizzati.

**Esempio: Raggruppare Regioni**
```
Selezione multipla (Ctrl+Click):
- Lombardia
- Piemonte
- Veneto

Click destro → Raggruppa selezione

Risultato:
▼ Gruppo1 (rinomina: "Nord")
  - Lombardia
  - Piemonte
  - Veneto
▼ Gruppo2 (rinomina: "Centro")
  - Lazio
  - Toscana
  - Marche
```

---

## Campi Calcolati

### Creare Campo Calcolato

**Excel:**
```
1. Analizza tabella pivot → Campi, elementi e set
2. Campo calcolato
3. Nome: Margine
4. Formula: = Ricavi - Costi
5. Inserisci campo (per usare campi esistenti)
6. OK
```

**Esempio:**

**Dati originali:**
```
Prodotto | Ricavi | Costi
---------|--------|-------
iPhone   | 45.600 | 32.400
iPad     | 28.400 | 19.900
```

**Campo calcolato: Margine**
```
Formula: = Ricavi - Costi

Prodotto | Ricavi | Costi  | Margine
---------|--------|--------|--------
iPhone   | 45.600 | 32.400 | 13.200
iPad     | 28.400 | 19.900 | 8.500
```

**Campo calcolato: % Margine**
```
Formula: = (Ricavi - Costi) / Ricavi

Prodotto | Ricavi | Margine%
---------|--------|----------
iPhone   | 45.600 | 28,9%
iPad     | 28.400 | 29,9%
```

---

### Elemento Calcolato

Aggiunge riga calcolata.

**Esempio:**
```
Prodotto       | Vendite
---------------|--------
iPhone         | 45.600
iPad           | 28.400
MacBook        | 67.200
---------------|--------
Apple Total    | 141.200  ← Somma automatica
Non-Apple      | 23.400   ← Elemento calcolato
---------------|--------
GRAND TOTAL    | 164.600
```

**Formula elemento calcolato:**
```
Non-Apple = SUM(Tutti) - SUM(iPhone, iPad, MacBook)
```

---

### Formule Esterne

Usare formule fuori dalla pivot per calcoli aggiuntivi.

**Esempio:**
```
Tabella Pivot:
A          B
Prodotto   Vendite
iPhone     45.600
iPad       28.400
MacBook    67.200

Formule esterne:
D1: Obiettivo
E1: 50.000

D2: Diff Obiettivo
E2: =B2-$E$1     → -4.400 (iPhone)
E3: =B3-$E$1     → -21.600 (iPad)
E4: =B4-$E$1     → +17.200 (MacBook)
```

**Vantaggio:** Più flessibilità  
**Svantaggio:** Non si aggiornano con pivot

---

## Grafici Pivot

### Creare Grafico Pivot

**Excel:**
```
1. Clicca su pivot
2. Analizza tabella pivot → Grafico pivot
   O
   Inserisci → Grafico pivot
3. Scegli tipo grafico
```

**Google Sheets:**
```
1. Seleziona celle pivot
2. Inserisci → Grafico
3. Editor grafico: Tipo grafico
```

---

### Grafici Raccomandati

**Per Righe Singole:**
```
Prodotto    | Vendite
------------|--------
iPhone      | 45.600
iPad        | 28.400
MacBook     | 67.200

→ Grafico colonne verticali
```

**Per Righe + Colonne:**
```
Prodotto  | Q1    | Q2    | Q3    | Q4
----------|-------|-------|-------|-------
iPhone    | 12.8k | 10.9k | 11.4k | 10.5k
iPad      | 7.1k  | 6.9k  | 7.2k  | 7.2k

→ Grafico colonne raggruppate
→ Grafico linee multiple
```

**Per Serie Temporali:**
```
Mese      | Vendite
----------|--------
Gen       | 45.600
Feb       | 42.100
Mar       | 48.300
...

→ Grafico linea
→ Grafico area
```

---

### Grafici Interattivi

**Caratteristica unica grafici pivot:**

```
Grafico ha pulsanti filtro integrati!

┌─────────────────────────────┐
│ [Regione ▼] [Anno ▼]        │ ← Pulsanti filtro
├─────────────────────────────┤
│                             │
│    [Grafico colonne]        │
│                             │
│                             │
└─────────────────────────────┘

Click su pulsante → Filtra grafico direttamente
```

**Vantaggi:**
- Esplorazione interattiva
- Drill-down immediato
- Collegato a pivot

---

### Best Practices Grafici Pivot

✅ **DA FARE:**
- Limitare categorie (max 10-12)
- Usare colori coerenti
- Titolo descrittivo
- Aggiornare con pivot (non separare)

❌ **EVITARE:**
- Troppe serie (confusione)
- Grafici 3D (distorsione)
- Separare grafico da pivot sorgente

---

## Analisi Dati Avanzata

### Tabelle Pivot Multiple

Analisi da prospettive diverse sugli stessi dati.

**Esempio Dashboard:**
```
┌───────────────────┬───────────────────┐
│ PIVOT 1:          │ PIVOT 2:          │
│ Vendite/Prodotto  │ Vendite/Regione   │
├───────────────────┼───────────────────┤
│ PIVOT 3:          │ GRAFICO:          │
│ Vendite/Mese      │ [Trend temporale] │
└───────────────────┴───────────────────┘

Tutti collegati agli stessi dati sorgente!
Slicer unico filtra tutte le pivot.
```

---

### Consolidamento

Unire dati da più tabelle in una pivot.

**Scenario:**
```
Vendite2024.xlsx
Vendite2025.xlsx
Vendite2026.xlsx

→ Pivot consolidata: Trend 3 anni
```

**Excel:**
```
1. Dati → Consolida
2. Funzione: Somma
3. Riferimento: Aggiungi ogni intervallo
4. OK

Poi crea pivot dal consolidamento
```

**Alternativa migliore: Power Query**
```
1. Dati → Recupera dati → Da file/Da cartella
2. Combina file
3. Crea connessione
4. Pivot su query unificata
```

---

### Modello Dati (Power Pivot)

Relazioni tra tabelle.

**Scenario:**
```
Tabella VENDITE:
VenditaID | DataVendita | ProdottoID | Importo

Tabella PRODOTTI:
ProdottoID | NomeProdotto | Categoria | Prezzo

Tabella CLIENTI:
ClienteID | Nome | Regione | Segmento

RELAZIONI:
VENDITE.ProdottoID → PRODOTTI.ProdottoID
VENDITE.ClienteID → CLIENTI.ClienteID
```

**Vantaggio:** Pivot può usare campi da tutte le tabelle collegate!

**Excel:**
```
1. Attiva Power Pivot (se disponibile)
2. Power Pivot → Gestisci modello dati
3. Diagramma: Crea relazioni trascinando campi
4. Crea pivot dal modello
```

---

### Misure DAX (Power Pivot)

Calcoli avanzati con linguaggio DAX.

**Esempi:**

**Totale Vendite:**
```
Vendite Totali = SUM(Vendite[Importo])
```

**Margine:**
```
Margine = SUM(Vendite[Importo]) - SUM(Vendite[Costo])
```

**Percentuale Margine:**
```
% Margine = DIVIDE([Margine], [Vendite Totali], 0)
```

**Vendite Anno Precedente:**
```
Vendite YoY = 
CALCULATE(
    [Vendite Totali],
    SAMEPERIODLASTYEAR(Date[Data])
)
```

**Crescita %:**
```
Crescita % = 
DIVIDE(
    [Vendite Totali] - [Vendite YoY],
    [Vendite YoY],
    0
)
```

---

### GETPIVOTDATA

Formula per estrarre dati da pivot.

**Sintassi:**
```
=GETPIVOTDATA(campo_dati, pivot, [campo1, valore1], ...)
```

**Esempio:**
```
Pivot in A1:C10:

Prodotto    | Vendite
------------|--------
iPhone      | 45.600
iPad        | 28.400

Formula:
=GETPIVOTDATA("Vendite", $A$1, "Prodotto", "iPhone")
→ Risultato: 45.600

Vantaggio: Si aggiorna con pivot anche se righe cambiano posizione
```

**Generazione automatica:**
```
Excel: = poi clicca su cella pivot → genera GETPIVOTDATA automaticamente
```

---

### Drill-Through

Esplorare dettaglio dietro aggregato.

**Excel:**
```
1. Doppio click su valore nella pivot
2. Nuovo foglio con dati dettagliati sorgenti

Esempio:
Pivot mostra: MacBook → 67.200€
Doppio click → Nuovo foglio con tutte le 37 transazioni MacBook
```

**Utile per:** Verificare dati, investigare anomalie, audit

---

### Analisi What-If

Scenari e previsioni.

**Excel:**
```
1. Dati → Analisi what-if → Gestione scenari
2. Crea scenari:
   - Ottimistico: Vendite +20%
   - Realistico: Vendite +5%
   - Pessimistico: Vendite -10%
3. Pivot su scenari
```

**Tabella dati:**
```
       | Sconto 5% | Sconto 10% | Sconto 15%
-------|-----------|------------|------------
Q1     | 42.300    | 39.800     | 37.100
Q2     | 38.900    | 36.600     | 34.100
```

---

## Best Practices

### 1. Preparazione Dati

✅ **Prima di creare pivot:**

```
□ Dati puliti (no errori, duplicati)
□ Intestazioni chiare e uniche
□ Formati uniformi per colonna
□ Nessuna riga/colonna vuota
□ Date in formato data (non testo)
□ Numeri come numeri (non testo)
□ Tabella formattata (Ctrl+T in Excel)
```

---

### 2. Progettazione Pivot

#### Layout Chiaro

```
✅ Buono:
Prodotto     | Q1    | Q2    | Q3    | Q4    | Totale
-------------|-------|-------|-------|-------|--------
iPhone       | 12.8k | 10.9k | 11.4k | 10.5k | 45.6k
iPad         | 7.1k  | 6.9k  | 7.2k  | 7.2k  | 28.4k

❌ Confuso:
Q1 iPhone iPad MacBook Q2 iPhone iPad...
12.8k 7.1k 18.3k 10.9k 6.9k 16.8k...
```

#### Totali Significativi

```
✅ Attiva:
- Totale complessivo (Grand Total)
- Totali riga/colonna se utili

❌ Disattiva:
- Totali quando danno somme senza senso
  (es. media di medie)
```

---

### 3. Formattazione

**Numeri:**
```
✅ 45.600 €        (valuta con separatore)
✅ 23,5%           (percentuale)
✅ 1,2M            (grandi numeri abbreviati)

❌ 45600           (no separatore)
❌ 0.235           (percentuale come decimale)
```

**Stile Tabella:**
```
Excel:
Progettazione → Stili tabella pivot
- Righe a bande (leggibilità)
- Intestazioni evidenti
- Totali in grassetto
```

---

### 4. Performance

**Pivot Veloci:**

✅ **DA FARE:**
- Usare tabelle Excel (Ctrl+T)
- Limitare campi calcolati complessi
- Aggiornare manualmente se dataset enorme
- Disattiva "Aggiorna all'apertura" per file grandi

❌ **EVITARE:**
- Migliaia di campi calcolati
- Connessioni dati lente
- Troppi livelli di raggruppamento
- Formule esterne che referenziano pivot

---

### 5. Aggiornamento Dati

**Manuale:**
```
Excel: 
- Click destro su pivot → Aggiorna
- Analizza tabella pivot → Aggiorna
- Alt+F5 (aggiorna pivot selezionata)
- Ctrl+Alt+F5 (aggiorna tutte le pivot)

Google Sheets:
- Automatico quando dati cambiano
```

**Automatico (Excel):**
```
Opzioni tabella pivot → Dati
☑ Aggiorna all'apertura del file
☑ Aggiorna ogni: 60 minuti
```

---

### 6. Documentazione

**Aggiungi contesto:**
```
[TITOLO]: Vendite per Prodotto - Q1 2025
[FONTE]: Database Vendite (aggiornato 21/01/26)
[FILTRI ATTIVI]: Solo vendite Italia
[NOTE]: Esclude resi e cancellazioni
```

---

### 7. Condivisione

**Excel:**
```
✅ Condividi file Excel con pivot
✅ Proteggi pivot (Analizza → Opzioni → Disattiva modifiche)
✅ Pubblica su SharePoint/OneDrive per collaborazione

❌ Non convertire in valori (perdi interattività)
```

**Google Sheets:**
```
✅ Condividi con permessi appropriati
✅ Usa filtri vista per personalizzare per utente
✅ Commenta per spiegare analisi

❌ Evita troppi editor simultanei (rallenta)
```

---

## Esempi Pratici

### Esempio 1: Analisi Vendite Multi-Dimensionale

**Dataset:**
```
Data       | Prodotto | Categoria | Regione | Venditore | Quantità | Importo
-----------|----------|-----------|---------|-----------|----------|--------
01/01/26   | iPhone15 | Telefoni  | Nord    | Rossi M.  | 5        | 4.500
01/01/26   | iPadAir  | Tablet    | Sud     | Verdi A.  | 3        | 1.800
...
(1.000+ righe)
```

**Obiettivo:** Dashboard completo vendite

**Pivot 1: Vendite per Prodotto**
```
RIGHE: Prodotto
VALORI: Somma Importo, Conta Ordini
ORDINA: Somma Importo (decrescente)

Prodotto     | Vendite | N.Ordini | Ticket Medio
-------------|---------|----------|-------------
MacBook Pro  | 89.500  | 45       | 1.989
iPhone 15    | 67.200  | 75       | 896
iPad Air     | 45.300  | 82       | 552
AirPods Pro  | 23.100  | 67       | 345
```

**Pivot 2: Trend Mensile**
```
RIGHE: Mese (raggruppato da Data)
VALORI: Somma Importo
GRAFICO: Linea con marcatori

Gen    | 72.400
Feb    | 68.900
Mar    | 79.200
Apr    | 84.500
```

**Pivot 3: Performance Regionale**
```
RIGHE: Regione
COLONNE: Categoria
VALORI: Somma Importo

          | Telefoni | Tablet | Computer | TOTALE
----------|----------|--------|----------|--------
Nord      | 45.600   | 28.400 | 67.200   | 141.200
Centro    | 42.100   | 25.600 | 61.800   | 129.500
Sud       | 38.200   | 22.800 | 54.300   | 115.300
TOTALE    | 125.900  | 76.800 | 183.300  | 386.000
```

**Pivot 4: Top 10 Venditori**
```
RIGHE: Venditore
VALORI: Somma Importo
FILTRO VALORE: Top 10

Venditore    | Vendite
-------------|--------
Rossi M.     | 45.600
Bianchi S.   | 42.300
Verdi A.     | 38.900
...
```

**Slicer per filtrare tutto:**
```
[Categoria ▼] [Regione ▼] [Anno ▼]
```

---

### Esempio 2: Analisi Budget vs Effettivo

**Dataset:**
```
Mese   | Categoria  | Budget | Effettivo
-------|------------|--------|----------
Gen    | Marketing  | 10.000 | 9.500
Gen    | Vendite    | 15.000 | 16.200
Gen    | IT         | 8.000  | 7.800
...
```

**Pivot:**
```
RIGHE: Categoria
COLONNE: Mese
VALORI: Somma Budget, Somma Effettivo

CAMPO CALCOLATO:
Scostamento = Effettivo - Budget
% Scostamento = (Effettivo - Budget) / Budget

Risultato:

             | Gen Budget | Gen Effettivo | Gen Scost | Gen %
-------------|------------|---------------|-----------|-------
Marketing    | 10.000     | 9.500         | -500      | -5,0%
Vendite      | 15.000     | 16.200        | +1.200    | +8,0%
IT           | 8.000      | 7.800         | -200      | -2,5%

FORMATTAZIONE CONDIZIONALE:
- Verde se Scostamento >= 0 e <= Budget*0,05
- Giallo se Scostamento < 0
- Rosso se Scostamento > Budget*0,05
```

---

### Esempio 3: Analisi Clienti RFM

**Dataset:**
```
ClienteID | UltimoAcquisto | NumOrdini | TotaleSpeso
----------|----------------|-----------|------------
C001      | 15/01/26       | 23        | 12.400
C002      | 10/12/25       | 8         | 3.200
C003      | 22/01/26       | 45        | 28.900
...
```

**Pivot Segmentazione:**
```
RIGHE: 
- Recency (raggruppato: 0-30gg, 31-90gg, 91-180gg, >180gg)
- Frequency (raggruppato: 1-5, 6-10, 11-20, >20)
VALORI: Conta Clienti, Media TotaleSpeso

Recency    | Frequency | Clienti | Spesa Media
-----------|-----------|---------|-------------
0-30gg     | >20       | 45      | 15.600 ← VIP
0-30gg     | 11-20     | 78      | 8.900  ← Regolari
0-30gg     | 6-10      | 123     | 4.200
0-30gg     | 1-5       | 234     | 1.800
31-90gg    | >20       | 23      | 12.300 ← A rischio
...

GRAFICO: Heatmap con formattazione condizionale
```

---

### Esempio 4: Analisi Inventario

**Dataset:**
```
Prodotto  | Categoria | Giacenza | VenditeMese | Costo | Prezzo
----------|-----------|----------|-------------|-------|-------
iPhone15  | Telefoni  | 45       | 75          | 700   | 900
iPadAir   | Tablet    | 123      | 82          | 400   | 550
...
```

**Pivot:**
```
RIGHE: Categoria, Prodotto
VALORI: 
- Giacenza
- VenditeMese
- Somma Costo * Giacenza (valore inventario)

CAMPO CALCOLATO:
Giorni Copertura = Giacenza / (VenditeMese / 30)
Stato = IF(GgCopertura < 15, "URGENTE", 
         IF(GgCopertura < 30, "ATTENZIONE", "OK"))

Risultato:

Categoria | Prodotto  | Giacenza | Vendite | Gg.Cop | Stato
----------|-----------|----------|---------|--------|----------
Telefoni  |           |          |         |        |
          | iPhone15  | 45       | 75      | 18     | ATTENZIONE
          | iPhone14  | 12       | 45      | 8      | URGENTE
Tablet    |           |          |         |        |
          | iPadAir   | 123      | 82      | 45     | OK
          | iPadPro   | 34       | 28      | 36     | OK

FORMATTAZIONE CONDIZIONALE:
- Rosso: URGENTE
- Giallo: ATTENZIONE
- Verde: OK
```

---

## Troubleshooting

### Problemi Comuni

#### 1. Pivot Non Aggiorna Nuovi Dati

**Problema:**
```
Aggiungo righe al dataset, ma pivot non le vede
```

**Soluzione:**
```
Excel:
- Usa tabelle (Ctrl+T): si espandono automaticamente
- O: Modifica sorgente dati (Analizza → Modifica origine dati)

Google Sheets:
- Espandi intervallo manualmente
- Editor → Intervallo dati
```

---

#### 2. Campi Calcolati Danno Errore

**Problema:**
```
Formula campo calcolato: = Ricavi - Costi
Errore: #NOME?
```

**Soluzione:**
```
- Usa nomi campo esatti (maiuscole/minuscole)
- Inserisci campo dal menu invece di digitare
- Verifica campo esiste in VALORI
```

---

#### 3. Date Non Raggruppano

**Problema:**
```
Campo Data in RIGHE mostra ogni singola data, non mesi
```

**Soluzione:**
```
- Verifica campo sia formato DATA (non testo)
- Converti testo in data: VALORE.DATA() o formattazione
- Click destro → Raggruppa manualmente
```

---

#### 4. Valori Mostrano "Conteggio" Invece di "Somma"

**Problema:**
```
Vendite mostra "Conta di Vendite" invece di somma
```

**Causa:**
```
Campo contiene valori non numerici (testi, errori, spazi)
```

**Soluzione:**
```
1. Controlla dati originali
2. Rimuovi celle vuote/errori
3. Assicura formato numero
4. Cambia manualmente funzione aggregazione
```

---

#### 5. Pivot Troppo Lenta

**Problema:**
```
Pivot impiega minuti per aggiornarsi
```

**Soluzione:**
```
- Riduci dataset (filtra prima di creare pivot)
- Limita campi calcolati complessi
- Disattiva aggiornamento automatico
- Usa Power Query per pre-aggregare
- Considera database esterno invece di Excel
```

---

## Strumenti Alternativi

### Power Query

**Pre-elaborazione dati prima di pivot.**

```
Power Query →
1. Importa dati da multiple fonti
2. Pulisci (rimuovi duplicati, errori)
3. Trasforma (pivot/unpivot, merge)
4. Aggrega preliminarmente
5. Carica in Excel
→ Crea pivot su dati puliti
```

**Vantaggi:**
- Automazione ETL
- Riproducibile
- Performance migliori

---

### Power BI

**Business Intelligence Microsoft.**

```
Excel Pivot →    Power BI →
Analisi semplici  Analisi complesse
1 dataset         Multiple fonti
Statico          Interattivo web
Locale           Cloud/condiviso
```

---

### Google Data Studio

**Alternativa Google a Power BI.**

```
Google Sheets →      Data Studio →
Dati grezzi         Dashboard interattivi
Formule             Visualizzazioni avanzate
Condivisione base   Pubblicazione web
```

---

### Tableau / Qlik Sense

**Strumenti BI professionali.**

```
Quando passare da Excel Pivot a BI tools:
- Dataset > 1M righe
- Multiple fonti dati complesse
- Real-time dashboards
- Condivisione enterprise
- Analisi predittiva
```

---

## Checklist Pivot Professionale

### Prima di Creare

- [ ] Dati puliti e validati
- [ ] Intestazioni uniche e chiare
- [ ] Formati corretti per colonna
- [ ] Nessuna riga/colonna vuota
- [ ] Tabella formattata (se Excel)
- [ ] Backup dati originali

### Durante Creazione

- [ ] Obiettivo analisi chiaro
- [ ] Campi appropriati in aree corrette
- [ ] Funzioni aggregazione verificate
- [ ] Filtri applicati se necessari
- [ ] Ordinamento logico
- [ ] Formattazione numeri

### Finalizzazione

- [ ] Titolo descrittivo
- [ ] Fonte dati documentata
- [ ] Legenda colori/codici
- [ ] Totali significativi
- [ ] Grafico pivot se utile
- [ ] Test aggiornamento dati
- [ ] Condivisione con permessi corretti

---

## Quiz Riepilogo

### 1. Dove metti categorie principali?
A) Colonne  
B) Righe ✅  
C) Valori  

### 2. Funzione default per numeri?
A) Media  
B) Somma ✅  
C) Conteggio  

### 3. Slicer serve per?
A) Ordinare  
B) Filtrare visualmente ✅  
C) Calcolare  

### 4. GETPIVOTDATA è utile per?
A) Creare pivot  
B) Estrarre dati da pivot ✅  
C) Formattare pivot  

### 5. Raggruppare date serve per?
A) Aggregare per mese/trimestre ✅  
B) Ordinare cronologicamente  
C) Filtrare periodi  

---

## Conclusione

### Riepilogo Vantaggi Pivot

```
🚀 Velocità:      Da ore a secondi
🔄 Flessibilità:  Riorganizzazione immediata
📊 Visualizzazione: Grafici integrati
🎯 Precisione:    Aggregazioni automatiche
💡 Insight:       Pattern nascosti emergono
🔗 Scalabilità:   Da 100 a 1M+ righe
```

### Percorso Apprendimento

```
Livello 1: Base (1-2 ore)
- Creare pivot semplice
- Righe, colonne, valori
- Filtri base
→ 80% casi d'uso coperti

Livello 2: Intermedio (3-5 ore)
- Campi calcolati
- Raggruppamenti
- Grafici pivot
- Slicer
→ Analisi complete

Livello 3: Avanzato (10+ ore)
- Modello dati
- DAX
- Power Query
- Dashboard complessi
→ Business Intelligence
```

### Prossimi Passi

1. ✅ Pratica con dataset reali
2. ✅ Crea 1 pivot al giorno per 30 giorni
3. ✅ Esplora Power Query
4. ✅ Studia DAX (se usi Power Pivot)
5. ✅ Costruisci dashboard personale

---

**Buona analisi!** 📊📈📉

*Tempo lettura: ~120 minuti*  
*Livello: Base → Avanzato*  
*Aggiornato: Gennaio 2026*
