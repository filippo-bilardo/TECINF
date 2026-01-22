# Guida alla Formattazione dei Fogli di Calcolo

**Formattazione professionale per Google Sheets e Microsoft Excel**

---

## Indice

1. [Introduzione alla Formattazione](#introduzione-alla-formattazione)
2. [Formattazione Caratteri e Testo](#formattazione-caratteri-e-testo)
3. [Formattazione Numeri](#formattazione-numeri)
4. [Allineamento e Orientamento](#allineamento-e-orientamento)
5. [Colori e Riempimento](#colori-e-riempimento)
6. [Bordi e Linee](#bordi-e-linee)
7. [Formattazione Condizionale](#formattazione-condizionale)
8. [Stili e Temi](#stili-e-temi)
9. [Formattazione Righe e Colonne](#formattazione-righe-e-colonne)
10. [Best Practices](#best-practices)
11. [Esempi Pratici](#esempi-pratici)

---

## Introduzione alla Formattazione

### Cos'è la Formattazione

La formattazione è l'insieme di **proprietà visive** applicate ai dati senza modificarne il contenuto:
- **Aspetto** del testo (font, dimensione, stile)
- **Rappresentazione** dei numeri (decimali, valuta, percentuale)
- **Colori** di sfondo e testo
- **Bordi** e linee separatrici
- **Allineamento** e orientamento
- **Formattazione condizionale** basata su regole

### Perché è Importante

✅ **Leggibilità**: Dati più facili da comprendere  
✅ **Professionalità**: Documenti curati e presentabili  
✅ **Comunicazione**: Evidenzia informazioni chiave  
✅ **Organizzazione**: Struttura visiva chiara  
✅ **Analisi**: Identifica rapidamente pattern e anomalie  

### Formattazione vs Contenuto

```
Contenuto:        1234.56
Formattazione:    € 1.234,56
                  1.234,56 €
                  $1,234.56
                  1,23E+03
```

**Il valore resta 1234.56, cambia solo come viene mostrato!**

---

## Formattazione Caratteri e Testo

### Font (Tipo di Carattere)

#### Font più Utilizzati

**Professionali:**
```
Arial          - Chiaro, leggibile, universale
Calibri        - Default Excel, moderno
Helvetica      - Elegante, professionale
Verdana        - Ottimo per monitor
```

**Serif (con grazie):**
```
Times New Roman - Formale, documenti ufficiali
Georgia         - Leggibile, elegante
```

**Monospazio:**
```
Courier New    - Codice, allineamento caratteri
Consolas       - Moderno, codice
```

#### Cambiare Font

**Excel:**
```
1. Seleziona celle
2. Home → Font → Scegli font
   O
   Ctrl+Shift+F → Seleziona
```

**Google Sheets:**
```
1. Seleziona celle
2. Barra strumenti → Menu font
3. Altri caratteri... (per font aggiuntivi)
```

---

### Dimensione Carattere

#### Dimensioni Standard

```
8 pt    - Molto piccolo (note a piè di pagina)
9 pt    - Piccolo (tabelle compatte)
10 pt   - Standard dati
11 pt   - Default Excel/Sheets
12 pt   - Leggibile, presentazioni
14 pt   - Sottotitoli
16 pt   - Titoli sezioni
18+ pt  - Titoli principali
```

#### Tasti Rapidi Dimensione

```
Ctrl+Shift+>    Aumenta
Ctrl+Shift+<    Diminuisce
```

---

### Stili Carattere

#### Grassetto (Bold)
```
Tasto rapido:   Ctrl+B (Win) / Cmd+B (Mac)
Quando usare:   Intestazioni, totali, valori importanti
```

**Esempio:**
```
| Prodotto | Vendite | ← Intestazioni in grassetto
|----------|---------|
| iPhone   | 1.250   |
| iPad     | 890     |
| TOTALE   | 2.140   | ← Totale in grassetto
```

#### Corsivo (Italic)
```
Tasto rapido:   Ctrl+I (Win) / Cmd+I (Mac)
Quando usare:   Note, citazioni, evidenziare termini
```

#### Sottolineato (Underline)
```
Tasto rapido:   Ctrl+U (Win) / Cmd+U (Mac)
Quando usare:   Raramente (può confondere con link)
```

#### Barrato (Strikethrough)
```
Tasto rapido:   Alt+Shift+5 (Excel)
Quando usare:   Elementi completati, deprecati
```

**Esempio:**
```
☐ Comprare latte
☑ Pagare bolletta   ← Barrato
☐ Chiamare Mario
```

---

### Colore Testo

#### Palette Standard

```
🔴 Rosso      - Negativi, errori, urgenze
🟢 Verde      - Positivi, successi, completati
🔵 Blu        - Informativi, link, note
🟡 Giallo     - Attenzione (meglio su sfondo)
🟠 Arancione  - Avvisi, priorità media
⚫ Nero       - Testo standard
⚪ Bianco     - Su sfondo scuro
```

#### Applicare Colore

**Excel:**
```
1. Seleziona celle
2. Home → Colore carattere (A▼)
3. Scegli colore
   O
   Altri colori → RGB/Esadecimale
```

**Google Sheets:**
```
1. Seleziona celle
2. Barra strumenti → Icona A
3. Seleziona colore
```

**Tasti Rapidi Colore:**
```
Non esistono tasti standard predefiniti
Consiglio: usa Formattazione condizionale per automazione
```

---

### Effetti Testo Speciali

#### Apice e Pedice

**Apice (Superscript):**
```
Uso: Potenze, note a piè
Esempio: X² + Y² = Z²
          E=mc²
```

**Pedice (Subscript):**
```
Uso: Formule chimiche
Esempio: H₂O, CO₂, C₆H₁₂O₆
```

**Come applicare (Excel):**
```
1. Seleziona carattere specifico
2. Ctrl+1 → Effetti
3. Apice o Pedice
```

**Google Sheets:**
```
Formato → Testo → Apice/Pedice
```

---

## Formattazione Numeri

### Tipi di Formato Numerico

#### 1. Numero Generale

```
Input:     1234.567
Output:    1234.567

Default, nessuna formattazione speciale
```

#### 2. Numero con Decimali

```
1 decimale:    1234.6
2 decimali:    1234.57
3 decimali:    1234.567

Separatore migliaia:
Italia:        1.234,57
USA:           1,234.57
```

**Formato Personalizzato:**
```
#.##0,00       - Italia (punto migliaia, virgola decimale)
#,##0.00       - USA (virgola migliaia, punto decimale)
```

#### 3. Valuta

```
Euro:          € 1.234,56
Dollaro:       $ 1,234.56
Sterlina:      £ 1,234.56
Yen:           ¥ 1,235
```

**Applicare Valuta:**
```
Excel:
Home → Formato numero → Valuta
O Ctrl+Shift+4 ($ in USA)

Google Sheets:
Formato → Numero → Valuta
Scegli simbolo
```

**Formato Personalizzato Valuta:**
```
€ #.##0,00            - Euro con 2 decimali
$ #,##0.00            - Dollaro con 2 decimali
€ #.##0,00;[Rosso]-€ #.##0,00  - Negativi in rosso
```

#### 4. Contabilità

```
Differenza con Valuta:
Valuta:        € 1.234,56
Contabilità:   €  1.234,56  ← Simbolo allineato a sinistra
               € (234,56)    ← Negativi tra parentesi
```

#### 5. Percentuale

```
0,25      →  25%
0,05      →  5%
1,50      →  150%
0,0025    →  0,25%

Tasto rapido: Ctrl+Shift+5
```

**Decimali Percentuale:**
```
25%       - 0 decimali
25,0%     - 1 decimale
25,00%    - 2 decimali
25,50%    - Valore intermedio
```

#### 6. Frazione

```
0,5       →  1/2
0,25      →  1/4
0,333     →  1/3
2,75      →  2 3/4
```

**Tipi Frazione:**
```
? ?/?         - Automatico (1/2)
? ??/??       - Fino a 2 cifre (33/99)
? ?/2         - Mezzi (1/2, 3/2)
? ?/4         - Quarti (1/4, 3/4)
? ?/8         - Ottavi
```

#### 7. Notazione Scientifica

```
1500000      →  1,50E+06
0,00032      →  3,20E-04
6,022E+23    ←  Numero di Avogadro
```

**Quando usare:**
- Numeri molto grandi
- Numeri molto piccoli
- Calcoli scientifici

---

### Data e Ora

#### Formati Data

**Standard Italia:**
```
21/01/2026          - gg/mm/aaaa
21/01/26            - gg/mm/aa
21 gennaio 2026     - gg mese aaaa
21 gen 2026         - gg mmm aaaa
Lunedì 21/01/2026   - Giorno gg/mm/aaaa
```

**Standard Internazionale:**
```
2026-01-21          - ISO 8601 (anno-mese-giorno)
01/21/2026          - USA (mm/gg/aaaa)
21.01.2026          - Germania
```

**Personalizzati:**
```
gg/mm/aaaa          21/01/2026
gg-mm-aaaa          21-01-2026
gggg, gg mmmm aaaa  Martedì, 21 gennaio 2026
mmm-aa              gen-26
mmmm aaaa           gennaio 2026
```

#### Formati Ora

```
14:30               - 24h
14:30:45            - 24h con secondi
2:30 PM             - 12h
2:30:45 PM          - 12h con secondi
14:30:45.123        - Con millisecondi
```

**Combinati:**
```
21/01/2026 14:30
2026-01-21 14:30:45
Martedì 21/01 alle 14:30
```

#### Codici Formato Data/Ora

```
gg      - Giorno (01-31)
g       - Giorno senza zero (1-31)
gggg    - Giorno settimana (Lunedì)
ggg     - Giorno settimana breve (Lun)
mm      - Mese (01-12)
m       - Mese senza zero (1-12)
mmmm    - Nome mese (Gennaio)
mmm     - Nome mese breve (Gen)
aaaa    - Anno 4 cifre (2026)
aa      - Anno 2 cifre (26)

hh      - Ora (00-23)
h       - Ora senza zero (0-23)
mm      - Minuti (00-59)
m       - Minuti senza zero (0-59)
ss      - Secondi (00-59)
AM/PM   - Indicatore 12h
```

---

### Formati Personalizzati

#### Sintassi Base

```
[Positivi];[Negativi];[Zero];[Testo]
```

**Esempio:**
```
#.##0,00;[Rosso]-#.##0,00;0,00;"Non numerico"

Positivo:  1.234,56
Negativo: -1.234,56 (in rosso)
Zero:      0,00
Testo:     Non numerico
```

#### Simboli Formato

```
0       - Cifra obbligatoria (mostra 0 se assente)
#       - Cifra facoltativa (nasconde 0 non significativi)
?       - Cifra con spazio (allineamento)
.       - Separatore decimale (dipende da locale)
,       - Separatore migliaia
%       - Percentuale (moltiplica per 100)
E+      - Notazione scientifica
"testo" - Testo letterale
@       - Segnaposto per testo
*       - Ripete carattere successivo
_       - Spazio largo come carattere successivo
```

#### Esempi Formati Personalizzati

**Numeri con Prefisso/Suffisso:**
```
#.##0,00" kg"          1.234,56 kg
"€ "#.##0,00           € 1.234,56
"Codice: "0000         Codice: 0123
```

**Numeri Positivi/Negativi Diversi:**
```
#.##0,00;(#.##0,00)    1.234,56  o  (1.234,56)
#.##0;-#.##0" ↓"       1234  o  -1234 ↓
[Verde]#.##0;[Rosso]-#.##0  (colorati)
```

**Nascondere Valori:**
```
;;;                    Nasconde tutto
;;                     Nasconde zero
#.##0;-#.##0;          Nasconde zero, mostra altri
```

**Telefono:**
```
"(+39) "000" "000" "0000    (+39) 333 123 4567
000"-"000"-"0000             123-456-7890
```

**Codici:**
```
"IT"00000                    IT00123
00000"-"0000                 00123-4567
```

**Misurazioni:**
```
#.##0,00" m²"                45,67 m²
#.##0,0" °C"                 23,5 °C
#.##0" kg"                   75 kg
```

---

## Allineamento e Orientamento

### Allineamento Orizzontale

#### Tipi di Allineamento

```
┌─────────────────┐
│ Sinistra        │  ← Standard per testo
│        Destra   │  ← Standard per numeri
│     Centro      │  ← Intestazioni
│  Giustificato   │  ← Testo lungo
└─────────────────┘
```

**Quando usare:**
- **Sinistra**: Testo, nomi, descrizioni
- **Destra**: Numeri, valute, quantità
- **Centro**: Intestazioni, titoli, etichette corte
- **Giustificato**: Paragrafi lunghi (raro nei fogli)

**Tasti Rapidi:**
```
Ctrl+Shift+L    Allinea sinistra
Ctrl+Shift+R    Allinea destra
Ctrl+Shift+E    Centra
```

#### Rientro

```
Livello 0:  Testo
Livello 1:    Testo rientrato
Livello 2:      Testo più rientrato
```

**Aumentare/Diminuire Rientro:**
```
Excel: Home → Aumenta/Diminuisci rientro
Tasti: Ctrl+Alt+Tab / Ctrl+Alt+Shift+Tab
```

---

### Allineamento Verticale

```
┌─────────────┐
│    Alto     │ ← Allinea in alto
├─────────────┤
│   Centro    │ ← Allinea al centro
├─────────────┤
│   Basso     │ ← Allinea in basso
└─────────────┘
```

**Default:** Basso per dati, Centro per intestazioni

---

### Orientamento Testo

#### Rotazione

```
  0°  → Orizzontale standard
 45°  → Diagonale ascendente ↗
 90°  → Verticale ↑
-45°  → Diagonale discendente ↘
-90°  → Verticale ↓
```

**Quando usare:**
- Intestazioni colonne strette
- Etichette grafici
- Design creativo
- Risparmio spazio

**Come applicare:**
```
Excel:
1. Seleziona celle
2. Home → Orientamento
3. Scegli angolo o personalizza

Google Sheets:
Formato → Rotazione testo
```

#### Testo Verticale

```
T
e
s
t
o
```

Ogni lettera su una riga.

---

### Testo a Capo

#### A Capo Automatico

```
Cella stretta:
┌────────────┐
│ Questo è un│
│ testo      │
│ lungo che  │
│ va a capo  │
└────────────┘
```

**Attivare:**
```
Excel:   Home → A capo automatico
Sheets:  Formato → Testo a capo → A capo automatico
Tasto:   Alt+Invio (a capo manuale nella cella)
```

#### Modalità A Capo

**A capo automatico:**
- Testo si adatta alla larghezza cella
- Altezza riga aumenta automaticamente

**Ritaglia:**
- Testo nascosto se troppo lungo
- Non aumenta altezza riga

**Overflow:**
- Testo invade celle adiacenti vuote
- Default per nuove celle

---

### Unione Celle

#### Tipi di Unione

**Unisci e centra:**
```
┌──────┬──────┬──────┐
│   TITOLO UNICO     │ ← 3 celle unite e centrate
├──────┼──────┼──────┤
│  A1  │  B1  │  C1  │
└──────┴──────┴──────┘
```

**Unisci attraverso:**
- Unisce celle in ogni riga separatamente

**Unisci celle:**
- Unisce senza centrare

**Annulla unione:**
- Ripristina celle separate

#### ⚠️ Problemi Unione Celle

❌ **Evitare quando possibile:**
- Problemi con ordinamento
- Difficoltà con formule
- Complicazioni copia/incolla
- Navigazione confusa

✅ **Alternative migliori:**
- Centra contenuto senza unire
- Usa formattazione condizionale per evidenziare
- Allinea testo in modo creativo

---

## Colori e Riempimento

### Colore Sfondo (Riempimento)

#### Colori Standard

```
🟥 Rosso       - Errori, urgenze, negativi
🟩 Verde       - Successi, positivi, completati
🟦 Blu         - Informazioni, intestazioni
🟨 Giallo      - Attenzione, evidenziazione
🟧 Arancione   - Avvisi, priorità media
🟪 Viola       - Categorie speciali
⬜ Bianco      - Standard, default
⬛ Grigio      - Disabilitato, totali
```

#### Applicare Colore Sfondo

**Excel:**
```
Home → Colore riempimento (secchio)
Tasto rapido: Alt+H, H (poi scegli colore)
```

**Google Sheets:**
```
Barra strumenti → Icona secchio
```

#### Sfumature e Motivi (Solo Excel)

**Sfumatura:**
```
1. Formato celle → Riempimento
2. Effetti riempimento
3. Sfumatura: verticale, orizzontale, diagonale
4. Scegli 2+ colori e direzione
```

**Motivo:**
```
- Punti
- Linee diagonali
- Griglia
- Righe orizzontali
```

**Uso:** Raro, meglio colori solidi per chiarezza.

---

### Schemi Colore Professionali

#### Schema Monocromatico

```
Basato su un colore con diverse tonalità:

Blu Scuro   #003366  ■ Intestazioni
Blu Medio   #0066CC  ■ Sottoheader
Blu Chiaro  #CCE5FF  ■ Dati alternati
```

#### Schema Complementare

```
Contrasto alto:

Blu     #0066CC  ■
Arancio #FF9900  ■
```

#### Schema Analogico

```
Colori vicini nella ruota:

Verde   #339933  ■
Giallo  #CCCC00  ■
Arancio #FF9900  ■
```

#### Schema Triadico

```
3 colori equidistanti:

Rosso   #CC3333  ■
Giallo  #CCCC00  ■
Blu     #3333CC  ■
```

---

### Palette Corporate

#### Esempi Aziendali

**Professionale/Corporate:**
```
Navy        #003366  ■
Grigio      #999999  ■
Bianco      #FFFFFF  □
```

**Tech/Startup:**
```
Blu elettrico  #0099FF  ■
Verde lime     #66FF66  ■
Nero           #000000  ■
```

**Finanziaria/Consulenza:**
```
Blu royal      #003D7A  ■
Oro            #FFD700  ■
Grigio scuro   #333333  ■
```

#### Accessibilità Colori

✅ **Buon Contrasto:**
```
Nero su bianco      ■ □  Ratio 21:1
Blu scuro su bianco ■ □  Ratio 12:1
Verde su bianco     ■ □  Ratio 7:1
```

❌ **Cattivo Contrasto:**
```
Giallo su bianco    ■ □  Ratio 1.8:1
Grigio chiaro su bianco  ■ □  Ratio 2:1
```

**Standard WCAG:**
- **AA:** Contrasto minimo 4.5:1
- **AAA:** Contrasto minimo 7:1

**Strumenti:**
- WebAIM Contrast Checker
- Coolors.co
- Adobe Color

---

### Righe Alternate (Banding)

Migliora leggibilità tabelle lunghe.

```
Riga 1  □□□□□ Bianco
Riga 2  ████ Grigio chiaro
Riga 3  □□□□□ Bianco
Riga 4  ████ Grigio chiaro
```

**Applicare (Google Sheets):**
```
1. Seleziona intervallo
2. Formato → Righe alternate
3. Scegli colori
```

**Applicare (Excel):**
```
1. Converti in tabella (Ctrl+T)
2. Stili predefiniti con banding automatico
   O
   Formattazione condizionale con formula:
   =RIF.RIGA(MOD(RIF.RIGA();2)=0
```

---

## Bordi e Linee

### Tipi di Bordo

#### Posizioni

```
┌────────┐
│ Bordo  │  ← Superiore
│ Celle  │
└────────┘  ← Inferiore
↑        ↑
Sinistra Destra

Bordo esterno: tutto il perimetro
Bordo interno: tra celle selezionate
Tutti i bordi: griglia completa
```

#### Stili Linea

```
─────────  Linea continua sottile
━━━━━━━━━  Linea continua spessa
─ ─ ─ ─ ─  Linea tratteggiata
─ · ─ · ─  Linea punto-tratto
═════════  Linea doppia
```

#### Colori Bordo

Personalizzabili, default nero.

---

### Applicare Bordi

#### Metodo Rapido (Excel)

```
Home → Bordi (icona griglia) → Scegli tipo
```

**Opzioni comuni:**
```
⊡  Bordo inferiore       (separa intestazioni)
□  Bordo esterno         (racchiude tabella)
▦  Tutti i bordi         (griglia completa)
⊟  Bordo superiore/inferiore (divide sezioni)
▥  Bordo spesso esterno  (enfasi tabella)
```

#### Metodo Avanzato

```
Excel:
1. Seleziona celle
2. Ctrl+1 (Formato celle)
3. Tab Bordo
4. Scegli stile, colore, posizione
5. Preview in anteprima

Google Sheets:
1. Seleziona celle
2. Bordi (icona griglia quadrata)
3. Stile, colore, tipo
```

#### Tasti Rapidi Bordi

```
Ctrl+Shift+&    Bordo esterno (Excel)
Ctrl+Shift+_    Rimuovi bordi (Excel)
```

---

### Best Practices Bordi

#### Tabelle Professionali

```
┌─────────────────────────────┐
│ Prodotto  │ Quantità │ Tot  │ ← Intestazioni: bordo inferiore doppio
├───────────┼──────────┼──────┤
│ iPhone    │    12    │ 1.200│
│ iPad      │     8    │   800│ ← Nessun bordo tra righe dati
│ MacBook   │     5    │ 2.500│
├───────────┼──────────┼──────┤
│ TOTALE    │    25    │ 4.500│ ← Totale: bordo superiore singolo, inferiore doppio
└═══════════╧══════════╧══════┘
```

#### Linee Guida

✅ **DA FARE:**
- Bordo doppio sotto intestazioni
- Bordo singolo sopra totali
- Bordo esterno attorno a tutta la tabella
- Usare grigio invece di nero per bordi interni (più leggero)

❌ **DA EVITARE:**
- Bordi su ogni singola cella (troppo carico)
- Bordi spessi ovunque
- Troppi colori diversi
- Stili misti senza logica

---

## Formattazione Condizionale

### Cos'è

Formattazione che **cambia automaticamente** in base al valore della cella o a regole definite.

### Tipi di Regole

#### 1. Scala di Colori (Color Scale)

```
Valori bassi → Rosso  🟥
Valori medi  → Giallo 🟨
Valori alti  → Verde  🟩
```

**Quando usare:** Heatmap, visualizzare distribuzione valori

**Esempio:**
```
Temperature:
5°C  ████ Blu
15°C ████ Giallo
25°C ████ Rosso
```

**Applicare:**
```
Excel/Sheets:
Formato → Formattazione condizionale → Scala di colori
Scegli: 2 colori, 3 colori, personalizza
```

---

#### 2. Barre dei Dati (Data Bars)

```
Vendite:
100  ██████████ 
80   ████████
60   ██████
40   ████
```

Barra proporzionale al valore nella cella.

**Quando usare:** Confronto visivo rapido, grafici in cella

**Opzioni:**
- Riempimento solido/gradiente
- Mostra/nascondi valore
- Colore positivi/negativi diverso
- Direzione: sinistra→destra, destra→sinistra

---

#### 3. Set di Icone (Icon Sets)

```
Prestazioni:
90%  ✅ Verde    (Eccellente)
70%  ⚠️ Giallo   (Buono)
40%  ❌ Rosso    (Insufficiente)
```

**Icone disponibili:**
```
Indicatori:   ●●●, ▲▼■, ☑☐✗
Frecce:       ↑→↓, ⬆➡⬇
Bandiere:     🏁🏁🏁
Emoticon:     😊😐😞
Stelle:       ★★★
Semafori:     🔴🟡🟢
```

**Quando usare:** KPI, dashboard, indicatori stato

---

#### 4. Regole Maggiore/Minore Di

```
Se cella > 100    → Sfondo verde
Se cella < 0      → Testo rosso
Se cella = 0      → Grigio
```

**Applicare:**
```
1. Seleziona celle
2. Formattazione condizionale → Regole celle
3. Maggiore di... / Minore di... / Uguale a...
4. Inserisci valore
5. Scegli formato
```

---

#### 5. Primi/Ultimi 10

```
Top 10 valori       → Verde
Bottom 10 valori    → Rosso
Sopra media         → Blu
Sotto media         → Grigio
```

**Esempio uso:**
```
Classifica studenti:
- Top 10%: Eccellenti
- Bottom 10%: Recupero necessario
```

---

#### 6. Valori Duplicati/Univoci

```
Valori duplicati    → Evidenzia rosso
Valori unici        → Evidenzia verde
```

**Quando usare:**
- Trovare duplicati in elenchi
- Validare dati
- Pulizia database

---

#### 7. Formule Personalizzate

La **più potente**: definisci regola con formula.

**Esempi:**

**Righe alternate colorate:**
```
Formula:  =RIF.RIGA(MOD(RIF.RIGA();2)=0
Formato:  Sfondo grigio chiaro
```

**Evidenziare intera riga se una cella soddisfa condizione:**
```
Formula:  =$E2>1000
Formato:  Sfondo verde
Applica:  $A$2:$F$100
```
($ prima di E fissa la colonna, niente $ su 2 permette cambio riga)

**Weekend colorati:**
```
Formula:  =GIORNI.SETTIMANA($A2;2)>5
Formato:  Sfondo azzurro
```

**Scadenze imminenti:**
```
Formula:  =E($B2<>"",$B2-OGGI()<=7)
Formato:  Testo rosso grassetto
```

**Valori sopra media:**
```
Formula:  =A2>MEDIA($A$2:$A$100)
Formato:  Sfondo verde
```

---

### Gestire Regole

#### Ordine Priorità

Regole valutate dall'alto verso il basso.

```
Priorità 1: Valore = 100      → Grassetto
Priorità 2: Valore > 50       → Verde
Priorità 3: Valore > 0        → Blu

Se valore = 100: applica Priorità 1 (e anche 2, 3 se "Interrompi" non attivo)
```

#### Modificare Regole

```
Excel:
Home → Formattazione condizionale → Gestisci regole
- Modifica regola
- Elimina regola
- Cambia priorità (↑↓)

Google Sheets:
Formato → Formattazione condizionale
- Elenco regole attive
- Modifica/Elimina
```

---

### Best Practices Formattazione Condizionale

✅ **DA FARE:**
- Usare per evidenziare eccezioni, non normalità
- Limitare colori (2-3 massimo)
- Testare su dataset completo
- Documentare regole complesse
- Usare intervalli specifici, non colonne intere (performance)

❌ **DA EVITARE:**
- Troppi colori (arcobaleno confuso)
- Sovrapposizione regole non gestite
- Formule volatili (OGGI(), CASUALE()) in fogli grandi
- Regole su colonne intere con milioni di righe
- Formattazione condizionale al posto di filtri

---

## Stili e Temi

### Stili Cella (Excel)

Formattazione predefinita salvata con un nome.

#### Stili Predefiniti

```
Buono        - Verde, grassetto
Errato       - Rosso, grassetto
Neutro       - Giallo
Calcolo      - Blu, grassetto
Titolo       - Grande, centrato
Intestazione - Grassetto, bordo
Input        - Giallo, bordo
Output       - Grigio, grassetto
```

#### Applicare Stile

```
1. Seleziona celle
2. Home → Stili cella
3. Scegli stile
```

#### Creare Stile Personalizzato

```
1. Formatta una cella come desiderato
2. Home → Stili cella → Nuovo stile cella
3. Assegna nome
4. Seleziona proprietà incluse:
   - Numero
   - Allineamento
   - Carattere
   - Bordo
   - Riempimento
   - Protezione
5. OK
```

**Vantaggio:** Modifica stile → aggiorna tutte le celle con quello stile.

---

### Temi (Excel)

Combinazione di colori, font ed effetti per tutto il documento.

#### Temi Predefiniti

```
Office        - Neutro, professionale
Facet         - Moderno, colorato
Integral      - Pulito, business
Ion           - Tech, dinamico
```

#### Componenti Tema

**Colori tema:**
- 12 colori (4 testo/sfondo, 6 accento, 2 link)
- Usati in grafici, formattazione condizionale, stili

**Font tema:**
- Font intestazioni
- Font corpo

**Effetti tema:**
- Ombre, riflessi, smussi
- Usati per forme, grafici

#### Applicare Tema

```
Layout di pagina → Temi → Scegli tema
```

**Personalizzare:**
```
Layout di pagina → Colori/Font/Effetti → Personalizza
Salva tema personalizzato
```

---

### Tabelle Formattate (Excel)

Converti intervallo in **tabella**.

#### Vantaggi Tabelle

✅ Filtri automatici  
✅ Formule strutturate: `=Tabella[@Colonna]`  
✅ Espansione automatica  
✅ Stili predefiniti  
✅ Riferimenti dinamici  
✅ Riga totali automatica  

#### Creare Tabella

```
1. Seleziona dati (incluse intestazioni)
2. Ctrl+T o Inserisci → Tabella
3. Conferma intervallo e intestazioni
4. OK
```

#### Stili Tabella

```
Strumenti tabella → Progettazione → Stili tabella
```

**Opzioni:**
- Chiaro, medio, scuro
- Righe alternate
- Colonne alternate
- Prima/ultima colonna evidenziata
- Riga intestazione
- Riga totali

---

## Formattazione Righe e Colonne

### Dimensioni

#### Altezza Righe

**Default:** ~15 punti (20 pixel)

**Modificare:**
```
1. Seleziona righe (click su numero)
2. Click destro → Altezza riga
3. Inserisci valore (punti)
   O
   Trascina bordo tra intestazioni righe
```

**Adatta automatica:**
```
Doppio click su bordo tra righe
O
Selezione → Click destro → Adatta altezza riga
```

**Tasti rapidi:**
```
Ctrl+Shift+8    - Excel: adatta altezza
```

#### Larghezza Colonne

**Default:** 64 pixel (~8,43 caratteri)

**Modificare:**
```
1. Seleziona colonne (click su lettera)
2. Click destro → Larghezza colonna
3. Inserisci valore (caratteri)
   O
   Trascina bordo tra intestazioni colonne
```

**Adatta automatica:**
```
Doppio click su bordo tra colonne
O
Selezione → Click destro → Adatta larghezza colonna
```

**Tasti rapidi:**
```
Alt+H, O, I     - Excel: adatta larghezza
```

---

### Nascondere/Mostrare

#### Nascondere

```
Righe/Colonne:
1. Seleziona
2. Click destro → Nascondi
   O
   Tasti: Ctrl+9 (righe) / Ctrl+0 (colonne)
```

**Indicatore:** Linea doppia tra intestazioni

#### Mostrare

```
1. Seleziona righe/colonne prima e dopo quella nascosta
2. Click destro → Scopri
   O
   Tasti: Ctrl+Shift+9 (righe) / Ctrl+Shift+0 (colonne)
```

---

### Blocca Righe/Colonne (Freeze)

Mantiene intestazioni visibili durante scroll.

#### Blocca Prima Riga

```
Visualizza → Blocca riquadri → Blocca riga superiore
```

```
Intestazione (visibile sempre)
─────────────────────────────
Dati (scrollabili)
```

#### Blocca Prima Colonna

```
Visualizza → Blocca riquadri → Blocca prima colonna
```

```
│ ID │ Nome │ Cognome │ ...scrollabile...
│ 1  │ Mario│ Rossi   │
```

#### Blocca Personalizzato

```
1. Click sulla cella DOPO riga/colonna da bloccare
   Es: B2 per bloccare colonna A e riga 1
2. Visualizza → Blocca riquadri
```

```
     ┌─ Bloccato ─┐
     │ A │ B  │ C  │ D  │ E  ...
─────┼───┼────┼────┼────┼────
  1  │ X │ Y  │ Z  │ A1 │ B1 ...  ← Bloccati
─────┼───┼────┼────┼────┼────
  2  │ 1 │ aa │ bb │ cc │ dd ...
  3  │ 2 │ ee │ ff │ gg │ hh ...
     ↓ Scrollabile
```

#### Sblocca

```
Visualizza → Blocca riquadri → Sblocca riquadri
```

---

## Best Practices

### 1. Gerarchia Visiva

```
LIVELLO 1 - TITOLO PRINCIPALE
  18pt, Grassetto, Colore scuro

  Livello 2 - Sottotitolo
  14pt, Grassetto

    Livello 3 - Sezione
    12pt, Grassetto

      Livello 4 - Dati
      10pt, Normale
```

### 2. Coerenza

✅ **Mantenere uniforme:**
- Font (massimo 2 diversi)
- Dimensioni carattere
- Colori (palette limitata)
- Stili bordi
- Allineamento

❌ **Evitare:**
- Ogni cella con font diverso
- Mistura di stili senza logica
- Arcobaleno di colori

---

### 3. Leggibilità

**Contrasto:**
```
✅ Buono:
   Nero su bianco
   Bianco su blu scuro

❌ Cattivo:
   Giallo su bianco
   Grigio chiaro su bianco
```

**Spaziatura:**
```
✅ Adeguata:
   Altezza righe: 15-20pt
   Padding celle: 2-5pt

❌ Troppo stretta:
   Altezza righe: 10pt
   Nessun padding
```

**Dimensioni:**
```
✅ Leggibile:
   Titoli: 14-18pt
   Dati: 10-12pt

❌ Troppo piccolo:
   Tutto 8pt
```

---

### 4. Professionalità

**Tabella Professionale:**

```
┌═══════════════════════════════════════════┐
│         RAPPORTO VENDITE Q1 2026          │ ← 16pt, centrato, grassetto
╞═══════════════╤══════════╤════════════════╡
│ Prodotto      │ Quantità │ Fatturato      │ ← 11pt, grassetto, bordo doppio sotto
├───────────────┼──────────┼────────────────┤
│ iPhone 15     │      142 │     € 99.400   │ ← 10pt, numeri allineati destra
│ MacBook Pro   │       67 │    € 133.500   │
│ iPad Air      │      189 │     € 94.500   │
│ AirPods Pro   │      423 │     € 84.600   │
├───────────────┼──────────┼────────────────┤
│ TOTALE        │      821 │    € 412.000   │ ← Grassetto, bordo sopra e doppio sotto
└═══════════════╧══════════╧════════════════┘
```

**Caratteristiche:**
- Titolo chiaro e centrato
- Intestazioni in grassetto con bordo
- Dati allineati correttamente
- Totale evidenziato
- Bordi essenziali (non su ogni cella)
- Numeri formattati (migliaia, decimali)

---

### 5. Accessibilità

**Contrasto colori:**
```
Tool: WebAIM Contrast Checker
Minimo AA: 4.5:1
Minimo AAA: 7:1
```

**Font leggibili:**
```
✅ Sans-serif: Arial, Calibri, Verdana
❌ Decorativi: Script, Fantasy
```

**Dimensioni adeguate:**
```
✅ Minimo 10pt per dati
❌ Mai sotto 8pt
```

**Evita solo colore:**
```
❌ Solo colore: Verde=OK, Rosso=Errore
✅ Colore + icone: ✅ Verde, ❌ Rosso
```

---

### 6. Performance

**Fogli Grandi:**
```
❌ Evitare:
- Formattazione condizionale su colonne intere (A:Z)
- Centinaia di regole complesse
- Formule volatili (OGGI, ADESSO, CASUALE)

✅ Preferire:
- Intervalli specifici (A1:Z1000)
- Poche regole ben ottimizzate
- Valori statici invece di formule quando possibile
```

---

## Esempi Pratici

### Esempio 1: Budget Familiare

```
┌════════════════════════════════════════════════┐
│           BUDGET FAMILIARE - GENNAIO 2026      │  ← 16pt, grassetto, centrato
╞════════════════╤═══════════╤═══════════════════╡
│ CATEGORIA      │  BUDGET   │  SPESA EFFETTIVA  │  ← 11pt, grassetto, sfondo blu
├────────────────┼───────────┼───────────────────┤
│ Affitto        │ € 1.200   │   € 1.200  ✅     │  ← Verde se OK
│ Alimentari     │ €   500   │   €   543  ⚠️     │  ← Giallo se vicino
│ Trasporti      │ €   200   │   €   180  ✅     │
│ Bollette       │ €   300   │   €   325  ⚠️     │
│ Intrattenimento│ €   150   │   €   220  ❌     │  ← Rosso se superato
│ Risparmi       │ €   350   │   €   250  ❌     │
├────────────────┼───────────┼───────────────────┤
│ TOTALE         │ € 2.700   │   € 2.718  ⚠️     │  ← Grassetto, bordo doppio
└════════════════╧═══════════╧═══════════════════┘

Formattazione condizionale:
- Verde: Spesa <= Budget
- Giallo: Spesa > Budget E <= Budget*1.1
- Rosso: Spesa > Budget*1.1
```

---

### Esempio 2: Dashboard Vendite

```
┌══════════════════════════════════════════════════════┐
│          KPI VENDITE - Q1 2026                       │
├══════════════════════════════════════════════════════┤
│                                                      │
│  Fatturato Totale:  € 412.000  ↑ +15%                │  ← 14pt, verde
│  Clienti Attivi:         1.245  ↑ +8%                │  ← Icone trend
│  Tasso Conversione:      23,5%  ↓ -2%                │  ← Rosso se negativo
│  Ticket Medio:        €    331  ↑ +6%                │
│                                                      │
├──────────────────────────────────────────────────────┤
│ TOP 5 PRODOTTI          │  VENDITE    │  ██████      │
├─────────────────────────┼─────────────┼──────────────┤
│ iPhone 15 Pro           │  € 99.400   │ ██████████   │
│ MacBook Pro M3          │  € 133.500  │ ██████████   │  ← Barre dati
│ iPad Air                │  € 94.500   │ ████████     │
│ AirPods Pro             │  € 84.600   │ ███████      │
│ Apple Watch             │  € 72.300   │ ██████       │
└─────────────────────────┴─────────────┴──────────────┘

Elementi:
- KPI grandi e colorati con trend
- Barre dati per confronto visivo
- Icone per direzione trend
- Sezioni separate con bordi
```

---

### Esempio 3: Calendario Turni

```
┌════════════════════════════════════════════════════┐
│         TURNI GENNAIO 2026                         │
├════╤═══╤═══╤═══╤═══╤═══╤═══╤═══╤═══╤═══╤═══╤═══╤═══┤
│Nome│ 1 │ 2 │ 3 │ 4 │ 5 │ 6 │ 7 │ 8 │ 9 │10 │...│31 │
├────┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┤
│Anna│ M │ M │ P │ P │ R │ R │ M │ M │ P │ P │...│ R │
│Luca│ P │ P │ M │ M │ M │ M │ R │ R │ M │ M │...│ M │
│Sara│ R │ R │ R │ R │ P │ P │ P │ P │ R │ R │...│ P │
└────┴───┴───┴───┴───┴───┴───┴───┴───┴───┴───┴───┴───┘

Legenda: M=Mattina  P=Pomeriggio  R=Riposo

Formattazione:
- M (Mattina):     Sfondo giallo chiaro
- P (Pomeriggio):  Sfondo azzurro chiaro  
- R (Riposo):      Sfondo verde chiaro
- Weekend:         Bordo spesso
- Festivi:         Sfondo rosso chiaro
```

---

### Esempio 4: Registro Voti

```
┌═══════════════════════════════════════════════════════┐
│         REGISTRO CLASSE 3A - MATEMATICA               │
├═══════════╤═════╤═════╤═════╤═════╤═════╤═════════════┤
│ Studente  │ V1  │ V2  │ V3  │ V4  │ V5  │  MEDIA      │
├───────────┼─────┼─────┼─────┼─────┼─────┼─────────────┤
│ Bianchi M.│  8  │  7  │  9  │  8  │  7½ │   7,9  ✅   │  ← Verde se >= 6
│ Rossi A.  │  5  │  6  │  5½ │  6  │  6  │   5,7  ❌   │  ← Rosso se < 6
│ Verdi L.  │  9  │ 10  │  9  │  8  │  9  │   9,0  ⭐   │  ← Stella se >= 9
│ Neri S.   │  6  │  6  │  7  │  6  │  6½ │   6,3  ✅   │
│ Gialli F. │  7  │  8  │  7  │  8  │  7  │   7,4  ✅   │
├───────────┼─────┼─────┼─────┼─────┼─────┼─────────────┤
│ MEDIA CL. │ 7,0 │ 7,4 │ 7,5 │ 7,2 │ 7,1 │   7,24      │  ← Grassetto
└═══════════╧═════╧═════╧═════╧═════╧═════╧═════════════┘

Scala colori media:
9-10:  Verde scuro  (Eccellente)
7-8,9: Verde chiaro (Buono)
6-6,9: Giallo       (Sufficiente)
<6:    Rosso        (Insufficiente)
```

---

## Shortcuts Riepilogo

### Windows/Excel

```
FORMATTAZIONE GENERALE
Ctrl+1              Finestra formato celle
Ctrl+Shift+F        Menu font
Alt+H, H            Colore riempimento
Alt+H, FC           Colore carattere

STILI CARATTERE
Ctrl+B              Grassetto
Ctrl+I              Corsivo
Ctrl+U              Sottolineato
Ctrl+5              Barrato
Ctrl+Shift+>        Aumenta dimensione
Ctrl+Shift+<        Diminuisci dimensione

ALLINEAMENTO
Ctrl+Shift+L        Allinea sinistra
Ctrl+Shift+E        Centra
Ctrl+Shift+R        Allinea destra

FORMATI NUMERO
Ctrl+Shift+1        Numero con separatore migliaia
Ctrl+Shift+4        Valuta
Ctrl+Shift+5        Percentuale
Ctrl+Shift+3        Data
Ctrl+Shift+2        Ora

BORDI
Ctrl+Shift+&        Aggiungi bordo esterno
Ctrl+Shift+_        Rimuovi bordi

RIGHE/COLONNE
Ctrl+9              Nascondi righe
Ctrl+0              Nascondi colonne
Ctrl+Shift+9        Mostra righe
Ctrl+Shift+0        Mostra colonne

ALTRO
Ctrl+Shift+C        Copia formato
Ctrl+Shift+V        Incolla formato
Alt+Invio           A capo nella cella
F4                  Ripeti ultima azione
```

### Mac/Excel

Sostituisci `Ctrl` con `Cmd` nella maggior parte dei casi.

### Google Sheets

```
Cmd/Ctrl+B          Grassetto
Cmd/Ctrl+I          Corsivo
Cmd/Ctrl+U          Sottolineato
Cmd/Ctrl+Shift+5    Barrato
Cmd/Ctrl+\          Rimuovi formattazione

Alt+Shift+1         Formato numero
Alt+Shift+2         Formato ora
Alt+Shift+3         Formato data
Alt+Shift+4         Formato valuta
Alt+Shift+5         Formato percentuale
Alt+Shift+6         Formato esponente

Cmd/Ctrl+Alt+V      Incolla solo formato
Cmd/Ctrl+Alt+C      Copia formato
```

---

## Checklist Formattazione Professionale

Prima di condividere un foglio di calcolo:

### ✅ Struttura
- [ ] Intestazioni chiare e in grassetto
- [ ] Bordi appropriati (non eccessivi)
- [ ] Colonne larghe abbastanza per contenuto
- [ ] Righe altezza uniforme (eccetto titoli)
- [ ] Prima riga/colonna bloccata se necessario

### ✅ Testo
- [ ] Font leggibile e coerente (max 2 tipi)
- [ ] Dimensioni appropriate (10-12pt dati)
- [ ] Grassetto usato con criterio
- [ ] Allineamento corretto (testo sx, numeri dx)
- [ ] Nessuna cella con testo troncato

### ✅ Numeri
- [ ] Formato appropriato (valuta, percentuale, decimali)
- [ ] Decimali uniformi nella stessa colonna
- [ ] Separatore migliaia attivo dove serve
- [ ] Date formato coerente

### ✅ Colori
- [ ] Palette limitata (2-4 colori max)
- [ ] Contrasto adeguato (leggibile)
- [ ] Significato coerente (rosso=negativo, verde=positivo)
- [ ] Non solo colore per trasmettere info (accessibilità)

### ✅ Formattazione Condizionale
- [ ] Regole logiche e documentate
- [ ] Non troppi colori sovrapposti
- [ ] Testata su tutti i dati
- [ ] Performance accettabile

### ✅ Layout
- [ ] Spaziatura adeguata
- [ ] Nessuna cella unita (se evitabile)
- [ ] Stampa su numero ragionevole di pagine
- [ ] Intestazioni/piè di pagina impostati

### ✅ Finale
- [ ] Revisione generale aspetto
- [ ] Test su dispositivi diversi (mobile?)
- [ ] Verifica accessibilità
- [ ] Documentazione/legenda se necessaria

---

## Risorse Aggiuntive

### Strumenti Online

**Palette Colori:**
- Coolors.co - Generatore palette
- Adobe Color - Color wheel
- Paletton.com - Schemi colore

**Contrasto:**
- WebAIM Contrast Checker
- Contrast Ratio Calculator

**Ispirazione:**
- Dribbble - Dashboard design
- Behance - Data visualization
- Excel Dashboard School

### Template

**Google Sheets:**
- Gallery Templates Google
- Template.net
- Vertex42.com

**Excel:**
- Microsoft Office Templates
- Smartsheet Templates
- Excel Easy Templates

### Tutorial

**Video:**
- ExcelIsFun (YouTube)
- Leila Gharani (YouTube)
- MyOnlineTrainingHub

**Testo:**
- Excel Campus
- Ablebits Blog
- Trump Excel

---

## Conclusione

La formattazione è un'**arte e una scienza**:

🎨 **Arte**: Creatività, design, estetica  
🔬 **Scienza**: Leggibilità, accessibilità, usabilità

### Regole d'Oro

1. **Meno è meglio**: Semplicità batte complessità
2. **Coerenza sempre**: Uniformità in tutto il documento
3. **Funzione prima**: Leggibilità > Bellezza
4. **Testa sempre**: Verifica su dispositivi e persone diverse
5. **Documenta**: Lascia legenda per formattazioni complesse

### Evoluzione delle Competenze

```
Principiante:    Font, colori, grassetto
Intermedio:      Bordi, formati numero, allineamento
Avanzato:        Formattazione condizionale, stili
Esperto:         Temi personalizzati, dashboard, automazione
```

---

**Buona formattazione!** 🎨📊

*Tempo lettura: ~60 minuti*  
*Livello: Base-Intermedio-Avanzato*  
*Software: Google Sheets, Microsoft Excel*
