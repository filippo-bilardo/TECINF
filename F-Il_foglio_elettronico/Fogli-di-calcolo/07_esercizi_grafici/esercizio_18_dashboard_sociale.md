# Esercizio 18: Dashboard Sociale Integrata

**Livello**: 🔴 Avanzato  
**Tipo grafico**: Dashboard Multi-Pannello + Radar/Colonne raggruppate  
**Tempo stimato**: 50 minuti  
**Tema**: Visione integrata benessere sociale, confronto territoriale  
**Competenze**: Dashboard design, KPI, sintesi multi-dimensionale, divari regionali

---

## 🎯 Obiettivo

Creare una dashboard integrata che sintetizzi in un colpo d'occhio lo stato di salute sociale di diverse regioni italiane attraverso 6 indicatori chiave (salute, alimentazione, ambiente, civica, sport, digitale), per identificare eccellenze, criticità e divari territoriali da colmare.

## 📖 Scenario

Sei data analyst per il Dipartimento per le Politiche Sociali della Presidenza del Consiglio. Ti è stato chiesto di creare una dashboard esecutiva per il Ministro che mostri in modo immediato e visivamente efficace come le diverse regioni italiane si posizionano su dimensioni chiave del benessere sociale, per orientare investimenti e politiche mirate.

## 📊 Dati Forniti

### Dataset 1: KPI Nazionali - Situazione Attuale vs Obiettivo 2030

Copia in celle A1:D8:

```
Dimensione	Valore_Attuale	Obiettivo_2030	Gap%
Salute_Copertura_Vaccinale%	89,2	95	-6,1
Alimentazione_Spreco_Kg_Anno	248	150	+65,3
Ambiente_Differenziata%	65,2	80	-18,5
Civica_Affluenza_Under30%	58,5	75	-22,0
Sport_Popolazione_Attiva%	38,5	55	-30,0
Digitale_Screen_Time_Ore	10,9	6	+81,7
```

**Note**: 
- Gap% negativo = sotto obiettivo (male)
- Gap% positivo = sopra obiettivo (male per spreco/screen time)

### Dataset 2: Confronto Regionale Multi-Dimensionale

Copia in celle F1:J7:

```
Regione	Salute_Score	Ambiente_Score	Sociale_Score	Digitale_Score
Trentino_AA	92	88	82	78
Lombardia	87	72	76	68
Emilia_Romagna	90	80	85	72
Lazio	82	68	71	65
Campania	76	58	64	58
Media_Italia	85	73	76	68
```

**Score**: 0-100, composito di vari indicatori per dimensione  
**Interpretazione**:
- 90-100: Eccellente ⭐⭐⭐
- 80-89: Buono ⭐⭐
- 70-79: Sufficiente ⭐
- <70: Critico ⚠️

### Dataset 3: Dettaglio Divari Nord-Sud (Per micro-grafici)

Copia in celle L1:N6:

```
Anno	Nord_Score	Sud_Score
2015	78	62
2017	80	64
2019	83	67
2021	85	69
2023	87	71
```

**Gap persistente**: ~16 punti (Nord avanti)  
**Trend**: Entrambi migliorano, ma gap non si chiude

---

## ✅ Requisiti

### Layout Dashboard (Foglio di lavoro organizzato)

Crea layout **2 righe × 3 colonne** (6 pannelli principali):

```
┌─────────────┬─────────────┬─────────────┐
│  KPI Card   │  KPI Card   │  KPI Card   │
│   Salute    │Alimentazione│  Ambiente   │
│  + Gauge    │  + Sparkline│  + Gauge    │
├─────────────┼─────────────┼─────────────┤
│  KPI Card   │  KPI Card   │  KPI Card   │
│   Civica    │    Sport    │  Digitale   │
│  + Gauge    │  + Gauge    │  + Sparkline│
└─────────────┴─────────────┴─────────────┘

┌───────────────────────────────────────────┐
│    Grafico Radar/Colonne Raggruppate     │
│      Confronto 5 Regioni (4 Score)       │
└───────────────────────────────────────────┘

┌───────────────────────────────────────────┐
│       Micro-Grafico Trend Nord-Sud        │
│          (Linee divergenti)               │
└───────────────────────────────────────────┘
```

