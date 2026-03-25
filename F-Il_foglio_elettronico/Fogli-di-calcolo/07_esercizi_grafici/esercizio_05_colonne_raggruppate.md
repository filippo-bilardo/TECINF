# Esercizio 5: Confronto Vendite Trimestrali Multi-Anno

**Livello**: 🟡 Intermedio  
**Tipo grafico**: Colonne raggruppate  
**Tempo stimato**: 25 minuti  
**Competenze**: Grafici multi-serie, confronti temporali, analisi anno su anno

---

## 🎯 Obiettivo

Creare un grafico a colonne raggruppate per confrontare le vendite trimestrali di tre anni consecutivi (2024-2025-2026) e identificare trend di crescita.

## 📖 Scenario

Sei l'analista finanziario di un'azienda retail. Il CFO ti ha chiesto di preparare una presentazione che mostri visivamente l'andamento trimestrale delle vendite negli ultimi tre anni per valutare la crescita dell'azienda.

## 📊 Dati Forniti

Copia questa tabella nel tuo Google Foglio (celle A1:D5):

```
Trimestre	2024	2025	2026
Q1	156000	168000	185000
Q2	172000	189000	210000
Q3	165000	182000	198000
Q4	195000	215000	238000
```

**Nota**: Usa Tab per separare le colonne quando copi.

---

## ✅ Requisiti

Crea un grafico a colonne raggruppate che rispetti questi criteri:

1. **Tipo**: Grafico a colonne raggruppate (non in pila)
2. **Dati**: Tutti e 4 i trimestri con le 3 serie annuali
3. **Titolo**: "Confronto Vendite Trimestrali 2024-2026"
4. **Sottotitolo**: "Valori in Euro" (opzionale)
5. **Asse X**: Etichetta "Trimestre"
6. **Asse Y**: 
   - Etichetta "Vendite (€)"
   - Formato: Numero con separatore migliaia
   - Range: 0 - 250.000
