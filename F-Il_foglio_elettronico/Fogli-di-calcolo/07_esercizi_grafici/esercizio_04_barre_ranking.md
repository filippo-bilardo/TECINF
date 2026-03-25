# Esercizio 4: Top 10 Prodotti per Vendite

**Livello**: 🟢 Base  
**Tipo grafico**: Barre orizzontali  
**Tempo stimato**: 20 minuti  
**Competenze**: Ranking, ordinamento, grafici a barre, confronto valori

---

## 🎯 Obiettivo

Creare un grafico a barre orizzontali per visualizzare i 10 prodotti più venduti dell'anno e facilitare il confronto delle performance.

## 📖 Scenario

Sei un analista di vendite e-commerce. Hai migliaia di prodotti, ma vuoi identificare e visualizzare rapidamente i top performer per una presentazione al management.

## 📊 Dati Forniti

Copia questa tabella (celle A1:B11):

```
Prodotto	Vendite_Unità
Smartphone X1	4250
Laptop Ultra	3890
Cuffie Wireless	3650
Tablet Pro	3120
Smartwatch Fit	2980
Mouse Gaming	2750
Tastiera RGB	2540
Monitor 27"	2310
SSD 1TB	2180
Webcam HD	2050
```

---

## ✅ Requisiti

1. **Tipo**: Grafico a barre orizzontali
2. **Ordinamento**: Dal più venduto (alto) al meno venduto (basso)
3. **Titolo**: "Top 10 Prodotti per Vendite 2026"
4. **Asse X**: "Unità Vendute", formato con separatore migliaia
5. **Asse Y**: Nomi prodotti, font leggibile
6. **Barre**: 
   - Colore: Verde (#34A853) o gradiente
   - Evidenzia la prima barra con colore diverso (oro/verde scuro)
7. **Etichette dati**: Mostra il valore alla fine di ogni barra
8. **Griglia**: Verticali sottili

---

## 🤔 Domande di Analisi

1. Quale prodotto ha venduto di più? Di quanto supera il secondo?
2. C'è un grande gap tra i primi 3 e il resto?
3. Quanto vendono in media i prodotti in top 10?
4. Se il prodotto #1 genera €850/unità, quale ricavo totale porta?
5. Il prodotto #10 vale la pena mantenerlo nel catalogo?

---

<details>
<summary><strong>📝 Soluzione</strong></summary>

## Passi

### 1. Preparazione
**Importante**: Ordina i dati per Vendite (decrescente) PRIMA di creare il grafico.

1. Seleziona A1:B11
2. Menu: **Dati → Ordina intervallo → Opzioni avanzate**
3. Ordina per: **Vendite_Unità**
4. Ordine: **Z → A** (decrescente)

### 2. Creazione Grafico
1. Seleziona A1:B11 (già ordinati)
2. **Inserisci → Grafico**
3. Tipo: **Grafico a barre** (orizzontale)
   - Se suggerisce colonne → Cambia tipo

### 3. Personalizzazioni

**Titolo**: `Top 10 Prodotti per Vendite 2026`

**Asse Orizzontale (X - Valori)**:
- Titolo: `Unità Vendute`
- Formato: Numero con separatore migliaia (4.250)
- Min: 0, Max: 5000 (auto)

**Asse Verticale (Y - Prodotti)**:
- Titolo: Nessuno (nomi parlano da sé)
- Font: 11pt
- Allineamento: Sinistra

**Barre**:
- Colore base: Verde (#34A853)
- Prima barra (Smartphone X1): Verde scuro (#0F9D58) o Oro (#F9AB00)

**Etichette dati**:
- Posizione: Fine barra (destra)
- Formato: 4.250 (con separatore)
- Font: 10pt, grassetto

### Risultato

```
Top 10 Prodotti per Vendite 2026

Smartphone X1    ████████████████████ 4.250
Laptop Ultra     ███████████████████  3.890
Cuffie Wireless  ██████████████████   3.650
Tablet Pro       ███████████████      3.120
Smartwatch Fit   ██████████████       2.980
Mouse Gaming     █████████████        2.750
Tastiera RGB     ████████████         2.540
Monitor 27"      ███████████          2.310
SSD 1TB          ██████████           2.180
Webcam HD        █████████            2.050
                 ├────────┼────────┼──────→
                 0      2000     4000  Unità
```

## Risposte

1. **Top prodotto**: Smartphone X1 (4.250 unità)
   - Supera il 2° di: 4.250 - 3.890 = **360 unità (+9,3%)**
   - Leadership chiara ma non schiacciante

2. **Gap Top 3**:
   - Top 3 media: 3.930 unità
   - Rimanenti 7 media: 2.616 unità
   - Differenza: **50% in più**
   - Sì, c'è un livello superiore (prodotti "best seller")

3. **Media Top 10**: (somma)/10 = 29.720/10 = **2.972 unità**
   - Sopra media: 5 prodotti
   - Sotto media: 5 prodotti
   - Distribuzione equilibrata

4. **Ricavi Smartphone X1**:
   - 4.250 unità × €850 = **€3.612.500**
   - Prodotto di punta sia in volume che valore

5. **Prodotto #10 (Webcam HD)**:
   - 2.050 unità = 69% del top
   - **Sì, vale la pena**: 2k unità è comunque significativo
   - In top 10 tra probabilmente centinaia di prodotti

**Insight**: Portfolio bilanciato con 3 super-seller (smartphone, laptop, cuffie) e 7 prodotti solidi. Nessun outlier negativo da eliminare.

</details>

---

## 🚀 Varianti

### Variante A: Colori Condizionali
- Verde scuro: >3500 unità
- Verde: 2500-3500
- Verde chiaro: <2500

### Variante B: Aggiungi Ricavi
Colonna C con prezzo unitario:
```
Prodotto	Unità	Prezzo	Ricavo
Smartphone	4250	850	3.612.500
```
Crea secondo grafico per Ricavi totali.

### Variante C: Sparkline Compatto
Invece del grafico, usa sparkline bar in tabella.

---

**Esercizio Precedente**: [Esercizio 3 - Budget Familiare](esercizio_03_torta_composizione.md)  
**Prossimo Esercizio**: [Esercizio 5 - Confronto Triennale](esercizio_05_colonne_raggruppate.md)