### Pannello 1-6: KPI Cards (6 Indicatori)

Per **ogni KPI Card** crea:

1. **Intestazione**:
   - Icona/Emoji dimensione + Nome dimensione
   - Font grande, bold
   - Colore semantico (verde/rosso a seconda gap)

2. **Numero grande centrale**:
   - Valore attuale (es: 89,2%)
   - Font gigante (36-48pt)
   - Colore: Verde se sopra 80, Arancione 70-80, Rosso <70

3. **Micro-visual**:
   - **Gauge (semicerchio)**: Per Salute, Ambiente, Civica, Sport
     - Mostra % progresso verso obiettivo 2030
     - Settori colorati: Rosso (0-60%), Giallo (60-85%), Verde (85-100%)
   - **Sparkline (linea micro)**: Per Alimentazione, Digitale
     - Trend ultimi 5 anni (se in miglioramento)

4. **Dettagli sotto**:
   - Obiettivo 2030: X
   - Gap: ±Y%
   - Icona: ✅ vicino obiettivo, ⚠️ lontano, 🚨 critico

**Esempio Card Salute**:
```
┌─────────────────────┐
│ 🏥 SALUTE           │
│                     │
│       89,2%         │ ← Grande
│     ╱─────╲         │
│   ╱│  ○   │╲        │ ← Gauge
│  ╱ └──┬───┘ ╲       │
│ └────┴────┴─┘       │
│  60% 85% 100%       │
│                     │
│ Obiettivo: 95%      │
│ Gap: -6,1% ⚠️       │
└─────────────────────┘
```

### Grafico 7: Confronto Regionale (Radar o Colonne raggruppate)

**Opzione A - Radar** (consigliato per impatto visivo):
1. **Tipo**: Grafico radar (spider/web chart)
2. **Titolo**: "Confronto Multi-Dimensionale Regioni Italiane"
3. **Assi**: 4 dimensioni (Salute, Ambiente, Sociale, Digitale)
4. **Serie**: 5 regioni sovrapposte
5. **Colori**:
   - Trentino: Verde scuro #2E7D32 (eccellenza)
   - Emilia-Romagna: Verde chiaro #7CB342
   - Lombardia: Blu #4285F4
   - Lazio: Arancione #FBBC04
   - Campania: Rosso #EA4335 (criticità)
6. **Linee**: Spessore 2-3px, trasparenza 60%
7. **Area riempita**: Trasparenza 20% per vedere sovrapposizioni
8. **Scala radiale**: 0-100
9. **Marcatori**: Cerchi su ogni vertice

**Opzione B - Colonne raggruppate**:
- 4 gruppi (dimensioni) × 5 colonne (regioni)
- Stessi colori Opzione A
- Etichette valori score

### Grafico 8: Divario Nord-Sud (Trend Temporale)

1. **Tipo**: Grafico a linee (2 serie)
2. **Titolo**: "Divario Nord-Sud: Il Gap Non Si Chiude"
3. **Serie**:
   - Nord: Blu #1976D2, spessore 3px
   - Sud: Rosso #D32F2F, spessore 3px
4. **Marcatori**: Cerchi grandi
5. **Area tra linee**: Riempimento grigio 30% (evidenzia gap)
6. **Annotazioni**:
   - Linea verticale tratteggiata su 2021: "COVID-19"
   - Testo "Gap persistente: ~16 punti" su area grigia
7. **Asse Y**: "Score Medio Benessere Sociale", 50-100
8. **Dimensioni**: Più largo che alto (trend orizzontale)

---

## 🤔 Domande di Analisi Critica

