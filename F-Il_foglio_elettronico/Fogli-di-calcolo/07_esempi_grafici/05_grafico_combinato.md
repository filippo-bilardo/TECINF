# Esempio 5: Grafico Combinato con Doppio Asse

**Livello**: 🟡 Intermedio  
**Tipo grafico**: Combinato (Colonne + Linea)  
**Obiettivo**: Visualizzare dati con scale diverse sullo stesso grafico

---

## Scenario

Analisi performance aziendale mensile:
- **Ricavi** (€50k-80k) → Colonne
- **Margine %** (18%-26%) → Linea
- **Costi Marketing** (€8k-15k) → Linea

Scale molto diverse richiedono asse Y secondario.

---

## Dati da Inserire

```
Mese	Ricavi	Margine%	Costi_Mkt	ROI
Gennaio	52000	22%	12000	4,3
Febbraio	58000	24%	13500	4,3
Marzo	61000	23%	14000	4,4
Aprile	65000	25%	12500	5,2
Maggio	69000	26%	13000	5,3
Giugno	72000	25%	14500	5,0
Luglio	68000	22%	15000	4,5
Agosto	58000	20%	10000	5,8
Settembre	71000	24%	13500	5,3
Ottobre	75000	25%	14000	5,4
Novembre	78000	26%	14500	5,4
Dicembre	82000	24%	15000	5,5
```

**Formule**:
- Colonna E (ROI): `=B2/D2` (Ricavi / Costi Marketing)
- Formatta colonna C come %

---

## Parte A: Grafico Combinato Base (Ricavi + Margine)

### Creazione

1. **Seleziona**: A1:C13 (Mese, Ricavi, Margine%)
2. **Inserisci → Grafico**
3. **Tipo**: Grafico combinato

### Configurazione Serie

**Editor → Tab Configurazione**

