# Esercizio 7: Ricavi e Margine - Grafico Combinato

**Livello**: 🟡 Intermedio  
**Tipo grafico**: Combinato (colonne + linea) con doppio asse Y  
**Tempo stimato**: 30 minuti  
**Competenze**: Grafici combinati, asse secondario, correlazioni, KPI multipli

---

## 🎯 Obiettivo

Creare un grafico combinato con colonne (ricavi) e linea (margine %) su doppio asse Y per analizzare la relazione tra volume di vendite e redditività.

## 📖 Scenario

Sei il Controller di un'azienda manifatturiera. Il CEO vuole capire se l'aumento dei ricavi negli ultimi 12 mesi ha mantenuto o migliorato i margini di profitto. Ti chiede un grafico che mostri entrambe le metriche contemporaneamente.

## 📊 Dati Forniti

Copia questa tabella nel tuo Google Foglio (celle A1:C13):

```
Mese	Ricavi	Margine %
Gen	52000	22.5
Feb	58000	23.2
Mar	54000	21.8
Apr	61000	24.1
Mag	68000	25.3
Giu	65000	24.7
Lug	59000	22.9
Ago	55000	21.5
Set	64000	25.8
Ott	72000	26.2
Nov	75000	25.9
Dic	78000	26.0
```

**Nota**: 
- Usa Tab per separare le colonne
- Margine % = (Profitto / Ricavi) × 100
- Valori esempio: Margine 25% su €60k = €15k di profitto

---

## ✅ Requisiti

Crea un grafico combinato che rispetti questi criteri:

1. **Tipo**: Grafico combinato
   - Serie 1 (Ricavi): **Colonne** verticali
   - Serie 2 (Margine %): **Linea** con marcatori
2. **Assi Y**:
   - **Asse sinistro**: Ricavi (€) - scala 50.000 - 80.000
   - **Asse destro**: Margine (%) - scala 20% - 27%