### Dashboard KPI (Generale):
1. Quali sono i 2 indicatori più critici (lontani da obiettivo 2030)?
2. Su 6 dimensioni, quante sono "verdi" (vicine a obiettivo)?
3. Calcola uno "score sociale medio" nazionale: Quanto siamo distanti da 100?
4. Se dovessi scegliere 1 sola priorità di investimento, quale e perché?

### Confronto Regionale:
1. Quale regione è la "migliore" overall? Calcola score medio 4 dimensioni
2. Campania ha score più bassi: Quali cause storiche/strutturali?
3. Trentino eccelle: Cosa fa diversamente? Modello replicabile?
4. Lazio (sede governo) è sotto media: Significativo?

### Divario Nord-Sud:
1. Il gap 2015-2023 aumenta, diminuisce o resta stabile?
2. Sud migliora in assoluto (+9 punti), ma gap non si chiude: Perché?
3. Quale impatto ha divario su coesione nazionale?
4. Quali politiche potrebbero ridurre gap nei prossimi 10 anni?

---

## 💡 Riflessioni Educative

Questo esercizio avanzato ci porta a riflettere su:

- **Complessità sociale**: Benessere non è mono-dimensionale, serve visione integrata
- **Divari territoriali**: Italia profondamente diseguale, non solo Nord-Sud
- **Dati per decisioni**: Dashboard trasforma numeri in insight azionabili
- **Eccellenze locali**: Trentino, Emilia modelli da studiare e replicare
- **Urgenza investimenti**: Gap digitale, sport, civica richiedono azione immediata
- **Interdipendenza**: Salute ↔ Ambiente ↔ Sociale (tutto connesso)
- **Responsabilità politica**: Dati non mentono, performance regionali oggettive

---

<details>
<summary><strong>📝 Soluzione Completa</strong></summary>

## Preparazione Workspace

### Step 1: Layout Foglio

Organizza il foglio Google Sheets:

1. **Righe 1-15**: Spazio per 6 KPI Cards (2 righe × 3 colonne)
   - Card 1: A1:D15 (Salute)
   - Card 2: F1:I15 (Alimentazione)
   - Card 3: K1:N15 (Ambiente)
   - Card 4: A17:D31 (Civica)
   - Card 5: F17:I31 (Sport)
   - Card 6: K17:N31 (Digitale)

2. **Righe 35-55**: Grafico Radar/Colonne (A35:N55)

3. **Righe 57-70**: Grafico Trend Nord-Sud (A57:N70)

### Step 2: Calcoli Helper

Crea foglio "Calcoli" per preparare dati gauge e sparkline.

**Gauge - Percentuale completamento obiettivo**:
```
Formula per Salute (esempio):
= (Valore_Attuale / Obiettivo_2030) * 100
= (89,2 / 95) * 100 = 93,9%
```

Calcola per tutti:
```
Salute: 93,9%
Alimentazione: 60,5% (inverso, spreco deve calare)
Ambiente: 81,5%
Civica: 78,0%
Sport: 70,0%
Digitale: 55,0% (inverso, screen time deve calare)
```

## KPI Cards - Creazione

### Card 1: Salute 🏥

**Cella A1** (Intestazione):
- Testo: `🏥 SALUTE`
- Font: Bold, 18pt
- Colore testo: Verde scuro #2E7D32
- Sfondo: Verde chiaro #E8F5E9

**Cella B4** (Numero grande):
- Testo: `89,2%`
- Font: Bold, 48pt
- Colore: Verde #34A853
- Allineamento: Centro

**Gauge (B6:C10)**:
Crea micro-grafico gauge:
1. Dati helper:
```
Range	Valore
0-60	60
60-85	25
85-100	15
Attuale	93,9
```

2. Inserisci grafico a ciambella:
   - Segmenti: Rosso (60), Giallo (25), Verde (15)
   - Punto attuale: Freccia/marcatore a 93,9%
   - Semicerchio (elimina metà inferiore)

