# Modulo 7: Grafici e Visualizzazioni

## 7.1 Tipi di Grafici

### Introduzione
I grafici trasformano i dati in visualizzazioni comprensibili, facilitando l'identificazione di tendenze, confronti e pattern. La scelta del grafico giusto è fondamentale per comunicare efficacemente.

### Grafico a Colonne (Istogramma)

**Quando usarlo**:
- Confrontare valori tra categorie diverse
- Mostrare cambiamenti nel tempo (pochi periodi)
- Confrontare dati categorici

**Varianti**:
- **Colonne verticali**: Standard, categorie sull'asse X
- **Colonne raggruppate**: Più serie di dati affiancate
- **Colonne sovrapposte**: Serie sovrapposte per confronto
- **Colonne in pila**: Serie impilate per mostrare totale e parti

**Esempio pratico**: Vendite per trimestre
```
Trimestre   Vendite
Q1          50.000€
Q2          65.000€
Q3          72.000€
Q4          58.000€

→ Grafico a colonne verticali
```

**Best practices**:
- Inizia l'asse Y da zero per evitare distorsioni
- Usa max 5-7 categorie per leggibilità
- Ordina per valore se non c'è ordine naturale

### Grafico a Barre

**Quando usarlo**:
- Confrontare molte categorie (>5-7)
- Etichette lunghe (nomi prodotti, paesi)
- Enfatizzare il ranking

**Differenza con colonne**: Orientamento orizzontale

**Esempio pratico**: Top 10 prodotti venduti
```
Prodotto A  ████████████████ 1.250 unità
Prodotto B  ████████████ 980 unità
Prodotto C  ██████████ 875 unità
...
```

**Best practices**:
- Ordina dal più alto al più basso (ranking)
- Evidenzia barra principale con colore diverso
- Etichette sulla destra delle barre

### Grafico a Linee

**Quando usarlo**:
- Mostrare tendenze nel tempo
- Dati continui (temperature, prezzi azioni)
- Confrontare più trend simultaneamente

**Caratteristiche**:
- Punti dati connessi da linee
- Asse X tipicamente temporale
- Può mostrare più serie

**Esempio pratico**: Andamento vendite mensili anno su anno
```
Mesi: Gen Feb Mar Apr Mag Giu Lug Ago Set Ott Nov Dic
2025: ──○──○──○──○──○──○──○──○──○──○──○──○
2026: ──○──○──○──○──○──○──○──○──○──○──○──○
```

**Best practices**:
- Max 4-5 linee per leggibilità
- Usa colori distinti e marcatori diversi
- Evidenzia linea più importante con colore forte

### Grafico a Torta

**Quando usarlo**:
- Mostrare proporzioni di un totale (100%)
- Max 5-6 categorie
- Composizione semplice

**⚠️ Limitazioni**:
- Difficile confrontare fette simili
- Non adatto per molte categorie
- Non per trend temporali

**Esempio pratico**: Distribuzione budget marketing
```
Social Media:    40%  (144°)
Google Ads:      30%  (108°)
Email Marketing: 20%  (72°)
Eventi:          10%  (36°)

→ Grafico a torta
```

**Best practices**:
- Ordina fette da più grande a più piccola (senso orario da 12)
- Evidenzia fetta principale ("Esplodi" fetta)
- Mostra percentuali sulle etichette
- Max 6 fette (altro → "Altro")

### Grafico a Ciambella

**Caratteristiche**:
- Come torta ma con buco centrale
- Spazio centrale per totale o KPI

**Quando usarlo**:
- Stesso uso del grafico a torta
- Quando vuoi mostrare il totale al centro
- Aspetto più moderno

**Esempio**: Budget totale al centro, categorie intorno

### Grafico ad Area

**Quando usarlo**:
- Mostrare volume totale nel tempo
- Enfatizzare grandezza del cambiamento
- Confrontare contributi di categorie al totale

**Varianti**:
- **Area semplice**: Una serie
- **Area in pila**: Più serie impilate (mostra totale)
- **Area in pila 100%**: Proporzioni nel tempo

**Esempio pratico**: Composizione ricavi per categoria nel tempo
```
          Stack: Prodotto A (alto) + B (medio) + C (basso)
Ricavi    ▲
          │     ┌─────────── Totale
          │    ╱│╲         
          │   ╱ │ ╲        ← Prodotto A
          │  ╱  │  ╲
          │ ╱───┴───╲      ← Prodotto B
          │╱─────────╲     ← Prodotto C
          └────────────→ Tempo
```

**Best practices**:
- Usa trasparenza per aree sovrapposte
- Ordina serie: più importante in basso
- Max 4-5 categorie

### Grafico a Dispersione (Scatter)

**Quando usarlo**:
- Mostrare relazione tra due variabili
- Identificare correlazioni
- Visualizzare distribuzioni

