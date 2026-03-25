# Esercizio 2: Trend Temperature Annuale

**Livello**: 🟢 Base  
**Tipo grafico**: Linee  
**Tempo stimato**: 15 minuti  
**Competenze**: Grafici temporali, linea di tendenza, trend analysis

---

## 🎯 Obiettivo

Creare un grafico a linee per visualizzare l'andamento delle temperature medie mensili e aggiungere una linea di tendenza per identificare il pattern annuale.

## 📖 Scenario

Sei un meteorologo e hai raccolto le temperature medie mensili della tua città nel 2026. Vuoi creare un grafico che mostri chiaramente il ciclo stagionale e il trend complessivo.

## 📊 Dati Forniti

Copia questa tabella nel tuo Google Foglio (celle A1:B13):

```
Mese	Temperatura_Media
Gennaio	8
Febbraio	10
Marzo	14
Aprile	18
Maggio	22
Giugno	27
Luglio	30
Agosto	29
Settembre	24
Ottobre	18
Novembre	12
Dicembre	9
```

---

## ✅ Requisiti

Crea un grafico a linee con queste caratteristiche:

1. **Tipo**: Grafico a linee
2. **Dati**: Tutti i 12 mesi
3. **Titolo**: "Temperature Medie Mensili 2026"
4. **Asse X**: Etichetta "Mese"
5. **Asse Y**: 
   - Etichetta "Temperatura (°C)"
   - Scala: 0-35°C