**Dettagli (A12:D14)**:
```
Obiettivo 2030: 95%
Gap: -6,1%
Status: ⚠️ Da migliorare
```

**Replica per altre 5 card** cambiando:
- Icone: 🍽️ Alimentazione, 🌍 Ambiente, 🗳️ Civica, ⚽ Sport, 📱 Digitale
- Colori semantici (rosso se critico, verde se buono)
- Gauge percentuali

### Card 2: Alimentazione 🍽️ (con Sparkline)

Differenza: Al posto di gauge, usa **sparkline** trend spreco:

**Dati trend spreco 2018-2023** (crea se non hai):
```
Anno	Kg_Spreco
2018	285
2019	278
2020	268
2021	262
2022	255
2023	248
```

**Sparkline (G7:I9)**:
1. Seleziona dati trend
2. Inserisci → Grafico → Linea semplice
3. Riduci dimensioni a mini (5cm × 2cm)
4. Rimuovi: Titolo, assi, griglia, legenda
5. Solo linea: Verde #34A853, spessore 2px
6. Posiziona nella card

**Interpretazione**: Trend positivo (cala), ma ancora lontano da 150 kg.

### Cards 3-6: Replica

- **Card 3 - Ambiente**: Gauge 81,5%, Verde chiaro ⭐
- **Card 4 - Civica**: Gauge 78%, Arancione ⚠️
- **Card 5 - Sport**: Gauge 70%, Arancione ⚠️
- **Card 6 - Digitale**: Sparkline screen time (crescente, critico) 🚨

## Grafico Radar - Confronto Regionale

### Preparazione Dati

Dati già in F1:J7. Formato per radar:

**Transponi** per avere regioni come serie:
```
Dimensione	Trentino	Lombardia	Emilia-R	Lazio	Campania
Salute	92	87	90	82	76
Ambiente	88	72	80	68	58
Sociale	82	76	85	71	64
Digitale	78	68	72	65	58
```

### Creazione Grafico

1. Seleziona dati trasposti
2. Inserisci → Grafico → Altri → Radar

**Configurazione**:
- Assi: 4 dimensioni (radiali)
- Serie: 5 regioni (linee sovrapposte)
- Scala: 0-100

**Personalizza Serie**:

**Trentino**:
- Colore linea: Verde scuro #2E7D32
- Spessore: 3px
- Area: Riempimento verde 20%
- Marcatori: Cerchi 8px

**Emilia-Romagna**:
- Colore: Verde chiaro #7CB342
- Spessore: 3px
- Area: Riempimento 20%
- Marcatori: Cerchi 8px

**Lombardia**:
- Colore: Blu #4285F4
- Spessore: 2px
- Area: Riempimento 20%
- Marcatori: Cerchi 6px

**Lazio**:
- Colore: Arancione #FBBC04
- Spessore: 2px
- Area: Riempimento 20%
- Marcatori: Cerchi 6px

**Campania**:
- Colore: Rosso #EA4335
- Spessore: 3px (evidenziare criticità)
- Area: Riempimento rosso 15%
- Marcatori: Cerchi 8px

**Titolo**: `Confronto Multi-Dimensionale Regioni Italiane`
**Sottotitolo**: `Score 0-100 su 4 dimensioni del benessere sociale`

**Griglia radiale**: Cerchi a 25, 50, 75, 100
**Etichette**: Valori su vertici

### Risultato Atteso

```
                Salute (100)
                     ●
                   ╱   ╲
                 ╱       ╲
               ╱           ╲
             ╱               ╲
           ╱                   ╲
  Digitale●                     ●Ambiente
  (100)    │╲                 ╱│(100)
           │  ╲             ╱  │
           │    ╲         ╱    │
           │      ╲     ╱      │
           │        ╲ ╱        │
           │         ●         │
           │      Sociale      │
           │      (100)        │
           
   ━ Trentino (ampio)
   ━ Emilia-R (ampio)
   ━ Lombardia (medio)
   ━ Lazio (stretto)
   ━ Campania (più stretto)
```