**Caratteristiche**:
- Asse X e Y entrambi numerici
- Ogni punto rappresenta un'osservazione
- Può includere linea di tendenza

**Esempio pratico**: Relazione Budget Marketing vs Vendite
```
Vendite ▲
        │        ○
        │     ○    ○
        │   ○  ○ ○
        │ ○  ○
        │○
        └────────────→ Budget
        
Tendenza: Correlazione positiva
```

**Best practices**:
- Aggiungi linea di tendenza per correlazione
- Usa dimensione bolle per terza variabile (grafico a bolle)
- Etichetta punti outlier

### Grafico a Bolle

**Caratteristiche**:
- Come scatter ma dimensione bolla = terza variabile
- Può includere quarta variabile (colore)

**Quando usarlo**:
- Analisi multidimensionale
- Confrontare entità su 3-4 dimensioni

**Esempio pratico**: Analisi prodotti
- Asse X: Prezzo
- Asse Y: Margine %
- Dimensione bolla: Volume vendite
- Colore: Categoria prodotto

### Grafico a Istogramma (Distribuzione)

**⚠️ Diverso da grafico a colonne!**

**Quando usarlo**:
- Mostrare distribuzione di frequenza
- Dati continui raggruppati in intervalli (bins)
- Analisi statistica

**Esempio**: Distribuzione età clienti
```
Frequenza ▲
          │  ┌──┐
          │  │  │┌──┐
          │┌─┤  ││  │┌──┐
          ││ │  ││  ││  │
          └┴─┴──┴┴──┴┴──┴→ Età
           18-30 31-45 46-60
```

### Grafico Combinato

**Quando usarlo**:
- Confrontare dati con scale diverse
- Mostrare relazione causa-effetto
- Combinare volume + trend

**Esempio pratico**: Vendite (colonne) + Margine % (linea)
```
€/% ▲ Colonne=Vendite    Linea=Margine%
    │  ┌──┐  ──○──
    │  │  │╱    ╲
    │┌─┤  │      ○
    ││ │  │
    └┴─┴──┴─────────→ Mesi
```

**Best practices**:
- Max 2 tipi di grafico
- Usa asse Y secondario se scale molto diverse
- Colori distinti per serie

---

## 7.2 Creazione e Inserimento Grafici

### Metodo 1: Inserimento Rapido

**Passi base**:
1. Seleziona i dati (incluse intestazioni)
2. Menu: **Inserisci → Grafico**
3. Google Fogli suggerisce il grafico più adatto
4. Clicca "Inserisci"

**Esempio**:
```
Seleziona:
     A          B
1   Mese    Vendite
2   Gen     12.000€
3   Feb     15.000€
4   Mar     13.500€

→ Inserisci → Grafico
→ Suggerimento: Grafico a colonne
```

### Metodo 2: Selezione Manuale Tipo Grafico

**Quando usare**: Il suggerimento automatico non è quello desiderato

**Passi**:
1. Inserisci → Grafico
2. Nella barra laterale "Editor grafico"
3. Tab **Configurazione**
4. Dropdown "Tipo di grafico"
5. Scegli il tipo desiderato

### Struttura Dati per Grafici

#### Dati Riga vs Colonna

**Formato consigliato**:
```
Etichette nella prima colonna/riga
Valori nelle celle successive

Formato corretto:
     A        B        C
1   Mese    2025     2026
2   Gen     1000     1100
3   Feb     1200     1300

Non consigliato:
1   Gen  Feb  Mar  (etichette in colonne → difficile)
2   1000 1200 1100
```

#### Intestazioni

**Importante**: Includi sempre le intestazioni nella selezione
- Prima riga/colonna diventano etichette asse
- Google Fogli riconosce automaticamente le intestazioni

**Best practice**:
```
✓ Corretto:
    A        B
1  Mese   Vendite    ← Intestazioni
2  Gen    10000      ← Dati
3  Feb    12000

✗ Errato (senza intestazioni):
    A        B
1  Gen    10000      ← Dati senza etichette
2  Feb    12000
→ Asse mostrerà "Serie 1" invece di "Vendite"
```

#### Celle Vuote

**Comportamento**:
- Grafici a linee: Saltano il punto o lo interpolano
- Grafici a colonne: Mostrano colonna zero
- Torta: Ignorano la fetta

**Soluzione**: Riempi celle vuote o rimuovi righe incomplete

### Intervalli Dati

#### Intervallo Continuo
```
Seleziona: A1:B10
→ Tutte celle consecutive
```

#### Intervalli Multipli
**Uso**: Selezionare colonne non consecutive

**Metodo**:
1. Seleziona primo intervallo (es. A1:A10)
2. Tieni premuto **Ctrl** (Windows) o **Cmd** (Mac)
3. Seleziona secondo intervallo (es. C1:C10)
4. Inserisci → Grafico