6. **Linea**:
   - Colore: Rosso/Arancione (#FF6D01)
   - Spessore: 3px
   - Marcatori: Cerchi, dimensione 6
7. **Linea di tendenza**:
   - Tipo: Polinomiale (grado 2 o 3)
   - Colore: Grigio tratteggiato
   - Mostra equazione: No (opzionale)
8. **Griglia**: Linee orizzontali e verticali sottili

---

## 🤔 Domande di Analisi

Dopo aver creato il grafico, rispondi:

1. In quale mese si registra la temperatura più alta? E la più bassa?
2. Qual è l'escursione termica annuale (differenza max-min)?
3. La linea di tendenza è lineare o curva? Cosa indica?
4. In quale periodo dell'anno (mesi) la temperatura cresce più rapidamente?
5. C'è simmetria tra il riscaldamento (Gen-Lug) e raffreddamento (Lug-Dic)?

---

## 💡 Suggerimenti

- Il grafico a linee è ideale per dati temporali continui
- La linea di tendenza polinomiale cattura meglio i cicli stagionali
- I marcatori aiutano a identificare i singoli punti dati
- Sperimenta con colori "caldi" (rosso/arancione) per temperature

---

<details>
<summary><strong>📝 Soluzione - Clicca per Espandere</strong></summary>

## Passi Dettagliati

### 1. Preparazione Dati
- Copia i dati in A1:B13
- Verifica che Temperature siano numeri

### 2. Creazione Grafico
1. Seleziona A1:B13
2. **Inserisci → Grafico**
3. Tipo: **Grafico a linee**
   - Se suggerisce colonne, cambia in Editor → Configurazione → Tipo → Linee

### 3. Personalizzazione Titolo e Assi

**Titolo**:
- Testo: `Temperature Medie Mensili 2026`
- Sottotitolo (opzionale): `Ciclo Stagionale`
- Font: 14pt, grassetto

**Asse X**:
- Titolo: `Mese`
- Etichette: Tutte visibili, 0° rotazione

**Asse Y**:
- Titolo: `Temperatura (°C)`
- Min: 0
- Max: 35
- Formato: Numero con 0 decimali
- Linee griglia: Principale (ogni 5°)

### 4. Personalizzazione Linea

Sezione **Serie → Temperatura_Media**:
- Colore linea: Arancione (#FF6D01) o Rosso (#EA4335)
- Spessore linea: 3px
- Tipo linea: Continua
- Opacità: 100%

**Marcatori punti**:
- Forma: Cerchi
- Dimensione: 6px
- Colore: Stesso della linea
- Bordo: Bianco sottile (opzionale)

**Etichette dati**:
- Opzione 1: Nessuna (grafico pulito)
- Opzione 2: Mostra su punti max/min (Luglio e Gennaio)

### 5. Linea di Tendenza

1. Sezione **Serie → Temperatura_Media**
2. Spunta **"Linea di tendenza"**
3. Tipo: **Polinomiale**
   - Grado: 2 (curva semplice) o 3 (più accurata)
4. Colore: Grigio scuro (#757575)
5. Spessore: 2px
6. Tipo linea: Tratteggiata
7. Opacità: 70%
8. Etichetta: Nessuna (o R² se vuoi precisione)

**Nota**: La tendenza polinomiale cattura il ciclo stagionale (crescita-decrescita) meglio di una linea retta.

### 6. Stile Grafico

- Sfondo: Bianco
- Font: Arial o Roboto
- Griglia: Sottile grigia
- Legenda: Nascondi (1 sola serie) o In basso

### Risultato Atteso

```
Temperature Medie Mensili 2026

°C ▲
35 │
   │           ╭──○───○──╮  ← Linea dati (arancione)
30 │          ╱           ╲
   │       ╭─○  ╭─ ─ ─ ─╮ ○─╮  ← Tendenza (grigia)
25 │      ╱    ╱         ╲   ╲
   │   ╭─○   ╱             ╲   ○─╮
20 │  ╱      │               │    ╲
   │○─╮      │               │     ○─╮
15 │   ╲    ╱                 ╲      ╲
   │    ○──╯                   ╰──○   ╲
10 │○─╮                              ╲ ○
   │   ○                               ╰─○
5  │
0  └─────────────────────────────────────→
    G F M A M G L A S O N D
```

**Caratteristiche visibili**:
- Crescita rapida Marzo-Luglio
- Picco a Luglio (30°C)
- Decrescita Agosto-Dicembre
- Minimo a Gennaio (8°C)
- Curva simmetrica (approssimativamente)

## Risposte Domande di Analisi

1. **Temperature estreme**:
   - Più alta: Luglio (30°C)
   - Più bassa: Gennaio (8°C)

2. **Escursione termica annuale**:
   - Differenza: 30 - 8 = 22°C
   - Escursione significativa, tipica di clima continentale/mediterraneo

3. **Forma della tendenza**:
   - Curva (non lineare)
   - Indica **ciclicità stagionale**: estate calda, inverno freddo
   - Polinomio di grado 2 crea una parabola che segue il ciclo

4. **Periodo crescita rapida**:
   - **Marzo-Maggio**: +8°C in 3 mesi (+2,7°C/mese)
   - Accelerazione primaverile
   - Da Maggio a Giugno: +5°C (massima crescita mensile)

5. **Simmetria riscaldamento/raffreddamento**:
   - **Riscaldamento** (Gen-Lug): 7 mesi, +22°C
   - **Raffreddamento** (Lug-Dic): 6 mesi, -21°C
   - Quasi simmetrico, raffreddamento leggermente più rapido
   - Pattern comune: estate "rallenta" il raffreddamento, inverno "rallenta" il riscaldamento

**Insight**: Il grafico mostra un ciclo stagionale classico con picco estivo centrato su Luglio. La temperatura cresce più rapidamente in primavera tarda (Mag-Giu) e decresce rapidamente in autunno (Set-Nov).

</details>

---

## 🚀 Varianti (Bonus)

### Variante A: Confronto con Anno Precedente
Aggiungi dati 2025:
```
Mese	Temp_2025	Temp_2026
Gen	7	8
Feb	9	10
...
```
Crea grafico a 2 linee (2025 vs 2026) con colori diversi.

### Variante B: Zone Climatiche
Usa formattazione condizionale o colori diversi per zone:
- Blu: <15°C (freddo)
- Verde: 15-25°C (mite)
- Rosso: >25°C (caldo)

### Variante C: Previsione
Estendi la linea di tendenza per 3 mesi futuri (Gen-Mar 2027) usando l'opzione "Previsione avanti".

### Variante D: Grafico ad Area
Cambia tipo da Linee ad **Area** per enfatizzare il "volume" di calore annuale.

---

## 📚 Concetti Chiave Appresi

✅ Grafici a linee per dati temporali  
✅ Uso dei marcatori per evidenziare punti  
✅ Linea di tendenza polinomiale per cicli  
✅ Interpretazione di trend stagionali  
✅ Analisi velocità di cambiamento (crescita/decrescita)  

---

**Esercizio Precedente**: [Esercizio 1 - Vendite Mensili](esercizio_01_colonne_base.md)  
**Prossimo Esercizio**: [Esercizio 3 - Budget Familiare](esercizio_03_torta_composizione.md)