**Insight visivi**:
- **Trentino**: Area massima, eccellenza su tutte dimensioni
- **Emilia-R**: Secondo, forte su Sociale (85)
- **Campania**: Area minima, sotto 70 su 3/4 dimensioni
- **Pattern**: Nord domina, Sud indietro su tutto

## Grafico Trend Nord-Sud

### Creazione

1. Seleziona L1:N6
2. Inserisci → Grafico → Linee

**Serie Nord**:
- Colore: Blu #1976D2
- Spessore: 3px
- Marcatori: Cerchi pieni 10px
- Etichette: Valori score

**Serie Sud**:
- Colore: Rosso #D32F2F
- Spessore: 3px
- Marcatori: Cerchi pieni 10px
- Etichette: Valori score

**Area Gap**:
- Riempimento tra linee: Grigio 30%
- Evidenzia divario persistente

**Annotazione COVID**:
- Linea verticale tratteggiata su 2021
- Testo: "COVID-19" sopra
- Nota: "Rallentamento temporaneo entrambe aree"

**Annotazione Gap**:
- Casella testo su area grigia centrale
- Testo: "Gap persistente: ~16 punti"
- Font: Bold, 14pt

**Titolo**: `Divario Nord-Sud: Il Gap Non Si Chiude`
**Sottotitolo**: `Score medio benessere sociale 2015-2023`

**Assi**:
- X: Anno
- Y: "Score Benessere Sociale", 50-100

**Dimensioni**: Largo (20cm) × Basso (10cm)

### Risultato Atteso

```
Score
100│
   │
 90│
   │                      ○────○
 85│              ○────○╱
   │          ○──╱     Gap ~16
 80│      ○──╱ ░░░░░░░░░░░░░
   │  ○──╱ ░░░░░░░░░░░░░░░░
 75│    ░░░░░░░░░░░░░░░░░░
   │ ░░░│░░░░░░░░░░░░░░░○────○
 70│░░░░│░░░░░░░○────○╱
   │░░░░│░○────○
 65│░░░░│╱
   │░○──○  COVID
 60│    ▼
   └────────────────────────────→ Anno
    2015 2017 2019 2021 2023

    ──○── Nord  ──○── Sud  ░ Gap
```

**Insight visivi**:
- **Entrambi migliorano**: Nord +9 punti, Sud +9 punti (2015-2023)
- **Gap stabile**: ~16 punti sempre
- **Trend paralleli**: Crescita proporzionale, divario non si colma
- **COVID**: Impatto lieve, recupero rapido

## Risposte Domande di Analisi

### Dashboard KPI

1. **2 indicatori più critici?**
   - **1. Sport**: Gap -30% (38,5% vs 55% obiettivo)
     - Solo 2 italiani su 5 attivi
     - Sedentarietà pandemica
     - Serve: Palestre pubbliche, sport scuola quotidiano
   - **2. Digitale**: Gap +81,7% (10,9h vs 6h obiettivo)
     - Screen time quasi doppio del target
     - Giovani più colpiti (14h weekend)
     - Serve: Educazione digitale, app controllo

2. **Quante dimensioni "verdi" (vicine)?**
   - **Verde (>85% obiettivo)**: Solo **Salute** (93,9%)
   - **Giallo (70-85%)**: Civica (78%), Ambiente (81,5%)
   - **Rosso (<70%)**: Sport (70%), Digitale (55%), Alimentazione (60,5%)
   - **Verdetto**: 1/6 verde, 5/6 problematiche

3. **Score sociale medio nazionale?**
   - Media 6 dimensioni (normalizzato 0-100):
   - Salute: 89,2 (già %)
   - Alimentazione: 60,5 (100 - eccesso su 150 kg)
   - Ambiente: 65,2 (già %)
   - Civica: 58,5 (già %)
   - Sport: 38,5 (già %)
   - Digitale: 55,0 (100 - eccesso su 6h)
   - **Media: (89,2+60,5+65,2+58,5+38,5+55,0)/6 = 61,2/100**
   - **Distanza da 100: -38,8 punti** 🚨