**Esempio**:
```
     A        B         C
1   Mese   Budget   Vendite
2   Gen    10000    12000
3   Feb    11000    13000

Seleziona A1:A10 + C1:C10 (salta Budget)
→ Grafico Mese vs Vendite (senza Budget)
```

### Posizionamento Grafico

**Dopo inserimento**:
- Grafico appare come oggetto "flottante"
- Trascina per posizionare
- Ridimensiona dai bordi/angoli

**Opzioni posizione**:
1. **Sopra i dati**: Grafico copre celle (oggetto flottante)
2. **Sotto i dati**: Sposta grafico in area vuota

**Allineamento**:
- Tieni premuto **Alt** mentre trascini → si aggancia alla griglia celle

### Spostamento Grafico in Altro Foglio

**Metodo**:
1. Clicca grafico (seleziona)
2. Menu tre puntini (⋮) → **Sposta in un foglio a sé**
3. Crea nuovo foglio dedicato al grafico

**Quando usare**:
- Dashboard grafici separata da dati
- Report di presentazione
- Grafici grandi che ingombrano

---

## 7.3 Personalizzazione Grafici

### Editor Grafico

**Accesso**:
- Doppio clic sul grafico
- Oppure: Clicca grafico → Menu (⋮) → Modifica grafico

**Due tab principali**:
1. **Configurazione**: Dati e tipo grafico
2. **Personalizza**: Aspetto e stile

### Tab Configurazione

#### Intervallo Dati
- **Visualizza**: Mostra intervallo selezionato
- **Modifica**: Clicca icona griglia per cambiare selezione

**Aggiungi serie**:
1. Clicca "+ Aggiungi serie"
2. Seleziona nuovo intervallo dati

**Esempio**: Aggiungere dati 2026 a grafico con solo 2025

#### Inverti Righe/Colonne
**Uso**: Cambia cosa va sull'asse X vs cosa diventa serie

**Esempio**:
```
Dati originali:
     A      B      C
1   Mese  2025   2026
2   Gen   1000   1100
3   Feb   1200   1300

Default: Asse X = Mese, Serie = Anni (2025, 2026)
Inverti: Asse X = Anno, Serie = Mesi (Gen, Feb)
```

#### Usa Riga/Colonna come Intestazione
- Attivo: Prima riga/colonna = etichette
- Disattivo: Prima riga/colonna = dati

### Tab Personalizza

#### Stile Grafico

**Colore sfondo**:
- Trasparente (default)
- Bianco
- Colori personalizzati

**Bordo grafico**:
- Nessuno
- Sottile/Spesso
- Colore personalizzato

**Font**:
- Famiglia font (Arial, Roboto, ecc.)
- Dimensione testo

**Trasparenza**:
- 0% = Opaco
- 100% = Completamente trasparente

#### Titolo Grafico

**Opzioni**:
- **Testo titolo**: "Vendite Mensili 2026"
- **Font e dimensione**: Arial, 16pt
- **Formato**: Grassetto, colore
- **Allineamento**: Sinistra, centro, destra
- **Sottotitolo**: Testo aggiuntivo sotto il titolo

**Best practice**:
- Titolo descrittivo ma conciso
- Include periodo di riferimento
- Es: "Vendite per Categoria - Q1 2026"

#### Legenda

**Posizione**:
- Destra (default)
- In alto
- In basso
- Sinistra
- Nessuna (per grafici con una serie)

**Formato**:
- Font e dimensione
- Colore testo

**Quando nascondere**:
- Grafico con una sola serie
- Etichette già chiare sull'asse

#### Assi

**Asse Orizzontale (X)**:

**Titolo asse**:
```
Testo: "Mesi dell'anno"
Font: Arial, 12pt
Formato: Corsivo
```

**Etichette**:
- Mostra/Nascondi
- Angolo rotazione (0°, 45°, 90°)
- Font e dimensione

**Formato testo**:
- Numero, Data, Ora, Percentuale

**Esempio rotazione**:
```
Etichette lunghe:
90°:  │ │ │ │
      G F M A
      e e a p
      n b r r

45°:  Gen
         Feb
            Mar
               Apr
```

**Asse Verticale (Y)**:

**Min/Max valori**:
- Auto (default)
- Personalizzato

**Esempio personalizzazione**:
```
Dati: 8500, 9200, 9800
Auto: Y va da 0 a 10000
Custom: Y va da 8000 a 10000 (zoom su variazioni)
```

**⚠️ Attenzione**: Modificare min/max può distorcere la percezione!

**Formato numeri**:
- Numero: 1234
- Valuta: €1.234
- Percentuale: 12%
- Breve: 1,2k (per migliaia)
- Nessuno: Nessun simbolo

**Linee griglia**:
- Linee principali (ogni 1000)
- Linee secondarie (ogni 500)
- Colore e spessore