#### Serie "Ricavi"
- Tipo: **Colonne**
- Asse: **Sinistro**
- Colore: Blu (#4285F4)

#### Serie "Margine%"
- Tipo: **Linea**
- Asse: **Destro** ⚠️ Importante!
- Colore: Verde (#34A853)
- Spessore: 3px
- Marcatori: Cerchi, dimensione 6

### Personalizzazione

#### Titolo
- Principale: `Performance Aziendale 2026`
- Sottotitolo: `Ricavi e Margine Mensili`

#### Asse Y Sinistro (Ricavi)
- Titolo: `Ricavi (€)`
- Formato: Valuta breve (50k, 60k, 70k...)
- Min: 0
- Max: 90000

#### Asse Y Destro (Margine)
- Titolo: `Margine %`
- Formato: Percentuale
- Min: 15%
- Max: 30%

#### Asse X
- Titolo: `Mese`
- Rotazione etichette: 45° (se necessario)

#### Legenda
- Posizione: In alto a destra
- Mostra entrambe le serie con icone corrette (quadrato blu, linea verde)

### Risultato Atteso

```
€ ▲                                              ▲ %
80k│  ▁▂▂▃▄▄▃▂▄▅▅▆                    ──○────── │30%
60k│▁ ││││││││││││  ──○──○─                      │25%
40k│└─┴┴┴┴┴┴┴┴┴┴┴┘      ○─○                    │20%
   └─────────────────────────────────────────────┘15%
    G F M A M G L A S O N D
    Colonne=Ricavi (asse sx)  Linea=Margine (asse dx)
```

---

## Parte B: Tre Serie con Due Assi

### Aggiunta Terza Serie

1. **Editor → Configurazione**
2. **Aggiungi serie**: Clicca "+ Aggiungi serie"
3. **Seleziona intervallo**: Colonna D (Costi_Mkt)

### Configurazione "Costi_Mkt"
- Tipo: **Linea**
- Asse: **Sinistro** (stessa scala dei Ricavi)
- Colore: Arancione (#FF6D01)
- Spessore: 2px
- Tipo linea: **Tratteggiata**
- Marcatori: Quadrati, dimensione 5

### Aggiorna Legenda
Ora mostra 3 elementi:
- 🔵 Ricavi (colonne blu)
- 🟢 Margine % (linea verde)
- 🟠 Costi Mkt (linea arancione tratteggiata)

---

## Parte C: Grafico Combinato Avanzato (4 Serie)

### Aggiungi ROI

**Problema**: Ora abbiamo 4 metriche!
- Ricavi: 50k-80k
- Margine%: 20-26%
- Costi: 10k-15k
- ROI: 4-6x

**Soluzione**: ROI su asse destro con Margine

### Setup
1. Aggiungi serie ROI (colonna E)
2. Tipo: **Linea**
3. Asse: **Destro**
4. Colore: Viola (#9C27B0)
5. Spessore: 3px
6. Tipo: Continua
7. Marcatori: Triangoli

### Problema Scala Asse Destro
Ora asse destro ha:
- Margine%: 20-26%
- ROI: 4-6x

**Scala molto diversa!**

**Soluzione 1**: Usa solo 3 serie (rimuovi una)  
**Soluzione 2**: Due grafici separati sovrapposti  
**Soluzione 3**: Normalizza i valori (avanzato)

### Raccomandazione
**Max 3 serie totali** con 2 assi per mantenere leggibilità.

**Setup consigliato**:
- Asse SX: Ricavi (colonne) + Costi Mkt (linea)
- Asse DX: Margine% (linea)

---

## Parte D: Analisi con Linee di Tendenza

### Aggiungi Trend ai Ricavi

1. Seleziona serie "Ricavi"
2. **Aggiungi linea di tendenza**
3. Tipo: **Lineare**
4. Colore: Blu scuro
5. Spessore: 1px
6. Tipo linea: Punteggiata
7. Mostra: **Equazione + R²**

### Interpretazione

**Equazione esempio**: y = 2.450x + 48.500  
**Significato**: Crescita media di €2.450/mese

**R² = 0,89**  
**Significato**: 89% della variabilità è spiegata dal trend lineare (buon fit)

### Previsione

Estendi la linea di tendenza:
- **Previsione avanti**: 3 periodi (Gen-Mar 2027)

**Risultato**: Proiezione ricavi futuri basata sul trend.

---

## Parte E: Confronto Grafico Singolo vs Combinato

### Alternativa: Due Grafici Separati

**Grafico 1** (Ricavi e Costi):
- Entrambe colonne
- Stessa scala
- Confronto diretto

**Grafico 2** (Margine e ROI):
- Entrambe linee
- Percentuali
- Trend qualità

**Quando preferire**:
- Grafici per presentazioni (un concetto per grafico)
- Necessità di dettaglio maggiore
- Scale troppo diverse

**Quando usare combinato**:
- Dashboard compatta
- Correlazioni causa-effetto evidenti
- Report esecutivo con spazio limitato

---

## Esercizi Pratici

### Esercizio 1: Correlazione Marketing-Ricavi

**Obiettivo**: Verificare se costi marketing influenzano ricavi

**Metodo**:
1. Crea grafico combinato con:
   - Costi Mkt (colonne, mese M)
   - Ricavi (colonne, mese M+1) - sfasati di 1 mese
2. Verifica visivamente la correlazione

### Esercizio 2: Target Lines

Aggiungi linee obiettivo:

**Dati helper** (colonna nascosta):
```
Obiettivo_Ricavi: 70000 (uguale per tutti i mesi)
Obiettivo_Margine: 24% (uguale per tutti i mesi)
```

**Aggiungi serie**:
- Tipo: Linea
- Stile: Tratteggiata rossa
- Etichetta: "Target"

### Esercizio 3: Area + Linea

**Variante**:
- Ricavi: **Area** (riempita) invece di colonne
- Costi Mkt: **Area** (riempita) con colore diverso
- Margine: Linea sopra

**Effetto**: Visualizzazione "profitto" come gap tra aree.

---

## Best Practice Grafici Combinati

✓ **Max 3 serie totali** per leggibilità  
✓ **Due assi solo se scale >10x diverse**  
✓ **Etichetta assi chiaramente** (includi unità)  
✓ **Colori distinti e significativi**  
✓ **Stili diversi per tipo** (continuo vs tratteggiato)  
✓ **Legenda sempre visibile**  
✗ **Evita >2 linee sullo stesso asse** (confusione)  
✗ **Non usare troppi colori** (max 3-4)  
✗ **Non mischiare troppe metriche non correlate**  

---

## Errori Comuni da Evitare

### ❌ Errore 1: Stessa Scala per Dati Diversi
```
Ricavi: 70.000€
Margine: 24%
Su stesso asse → 24% invisibile!
```

**Soluzione**: Asse secondario

### ❌ Errore 2: Troppe Serie
4-5 linee sovrapposte → Indecifrabile

**Soluzione**: Separa in grafici multipli o usa filtro interattivo

### ❌ Errore 3: Colori Simili
Blu chiaro e azzurro per due linee → Difficile distinguere

**Soluzione**: Contrasto forte (blu + arancione, verde + rosso)

---

## Domande di Analisi

1. C'è correlazione tra Ricavi e Margine%?
2. Agosto mostra calo Ricavi ma ROI alto: perché?
3. Quale mese ha il miglior equilibrio Ricavi/Margine?
4. Il trend suggerisce crescita sostenibile?

---

## Checklist Grafico Combinato Professionale

- [ ] Max 3 serie mostrate
- [ ] Asse Y secondario per scale diverse (>10x)
- [ ] Entrambi gli assi etichettati con unità
- [ ] Colori ad alto contrasto
- [ ] Stili linea variati (continuo/tratteggiato)
- [ ] Legenda chiara e posizionata bene
- [ ] Marcatori su linee (opzionale, per precisione)
- [ ] Titolo descrittivo con periodo
- [ ] Linee griglia per facilitare lettura
- [ ] Dimensione adeguata (min 400x300px)
