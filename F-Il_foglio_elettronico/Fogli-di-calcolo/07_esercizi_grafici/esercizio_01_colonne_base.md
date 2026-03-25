# Esercizio 1: Vendite Mensili Negozio

**Livello**: 🟢 Base  
**Tipo grafico**: Colonne verticali  
**Tempo stimato**: 15 minuti  
**Competenze**: Creazione grafico base, formattazione assi, titoli

---

## 🎯 Obiettivo

Creare un grafico a colonne per visualizzare le vendite mensili di un negozio e identificare il mese con le migliori performance.

## 📖 Scenario

Sei il responsabile di un negozio di elettronica. Hai raccolto i dati delle vendite mensili del primo semestre 2026 e vuoi creare un grafico per presentare i risultati al team.

## 📊 Dati Forniti

Copia questa tabella nel tuo Google Foglio (celle A1:B7):

```
Mese	Vendite
Gennaio	28500
Febbraio	31200
Marzo	29800
Aprile	34500
Maggio	37200
Giugno	35800
```

**Nota**: Usa Tab per separare le colonne quando copi.

---

## ✅ Requisiti

Crea un grafico a colonne che rispetti questi criteri:

1. **Tipo**: Grafico a colonne verticali
2. **Dati**: Include tutti i 6 mesi
3. **Titolo**: "Vendite Primo Semestre 2026"
4. **Asse X**: Etichetta "Mese"
5. **Asse Y**: 
   - Etichetta "Vendite (€)"
   - Formato: Valuta o numero con separatore migliaia
6. **Colonne**: Colore blu (#4285F4)
7. **Griglia**: Linee orizzontali visibili
8. **Sfondo**: Bianco

---

## 🤔 Domande di Analisi

Dopo aver creato il grafico, rispondi:

1. Quale mese ha registrato le vendite più alte?
2. C'è un trend di crescita o decrescita evidente?
3. Quanto variano le vendite tra il mese migliore e peggiore?
4. In quale trimestre (Q1: Gen-Mar, Q2: Apr-Giu) le vendite sono state maggiori?

---

## 💡 Suggerimenti

- Seleziona l'intervallo A1:B7 prima di inserire il grafico
- Google Fogli dovrebbe suggerire automaticamente un grafico a colonne
- Usa Editor grafico → Tab "Personalizza" per le modifiche estetiche
- Se le colonne sono troppo larghe, ridimensiona il grafico

---

<details>
<summary><strong>📝 Soluzione - Clicca per Espandere</strong></summary>

## Passi Dettagliati

### 1. Preparazione Dati
- Copia i dati nelle celle A1:B7
- Verifica che "Vendite" sia riconosciuto come numero (allineato a destra)

### 2. Creazione Grafico
1. Seleziona A1:B7
2. Menu: **Inserisci → Grafico**
3. Tipo dovrebbe essere automaticamente "Grafico a colonne"
4. Se no: Editor → Configurazione → Tipo → Istogramma a colonne

### 3. Personalizzazione Titolo
1. Editor grafico → Tab **Personalizza**
2. Sezione **Titolo grafico**
3. Testo titolo: `Vendite Primo Semestre 2026`
4. Font: Arial, 14pt (opzionale)
5. Grassetto: Sì

### 4. Personalizzazione Assi

**Asse Orizzontale (X)**:
1. Sezione **Asse orizzontale**
2. Titolo: `Mese`
3. Font etichette: 10pt
4. Angolo: 0° (orizzontale)

**Asse Verticale (Y)**:
1. Sezione **Asse verticale**
2. Titolo: `Vendite (€)`
3. Formato numeri: 
   - Opzione 1: **Valuta arrotondata** (28.500 €)
   - Opzione 2: **Numero** con separatore migliaia (28.500)
4. Min: 0 (automatico)
5. Max: 40000 (automatico o personalizzato)

### 5. Personalizzazione Serie

1. Sezione **Serie**
2. Formato: Colonne
3. Colore riempimento: Blu (#4285F4)
4. Opacità: 100%
5. Etichette dati: Nessuna (opzionale: aggiungi se vuoi valori sopra colonne)

### 6. Stile Grafico

1. Sezione **Stile grafico**
2. Colore sfondo: Bianco (#FFFFFF)
3. Bordo grafico: Nessuno o grigio chiaro
4. Linee griglia: 
   - Principali: Sì (orizzontali)
   - Colore: Grigio chiaro (#E0E0E0)

### Risultato Atteso

```
Vendite Primo Semestre 2026

€  ▲
40k│
   │
35k│       ┌──┐    ┌──┐
   │       │  │    │  │
30k│  ┌──┐ │  │┌──┐│  │
   │┌─┤  │┌┤  ││  ││  │
25k││ │  │││  ││  ││  │
   │└─┴──┴┘└──┴└──┴└──┘
   └──────────────────────→
    Gen Feb Mar Apr Mag Giu
```

Il grafico mostra chiaramente:
- Crescita da Gennaio a Maggio
- Maggio è il picco (€37.200)
- Leggero calo a Giugno
- Trend generale positivo

## Risposte Domande di Analisi

1. **Mese con vendite più alte**: Maggio (€37.200)

2. **Trend**: Crescita generale con leggera flessione a Giugno
   - Da Gen a Mag: +30,5%
   - Da Mag a Giu: -3,8%

3. **Variazione**: 
   - Migliore: Maggio (€37.200)
   - Peggiore: Gennaio (€28.500)
   - Differenza: €8.700 (+30,5%)

4. **Confronto Trimestrale**:
   - Q1 (Gen-Mar): €89.500 (media €29.833)
   - Q2 (Apr-Giu): €107.500 (media €35.833)
   - Q2 superiore del 20,1% rispetto a Q1

**Insight**: Le vendite mostrano un trend positivo, con il secondo trimestre significativamente migliore del primo. Il calo di Giugno potrebbe essere stagionale o richiedere investigazione.

</details>

---

## 🚀 Varianti (Bonus)

Prova queste estensioni:

### Variante A: Aggiungi Obiettivo
- Aggiungi colonna "Obiettivo" con valore 32000 per ogni mese
- Crea grafico con due serie (Vendite + Obiettivo)
- Colora Obiettivo in rosso tratteggiato

### Variante B: Evidenzia il Miglior Mese
- Colora Maggio di verde diverso dalle altre colonne
- Aggiungi etichetta dati solo su Maggio

### Variante C: Aggiungi Crescita %
- Crea colonna "Crescita %" con formula: `=(B3-B2)/B2`
- Crea secondo grafico a colonne per mostrare crescita mensile

---

## 📚 Concetti Chiave Appresi

✅ Selezione dati per grafici  
✅ Scelta tipo grafico appropriato  
✅ Personalizzazione titolo e assi  
✅ Formattazione valori numerici  
✅ Interpretazione visuale dei dati  

---

**Prossimo Esercizio**: [Esercizio 2 - Trend Temperature](esercizio_02_linee_trend.md)