**Asse Y Secondario**:
**Quando usare**: Due serie con scale molto diverse

**Esempio**:
```
Serie 1 (Vendite): 10.000 - 50.000€  → Asse Y sinistro
Serie 2 (Margine%): 10% - 40%        → Asse Y destro
```

**Setup**:
1. Editor grafico → Configurazione
2. Seleziona serie
3. Asse: "Destra"

#### Serie Dati

**Personalizzazione per serie**:

**Colore**:
- Colore solido
- Gradiente
- Trasparenza

**Spessore linea** (per grafici a linee):
- Sottile: 1-2px
- Medio: 3-4px
- Spesso: 5-6px

**Tipo linea**:
- Continua ────
- Tratteggiata ─ ─ ─
- Punteggiata ··········

**Marcatori punto** (grafici a linee):
- Nessuno
- Cerchio ○
- Quadrato □
- Diamante ◇
- Triangolo △

**Dimensione marcatori**: 3-10px

**Etichette dati**:
- Nessuna
- Valore (1234)
- Percentuale (45%)
- Entrambi

**Posizione etichette**:
- Centro
- Sopra/Sotto (colonne)
- Sinistra/Destra (barre)
- Esterno (torta)

**Esempio personalizzazione serie**:
```
Serie "2025": 
- Colore: Blu chiaro (#A4C2F4)
- Linea tratteggiata
- Marcatori cerchio piccoli

Serie "2026":
- Colore: Blu scuro (#1155CC)
- Linea continua spessa
- Marcatori cerchio grandi
```

#### Linea di Tendenza

**Quando aggiungere**:
- Identificare trend generale
- Previsioni
- Correlazioni (scatter)

**Tipi**:
- **Lineare**: y = mx + b
- **Esponenziale**: y = a·e^(bx)
- **Polinomiale**: y = ax² + bx + c
- **Media mobile**: Media su N periodi

**Opzioni**:
- **Etichetta**: Nessuna, Equazione, R²
- **Colore e spessore**
- **Previsione avanti/indietro**: N periodi

**Esempio**:
```
Vendite mensili + Linea tendenza lineare
→ Mostra crescita media
→ Etichetta: y = 1200x + 5000, R² = 0,85
```

---

## 7.4 Grafici Combinati

### Introduzione
I grafici combinati uniscono due tipi di grafico (tipicamente colonne + linea) per confrontare dati con scale o significati diversi.

### Quando Usare Grafici Combinati

**Casi d'uso comuni**:
1. **Volume + Percentuale**: Vendite (colonne) + Crescita % (linea)
2. **Assoluto + Relativo**: Ricavi (colonne) + Margine % (linea)
3. **Causa + Effetto**: Investimento Marketing (colonne) + Vendite (linea)
4. **Target vs Reale**: Vendite (colonne) + Obiettivo (linea)

### Creazione Grafico Combinato

**Metodo**:
1. Seleziona dati con almeno 2 serie
2. Inserisci → Grafico
3. Editor grafico → Tab Configurazione
4. Tipo grafico: **"Grafico combinato"**
5. Per ogni serie, scegli tipo (colonna o linea)

**Esempio setup**:
```
Dati:
     A       B        C
1   Mese  Vendite  Margine%
2   Gen   50000    22%
3   Feb   55000    24%
4   Mar   52000    21%

Configurazione:
- Serie "Vendite": Colonne, asse sinistro
- Serie "Margine%": Linea, asse destro
```

### Configurazione Assi Multipli

**Problema**: Scale molto diverse
```
Vendite: 50.000 - 100.000€
Margine: 15% - 30%
```

**Soluzione**: Asse Y secondario

**Setup**:
1. Editor grafico → Configurazione
2. Clicca su serie (es. "Margine%")
3. Asse: Seleziona **"Destra"**

**Risultato**:
```
Vendite ▲           ▲ Margine
€       │  ┌─┐ ─○─  │ %
100k    │  │ │╱  ╲  │ 30%
        │  │ │    ○ │
50k     │┌─┤ │      │ 20%
        │├─┼─┼─────┤│
        └┴─┴─┴─────┴┘ 10%
```

### Personalizzazione Serie

**Serie Colonne**:
- Colore solido (es. blu)
- Larghezza colonne: 50-75%
- Etichette: Valori

**Serie Linea**:
- Colore contrastante (es. arancione)
- Spessore linea: 3-4px
- Marcatori: Cerchi
- Etichette: Percentuali

**Legenda**:
- Posizione: In alto o in basso
- Mostra entrambe le serie

### Esempi Pratici

#### Esempio 1: Vendite vs Obiettivo
```
Configurazione:
- Vendite: Colonne blu
- Obiettivo: Linea rossa tratteggiata
- Un solo asse (stessa scala)

Insight: Evidenzia mesi sotto obiettivo
```

