# Esempio 6: Analisi Correlazione con Scatter Plot

**Livello**: 🔴 Avanzato  
**Tipo grafico**: Dispersione (Scatter) e Bolle  
**Obiettivo**: Analizzare relazioni tra variabili e identificare pattern

---

## Scenario

Analisi prodotti per ottimizzare portfolio:
- **Asse X**: Prezzo medio
- **Asse Y**: Margine %
- **Dimensione bolla**: Volume vendite
- **Colore**: Categoria prodotto

---

## Dati da Inserire

```
Prodotto	Prezzo	Margine%	Volume	Categoria	Ricavi
Smartphone X	899	28%	1250	Elettronica	1123750
Laptop Pro	1299	32%	850	Elettronica	1104150
Tablet Y	599	25%	1580	Elettronica	946420
Cuffie BT	149	45%	2350	Elettronica	350150
Smartwatch	399	38%	1680	Elettronica	670320
Jeans Classic	89	52%	3200	Abbigliamento	284800
Giacca Sport	199	48%	1850	Abbigliamento	368150
T-shirt Basic	29	55%	5800	Abbigliamento	168200
Scarpe Run	129	50%	2900	Abbigliamento	374100
Divano 3p	1299	35%	420	Casa	545580
Lampada LED	79	58%	3500	Casa	276500
Tavolo Legno	599	40%	780	Casa	467220
Sedia Design	189	42%	1850	Casa	349650
```

**Formula colonna F (Ricavi)**:
```
=B2*D2
```

---

## Parte A: Scatter Plot Base (Prezzo vs Margine)

### Creazione

1. **Seleziona**: B1:C14 (Prezzo e Margine%)
2. **Inserisci → Grafico**
3. **Tipo**: Dispersione (Scatter chart)

### Personalizzazione

#### Titolo
- Testo: `Analisi Prezzo-Margine Prodotti`
- Sottotitolo: `Ogni punto = un prodotto`

#### Assi
- **X**: Titolo "Prezzo (€)", Formato valuta
- **Y**: Titolo "Margine %", Formato percentuale