4. **Priorità investimento singola?**
   - **Sport/Movimento** perché:
     - Impact massimo: Movimento migliora salute (costi SSN -20%), sonno (+1h), umore (+30%), rendimento scuola (+15%)
     - Costo basso: Palestre pubbliche, piste ciclabili, educazione fisica
     - Effetto domino: Sport → Meno schermi + Meno obesità + Più socialità
     - ROI altissimo: €1 sport = €7 risparmiati sanità
     - Urgenza: 60% bambini sedentari = adulti malati futuri

### Confronto Regionale

1. **Regione migliore overall?**
   - Calcolo score medio 4 dimensioni:
   - **Trentino**: (92+88+82+78)/4 = **85,0** 🥇
   - **Emilia-Romagna**: (90+80+85+72)/4 = **81,8** 🥈
   - **Lombardia**: (87+72+76+68)/4 = **75,8** 🥉
   - **Lazio**: (82+68+71+65)/4 = **71,5**
   - **Campania**: (76+58+64+58)/4 = **64,0**
   - **Vincitore**: Trentino-Alto Adige (eccellenza su tutto)

2. **Campania score bassi - cause?**
   
   **Storiche**:
   - Sottosviluppo post-unità (1861)
   - Investimenti concentrati Nord (industria)
   - Emigrazione cervelli (Sud → Nord/Estero)
   - Criminalità organizzata (camorra)
   
   **Strutturali attuali**:
   - Sanità: Commissariamento, deficit, liste attesa lunghe
   - Lavoro: Disoccupazione giovanile 50% (vs 20% Nord)
   - Ambiente: Terra dei fuochi, differenziata bassa
   - Educazione: Abbandono scolastico 17% (vs 10% Nord)
   - Infrastrutture: Trasporti obsoleti, digital divide
   
   **Circolo vizioso**:
   - Servizi scarsi → Giovani emigrano → Meno talenti → Meno innovazione → Servizi scarsi

3. **Trentino eccellenza - cosa fa diversamente?**
   
   **Autonomia speciale**:
   - Statuto speciale dal 1948
   - Trattiene 90% tasse (vs 40% regioni ordinarie)
   - Autogoverno su sanità, scuola, trasporti
   
   **Investimenti mirati**:
   - **Sanità**: 3.200€/capita (vs 1.900€ Campania)
   - **Educazione**: Scuole bilinguismo, digitale avanzato
   - **Ambiente**: 85% differenziata, mobilità sostenibile
   - **Sociale**: Asili gratuiti, welfare famiglia
   
   **Modello replicabile?**
   - **In parte sì**: Best practices copiabili (es: asili gratis, trasporti)
   - **In parte no**: Risorse speciali non replicabili (autonomia fiscale)
   - **Lezione**: Investire in sociale paga (Trentino PIL +30% media)

4. **Lazio sotto media - significativo?**
   - **Sì, paradosso del potere**:
     - Sede governo, parlamento, ministeri
     - Ma score 71,5 (sotto media 76)
     - Peggio di Emilia-R (81,8) senza poteri centrali
   
   **Cause Roma "buco nero"**:
   - Megalopoli (4,3M abitanti): Servizi sovraccarichi
   - Turismo: Risorse a visitatori, non residenti
   - Burocrazia: Lentezza amministrativa
   - Immigrazione: Pressione welfare (positiva ma costosa)
   - Sprechi: Scandali, corruzione, inefficienze
   
   **Segnale**: Centralismo non garantisce qualità vita

### Divario Nord-Sud