#### Esempio 2: Performance Marketing
```
Configurazione:
- Investimento (€): Colonne grigie, asse sinistro
- ROI (%): Linea verde, asse destro
- Conversioni (#): Linea arancione, asse destro

Insight: Correlazione investimento-risultati
```

#### Esempio 3: Produzione e Qualità
```
Configurazione:
- Unità prodotte: Colonne blu, asse sinistro
- % difetti: Linea rossa, asse destro

Insight: Impatto volume su qualità
```

### Best Practices

✓ **Max 3 serie totali** (leggibilità)  
✓ **Colori distinti** per ogni serie  
✓ **Etichette assi chiare** (indica unità di misura)  
✓ **Legenda sempre visibile**  
✓ **Usa asse secondario** per scale diverse (>10x)  
✗ **Evita** troppi tipi di grafico (max 2)  
✗ **Non usare** se serie sono comparabili (usa solo colonne)  

---

## 7.5 Grafici Sparkline

### Introduzione
Gli sparkline sono mini-grafici compatti visualizzati dentro una singola cella, perfetti per mostrare tendenze in modo rapido senza occupare spazio.

### Funzione SPARKLINE

**Sintassi base**:
```
=SPARKLINE(dati; [opzioni])
```

**Caratteristiche**:
- Grafico in-cell (dentro cella)
- Nessun asse o etichetta
- Perfetto per dashboard compatte

### Tipi di Sparkline

#### 1. SPARKLINE Linea (Line)

**Uso**: Tendenze nel tempo

**Sintassi**:
```
=SPARKLINE(A1:A12)
```

**Opzioni avanzate**:
```
=SPARKLINE(A1:A12; {
  "charttype", "line";
  "linewidth", 2;
  "color", "blue";
  "max", 100;
  "min", 0
})
```

**Esempio pratico**:
```
     A     B      C      D      E      F    G
1   Gen   Feb    Mar    Apr    Mag    Sparkline
2   120   135    142    138    155    ───╱──
```

Formula in G2: `=SPARKLINE(A2:E2)`

#### 2. SPARKLINE Colonne (Column)

**Uso**: Confronti rapidi

**Sintassi**:
```
=SPARKLINE(A1:A12; {"charttype", "column"})
```

**Opzioni colori**:
```
=SPARKLINE(A1:A12; {
  "charttype", "column";
  "color", "green";
  "negcolor", "red";    ← Colonne negative in rosso
  "firstcolor", "blue";  ← Prima colonna
  "lastcolor", "orange"; ← Ultima colonna
  "highcolor", "darkgreen"; ← Valore max
  "lowcolor", "darkred"     ← Valore min
})
```

**Esempio**:
```
Profitti mensili (positivi e negativi):
     A      B     C     D     E    Sparkline
1   100   -50    75    125   -25   ▂▁▂▃▁
                                    G R G G R
```
(G=verde, R=rosso)

#### 3. SPARKLINE Vincita/Perdita (Win/Loss)

**Uso**: Visualizzare successi/fallimenti binari

**Sintassi**:
```
=SPARKLINE(A1:A10; {"charttype", "winloss"})
```

**Comportamento**:
- Valori positivi: Barra su ▄
- Valori negativi: Barra giù ▃
- Zero: Nessuna barra

**Esempio**: Tracking obiettivi giornalieri
```
Obiettivo raggiunto? (1=sì, -1=no, 0=non lavorato)
     L    M    M    G    V    S    D   Sparkline
1    1    1   -1    1    1    0    0   ▀▀▁▀▀
```

Formula: `=SPARKLINE(A1:G1; {"charttype", "winloss"})`

#### 4. SPARKLINE Barre (Bar)

**Uso**: Confronto orizzontale compatto (come barre dati)

**Sintassi**:
```
=SPARKLINE(A1:A5; {"charttype", "bar"})
```

**Opzioni**:
```
=SPARKLINE(A1:A5; {
  "charttype", "bar";
  "max", 100;           ← Scala max
  "color1", "blue";     ← Colore primario
  "color2", "lightblue" ← Colore secondario (pattern alternato)
})
```

**Esempio**: Progress bar
```
     A          B
1   Vendite   Progress
2   85%       ████████████░░░  
3   60%       ████████░░░░░░░
4   95%       ███████████████
```

Formula colonna B: `=SPARKLINE(A2; {"charttype", "bar"; "max", 1; "color1", "green"})`

### Opzioni Comuni SPARKLINE

#### Parametri disponibili

**charttype**:
- `"line"` - Linea (default)
- `"column"` - Colonne
- `"winloss"` - Vincita/Perdita
- `"bar"` - Barre orizzontali