#### Punti
- Dimensione: 8px
- Colore: Blu (#4285F4)
- Forma: Cerchi

#### Linea di Tendenza
1. Aggiungi linea di tendenza
2. Tipo: **Lineare**
3. Mostra **equazione + R²**
4. Colore: Rosso tratteggiato

### Interpretazione

**Se R² alto (>0,7)**: Forte correlazione  
**Se R² basso (<0,3)**: Nessuna correlazione chiara

**Pendenza positiva**: ↗ Prezzo alto = Margine alto  
**Pendenza negativa**: ↘ Prezzo alto = Margine basso  
**Pendenza piatta**: → Nessuna relazione

---

## Parte B: Grafico a Bolle (3 Variabili)

### Creazione

1. **Seleziona**: B1:D14 (Prezzo, Margine, Volume)
2. **Inserisci → Grafico**
3. **Tipo**: Grafico a bolle

### Configurazione

**Editor → Configurazione**:
- **Asse X**: Prezzo
- **Asse Y**: Margine%
- **Dimensione bolla**: Volume
- **Etichetta**: Prodotto (colonna A)

### Personalizzazione

#### Bolle
- Opacità: 60% (per vedere sovrapposizioni)
- Bordo: Sottile grigio scuro
- Dimensione min: 5px
- Dimensione max: 50px

#### Etichette
- Mostra: Solo per bolle più grandi (>2000 volume)
- Posizione: Centro bolla
- Font: 9pt

#### Quadranti (Analisi Portfolio)

**Aggiungi linee di riferimento**:

Calcola medie:
```
Prezzo medio: =MEDIA(B2:B14)  → es. 490€
Margine medio: =MEDIA(C2:C14) → es. 42%
```

**Aggiungi serie linee verticali/orizzontali** (dati helper):

Colonna G-H (Linea verticale prezzo medio):
```
	G	H
1	Prezzo	Margine
2	490	0%
3	490	60%
```

Colonna I-J (Linea orizzontale margine medio):
```
	I	J
1	Prezzo	Margine
2	0	42%
3	1500	42%
```

**Aggiungi come serie**:
- Tipo: Linea
- Colore: Grigio tratteggiato
- Nessuna legenda

### Interpretazione Quadranti

```
          │ Alto Margine
          │
  Niche   │   Stars ⭐
  Products│   (High Price, High Margin, Big Volume)
─────────┼─────────
  Budget  │   Cash Cows 💰
  Items   │   (Low Price, Good Margin, High Volume)
          │
    Basso Prezzo → Alto Prezzo
```

**Strategia**:
- ⭐ **Stars**: Investire e promuovere
- 💰 **Cash Cows**: Mantenere e ottimizzare
- 🏷️ **Niche**: Valutare nicchia o sconto
- 💸 **Budget**: Valutare discontinuazione

---

## Parte C: Scatter con Categorie Colorate

### Setup Dati

Per colorare per categoria, serve un grafico per categoria.

**Metodo 1: Serie Multiple**

Crea 3 scatter separati:
1. Filtra solo "Elettronica" → Serie 1 (Blu)
2. Filtra solo "Abbigliamento" → Serie 2 (Verde)
3. Filtra solo "Casa" → Serie 3 (Arancione)

**Passi**:
1. Ordina dati per categoria
2. Seleziona intervalli separati con Ctrl:
   - B2:C6 (Elettronica)
   - B7:C10 (Abbigliamento)
   - B11:C14 (Casa)
3. Inserisci grafico scatter
4. Assegna colori diversi a ogni serie

**Metodo 2: Google Charts (Avanzato)**

Usa Apps Script per grafico bubble interattivo con colori automatici per categoria.

---

## Parte D: Analisi Outlier

### Identificare Anomalie

**Outlier**: Punti molto distanti dalla tendenza generale

**Nel nostro esempio**:
- **Cuffie BT**: Prezzo basso (149€) ma margine altissimo (45%)
  - **Insight**: Prodotto ad alto valore percepito, basso costo produzione
  - **Azione**: Modello da replicare!

- **Smartphone X**: Prezzo alto (899€) ma margine relativamente basso (28%)
  - **Insight**: Mercato competitivo, costi alti
  - **Azione**: Valutare aumento prezzo o riduzione costi

### Evidenziare Outlier

**Metodo**:
1. Crea serie separata per outlier
2. Dimensione bolla maggiore
3. Colore rosso/giallo
4. Etichetta sempre visibile

---

## Parte E: Matrici di Correlazione

### Analisi Multi-Variabile

Verifica correlazione tra tutte le coppie:

**Variabili**:
- Prezzo
- Margine
- Volume
- Ricavi

### Calcolo Coefficienti Correlazione

Formula in Google Fogli:
```
=CORRELAZIONE(B2:B14; C2:C14)
```

**Matrice**:
```
		Prezzo	Margine	Volume	Ricavi
Prezzo	1,00	-0,35	-0,52	0,28
Margine	-0,35	1,00	0,15	-0,18
Volume	-0,52	0,15	1,00	0,45
Ricavi	0,28	-0,18	0,45	1,00
```

**Interpretazione**:
- **1,00**: Correlazione perfetta positiva
- **0,00**: Nessuna correlazione
- **-1,00**: Correlazione perfetta negativa

**Esempio**: Prezzo-Volume = -0,52  
→ Correlazione negativa moderata: prodotti costosi vendono meno unità (logico)

### Visualizzare Matrice

**Formattazione condizionale**:
- Verde: Correlazione positiva forte (>0,7)
- Giallo: Correlazione debole (0,3-0,7)
- Bianco: Nessuna (< 0,3)
- Arancione: Negativa debole (-0,3 a -0,7)
- Rosso: Negativa forte (<-0,7)

---

## Esercizi Pratici

### Esercizio 1: Segmentazione Clienti

**Dati**: Clienti con:
- Asse X: Età
- Asse Y: Spesa media
- Dimensione: Frequenza acquisti
- Colore: Segmento (VIP, Regular, Occasionale)

**Obiettivo**: Identificare segmenti ad alto valore

### Esercizio 2: Analisi Vendite Regionali

**Dati**: Regioni con:
- X: PIL regionale
- Y: Vendite azienda
- Dimensione: Popolazione

**Obiettivo**: Trovare regioni under-performing rispetto al potenziale

### Esercizio 3: R&D Portfolio

**Dati**: Progetti con:
- X: Costo sviluppo
- Y: Ricavi attesi
- Dimensione: Tempo market
- Colore: Rischio (Alto/Medio/Basso)

**Obiettivo**: Ottimizzare portfolio progetti

---

## Best Practice Scatter/Bubble Charts

✓ **Linea di tendenza per correlazioni**  
✓ **Etichette sui punti chiave** (outlier, best/worst)  
✓ **Quadranti per analisi strategica**  
✓ **Max 50-60 punti** (oltre → troppo denso)  
✓ **Assi con scala appropriata** (zero non sempre necessario)  
✗ **Evita troppe dimensioni** (max 4: x, y, size, color)  
✗ **Non usare se nessuna relazione attesa**  
✗ **Evita sovrapposizione punti** (usa trasparenza)  

---

## Interpretazione R² (Coefficiente Determinazione)

**R² = 0,95**: 95% variabilità Y spiegata da X → Correlazione fortissima  
**R² = 0,70**: 70% spiegata → Correlazione forte  
**R² = 0,50**: 50% spiegata → Correlazione moderata  
**R² = 0,30**: 30% spiegata → Correlazione debole  
**R² < 0,10**: Nessuna correlazione significativa  

---

## Domande di Analisi

1. Esiste trade-off Prezzo-Margine nei tuoi dati?
2. I prodotti alto-volume hanno margini più bassi?
3. Quali prodotti sono candidati per price increase?
4. Quale categoria ha il miglior rapporto Prezzo-Margine?
5. Ci sono outlier che meritano investigazione?

---

## Quando Usare Scatter vs Altri Grafici

**Usa Scatter quando**:
- Vuoi mostrare correlazione tra 2 variabili continue
- Cerchi pattern o cluster
- Devi identificare outlier
- Nessuna variabile è "tempo"

**Non usare Scatter per**:
- Dati categorici (usa colonne/barre)
- Trend temporali (usa linee)
- Proporzioni (usa torta)
- Una sola variabile (usa istogramma distribuzione)

---

## Checklist Scatter Plot Professionale

- [ ] Linea di tendenza con R² mostrato
- [ ] Assi etichettati con unità di misura
- [ ] Punti dimensione adeguata (visibili ma non invadenti)
- [ ] Outlier identificati ed etichettati
- [ ] Scala assi appropriata (non necessariamente da zero)
- [ ] Griglia per facilitare lettura
- [ ] Titolo descrittivo della relazione indagata
- [ ] Legenda chiara se più serie/categorie
- [ ] Colori accessibili e distinti
- [ ] Note interpretative su insight chiave
