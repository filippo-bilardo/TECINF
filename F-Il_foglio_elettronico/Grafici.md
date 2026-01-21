# Guida ai Grafici nei Fogli di Calcolo

**Visualizzazione dati professionale con Google Sheets e Microsoft Excel**

---

## Indice

1. [Introduzione ai Grafici](#introduzione-ai-grafici)
2. [Tipi di Grafici](#tipi-di-grafici)
3. [Creare un Grafico](#creare-un-grafico)
4. [Personalizzare i Grafici](#personalizzare-i-grafici)
5. [Grafici Avanzati](#grafici-avanzati)
6. [Grafici Combinati](#grafici-combinati)
7. [Dashboard e Report](#dashboard-e-report)
8. [Best Practices](#best-practices)
9. [Errori Comuni](#errori-comuni)
10. [Esempi Pratici](#esempi-pratici)

---

## Introduzione ai Grafici

### Cos'è un Grafico

Un **grafico** (chart) è una rappresentazione visiva di dati numerici che:
- Facilita la comprensione di informazioni complesse
- Evidenzia pattern, trend e relazioni
- Comunica risultati in modo immediato
- Supporta decisioni basate su dati

### Perché Usare i Grafici

```
Dati in tabella:
Gen: 1.200€, Feb: 1.350€, Mar: 1.180€, Apr: 1.520€...

Dati in grafico:
      1.600 ┤        ●
      1.400 ┤   ●       
      1.200 ┤●    ●     ← Trend visibile immediatamente!
      1.000 ┤
           └─┬──┬──┬──┬─
            Gen Feb Mar Apr
```

**Vantaggi:**
- ✅ Immediata comprensione
- ✅ Identifica trend rapidamente
- ✅ Confronti visuali semplici
- ✅ Comunicazione efficace
- ✅ Memorabilità maggiore

### Quando NON Usare Grafici

❌ **Evitare grafici quando:**
- Pochi dati (2-3 valori): la tabella è più chiara
- Precisione assoluta richiesta: meglio numeri esatti
- Confronti multipli complessi: troppo carico
- Dati non numerici o categorici inappropriati

---

## Tipi di Grafici

### Panoramica Tipologie

```
📊 Colonne/Barre     - Confronti tra categorie
📈 Linee             - Trend nel tempo
🥧 Torta/Ciambella   - Proporzioni di un totale
📉 Area              - Volume e trend cumulativi
🔵 Dispersione (XY)  - Correlazioni tra variabili
💹 Azionario         - Dati finanziari (apertura/chiusura)
🌐 Radar             - Confronti multi-dimensionali
📊 Istogramma        - Distribuzione frequenze
🗺️ Geografici       - Dati per regioni/paesi
🔥 Heatmap           - Intensità valori in matrice
```

---

## 📊 Grafici a Colonne

### Quando Usare

✅ **Ideale per:**
- Confrontare valori tra categorie diverse
- Mostrare cambiamenti nel tempo (periodi discreti)
- Evidenziare differenze tra gruppi

### Tipi di Grafici a Colonne

#### 1. Colonne Semplici

```
Vendite per Prodotto:

  3.000 ┤     ███
  2.500 ┤     ███
  2.000 ┤ ███ ███ ███
  1.500 ┤ ███ ███ ███
  1.000 ┤ ███ ███ ███ ███
    500 ┤ ███ ███ ███ ███
      0 └─┴───┴───┴───┴───
         A   B   C   D
```

**Quando usare:** Confronto singola metrica, più categorie

**Dati esempio:**
```
Prodotto | Vendite
---------|--------
iPhone   | 2.400
iPad     | 1.800
MacBook  | 2.900
AirPods  | 1.200
```

#### 2. Colonne Raggruppate (Clustered)

```
Confronto Trimestrale:

  400 ┤  ■  ■     ■  ■
  300 ┤  ■  ■  ■  ■  ■  ■
  200 ┤  ■  ■  ■  ■  ■  ■
  100 ┤  ■  ■  ■  ■  ■  ■
    0 └──┴──┴──┴──┴──┴──
       Q1   Q2   Q3
       ■ = 2024  ■ = 2025
```

**Quando usare:** Confrontare 2-4 serie di dati per categoria

**Dati esempio:**
```
Trimestre | 2024 | 2025
----------|------|------
Q1        |  320 |  380
Q2        |  280 |  340
Q3        |  360 |  410
```

#### 3. Colonne Sovrapposte (Stacked)

```
Budget Spesa:

  1.000 ┤ ┌──┐     ← Altro
    900 ┤ │░░│     ← Trasporti
    800 ┤ │▒▒│     ← Bollette
    700 ┤ │▓▓│     ← Alimentari
    600 ┤ │██│     ← Affitto
        └─┴──┴─
         Gen Feb
```

**Quando usare:** Mostrare parti di un totale per categoria

**Dati esempio:**
```
Categoria    | Gen | Feb
-------------|-----|-----
Affitto      | 800 | 800
Alimentari   | 300 | 350
Bollette     | 150 | 140
Trasporti    | 100 | 120
Altro        |  50 |  60
TOTALE       |1400 |1470
```

#### 4. Colonne Sovrapposte 100%

```
Proporzioni:

 100% ┤ ┌──┐ ┌──┐
  80% ┤ │░░│ │░░│
  60% ┤ │▒▒│ │▒▒│
  40% ┤ │▓▓│ │▓▓│
  20% ┤ │██│ │██│
   0% └─┴──┴─┴──┴─
        Gen  Feb
```

**Quando usare:** Confrontare proporzioni percentuali

---

## 📊 Grafici a Barre

### Differenza con Colonne

```
Colonne (verticali):        Barre (orizzontali):
  ║                         A ▓▓▓▓▓▓▓▓
  ║ █                       B ▓▓▓▓▓▓▓▓▓▓
  ║ █ █                     C ▓▓▓▓▓
  ║ █ █ █                   D ▓▓▓▓▓▓▓
  ╚═╧═╧═╧═                    0  5  10
```

### Quando Usare Barre

✅ **Preferire barre quando:**
- Etichette categorie sono lunghe
- Molte categorie (>7-8)
- Confronto immediato lunghezze
- Classifica/ranking

**Esempio:**
```
Vendite per Regione:

Trentino-Alto Adige ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓ 1.520
Friuli-Venezia G.   ▓▓▓▓▓▓▓▓▓▓▓▓▓ 1.340
Emilia-Romagna      ▓▓▓▓▓▓▓▓▓▓▓▓ 1.280
Lombardia           ▓▓▓▓▓▓▓▓▓▓▓ 1.180
Veneto              ▓▓▓▓▓▓▓▓▓▓ 1.050
```

---

## 📈 Grafici a Linee

### Quando Usare

✅ **Ideale per:**
- Mostrare trend nel tempo (serie temporali)
- Dati continui
- Più serie da confrontare
- Evidenziare variazioni e pattern

### Tipi Grafici a Linee

#### 1. Linea Singola

```
Temperatura Media Mensile:

 30°C ┤           ╭─╮
 25°C ┤       ╭───╯ ╰─╮
 20°C ┤   ╭───╯       ╰──╮
 15°C ┤ ──╯              ╰─
 10°C ┤
      └─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─
       G F M A M G L A S O N D
```

**Quando usare:** Singolo trend temporale

#### 2. Linee Multiple

```
Confronto Vendite:

 500 ┤        ●══════●     ← Prodotto A
 400 ┤    ●──┘      └──●  ← Prodotto B
 300 ┤ ●━━━━━━━━━━━━━━━●  ← Prodotto C
 200 ┤
     └─┴──┴──┴──┴──┴──┴──
      Q1  Q2  Q3  Q4
```

**Quando usare:** Confrontare trend multipli

**⚠️ Limite:** Max 5-6 linee (oltre diventa confuso)

#### 3. Linea con Marcatori

```
Punti Dati Evidenziati:

 100 ┤           ●
  80 ┤       ●──┘
  60 ┤   ●──┘
  40 ┤ ●┘
     └─┴─┴─┴─┴─
      1 2 3 4 5
```

**Quando usare:** Evidenziare punti dati specifici

---

## 🥧 Grafici a Torta

### Quando Usare

✅ **Ideale per:**
- Mostrare parti di un totale (100%)
- 3-7 categorie (massimo)
- Proporzioni immediatamente visibili
- Dati che sommano al 100%

❌ **NON usare per:**
- Confronti precisi (difficile stimare angoli)
- Molte categorie (>7)
- Valori simili (fette indistinguibili)
- Comparazioni multiple

### Esempio Torta

```
Budget Spesa Mensile:

        Affitto 50%
    ╱─────────────╲
   ╱       ░░░░░░░ ╲
  │   ▓▓   ░░░░░░░  │
  │  ▓▓▓   ░░░░░░░  │
   ╲ ▓▓▓   ░░░░░░░ ╱
    ╲─────────────╱
    
▓ Cibo 20%
░ Altro 30%
```

**Dati:**
```
Categoria | Importo | %
----------|---------|----
Affitto   | 1.000€  | 50%
Cibo      |   400€  | 20%
Trasporti |   300€  | 15%
Altro     |   300€  | 15%
TOTALE    | 2.000€  | 100%
```

### Best Practices Torta

✅ **DA FARE:**
- Ordinare fette da grande a piccola
- Iniziare da ore 12 con fetta più grande
- Usare colori contrastanti
- Etichettare con % E valore
- Max 7 fette, unire "Altro" se necessario

❌ **EVITARE:**
- Torta 3D (distorce percezione)
- Troppi colori simili
- Etichette sovrapposte
- Confronto tra più torte
- Angoli troppo piccoli (<5%)

---

## 🍩 Grafico a Ciambella (Donut)

Variante della torta con buco centrale.

### Vantaggi vs Torta

```
Torta:              Ciambella:
  ╱───╲              ╱─╲
 │ ░▓▒ │            │ ○ │  ← Spazio per info
  ╲───╱              ╲─╱
```

✅ **Vantaggi ciambella:**
- Spazio centrale per totale/KPI
- Più moderna e pulita
- Meno distorsione visiva

**Esempio:**
```
         ╱──────╲
        │  1.250 │  ← Totale vendite
        │ vendite│
         ╲──────╱
    ░▓▒▒▒▒▒▓▓▓░
    
░ Nord 30%
▓ Centro 40%
▒ Sud 30%
```

---

## 📉 Grafici ad Area

### Quando Usare

✅ **Ideale per:**
- Enfatizzare volume/magnitudo nel tempo
- Mostrare contributo cumulativo
- Trend con senso di "quantità"

### Tipi Area

#### 1. Area Semplice

```
Profitto Mensile:

 500 ┤        ╱▀▀▀╲
 400 ┤     ╱▀▀░░░░▀╲
 300 ┤  ╱▀▀░░░░░░░░░▀╲
 200 ┤▀▀░░░░░░░░░░░░░░▀
     └─┴──┴──┴──┴──┴──┴─
      G  F  M  A  M  G
```

#### 2. Area Sovrapposta

```
Traffico Web (Stacked):

 1k ┤ ┌──────────────┐  ← Social
800 ┤ │░░░░░░░░░░░░░░│
600 ┤ │▒▒▒▒▒▒▒▒▒▒▒▒▒▒│  ← Organico
400 ┤ │▓▓▓▓▓▓▓▓▓▓▓▓▓▓│
200 ┤ │██████████████│  ← Diretto
    └─┴──┴──┴──┴──┴──
      Lun Mar Ven
```

**Quando usare:** Parti contribuiscono a totale cumulativo

#### 3. Area 100%

```
Composizione Percentuale:

100%┤░░░░░░░░░░░░░░░░
 80%┤▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒
 60%┤▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓
 40%┤████████████████
 20%┤████████████████
  0%└─┴──┴──┴──┴──┴──
```

**Quando usare:** Proporzioni che cambiano nel tempo

---

## 🔵 Grafico a Dispersione (Scatter/XY)

### Quando Usare

✅ **Ideale per:**
- Mostrare correlazioni tra 2 variabili
- Dati scientifici/statistici
- Identificare pattern o cluster
- Outlier detection

### Esempio Scatter

```
Altezza vs Peso:

100kg┤             ●
 90kg┤          ●  ●
 80kg┤       ●  ●
 70kg┤    ●  ●
 60kg┤ ●  ●
     └─┴──┴──┴──┴──
     160 170 180 190cm

Correlazione positiva visibile!
```

**Dati:**
```
Persona | Altezza | Peso
--------|---------|------
A       | 165 cm  | 62 kg
B       | 172 cm  | 68 kg
C       | 180 cm  | 78 kg
D       | 185 cm  | 85 kg
E       | 190 cm  | 92 kg
```

### Elementi Scatter

**Linea di Tendenza:**
```
      ●
   ●  ╱  ● 
 ●  ╱●
  ╱ ●     ← Linea di tendenza (regressione)
╱
```

**Tipi linea tendenza:**
- **Lineare:** y = mx + q
- **Polinomiale:** curve complesse
- **Esponenziale:** crescita/decrescita rapida
- **Logaritmica:** crescita che rallenta
- **Potenza:** y = ax^b

---

## 📊 Istogramma

### Differenza con Colonne

```
Colonne (categorie):    Istogramma (intervalli):
  ║                       ║
  ║ █ █                   ║  ██
  ║ █ █ █                 ║  ████
  ╚═╧═╧═╧═                ║  ████ ██
  A B C D                 ╚═══╧═══╧═══
                          0-10 10-20 20-30
```

**Istogramma:**
- Asse X: intervalli numerici continui (bins)
- Asse Y: frequenza/conteggio
- No spazi tra barre
- Analisi distribuzione

### Quando Usare

✅ **Ideale per:**
- Distribuzione frequenze
- Analisi statistica
- Identificare normalità/skewness
- Range e concentrazione dati

**Esempio: Distribuzione Voti**

```
Frequenza Voti Esame:

 15 ┤
 12 ┤     ████
  9 ┤   ████████
  6 ┤ ████████████
  3 ┤ ████████████ ██
  0 └─┴───┴───┴───┴───
    18  21  24  27  30
    
Distribuzione quasi normale
```

---

## 💹 Grafico Azionario (Candlestick)

### Quando Usare

✅ **Ideale per:**
- Dati finanziari (azioni, criptovalute)
- Mostrare: Apertura, Chiusura, Massimo, Minimo
- Analisi tecnica trading

### Anatomia Candela

```
     │   ← Massimo (wick superiore)
     ├─┐
     │█│ ← Corpo (apertura-chiusura)
     │█│
     └─┤
       │ ← Minimo (wick inferiore)

Verde: Chiusura > Apertura (rialzo)
Rosso: Chiusura < Apertura (ribasso)
```

**Dati:**
```
Data      | Apertura | Massimo | Minimo | Chiusura
----------|----------|---------|--------|----------
21/01/26  |   150 €  |  156 €  | 148 €  |  154 € ↑
22/01/26  |   154 €  |  158 €  | 152 €  |  151 € ↓
23/01/26  |   151 €  |  155 €  | 150 €  |  155 € ↑
```

---

## 🌐 Grafico Radar (Spider)

### Quando Usare

✅ **Ideale per:**
- Confronto multi-dimensionale
- Valutazioni su più criteri
- Performance review
- Skill assessment

### Esempio Radar

```
        Velocità
            ↑
            ●
         ╱ │ ╲
  Qualità ●─┼─● Prezzo
         ╲ │ ╱
            ●
       Assistenza

● = Fornitore A
```

**Dati:**
```
Criterio    | Fornit.A | Fornit.B
------------|----------|----------
Velocità    |    9     |    7
Prezzo      |    6     |    9
Qualità     |    8     |    7
Assistenza  |    7     |    8
Flessibilità|    8     |    6
```

**Buono per:** Confrontare 2-3 entità su 5-8 dimensioni

---

## 🗺️ Grafici Geografici

### Mappe Cloropleta (Choropleth)

Colori rappresentano valori per regioni geografiche.

```
Vendite per Regione Italia:

   ██████  ← Nord (verde scuro = alto)
   ██████
   ░░░░░░  ← Centro (verde chiaro = medio)
   ▓▓▓▓▓▓  ← Sud (verde medio)
   ▓▓▓▓

Scala: ░ Basso  ▓ Medio  █ Alto
```

### Quando Usare

✅ **Ideale per:**
- Dati per paese/regione/stato
- Confronti geografici
- Distribuzione territoriale
- Analisi di mercato per area

**Google Sheets:**
```
Inserisci → Grafico → Mappa geografica
```

**Dati formato:**
```
Paese    | Vendite
---------|--------
Italia   | 12.500
Francia  |  9.800
Germania | 15.200
Spagna   |  7.600
```

---

## 🔥 Heatmap (Mappa di Calore)

### Quando Usare

✅ **Ideale per:**
- Matrice di valori
- Intensità su 2 dimensioni
- Correlazioni multiple
- Schedule/calendari

### Esempio Heatmap

```
Traffico Web per Giorno/Ora:

Ora   Lun  Mar  Mer  Gio  Ven  Sab  Dom
0-2   ░░░  ░░░  ░░░  ░░░  ░░░  ░░░  ░░░  ← Basso
2-4   ░░░  ░░░  ░░░  ░░░  ░░░  ░░░  ░░░
...
8-10  ███  ███  ███  ███  ███  ▓▓▓  ▓▓▓  ← Picco
10-12 ███  ███  ███  ███  ███  ▓▓▓  ▓▓▓
...
22-24 ▓▓▓  ▓▓▓  ▓▓▓  ▓▓▓  ███  ███  ███

Legenda: ░ 0-100  ▓ 100-500  █ 500+
```

**Creazione:**
- Google Sheets: Formattazione condizionale + scala colori
- Excel: Formattazione condizionale

---

## Creare un Grafico

### Processo Base

#### Excel

```
1. Seleziona dati (incluse intestazioni)
2. Inserisci → Grafici consigliati
   O
   Inserisci → Tipo grafico specifico
3. Clicca sul grafico desiderato
4. Personalizza
```

**Tasto rapido:** `Alt+F1` (grafico default su foglio corrente)

#### Google Sheets

```
1. Seleziona dati
2. Inserisci → Grafico
3. Editor grafico si apre a destra:
   - Tipo grafico
   - Intervallo dati
   - Configurazione
4. Inserisci
```

---

### Selezione Dati

#### ✅ Buona Struttura Dati

```
┌────────┬─────────┬─────────┐
│ Mese   │ 2024    │ 2025    │  ← Intestazioni chiare
├────────┼─────────┼─────────┤
│ Gen    │  1.200  │  1.350  │  ← Dati uniformi
│ Feb    │  1.180  │  1.420  │
│ Mar    │  1.350  │  1.580  │
└────────┴─────────┴─────────┘
```

**Includere:**
- Prima riga: etichette categorie/serie
- Prima colonna: etichette asse X
- Solo dati numerici (no formule visibili se possibile)

#### ❌ Struttura Problematica

```
┌────────┬─────────┬─────────┐
│        │         │         │  ← No intestazioni
├────────┼─────────┼─────────┤
│ Gen 24 │  1.200  │  TOTALE │  ← Mix dati
│ 2      │  testo  │  1.180  │  ← Non uniforme
│        │         │         │  ← Righe vuote
└────────┴─────────┴─────────┘
```

---

### Intervallo Dati

#### Specificare Intervallo

**Metodo 1: Selezione manuale**
```
1. Clicca su grafico
2. Grafico ha bordi colorati sui dati sorgente
3. Trascina bordi per modificare
```

**Metodo 2: Editor**
```
Excel: Progettazione grafico → Seleziona dati
Sheets: Editor grafico → Intervallo dati
```

**Formato intervallo:**
```
Foglio1!A1:C10
'Nome Foglio'!A1:C10  (con spazi)
Vendite!$A$1:$C$10    (riferimento assoluto)
```

---

### Grafici Dinamici

Usare **Tabelle** (Excel) o **Intervalli Denominati** per grafici che si aggiornano automaticamente.

#### Excel con Tabella

```
1. Seleziona dati
2. Ctrl+T (converti in tabella)
3. Crea grafico dalla tabella
4. Nuove righe aggiunte alla tabella → grafico si aggiorna automaticamente
```

#### Intervallo Dinamico

```
Nome: Vendite_Anno
Formula: =OFFSET(Foglio1!$A$1,0,0,CONTA.VALORI(Foglio1!$A:$A),3)

Grafico usa: =Vendite_Anno
```

---

## Personalizzare i Grafici

### Elementi del Grafico

```
         [Titolo Grafico]
    ↑
    │   Legenda → ■ Serie 1  ■ Serie 2
Ass │     ┌────────────────┐
e Y │     │    ╱╲          │
    │     │   ╱  ╲    ╱╲   │
    │     │  ╱    ╲  ╱  ╲  │
    └─────┴─┴──────┴─┴────┴─
          Etichette Asse X
```

**Elementi principali:**
1. Titolo grafico
2. Assi (X e Y)
3. Etichette assi
4. Legenda
5. Serie dati
6. Griglia
7. Etichette dati
8. Area grafico
9. Area tracciato

---

### Titoli e Etichette

#### Titolo Grafico

**Best practices:**
```
✅ Buoni titoli:
- "Vendite Mensili 2025 vs 2024"
- "Distribuzione Budget Familiare - Gennaio 2026"
- "Correlazione Temperatura-Vendite Gelato"

❌ Titoli vaghi:
- "Grafico"
- "Dati"
- "Vendite" (quale periodo? quale prodotto?)
```

**Personalizzare:**
```
Excel:
1. Clicca su titolo
2. Modifica testo
3. Home → Formatta carattere
   O
   Click destro → Formato titolo

Sheets:
Editor grafico → Personalizza → Titolo grafico
```

#### Titoli Assi

```
Asse Y: "Vendite (€)"      ← Includi unità di misura!
Asse X: "Mese"
```

**Quando omettere:**
- Se ovvio dal contesto (mesi su asse X)
- Spazio limitato
- Dashboard con multiple visualizzazioni

---

### Legenda

#### Posizione

```
Sopra:    ■ A ■ B ■ C
         ┌────────────┐
Destra:  │         ╱  │ ■ Serie 1
         │      ╱     │ ■ Serie 2
         └────────────┘

Sotto:   ┌────────────┐
         │            │
         └────────────┘
         ■ A ■ B ■ C
```

**Scegliere in base a:**
- Spazio disponibile
- Numero serie
- Layout generale

#### Etichette Legenda

✅ **Chiare e descrittive:**
```
Invece di:   Serie1, Serie2
Usare:       iPhone, iPad
```

**Modificare:**
```
Excel: Seleziona dati → Modifica → Nomi serie
Sheets: Editor grafico → Configura → Serie
```

---

### Colori e Stili

#### Palette Colori

**Professionali:**
```
Business:     Blu #0066CC, Grigio #999999
Finanziaria:  Verde #339933 (pos), Rosso #CC3333 (neg)
Creativa:     Palette personalizzata brand
Accessibile:  Alto contrasto, colorblind-friendly
```

**Evitare:**
- Colori troppo simili
- Neon su sfondo chiaro
- Grigio su grigio
- Rosso-Verde puro (daltonismo)

#### Stili Predefiniti

**Excel:**
```
Progettazione → Stili grafico
- Colorati
- Monocromatici
- Personalizzati
```

**Google Sheets:**
```
Editor grafico → Personalizza → Stile grafico
- Semplice
- 3D (evitare!)
- Personalizza colori singolarmente
```

---

### Assi

#### Scala Assi

**Scala Automatica:**
```
Default, adatta ai dati
```

**Scala Manuale:**
```
Min: 0
Max: 1000
Intervallo principale: 200
Intervallo secondario: 100
```

**Quando personalizzare:**
- Enfatizzare differenze piccole
- Allineare più grafici
- Iniziare da valore != 0 (⚠️ attenzione alla percezione!)

#### ⚠️ Manipolazione Visiva

```
Scala 0-100:         Scala 80-100:
100┤                100┤ █
 80┤                 95┤ █
 60┤ █                90┤ █  ← Differenze amplificate!
 40┤ █                85┤ █
 20┤ █                80┤ █
  0└─                  └─
```

**Etico:** Sempre partire da 0 per colonne/barre (salvo casi particolari documentati)

#### Formato Numeri

```
1234.56 → € 1.235     (valuta, arrotondato)
0.25    → 25%         (percentuale)
1500000 → 1,5M        (abbreviato)
1.5E6   → 1.500.000   (notazione standard)
```

**Impostare:**
```
Excel: Formato asse → Numero
Sheets: Editor grafico → Personalizza → Asse verticale → Formato numero
```

---

### Griglia

```
Griglia principale (spessa):
  1000┼─────────────
   800┼─────────────
   600┼─────────────
   
Griglia secondaria (sottile):
  1000┼─────────────
   900├─ ─ ─ ─ ─ ─
   800┼─────────────
```

**Best practices:**
- Griglia principale: sempre (aiuta lettura)
- Griglia secondaria: solo se necessaria
- Colore: grigio chiaro (non distrarre dai dati)
- Asse X: griglia spesso non necessaria

---

### Etichette Dati

Mostra valori direttamente sul grafico.

```
Senza etichette:        Con etichette:
     ████                   ████
     ████                   ████ 1.250
     ████                   ████
     ████                   ████ 890
```

**Quando usare:**
- Pochi dati (max 10-15 valori)
- Valori esatti importanti
- Presentazioni

**Quando NON usare:**
- Molti punti dati (sovraffollamento)
- Grafici linea complessi
- Quando trend più importante di valori esatti

**Posizione etichette:**
- Colonne: sopra barra
- Torta: dentro fetta o fuori con frecce
- Linee: vicino ai punti
- Personalizzata: trascinare manualmente

---

## Grafici Avanzati

### Asse Secondario

Per serie con scale diverse.

**Esempio:**
```
Vendite (€) + Temperatura (°C)

Vendite €          Temp °C
3.000 ┤              30°
2.500 ┤ ████   ╱╲    25°
2.000 ┤ ████  ╱  ╲   20°
1.500 ┤ ████ ╱    ╲  15°
1.000 ┤ ████╱      ╲ 10°
      └─┴──┴──┴──┴──┴─
       Gen Feb Mar Apr

█ Vendite (asse sin.)
╱ Temperatura (asse des.)
```

**Quando usare:**
- 2 serie con unità di misura diverse
- Range di valori molto diversi

**Creare:**
```
Excel:
1. Click destro su serie → Formato serie dati
2. Opzioni serie → Asse secondario

Sheets:
Editor grafico → Personalizza → Serie → Asse
```

---

### Linee di Tendenza

Mostrano trend generale dei dati.

```
Dati effettivi + Tendenza:

 100┤        ●         ╱
  80┤     ●    ●    ╱  ← Linea tendenza
  60┤  ●          ╱
  40┤         ●╱
  20┤   ●  ╱
    └─┴─┴─┴─┴─┴─
```

**Tipi:**

1. **Lineare:** `y = mx + b`
   - Crescita/decrescita costante

2. **Esponenziale:** `y = ab^x`
   - Crescita accelerata

3. **Logaritmica:** `y = a ln(x) + b`
   - Crescita che rallenta

4. **Polinomiale:** `y = ax^2 + bx + c`
   - Curve complesse

5. **Potenza:** `y = ax^b`
   - Relazioni proporzionali

6. **Media mobile:** media ultimi N punti
   - Smussare fluttuazioni

**Aggiungere:**
```
Excel:
Click su serie → Aggiungi linea di tendenza

Sheets:
Editor grafico → Personalizza → Serie → Linea di tendenza
```

**Opzioni utili:**
- Mostra equazione sul grafico
- Mostra R² (coefficiente determinazione)
- Previsione avanti/indietro

---

### Barre di Errore

Indicano incertezza o variabilità.

```
 10┤    I
  9┤    ■
  8┤    I    ← Barra errore
  7┤
```

**Tipi errore:**
- Deviazione standard
- Errore standard
- Percentuale
- Valore fisso
- Personalizzato

**Quando usare:**
- Dati scientifici
- Statistiche
- Misurazioni con incertezza
- A/B testing results

---

### Grafici Sparkline

Mini-grafici in celle singole.

```
Prodotto | Trend Q1-Q4
---------|-------------
iPhone   | ▂▄▆█
iPad     | █▆▄▂
MacBook  | ▃▃▆█
```

**Excel:**
```
Inserisci → Sparkline → Tipo (linea/colonna/+-) → Intervallo dati
```

**Google Sheets:**
```
=SPARKLINE(A2:D2)
=SPARKLINE(A2:D2, {"charttype","column"})
=SPARKLINE(A2:D2, {"charttype","winloss"})
```

**Uso:** Dashboard compatti, tabelle con trend visivi

---

## Grafici Combinati

### Colonne + Linee

**Classico business chart:**

```
Vendite + Margine:

€4k ┤ ████      ╱───●  40%
€3k ┤ ████   ●──┘      30%
€2k ┤ ████ ──●         20%
€1k ┤ ████             10%
    └─┴──┴──┴──        0%
     Q1  Q2  Q3

█ Vendite (colonne, asse sin.)
● Margine % (linea, asse des.)
```

**Quando usare:**
- Valore assoluto + percentuale/tasso
- Volume + prezzo
- Quantità + efficienza

---

### Colonne Sovrapposte + Linea

```
Budget vs Spesa + Scostamento:

€2k ┤ ▓▓▓   ●
€1k ┤ ▓▓▓ ──●
  0 └─┴──┴──┴──  0%
€-1k       ●    -10%
           
▓ Budget  ░ Spesa  ● Scostamento %
```

---

### Torta + Barra

**Torta con esplosione dettaglio:**

```
    Budget Totale (Torta)
         ╱─╲
        │ ○ │  
         ╲─╱
    ▓▓▓ 50% Affitto
    ░░  30% Variabile ━━━→  Dettaglio variabile (Barre):
    ▒▒  20% Fisso           Cibo  ████ 15%
                            Altro ██   5%
```

---

## Dashboard e Report

### Principi Dashboard

#### Layout

```
┌─────────────────────────────────────┐
│  [TITOLO DASHBOARD]        [FILTRI] │
├──────────────┬──────────────────────┤
│  KPI Box 1   │    KPI Box 2         │
│   1.250      │     +15%             │
├──────────────┴──────────────────────┤
│  Grafico Principale (Grande)        │
│  [Trend Vendite Mensili]            │
│                                     │
├─────────────────────┬───────────────┤
│ Grafico 2           │ Grafico 3     │
│ [Per Categoria]     │ [Top 5]       │
└─────────────────────┴───────────────┘
```

**Principi:**
1. Più importante in alto/grande
2. Flow: top-left → bottom-right
3. Raggruppare info correlate
4. Spazio bianco per respiro
5. Gerarchia chiara

---

### KPI Cards

Valori chiave evidenziati.

```
┌──────────────┐  ┌──────────────┐
│ FATTURATO    │  │ CLIENTI      │
│              │  │              │
│  € 125.400   │  │    1.245     │
│  ↑ +12%      │  │    ↑ +8%     │
└──────────────┘  └──────────────┘
```

**Elementi:**
- Etichetta chiara
- Valore grande
- Trend (↑↓) e variazione %
- Colore (verde pos, rosso neg)

**Creare:**
- Celle formattate grandi
- Formattazione condizionale per colori
- Icone/simboli per frecce

---

### Filtri Interattivi

**Excel: Slicer**
```
1. Seleziona tabella/pivot
2. Inserisci → Filtro dati
3. Scegli campi
4. Collega a grafici
```

**Google Sheets: Controlli**
```
1. Dati → Controlli intervallo
2. Casella combinata/Casella di controllo
3. Collega a celle
4. Usa celle in formule grafici
```

**Esempio:**
```
[Seleziona Anno: 2024 ▼]  ← Dropdown

Grafico aggiorna automaticamente in base a selezione
```

---

### Grafici Piccoli Multipli

Serie di grafici identici per confronto.

```
Vendite per Regione:

Nord:           Centro:         Sud:
 ║ ▄▆█          ║ ▃▅▆          ║ ▂▃▅
 ╚═══           ╚═══           ╚═══
```

**Quando usare:**
- Confrontare pattern tra categorie
- Stesso tipo grafico, dati diversi
- Trend regionali/per prodotto

**Best practices:**
- Stesse scale per comparabilità
- Layout griglia ordinato
- Minimale (rimuovi decorazioni)

---

### Report Stampa

**Ottimizzazione per stampa:**

```
✅ Checklist stampa:
- [ ] Dimensioni pagina (A4, Letter)
- [ ] Orientamento (Portrait/Landscape)
- [ ] Margini adeguati
- [ ] Intestazione/piè di pagina
- [ ] Grafici ridimensionati bene
- [ ] Colori stampabili (non troppo chiari)
- [ ] Testo leggibile (min 10pt)
- [ ] Anteprima stampa OK
```

**Layout di pagina Excel:**
```
Layout di pagina → 
- Orientamento
- Dimensioni
- Margini
- Interruzioni di pagina
```

---

## Best Practices

### Regola d'Oro: Semplicità

```
"Il miglior grafico è quello più semplice
che comunica efficacemente il messaggio."
```

#### Less is More

❌ **Grafico sovraccarico:**
```
- 10 serie dati
- Tutti i colori dell'arcobaleno
- Griglia fitta
- Etichette ovunque
- Effetti 3D
- Ombre, gradienti
- Legenda enorme
```

✅ **Grafico pulito:**
```
- 2-3 serie principali
- Colori coerenti
- Griglia essenziale
- Etichette sui punti chiave
- 2D
- Stile minimale
- Legenda concisa
```

---

### Scegliere il Grafico Giusto

#### Flowchart Decisionale

```
                  Qual è l'obiettivo?
                         │
         ┌───────────────┼───────────────┐
         │               │               │
    Confronto        Trend         Composizione
         │               │               │
    Categorie?      Tempo?         Parti/Totale?
         │               │               │
    Colonne/Barre    Linee          Torta/Ciambella
         │               │               │
    Quante serie?   Continue?      Quante parti?
         │               │               │
    1→Semplice      Sì→Area        3-7→OK
    2+→Raggruppate  No→Colonne     >7→Barre
```

---

### Regole Fondamentali

#### 1. Titolo Chiaro

```
✅ "Vendite iPhone vs iPad - Q1 2025"
❌ "Grafico 1"
```

#### 2. Etichette Assi

```
✅ "Vendite (migliaia €)"
❌ Nessuna etichetta
```

#### 3. Legenda Intuitiva

```
✅ ■ iPhone 15  ■ iPhone 14
❌ ■ Serie1     ■ Serie2
```

#### 4. Colori Significativi

```
✅ Verde=Positivo, Rosso=Negativo
❌ Colori casuali
```

#### 5. Fonte Dati

```
✅ "Fonte: Vendite Interne 2025"
❌ Nessuna fonte
```

#### 6. Data/Versione

```
✅ "Aggiornato: 21/01/2026"
❌ Non datato
```

---

### Accessibilità

#### Daltonismo

```
❌ EVITARE:
- Rosso-verde puro
- Affidarsi solo a colore

✅ USARE:
- Pattern/texture diverse
- Etichette chiare
- Tool: Color Brewer (colorblind-safe)
```

**Test:** Simula daltonismo con tool online (Coblis, Adobe Color)

#### Contrasto

```
✅ Alto contrasto:
- Nero su bianco
- Blu scuro su bianco

❌ Basso contrasto:
- Grigio chiaro su bianco
- Giallo su bianco
```

#### Dimensioni Testo

```
✅ Leggibile:
- Titolo: 14-18pt
- Assi: 10-12pt
- Etichette: 8-10pt

❌ Troppo piccolo:
- Tutto < 8pt
```

---

### Performance

#### Grafici Pesanti

```
❌ Rallentano il foglio:
- 1000+ punti dati
- 20+ serie
- Grafici complessi multipli
- Aggiornamento in tempo reale

✅ Ottimizzazioni:
- Aggregare dati (medie, totali)
- Limitare serie visibili
- Usare tabelle pivot
- Grafici statici (immagini) per report
```

---

### Storytelling con Dati

#### Struttura Narrativa

```
1. Contesto:    Dove siamo?
2. Problema:    Cosa non va?
3. Analisi:     Perché succede?
4. Soluzione:   Che fare?
5. Risultati:   Cosa aspettarci?
```

**Esempio:**

```
1. Contesto:   "Vendite totali Q1: € 125k"
               [Grafico colonne semplice]

2. Problema:   "Calo 15% rispetto Q1 2024"
               [Grafico linea confronto anni]

3. Analisi:    "Prodotto X in forte calo (-40%)"
               [Grafico barre per prodotto]

4. Soluzione:  "Piano marketing Prodotto X"
               [Bullet points + proiezioni]

5. Risultati:  "Obiettivo Q2: +20%"
               [Grafico proiezione con target]
```

---

## Errori Comuni

### 1. Grafico 3D

```
❌ NO:
   ╱█╲        ← Distorce percezione
  ╱ █ ╲       ← Difficile leggere valori
 ╱  █  ╲      ← "Cool" ma inutile
╱───█───╲

✅ SI:
 █ █ █         ← Chiaro, leggibile
 █ █ █
 █ █ █
```

**Mai usare 3D a meno che sia assolutamente necessario (rarissimo)**

---

### 2. Torta con Troppi Spicchi

```
❌ NO (12 fette):
    Very confusing!
    ╱─────────╲
   ╱░▓▒█░▓▒█░▓╲
  │▒█░▓▒█░▓▒█░│  ← Illeggibile
   ╲▓▒█░▓▒█░▓▒╱
    ╲─────────╱

✅ SI (5 fette + "Altro"):
    ╱─────╲
   ╱ ░▓▒█ ╲    ← Chiaro
  │  ░▓▒█  │
   ╲ ░▓▒█ ╱
    ╲─────╱
```

**Regola:** Max 7 fette, accorpa resto in "Altro"

---

### 3. Asse Y Non da Zero (Colonne)

```
❌ FUORVIANTE:

Vendite    80│ █       █
           70│ █   █   █  ← Differenze amplificate!
           60│ █   █   █
              └─┴───┴───┴─
               A   B   C

Sembra che A sia 3x B, ma è solo 80 vs 70!

✅ ONESTO:

Vendite   100│
           80│ █       █
           60│ █   █   █  ← Proporzioni reali
           40│ █   █   █
           20│ █   █   █
            0└─┴───┴───┴─
              A   B   C
```

**Eccezione:** Linee temporali possono non partire da zero se documentato

---

### 4. Colori Inappropriati

```
❌ NO:
Verde = Perdite   ← Controintuitivo!
Rosso = Profitti

✅ SI:
Verde = Profitti  ← Standard
Rosso = Perdite
```

---

### 5. Troppi Elementi

```
❌ Chart Junk:
- Immagini di sfondo
- Texture elaborate
- Ombre pesanti
- Molti colori brillanti
- Decorazioni inutili
- Gif animate (😱)

✅ Essenziale:
- Dati
- Assi
- Etichette minime
- Colori funzionali
- Bianco/grigio chiaro sfondo
```

---

### 6. Etichette Sovrapposte

```
❌ NO:
  │ TextTextTextTextText  ← Illeggibile
  │ TextTextTextTextText
  └─

✅ SI:
  │ Text
  │     Text
  │         Text  ← Rotazione, skip, o orientamento diverso
  └─
```

---

### 7. Scala Ingannevole

```
❌ Manipolazione:

Prodotto A vs B:
80│           B=81
79│ A=79  ████
78│ ████  ████  ← Sembra B sia molto > A
  └─┴────┴────

Differenza reale: 2 unità!

✅ Onesto:
Mostra scala completa O documenta chiaramente truncation
```

---

## Esempi Pratici

### Esempio 1: Report Vendite Mensili

**Obiettivo:** Mostrare trend vendite 2024 vs 2025

**Dati:**
```
Mese | 2024  | 2025
-----|-------|-------
Gen  | 8.200 | 9.500
Feb  | 7.800 | 9.200
Mar  | 9.100 | 10.800
Apr  | 8.600 | 10.200
Mag  | 9.400 | 11.500
```

**Grafico scelto:** Linee multiple

**Perché:**
- Trend temporale
- Confronto 2 anni
- Dati continui

**Personalizzazioni:**
```
Titolo: "Vendite Mensili 2024 vs 2025"
Asse Y: "Vendite (€)"
Legenda: ● 2024  ● 2025
Colori: Blu (2024), Verde (2025)
Linea tendenza: Lineare su 2025
```

---

### Esempio 2: Quota Mercato

**Obiettivo:** Mostrare distribuzione quota mercato

**Dati:**
```
Azienda  | Quota
---------|-------
Apple    | 35%
Samsung  | 28%
Xiaomi   | 15%
Huawei   | 12%
Altri    | 10%
```

**Grafico scelto:** Ciambella

**Perché:**
- Parti di un totale (100%)
- 5 categorie (OK)
- Proporzioni chiare

**Personalizzazioni:**
```
Titolo: "Quota Mercato Smartphone - Q1 2025"
Centro ciambella: "Totale: 100%"
Ordine: Decrescente per quota
Colori: Blu (leader) → grigio (altri)
Etichette: Nome + percentuale
```

---

### Esempio 3: Confronto Performance

**Obiettivo:** Valutare 3 fornitori su 5 criteri

**Dati:**
```
Criterio   | For.A | For.B | For.C
-----------|-------|-------|-------
Prezzo     |   8   |   6   |   9
Qualità    |   7   |   9   |   7
Velocità   |   9   |   7   |   6
Assistenza |   7   |   8   |   8
Flessibilità|  8   |   7   |   7
```

**Grafico scelto:** Radar

**Perché:**
- Multi-dimensionale
- Confronto 3 entità
- Profilo completo visibile

**Personalizzazioni:**
```
Titolo: "Valutazione Fornitori - 5 Criteri"
Serie: 3 linee colorate diverse
Scala: 0-10
Evidenzia: Fornitore A (raccomandato)
```

---

### Esempio 4: Dashboard Esecutivo

**Obiettivo:** Overview KPI aziendali

**Layout:**
```
┌────────────────────────────────────────────┐
│  DASHBOARD ESECUTIVO - Q1 2025             │
├──────────┬──────────┬──────────┬───────────┤
│ FATTURATO│ MARGINE  │ CLIENTI  │ NPS       │
│ €412k    │  23,5%   │  1.245   │  +67      │
│ ↑ +15%   │ ↓ -1,2%  │ ↑ +8%    │ ↑ +3      │
├──────────┴──────────┴──────────┴───────────┤
│ TREND VENDITE (Linea)                      │
│ [Grafico linee ultimo anno]                │
├─────────────────────┬──────────────────────┤
│ TOP 5 PRODOTTI      │ VENDITE PER REGIONE  │
│ [Barre orizzontali] │ [Mappa geografica]   │
├─────────────────────┴──────────────────────┤
│ PIPELINE VENDITE (Imbuto)                  │
│ [Funnel chart]                             │
└────────────────────────────────────────────┘
```

**Elementi chiave:**
- KPI cards in alto (attenzione immediata)
- Trend centrale (grande, importante)
- Dettagli sotto (supporto decisioni)
- Colori coerenti (verde pos, rosso neg)
- Aggiornamento: automatico da dati

---

## Strumenti e Risorse

### Software Grafici Avanzati

**Business Intelligence:**
- **Tableau:** Dashboard interattivi professionali
- **Power BI:** Integrazione Microsoft, potente
- **Google Data Studio:** Gratuito, web-based
- **Qlik Sense:** Analisi associative

**Programmazione:**
- **Python:** Matplotlib, Seaborn, Plotly
- **R:** ggplot2, Lattice
- **JavaScript:** D3.js, Chart.js, Highcharts

### Template e Ispirazione

**Gallerie:**
- Tableau Public Gallery
- Power BI Community
- Dribbble (data visualization)
- Information is Beautiful Awards

**Tutorial:**
- **YouTube:** Chandoo, ExcelIsFun
- **Blog:** Storytelling with Data, FlowingData
- **Libri:** 
  - "The Visual Display of Quantitative Information" - Tufte
  - "Storytelling with Data" - Knaflic
  - "Good Charts" - Berinato

### Verifica Accessibilità

**Tool online:**
- Coblis (Color Blindness Simulator)
- WebAIM Contrast Checker
- Colorbrewer2.org (palette safe)

---

## Checklist Grafico Perfetto

Prima di pubblicare un grafico:

### ✅ Contenuto
- [ ] Tipo grafico appropriato per i dati
- [ ] Dati accurati e aggiornati
- [ ] Messaggio chiaro e univoco
- [ ] Nessun dato fuorviante o manipolato

### ✅ Design
- [ ] Titolo descrittivo e chiaro
- [ ] Assi etichettati con unità di misura
- [ ] Legenda leggibile (se presente)
- [ ] Colori significativi e coerenti
- [ ] Font leggibili (min 10pt)
- [ ] Nessun elemento decorativo inutile
- [ ] Spazio bianco adeguato

### ✅ Tecnico
- [ ] Scala assi appropriata
- [ ] Formato numeri corretto
- [ ] Griglia utile ma non invadente
- [ ] Risoluzione adeguata (se esportato)
- [ ] Stampa/visualizzazione OK

### ✅ Accessibilità
- [ ] Contrasto colori adeguato (4.5:1)
- [ ] Palette colorblind-friendly
- [ ] Non solo colore per trasmettere info
- [ ] Testo sufficientemente grande

### ✅ Contestuale
- [ ] Fonte dati citata
- [ ] Data/versione indicata
- [ ] Note esplicative se necessarie
- [ ] Audience appropriata

---

## Quiz Rapido

### 1. Quale grafico per trend temporale?
A) Torta  
B) Linea ✅  
C) Radar  

### 2. Max fette torta consigliate?
A) Illimitate  
B) 3  
C) 5-7 ✅  

### 3. Colonne iniziano sempre da 0?
A) Si ✅  
B) No  
C) Dipende  

### 4. Grafici 3D sono raccomandati?
A) Si  
B) No ✅  
C) Solo per presentazioni  

### 5. Scatter plot mostra?
A) Trend temporale  
B) Correlazioni ✅  
C) Proporzioni  

---

## Conclusione

### Riepilogo

I grafici sono **strumenti potenti** per:
- 📊 Comunicare dati complessi
- 📈 Evidenziare trend
- 🎯 Supportare decisioni
- 💡 Raccontare storie

### Regole d'Oro

```
1. Semplicità > Complessità
2. Chiarezza > Bellezza
3. Onestà > Effetto
4. Funzione > Forma
5. Audience > Autore
```

### Pratica

```
"Il miglior modo per imparare
è creare molti grafici,
chiedere feedback,
e iterare."
```

### Next Steps

1. ✅ Crea 1 grafico al giorno per 30 giorni
2. ✅ Studia grafici nei media (buoni e cattivi)
3. ✅ Sperimenta tipi diversi su stessi dati
4. ✅ Chiedi feedback a colleghi/amici
5. ✅ Analizza grafici di professionisti

---

**Buona visualizzazione!** 📊📈🥧

*Tempo lettura: ~90 minuti*  
*Livello: Base → Avanzato*  
*Aggiornato: Gennaio 2026*