**Colori**:
- `"color"` - Colore principale
- `"negcolor"` - Colore valori negativi
- `"firstcolor"` - Prima colonna/punto
- `"lastcolor"` - Ultima colonna/punto
- `"highcolor"` - Valore massimo
- `"lowcolor"` - Valore minimo
- `"color1"` / `"color2"` - Pattern alternato (bar)

**Scale**:
- `"max"` - Valore massimo asse (default: auto)
- `"min"` - Valore minimo asse (default: auto)

**Linee (solo type="line")**:
- `"linewidth"` - Spessore linea (1-10)
- `"xmin"` / `"xmax"` - Range asse X
- `"ymin"` / `"ymax"` - Range asse Y
- `"empty"` - Gestione celle vuote: `"zero"` o `"ignore"`

**Assi (solo type="line"/"column")**:
- `"axis"` - Mostra asse: `true` / `false`
- `"axiscolor"` - Colore asse

### Esempi Pratici Dashboard

#### Dashboard Performance Venditori

```
      A          B      C      D      E      F       G
1   Venditore  Gen    Feb    Mar    Totale  Trend
2   Mario      120    135    142    397     ──╱─
3   Luigi      95     88     102    285     ╲──╱
4   Anna       150    165    172    487     ───╱
5   Sara       110    105    98     313     ─╲──
```

Formula colonna G:
```
G2: =SPARKLINE(B2:D2; {"color", "blue"; "linewidth", 2})
```

#### Dashboard KPI con Soglie

```
      A         B      C              D
1   Metrica   Valore  Obiettivo    Visual
2   Vendite   85%     80%          ████████████░░
3   Qualità   92%     95%          ██████████████
4   Tempo     78%     85%          ███████████░░░
```

Formula colonna D (con colore condizionale):
```
D2: =SPARKLINE(B2; {
  "charttype", "bar"; 
  "max", 1; 
  "color1", IF(B2>=C2, "green", "orange")
})
```

#### Tabella con Trend Mensili

```
      A          B      ...   Trend
1   Prodotto   Gen          ████░░░██
2   A          20           ▂▁▁▃▃▄▂▄
3   B          35           ▃▄▄▅▅▃▂▃
4   C          10           ▂▁▂▂▃▃▃w
```

Formula Trend (colonne):
```
=SPARKLINE(B2:M2; {
  "charttype", "column";
  "highcolor", "green";
  "lowcolor", "red"
})
```

### Best Practices Sparkline

✓ **Usa per tendenze rapide**, non analisi dettagliate  
✓ **Dimensione cella adeguata**: Min 100px larghezza  
✓ **Colori semplici**: Max 2-3 colori  
✓ **Scale coerenti**: Stessa scala per sparkline comparabili  
✓ **Posizione**: Ultima colonna tabella  
✗ **Evita in celle piccole**: Illeggibile  
✗ **Non per dati complessi**: Usa grafico normale  

---

## 7.6 Grafici a Cascata e Gauge

### Grafico a Cascata (Waterfall)

#### Introduzione
Il grafico a cascata mostra come valori positivi e negativi contribuiscono a un totale finale, visualizzando incrementi e decrementi.

#### Quando Usarlo
- Analisi P&L (Profit & Loss)
- Flusso di cassa
- Variazioni inventario
- Bridge analysis (da Budget a Reale)

#### Struttura Dati

**Formato richiesto**:
```
     A              B
1   Categoria    Valore
2   Inizio       10000    ← Totale iniziale
3   Ricavi       +5000    ← Incremento
4   Costi        -3000    ← Decremento
5   Tasse        -500     ← Decremento
6   Finale       11500    ← Totale finale
```

#### Creazione in Google Fogli

**⚠️ Nota**: Google Fogli non ha grafico waterfall nativo

**Soluzione 1: Grafico colonne sovrapposte + Trucco**

**Dati preparati**:
```
     A         B        C        D
1   Item    Invisibile Base   Valore
2   Inizio    0       10000    0
3   +Ricavi   10000   0        +5000
4   -Costi    10000   0        -3000
5   -Tasse    12000   0        -500
6   Finale    0       11500    0
```

**Formula colonna B (Invisibile)**:
```
B3: =C2         → 10000 (mantiene altezza precedente)
B4: =C2+D3      → 15000
B5: =C2+D3+D4   → 12000
```

**Formula colonna C (Base)**:
Solo per valori iniziali/finali

**Passi**:
1. Seleziona A1:D6
2. Inserisci → Grafico → Colonne sovrapposte
3. Editor grafico:
   - Serie "Invisibile": Colore trasparente (o bianco)
   - Serie "Base": Colore pieno
   - Serie "Valore": Colore verde (positivo), rosso (negativo)

**Soluzione 2: Add-on**

Cerca in G Suite Marketplace:
- "Waterfall Chart"
- "ChartExpo"

#### Interpretazione