1. **Gap aumenta, diminuisce o stabile?**
   - **Stabile** (~16 punti costanti 2015-2023)
   - 2015: 78-62 = 16 punti
   - 2023: 87-71 = 16 punti
   - **Crescita parallela**: Entrambi +9, gap proporzionale
   - **Problema**: Convergenza NON sta avvenendo

2. **Sud migliora +9 ma gap non si chiude - perché?**
   - **Crescita proporzionale, non assoluta**:
     - Se Nord cresce +10%, Sud +10%, gap resta
     - Serve Sud +15%, Nord +5% per convergere
   
   **Cause mancata convergenza**:
   - Investimenti europei (2014-2020) equi Nord-Sud → Gap persiste
   - Brain drain: Laureati Sud (30%) → Nord/Estero
   - Innovazione: Startup 80% Nord, 20% Sud
   - Infrastrutture: Alta velocità ferma a Salerno
   - Attrattività: Imprese evitano Sud (burocrazia, criminalità)
   
   **Teoria economica**:
   - Convergenza richiede: Capitale umano + Istituzioni + Infrastrutture
   - Sud ha solo crescita "trascinata", non autonoma

3. **Impatto divario su coesione nazionale?**
   
   **Sociale**:
   - Emigrazione interna: 130.000/anno Sud → Nord
   - Famiglie spezzate (genitori Sud, figli Nord)
   - Risentimento: "Nord paga, Sud spreca" vs "Nord sfrutta, Sud abbandonato"
   - Stereotipi: Pigri/parassiti vs Razzisti/egoisti
   
   **Economico**:
   - PIL: Nord €38k/capita, Sud €20k/capita (divario 90%!)
   - Mercato interno debole: Sud basso potere acquisto
   - Competitività: Italia intera penalizzata da squilibri
   
   **Politico**:
   - Populismi: Lega Nord (anti-Sud) vs M5S (anti-casta Nord)
   - Autonomia differenziata: Rischio frammentazione
   - Astensionismo: Sud sfiduciato (voto inutile)
   
   **Culturale**:
   - Identità nazionale fragile
   - "Due Italie" narrative
   - Talenti Sud ignorati/svalutati

4. **Politiche per ridurre gap prossimi 10 anni?**
   
   **Investimenti massicci mirati** (PNRR 2.0):
   - €100 mld extra Sud (non equi): 70% risorse Sud, 30% Nord
   - Infrastrutture: Alta velocità fino Reggio Calabria, banda larga 100%
   - Asili nido: Sud 12% copertura vs 30% Nord → Portare a 60% (lavoro donne)
   
   **Fiscalità di vantaggio**:
   - Decontribuzione imprese Sud (5 anni)
   - Startup hub: Incubatori pubblici (Napoli, Palermo, Bari)
   - Incentivi rientro cervelli: €20k/anno per 3 anni laureati che tornano
   
   **Legalità e trasparenza**:
   - Investire antimafia: Confisca beni, educazione legalità
   - Pubblica amministrazione: Concorsi meritocratici, valutazione performance
   - Trasparenza: Open data spesa pubblica (no sprechi)
   
   **Capitale umano**:
   - Scuola: Tempo pieno ovunque (ora 30% Sud vs 80% Nord)
   - Università: Borse studio +50%, finanziamenti ricerca equi
   - Formazione: Riqualificazione disoccupati (digitale, green)
   
   **Modello**: 
   - Non assistenzialismo (perpetua dipendenza)
   - Investimenti per competitività autonoma Sud
   - Obiettivo: Gap da 16 a 8 punti entro 2033

## Riflessioni Finali

**Messaggi chiave dashboard**:
1. 📊 **Visione integrata**: 1 score non basta, serve analisi multi-dimensionale
2. 🚨 **5/6 dimensioni critiche**: Sport e digitale emergenze, salute unica sufficiente
3. 🏆 **Eccellenze replicabili**: Trentino ed Emilia mostrano la via
4. ⚖️ **Divari inaccettabili**: 16 punti Nord-Sud = Due Paesi diversi
5. 📈 **Trend positivi ma lenti**: Tutti migliorano, ma non abbastanza veloce
6. 🎯 **Obiettivi 2030 a rischio**: Con trend attuale, falliremo 5/6 target