3. **Titolo**: "Ricavi Mensili e Margine di Profitto 2026"
4. **Asse X**: Etichetta "Mese", tutti i 12 mesi visibili
5. **Colori**:
   - Ricavi (colonne): Blu (#4285F4)
   - Margine % (linea): Verde (#34A853)
6. **Formattazione Assi**:
   - Asse sinistro: Numero con separatore migliaia + simbolo €
   - Asse destro: Percentuale con 1 decimale (es: 25,3%)
7. **Linea Margine**:
   - Spessore: 3px
   - Marcatori: Cerchi dimensione 6
   - Stile: Continuo
8. **Legenda**: Posizione in alto, mostra "Ricavi (€)" e "Margine %"
9. **Griglia**: Linee orizzontali riferite all'asse sinistro

---

## 🤔 Domande di Analisi

Dopo aver creato il grafico, rispondi:

1. C'è correlazione positiva tra ricavi e margine? (Quando ricavi↑, margine↑?)
2. Quale mese ha il miglior margine? E i ricavi più alti?
3. In quale mese il margine è calato nonostante ricavi alti?
4. Qual è il trend generale del margine nel secondo semestre?
5. Calcola il profitto effettivo di Ottobre (ricavi × margine)
6. È meglio avere ricavi alti con margine basso o ricavi medi con margine alto?

---

## 💡 Suggerimenti

- Crea prima il grafico con entrambe le serie come colonne
- Poi converti "Margine %" in linea tramite Editor grafico
- Per asse secondario: Personalizza → Serie "Margine %" → Asse: Destra
- Verifica che le scale degli assi siano appropriate (no distorsioni)
- Se la linea è sopra le colonne: aumenta opacità colonne o abbassa linea
- Usa tooltip (passaggio mouse) per vedere valori esatti

---

<details>
<summary><strong>📝 Soluzione - Clicca per Espandere</strong></summary>

## Passi Dettagliati

### 1. Preparazione Dati
- Copia i dati in A1:C13
- Verifica che "Ricavi" sia numerico (allineato destra)
- Verifica che "Margine %" sia decimale (22.5 non 22,5 se locale italiano)
- Formatta intestazioni in grassetto

### 2. Creazione Grafico Base
1. Seleziona **A1:C13** (tutto)
2. Menu: **Inserisci → Grafico**
3. Google Fogli mostrerà probabilmente grafico a colonne con 2 serie
4. Configurazione → Tipo → **Grafico combinato**
5. Se non disponibile: seleziona "Istogramma a colonne" temporaneamente

### 3. Configurazione Serie Combinate

**Serie "Ricavi"**:
1. Editor → Tab **Configurazione**
2. Sezione **Serie**
3. Trova serie "Ricavi"
4. Tipo: **Colonne**
5. Asse: **Sinistro**

**Serie "Margine %"**:
1. Sezione **Serie**
2. Trova serie "Margine %"
3. Tipo: **Linea**
4. Asse: **Destro** ⚠️ (questo crea il secondo asse Y)

### 4. Personalizzazione Titolo e Assi

**Titolo**:
1. Tab **Personalizza** → Sezione **Titolo grafico**
2. Testo: `Ricavi Mensili e Margine di Profitto 2026`
3. Font: Arial, 16pt, Grassetto

**Asse Orizzontale (X)**:
1. Sezione **Asse orizzontale**
2. Titolo: `Mese`
3. Mostra tutte le etichette: ✓

**Asse Verticale Sinistro** (Ricavi):
1. Sezione **Asse verticale sinistro**
2. Titolo: `Ricavi (€)`
3. Formato: Personalizzato → `#.##0 €` 
   - O usa "Valuta arrotondata"
4. Min: `50000`
5. Max: `80000`
6. Intervalli: `5000` (opzionale)

**Asse Verticale Destro** (Margine):
1. Sezione **Asse verticale destro**
2. Titolo: `Margine (%)`
3. Formato: Percentuale con 1 decimale
   - Se valori sono già %, usa "Numero" con 1 decimale + "%" manuale
   - Oppure divide valori per 100 e usa formato percentuale
4. Min: `20` (o 0.20 se usi percentuale)
5. Max: `27` (o 0.27)
6. Intervalli: `1` (20%, 21%, 22%...)

### 5. Personalizzazione Estetica Serie

**Serie "Ricavi" (Colonne)**:
1. Tab **Personalizza** → **Serie** → "Ricavi"
2. Colore riempimento: Blu `#4285F4`
3. Opacità: 90% (per vedere linea se sovrapposta)
4. Bordo colonne: Nessuno o blu più scuro
5. Etichette dati: Nessuna (opzionale: solo massimo)

**Serie "Margine %" (Linea)**:
1. **Serie** → "Margine %"
2. Colore linea: Verde `#34A853`
3. Spessore: 3px
4. Tipo punto: **Cerchio** (●)
5. Dimensione punto: 6
6. Colore punto: Verde (uguale linea)
7. Opacità: 100%

### 6. Legenda e Stile

**Legenda**:
1. Sezione **Legenda**
2. Posizione: **In alto a destra**
3. Font: 10pt
4. Verifica che mostri:
   - ■ Ricavi (€)
   - ─●─ Margine (%)

**Stile Grafico**:
1. Sezione **Stile grafico**
2. Sfondo: Bianco
3. Bordo: Nessuno
4. Linee griglia: 
   - Orizzontali principali: ✓ (riferite ad asse sinistro)
   - Colore: Grigio chiaro (#E8E8E8)
   - Verticali: Facoltativo (leggere)

### 7. Verifica Finale

- ✓ Colonne blu per ricavi (scala sinistra)
- ✓ Linea verde per margine % (scala destra)
- ✓ Entrambi gli assi Y visibili e ben etichettati
- ✓ Scale appropriate (no distorsioni visive)
- ✓ Marcatori visibili sulla linea
- ✓ Legenda chiara
- ✓ Tutti i 12 mesi sull'asse X

### Risultato Atteso

```
       Ricavi Mensili e Margine di Profitto 2026
                                              Legend:
€ (sinistro)  ▲                          ▲ % (destro)  ■ Ricavi (€)
              │                          │             ─●─ Margine (%)
80k          ┌┴┐                        27%
             │●│●─────●●─────────●──●──●
75k         ┌┴┼┴┐┌───┐              ●  26%
            │ │ ││   │          ┌───┤
70k         │ │ ││   │     ┌───┐│   │  25%
           ┌┤ │ │└───┘┌───┐│●  ││   │
65k        ││ │ │ ●   ││   ││   ││   │  24%
           ││ │ │  ─  ││   ││   ││   │
60k        ││ │●│    ●││   ││   ││   │  23%
          ┌┤└┬┘●│     │└───┘│   ││   │
55k       ││ │  │     │     │   ││   │  22%
         ┌┤│●│  │    ●│     │   ││   │
50k      ││ │  │     │     │   ││   │  21%
         └┴─┴──┴─────┴─────┴───┴┴───┘  20%
         Gen Feb Mar Apr Mag Giu Lug Ago Set Ott Nov Dic
```

Il grafico mostra:
- Ricavi in crescita generale (colonne blu)
- Margine % fluttua ma trend positivo (linea verde)
- Correlazione visibile: ricavi alti → margine alto (es. Ott-Dic)
- Agosto = ricavi e margine bassi (stagionalità)

## Risposte Domande di Analisi

1. **Correlazione ricavi-margine**:
   
   Analisi visuale:
   - Ott-Nov-Dic: ricavi ↑ e margine ↑ (correlazione positiva)
   - Gen-Mag: ricavi ↑ e margine ↑ (correlazione positiva)
   - Ago-Set: ricavi ↓ poi ↑, margine ↓ poi ↑ massimo
   
   **Correlazione positiva generale**: quando l'azienda vende di più, tende ad avere margini migliori (economie di scala, potere negoziale, mix prodotti premium)

2. **Miglior margine e ricavi più alti**:
   - **Miglior margine**: Ottobre con **26,2%**
   - **Ricavi più alti**: Dicembre con **€78.000**
   
   Non coincidono! Dicembre ha ricavi massimi ma margine 26,0% (leggermente sotto Ottobre)

3. **Margine calato con ricavi alti**:
   - **Marzo**: Ricavi €54k (medi), margine 21,8% (basso)
   - **Giugno**: Ricavi €65k (alti), margine 24,7% (calo vs 25,3% di Maggio)
   - **Agosto**: Ricavi €55k (bassi), margine 21,5% (minimo anno)
   
   **Agosto** è il caso più evidente: sia ricavi che margine calano (vacanze estive = minor volume e sconti promozionali)

4. **Trend margine secondo semestre** (Lug-Dic):
   - Lug: 22,9%
   - Ago: 21,5% (minimo)
   - Set: 25,8% (ripresa forte)
   - Ott: 26,2% (massimo)
   - Nov: 25,9%
   - Dic: 26,0%
   
   **Trend fortemente positivo**: da 21,5% ad 26,0% (+4,5 punti percentuali)
   
   Dopo il calo estivo, forte recupero autunnale con margini eccellenti

5. **Profitto effettivo Ottobre**:
   ```
   Ricavi: €72.000
   Margine: 26,2%
   Profitto = €72.000 × 0,262 = €18.864
   ```
   
   **Profitto Ottobre: €18.864** (miglior mese dell'anno)

6. **Ricavi alti/margine basso vs ricavi medi/margine alto**:
   
   Confrontiamo due scenari:
   
   **Scenario A - Febbraio**:
   - Ricavi: €58.000
   - Margine: 23,2%
   - Profitto: €13.456
   
   **Scenario B - Ottobre**:
   - Ricavi: €72.000
   - Margine: 26,2%
   - Profitto: €18.864
   
   **Scenario C - Dicembre** (ricavi max, margine buono):
   - Ricavi: €78.000
   - Margine: 26,0%
   - Profitto: €20.280 (massimo!)
   
   **Risposta**: **L'ideale è ricavi alti CON margine alto** (Dicembre)
   
   Ma se devo scegliere:
   - Ricavi €80k con margine 20% = €16.000 profitto
   - Ricavi €60k con margine 27% = €16.200 profitto
   
   **Margine alto vince leggermente**, ma volume alto è più scalabile
   
   **Strategia ottimale**: Crescere ricavi mantenendo/migliorando margine (come Ott-Dic)

## Analisi Approfondita

### Calcolo Profitti Mensili

Aggiungi colonna D "Profitto (€)":

```
=B2*(C2/100)
```

Totali annui:
- Ricavi totali: €761.000
- Margine medio: 24,2%
- Profitto totale: **€184.162**

### Momenti Chiave

**Maggio** (punto di svolta):
- Ricavi €68k (+11% vs Apr)
- Margine 25,3% (+1,2pp vs Apr)
- Profitto €17.204 (eccellente)

**Agosto** (crisi estiva):
- Ricavi €55k (-7% vs Lug)
- Margine 21,5% (-1,4pp)
- Profitto €11.825 (minimo anno)
- **Azione**: Pianificare meglio campagne estive

**Settembre-Ottobre** (rimbalzo):
- Set: margine balza da 21,5% a 25,8%
- Ott: massimo margine 26,2% + ricavi €72k
- Probabile: fine sconti estivi + lancio prodotti autunnali

## Formule Utili

**Profitto mensile** (colonna D):
```
=B2*C2/100
```

**Crescita ricavi mese su mese**:
```
=(B3-B2)/B2*100
```

**Variazione margine (punti percentuali)**:
```
=C3-C2
```

**Profitto totale annuo**:
```
=SOMMA.PIÙ.SE(D2:D13)
oppure
=SOMMA(B2:B13*C2:C13/100)  [formula array]
```

</details>

---

## 🚀 Varianti (Bonus)

Prova queste estensioni:

### Variante A: Aggiungi Obiettivo Margine
- Crea terza serie: "Obiettivo Margine" = 24% fisso
- Linea tratteggiata rossa sull'asse destro
- Evidenzia mesi sotto obiettivo con formattazione condizionale

### Variante B: Calcola Profitto Effettivo
- Aggiungi colonna D: Profitto = Ricavi × (Margine/100)
- Crea secondo grafico: Profitto (colonne) vs Margine (linea)
- Quale mese ha il miglior profitto assoluto?

### Variante C: Analisi Trimestrale
- Crea tabella riepilogativa per trimestre
- Q1, Q2, Q3, Q4 con ricavi totali e margine medio
- Grafico colonne raggruppate: Ricavi vs Profitto per trimestre

### Variante D: Scenari "What-If"
- Aggiungi slider: "Se aumento ricavi del X%, margine varia di Y%"
- Tabella scenari: combinazioni ricavi/margine
- Calcola profitto per ogni scenario
- Identifica scenario ottimale

### Variante E: Benchmark Settoriale
- Aggiungi serie "Margine Medio Settore" = 23%
- Linea tratteggiata grigia sull'asse destro
- Calcola quanti mesi siamo sopra/sotto benchmark
- Analizza gap competitivo

---

## 📚 Concetti Chiave Appresi

✅ Grafici combinati (colonne + linea)  
✅ Doppio asse Y per scale diverse  
✅ Rappresentazione multi-KPI  
✅ Analisi correlazioni visive  
✅ Trade-off volume vs margine  
✅ Formattazione assi personalizzata  
✅ Interpretazione grafici complessi  

---

**Esercizio Precedente**: [Esercizio 6 - Linee Multiple](esercizio_06_linee_multiple.md)  
**Prossimo Esercizio**: [Esercizio 8 - Sparkline Dashboard](esercizio_08_sparkline_dashboard.md)