**Visuale tipica**:
```
€    ┌────┐              ┌────┐
15k  │    │              │    │
     │    │  ┌────┐      │    │
10k  │    │  │ ░░ │┌────┐│    │
     │    │  │ ░░ ││░░░░││    │
5k   │    │  │ ░░ ││░░░░││    │
     └────┘  └────┘└────┘└────┘
     Inizio +Ric  -Cost  Finale
```
- Verde: Positivi (su)
- Rosso: Negativi (giù)
- Grigio: Base invisibile
- Blu scuro: Totali

### Grafico Gauge (Indicatore)

#### Introduzione
Il grafico gauge (o tachimetro) visualizza un singolo valore su una scala, mostrando performance rispetto a obiettivi.

#### Quando Usarlo
- Dashboard KPI
- Percentuale completamento
- Livello stock
- Punteggio soddisfazione

#### ⚠️ Google Fogli Limitazioni

**Problema**: Non esiste gauge nativo in Google Fogli

**Soluzioni alternative**:

#### Soluzione 1: Grafico a Ciambella Parziale

**Simula un gauge con ciambella**:

**Dati**:
```
     A          B
1   Stato     Valore
2   Completo   75
3   Restante   25
```

**Setup**:
1. Inserisci → Grafico → Ciambella
2. Editor:
   - Angle apertura: 180° (mezza ciambella)
   - Rotazione: -90° (inizia da sinistra)
3. Colori:
   - Completo: Verde
   - Restante: Grigio chiaro
4. Nascondi legenda
5. Aggiungi etichetta centrale: "75%"

**Risultato visivo**:
```
       ╭────────╮
      │    75%   │
      │          │
      ╰────░░████╯
      Grigio Verde
```

#### Soluzione 2: Sparkline con Zone Colorate

**Grafico barra con soglie**:
```
=SPARKLINE(75; {
  "charttype", "bar";
  "max", 100;
  "color1", IF(75<50, "red", IF(75<80, "orange", "green"))
})
```

**Visualizzazione**:
```
0%                                    100%
├─────────────────────────────────────┤
████████████████████████░░░░░░░░░░░░░  75%
```

#### Soluzione 3: Add-on Gauge Charts

**Add-on consigliati**:
1. **ChartExpo** - Include gauge charts
2. **Awesome Table Connector** - Dashboard con gauge

**Installazione**:
1. Estensioni → Componenti aggiuntivi → Scarica componenti aggiuntivi
2. Cerca "Gauge" o "KPI Dashboard"
3. Installa e autorizza

#### Soluzione 4: Google Charts API (Avanzato)

**Per utenti esperti**: Incorpora gauge usando Apps Script

**Codice esempio** (Apps Script):
```javascript
function createGauge() {
  var html = HtmlService.createHtmlOutput(`
    <html>
      <script src="https://www.gstatic.com/charts/loader.js"></script>
      <script>
        google.charts.load('current', {'packages':['gauge']});
        google.charts.setOnLoadCallback(drawChart);
        
        function drawChart() {
          var data = google.visualization.arrayToDataTable([
            ['Label', 'Value'],
            ['Performance', 75]
          ]);
          
          var options = {
            width: 400, height: 120,
            redFrom: 0, redTo: 50,
            yellowFrom: 50, yellowTo: 80,
            greenFrom: 80, greenTo: 100,
            minorTicks: 5
          };
          
          var chart = new google.visualization.Gauge(
            document.getElementById('chart_div')
          );
          chart.draw(data, options);
        }
      </script>
      <div id="chart_div"></div>
    </html>
  `);
  SpreadsheetApp.getUi().showModalDialog(html, 'KPI Gauge');
}
```

### Dashboard Gauge Semplice (Senza Add-on)

**Combinazione testo + formattazione**:

```
      A              B
1   ┌─────────────────────────┐
2   │    PERFORMANCE 2026     │
3   ├─────────────────────────┤
4   │                         │
5   │    🎯 Vendite: 75%      │
6   │    ███████████░░░░░     │
7   │                         │
8   │    🎯 Qualità: 92%      │
9   │    ██████████████░      │
10  │                         │
11  │    🎯 Tempo: 68%        │
12  │    ██████████░░░░░░     │
13  │                         │
14  └─────────────────────────┘
```

**Implementazione**:
- Bordi: Formato → Bordi
- Barre: Formattazione condizionale → Barre dati
- Icone: Copia-incolla emoji
- Sfondo: Colori alternati

---

## Esercizi Pratici Modulo 7

### Esercizio 1: Analisi Vendite Multi-Grafico

**Obiettivo**: Creare 3 grafici diversi dagli stessi dati

**Dati**:
```
     A        B        C        D
1   Trim    2024     2025     2026
2   Q1      45000    48000    52000
3   Q2      52000    55000    58000
4   Q3      48000    51000    54000
5   Q4      58000    62000    67000
```