**Azioni concrete governance**:
- 💰 **Riallocare risorse**: Da assistenza a investimenti produttivi
- 📍 **Politiche territoriali**: Taglia unica non funziona (Campania ≠ Trentino)
- 📊 **Monitoraggio continuo**: Dashboard aggiornata trimestrale (accountability)
- 🤝 **Patti sviluppo**: Fondi vincolati a obiettivi misurabili
- 🔬 **Evidenze scientifiche**: Ogni euro investito dove ROI massimo
- 🗣️ **Coinvolgimento cittadini**: Dati pubblici, consultazioni online

**Dashboard come strumento democrazia**:
- **Trasparenza**: Cittadini vedono performance reale (no propaganda)
- **Accountability**: Politici giudicati su risultati oggettivi
- **Empowerment**: Ognuno capisce dove agire individualmente
- **Confronto**: Regioni imparano da best practice
- **Urgenza visiva**: Rosso/verde immediato (no numeri nascosti)

</details>

---

## 🚀 Varianti e Approfondimenti

### Variante A: Dashboard Provinciale Micro
Replica per 10 province specifiche (es: Milano, Roma, Napoli, Palermo, Catania, Bari, Torino, Bologna, Firenze, Venezia). Dettaglio ultra-locale.

### Variante B: Correlazioni KPI
Matrice correlazione tra 6 dimensioni:
```
        Salute Alim Amb Civ Sport Dig
Salute   1,0  0,6  0,5 0,4  0,7  -0,6
Sport    0,7  0,5  0,4 0,3  1,0  -0,8
```
Heatmap: Movimento correlato con salute (+) e schermi (-)

### Variante C: Simulatore Obiettivi 2030
Slider interattivi: "Se investiamo X mld in Sport, score cresce Y punti". Calcola investimento ottimale per raggiungere tutti target 2030.

### Variante D: Benchmark Internazionale
Aggiungi dati Paesi UE comparabili:
```
Paese	Score_Medio
Norvegia	92
Germania	88
Italia	68
Spagna	75
Grecia	64
```
Posizionamento Italia in Europa (sotto media).

### Variante E: Dashboard Temporale
Stesso layout 6 KPI cards, ma confronta 2015 vs 2023 vs Proiezione 2030. Tre colonne affiancate per vedere evoluzione.

---

## 🔗 Risorse Approfondimento

### Dashboard e Data Visualization:
- **Alberto Cairo** - "The Functional Art" (teoria dashboard)
- **Stephen Few** - "Information Dashboard Design" (best practices)
- **Google Data Studio**: www.datastudio.google.com (tool dashboard gratuito)
- **Tableau Public**: www.public.tableau.com (esempi dashboard)

### Dati Benessere Italia:
- **ISTAT BES** (Benessere Equo Sostenibile): www.istat.it/bes
- **OCSE Better Life Index**: www.oecdbetterlifeindex.org
- **Eurostat Quality of Life**: ec.europa.eu/eurostat
- **Sole 24 Ore Qualità Vita**: lab24.ilsole24ore.com/qualita-vita

### Divari Territoriali:
- **SVIMEZ** (Sud Italia): www.svimez.info
- **Rapporto CENSIS**: www.censis.it
- **Istituto Cattaneo**: www.cattaneo.org

### Tools Tecnici:
- **Gauge Charts**: Grafici semicerchio (plugin Google Sheets)
- **Sparklines**: `=SPARKLINE(range, options)` funzione integrata Sheets
- **Radar Charts**: Add-on "ChartExpo" per Google Sheets

---

**Esercizio Precedente**: [Esercizio 17 - Stili di Vita](esercizio_17_stili_vita.md)  
**Torna all'Indice**: [README Esercizi Grafici](README.md)