7. **Colori serie**: Gradazioni di blu
   - 2024: Blu chiaro (#9FC5E8)
   - 2025: Blu medio (#4285F4)
   - 2026: Blu scuro (#1C4587)
8. **Legenda**: Posizione in alto a destra, ben leggibile
9. **Griglia**: Linee orizzontali principali
10. **Spaziatura**: Colonne ben separate tra trimestri

---

## 🤔 Domande di Analisi

Dopo aver creato il grafico, rispondi:

1. Quale trimestre ha mostrato la crescita percentuale più alta dal 2024 al 2026?
2. C'è un pattern stagionale ricorrente (trimestre sempre più forte)?
3. Qual è il tasso di crescita medio annuo tra 2024 e 2026?
4. Quale anno ha avuto le vendite totali più alte?
5. Q3 è sempre inferiore a Q2 e Q4? Cosa potrebbe spiegarlo?

---

## 💡 Suggerimenti

- Seleziona tutto l'intervallo A1:D5 incluso gli header
- Google Fogli dovrebbe riconoscere automaticamente le 3 serie
- Per cambiare il colore di ogni serie: Personalizza → Serie → Seleziona anno → Formato
- Verifica che le colonne siano "raggruppate" e non "in pila"
- Usa "Opacità" 100% per colori pieni e ben distinguibili

---

<details>
<summary><strong>📝 Soluzione - Clicca per Espandere</strong></summary>

## Passi Dettagliati

### 1. Preparazione Dati
- Copia i dati nelle celle A1:D5
- Verifica che i valori numerici siano allineati a destra
- Controlla che gli header (Trimestre, 2024, 2025, 2026) siano in grassetto

### 2. Creazione Grafico
1. Seleziona **A1:D5** (include header)
2. Menu: **Inserisci → Grafico**
3. Google Fogli dovrebbe suggerire grafico a colonne
4. Se le colonne sono "in pila": 
   - Editor → Configurazione → Tipo
   - Seleziona **Istogramma a colonne raggruppate**

### 3. Personalizzazione Titolo
1. Editor grafico → Tab **Personalizza**
2. Sezione **Titolo grafico**
3. Testo titolo: `Confronto Vendite Trimestrali 2024-2026`
4. Font: Arial, 16pt, Grassetto
5. (Opzionale) Sottotitolo: `Valori in Euro`

### 4. Personalizzazione Assi

**Asse Orizzontale (X)**:
1. Sezione **Asse orizzontale**
2. Titolo: `Trimestre`
3. Font: 11pt
4. Angolo testo: 0° (orizzontale)

**Asse Verticale (Y)**:
1. Sezione **Asse verticale**
2. Titolo: `Vendite (€)`
3. Formato numeri: **Numero** con separatore migliaia
4. Valore min: `0`
5. Valore max: `250000` (per lasciare spazio sopra)

### 5. Personalizzazione Serie

Ripeti per ogni anno:

**Serie "2024"**:
1. Sezione **Serie** → Dropdown: seleziona "2024"
2. Colore: Blu chiaro `#9FC5E8`
3. Opacità: 100%
4. Spessore bordo: 0 (nessun bordo) o 1px grigio

**Serie "2025"**:
1. Sezione **Serie** → Dropdown: seleziona "2025"
2. Colore: Blu medio `#4285F4`
3. Opacità: 100%

**Serie "2026"**:
1. Sezione **Serie** → Dropdown: seleziona "2026"
2. Colore: Blu scuro `#1C4587`
3. Opacità: 100%

### 6. Legenda e Stile

**Legenda**:
1. Sezione **Legenda**
2. Posizione: **In alto a destra** o **Destra**
3. Font: 10pt
4. Allineamento: Destra

**Stile Generale**:
1. Sezione **Stile grafico**
2. Sfondo: Bianco
3. Bordo: Nessuno
4. Linee griglia: Orizzontali principali
5. Colore griglia: Grigio chiaro (#E0E0E0)

### 7. Ottimizzazioni Finali

- Verifica che le colonne siano ben distanziate
- Se troppo strette: ingrandisci il grafico orizzontalmente
- Controlla che i 3 colori siano ben distinguibili
- Verifica leggibilità della legenda

### Risultato Atteso

```
        Confronto Vendite Trimestrali 2024-2026
                    Valori in Euro                   Legend:
€                                                     ■ 2024
250k│                                                 ■ 2025
    │                                      ┌──┐       ■ 2026
    │                               ┌──┐   │  │
200k│                    ┌──┐┌──┐   │  │   │  │
    │         ┌──┐┌──┐   │  ││  │┌──┤  │┌──┤  │
    │         │  ││  │┌──┤  ││  ││  │  ││  │  │
150k│   ┌──┐  │  ││  ││  │  ││  ││  │  ││  │  │
    │   │  │  │  ││  ││  │  ││  ││  │  ││  │  │
    │   │  │  │  ││  ││  │  ││  ││  │  ││  │  │
    │   │24│  │24││25││26││24││25││26││24││25││26│
 0  └───┴──┴──┴──┴┴──┴┴──┴┴──┴┴──┴┴──┴┴──┴┴──┴┴──┴──→
         Q1     Q2      Q3      Q4
```

Il grafico mostra chiaramente:
- Crescita anno su anno costante in tutti i trimestri
- Q4 sempre il trimestre più forte
- Q3 sempre in flessione rispetto a Q2
- 2026 supera sempre 2024 e 2025

## Risposte Domande di Analisi

1. **Trimestre con maggior crescita 2024→2026**:
   - Q2: da €172k a €210k = **+22,1%**
   - Q1: da €156k a €185k = +18,6%
   - Q4: da €195k a €238k = +22,1%
   - Q3: da €165k a €198k = +20,0%
   
   **Q2 e Q4 a pari merito** con +22,1%

2. **Pattern stagionale**:
   - **Q4 sempre il più forte** in tutti e 3 gli anni
   - Q1 sempre il più debole
   - Q2 supera sempre Q3 (flessione estiva tipica del retail)
   - Pattern ricorrente: Q1 < Q3 < Q2 < Q4

3. **Tasso di crescita medio annuo**:
   - 2024 totale: €688.000
   - 2026 totale: €831.000
   - Crescita totale: +20,8% su 2 anni
   - **Crescita media annua: ~9,9%** (CAGR)

4. **Anno con vendite totali più alte**:
   - 2024: €688.000
   - 2025: €754.000 (+9,6%)
   - 2026: €831.000 (+10,2%)
   
   **2026** è il migliore con €831k totali

5. **Q3 sempre inferiore a Q2 e Q4**:
   - Sì, confermato in tutti e 3 gli anni
   - **Possibili spiegazioni**:
     - Periodo estivo = vacanze = meno acquisti
     - Budget consumatori esaurito dopo Q2
     - Attesa saldi autunnali/Black Friday Q4
     - Riduzione attività aziendali in agosto
   
   **Insight**: Tipico pattern retail con picco Q4 (festività) e calo Q3 (estate)

## Formule Utili (Bonus)

Aggiungi queste colonne per analisi approfondita:

**Colonna E - Crescita 2024→2026**:
```
=((D2-B2)/B2)*100
```

**Riga 6 - Totali Annui**:
```
=SOMMA(B2:B5)
```

**Riga 7 - Media Trimestrale**:
```
=MEDIA(B2:B5)
```

</details>

---

## 🚀 Varianti (Bonus)

Prova queste estensioni:

### Variante A: Aggiungi Previsione 2027
- Aggiungi colonna "2027" con crescita 10% su 2026
- Usa colore blu con pattern tratteggiato per indicare "stima"
- Aggiorna titolo: "2024-2027 (2027 previsto)"

### Variante B: Focus sul Trimestre Migliore
- Crea secondo grafico: solo Q4 dei 3 anni
- Aggiungi etichette dati sopra ogni colonna
- Calcola crescita anno su anno (%)

### Variante C: Grafico Totali Annui
- Crea tabella riassuntiva con totali per anno
- Grafico a colonne semplice: un asse X = anni
- Aggiungi linea di tendenza lineare

### Variante D: Analisi Variazione Trimestrale
- Calcola variazione % trimestre su trimestre per ogni anno
- Crea grafico a linee: 3 linee (una per anno)
- Identifica quale anno ha volatilità maggiore

---

## 📚 Concetti Chiave Appresi

✅ Grafici multi-serie (colonne raggruppate)  
✅ Confronto temporale multi-dimensionale  
✅ Scelta palette colori coerente (gradazioni)  
✅ Analisi anno su anno (YoY)  
✅ Identificazione pattern stagionali  
✅ Interpretazione trend di crescita  

---

**Esercizio Precedente**: [Esercizio 4 - Classifiche con Barre](esercizio_04_barre_ranking.md)  
**Prossimo Esercizio**: [Esercizio 6 - Linee Multiple](esercizio_06_linee_multiple.md)