**Compiti**:
1. Grafico a colonne raggruppate (confronto anni)
2. Grafico a linee (trend trimestrale per anno)
3. Grafico a barre (ranking trimestri 2026)

**Personalizzazione**:
- Titoli descrittivi
- Legenda appropriata
- Colori tema coerenti

### Esercizio 2: Dashboard con Sparkline

**Obiettivo**: Creare dashboard venditori compatta

**Dati**: Vendite mensili per 5 venditori (Gen-Dic)

**Compiti**:
1. Colonna "Totale" con SOMMA
2. Colonna "Media" con MEDIA
3. Colonna "Trend" con SPARKLINE linea
4. Colonna "Performance" con SPARKLINE colonne
   - Verde per mesi sopra media
   - Rosso per mesi sotto media
5. Formattazione condizionale su Totale

### Esercizio 3: Grafico Combinato Performance

**Obiettivo**: Visualizzare vendite e margine insieme

**Dati**:
```
     A        B         C
1   Mese   Vendite   Margine%
2   Gen    120000    22%
3   Feb    135000    24%
4   Mar    142000    21%
...
```

**Compiti**:
1. Grafico combinato:
   - Vendite: Colonne blu
   - Margine: Linea arancione
2. Asse Y secondario per Margine
3. Etichette valori su entrambe le serie
4. Linea di tendenza su Vendite
5. Titolo: "Performance Vendite e Margini - 2026"

### Esercizio 4: Analisi Composizione

**Obiettivo**: Mostrare composizione ricavi per categoria

**Dati**: 5 categorie prodotto con ricavi

**Compiti**:
1. Grafico a torta:
   - Mostra percentuali
   - "Esplodi" categoria principale
   - Max 6 fette (raggruppa resto in "Altro")
2. Grafico a ciambella:
   - Stesso dataset
   - Totale al centro (usa casella testo sovrapposta)
3. Confronta i due approcci

### Esercizio 5: Dashboard Esecutiva

**Obiettivo**: Dashboard completa con 4 grafici

**Layout**:
```
┌─────────────┬─────────────┐
│  Vendite    │  Categorie  │
│  (Colonne)  │  (Torta)    │
├─────────────┼─────────────┤
│  Trend      │  Gauge KPI  │
│  (Linee)    │  (Ciambella)│
└─────────────┴─────────────┘
```

**Compiti**:
1. Quattro grafici su un foglio
2. Titolo dashboard unito e centrato
3. Colori coordinati (tema blu)
4. Sparkline per quick stats
5. Formattazione professionale

---

## Riepilogo Modulo 7

### Scegliere il Grafico Giusto

**Flowchart decisionale**:
```
Devo mostrare...

→ Confronto tra categorie?
  └→ Poche categorie: Colonne
  └→ Molte categorie: Barre

→ Cambiamento nel tempo?
  └→ Trend continuo: Linee
  └→ Periodi discreti: Colonne
  └→ Volume totale: Area

→ Parti di un totale?
  └→ Semplice (≤6 parti): Torta/Ciambella
  └→ Nel tempo: Area in pila 100%

→ Relazione tra variabili?
  └→ Correlazione: Scatter
  └→ 3 variabili: Bolle

→ Dati con scale diverse?
  └→ Grafico combinato + asse Y secondario

→ Tendenza compatta?
  └→ Sparkline
```

### Best Practices Grafici

✓ **Semplicità**: Un grafico, un messaggio  
✓ **Titoli chiari**: Descrivi cosa mostra il grafico  
✓ **Assi etichettati**: Sempre, con unità di misura  
✓ **Legenda leggibile**: Quando necessaria  
✓ **Colori significativi**: Verde=positivo, Rosso=negativo  
✓ **Scala appropriata**: Inizia da zero per colonne/barre  
✗ **Evita 3D**: Distorce percezione  
✗ **Non sovraffollare**: Max 5-7 serie  
✗ **No effetti inutili**: No ombre eccessive, gradienti complessi  

### Checklist Grafico Professionale

Prima di finalizzare un grafico, verifica:
- [ ] Titolo descrittivo presente
- [ ] Assi etichettati con unità
- [ ] Legenda chiara (se necessaria)
- [ ] Scala appropriata (di solito da zero)
- [ ] Colori distinti e accessibili
- [ ] Font leggibile (min 10pt)
- [ ] Dimensione adeguata (non troppo piccolo)
- [ ] Dati sorgente corretti
- [ ] Tipo grafico appropriato per i dati
- [ ] Posizionamento ordinato nel foglio

### Prossimi Passi

Nel Modulo 8 esploreremo:
- Gestione fogli multipli
- Collegamenti tra fogli
- Collaborazione e condivisione
- Protezione e permessi

**Continuiamo il viaggio verso la maestria in Google Fogli! 📊**
