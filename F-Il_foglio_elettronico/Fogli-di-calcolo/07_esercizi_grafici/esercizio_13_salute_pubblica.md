# Esercizio 13: Salute Pubblica - Analisi Dati Sanitari

**Livello**: 🟡 Intermedio  
**Tipo grafico**: Multiplo (Linee + Scatter + Combinato)  
**Tempo stimato**: 40 minuti  
**Tema**: Educazione sanitaria e prevenzione  
**Competenze**: Grafici multipli, analisi correlazioni, interpretazione dati sociali

---

## 🎯 Obiettivo

Analizzare tre aspetti della salute pubblica attraverso grafici diversi per comprendere l'importanza della prevenzione, vaccinazioni e investimento sanitario.

## 📖 Scenario

Lavori per il Dipartimento di Salute Pubblica e devi preparare una presentazione per sensibilizzare cittadini e decisori politici sull'importanza della prevenzione sanitaria. Hai a disposizione dati su copertura vaccinale, correlazione spesa-salute e impatto degli screening.

## 📊 Dati Forniti

### Dataset 1: Copertura Vaccinale per Età

Copia in celle A1:D7:

```
Fascia_Età	Morbillo	Polio	HPV
0-2 anni	94,2	95,8	0
3-5 anni	93,5	94,9	0
6-12 anni	91,8	93,2	0
13-17 anni	88,5	90,1	65,3
18-24 anni	85,2	87,5	58,7
25-40 anni	78,9	82,3	45,2
```

**Nota**: 0 = Non applicabile per quella fascia d'età

### Dataset 2: Aspettativa di Vita vs Spesa Sanitaria (Regioni)

Copia in celle F1:H6:

```
Regione	Aspettativa_Vita	Spesa_ProCapite
Lombardia	83,5	2580
Toscana	83,9	2420
Lazio	82,8	2680
Campania	80,5	1950
Sicilia	81,2	1890
```

### Dataset 3: Malattie Prevenibili - Screening

Copia in celle J1:L6:

```
Screening	Diagnosi_Precoci	Mortalità_Evitata%
Mammografia	8500	35
Pap test	6200	45
Colonscopia	4800	40
PSA prostata	3100	25
Melanoma	2400	60
```

---

## ✅ Requisiti

### Grafico 1: Copertura Vaccinale (Dataset 1)

1. **Tipo**: Grafico a linee multiple
2. **Serie**: 3 linee (Morbillo, Polio, HPV)
3. **Titolo**: "Copertura Vaccinale per Fascia d'Età - Italia 2026"
4. **Asse Y**: "Copertura (%)", scala 0-100%
5. **Linee**:
   - Morbillo: Rosso, spessore 3px
   - Polio: Blu, spessore 3px  
   - HPV: Verde, spessore 3px, marcatori cerchio
6. **Annotazione**: Linea orizzontale al 95% (soglia immunità di gregge)
7. **Legenda**: Visibile

### Grafico 2: Salute vs Spesa (Dataset 2)

1. **Tipo**: Grafico a dispersione (scatter)
2. **Asse X**: Spesa pro capite (€)
3. **Asse Y**: Aspettativa di vita (anni)
4. **Titolo**: "Aspettativa di Vita vs Spesa Sanitaria Regionale"
5. **Punti**: Dimensione 8, con etichette regione
6. **Linea di tendenza**: Lineare, mostra R²
7. **Colore**: Blu, bordo marcato

### Grafico 3: Efficacia Screening (Dataset 3)

1. **Tipo**: Grafico combinato (colonne + linea)
2. **Titolo**: "Efficacia degli Screening Preventivi"
3. **Colonne**: Diagnosi precoci (asse sx)
4. **Linea**: Mortalità evitata % (asse dx)
5. **Colori**: Colonne verde, linea arancione
6. **Etichette**: Valori su entrambe le serie

---

## 🤔 Domande di Analisi Critica

### Sul Grafico 1 (Vaccinazioni):
1. Perché la copertura vaccinale diminuisce con l'età?
2. Quali fasce d'età sono sotto la soglia del 95% (immunità di gregge)?
3. Cosa comporta il calo di copertura per la salute collettiva?
4. HPV ha copertura più bassa: quali potrebbero essere le cause?

### Sul Grafico 2 (Spesa-Salute):
1. C'è correlazione tra spesa sanitaria e aspettativa di vita?
2. Quale regione ha il miglior "rapporto qualità-prezzo"?
3. Perché Lazio spende di più ma ha aspettativa inferiore a Toscana?
4. Cosa suggerisce il grafico sull'efficienza del sistema sanitario?

### Sul Grafico 3 (Screening):
1. Quale screening salva più vite in percentuale?
2. C'è correlazione tra numero diagnosi e mortalità evitata?
3. Qual è il valore economico e sociale della prevenzione?
4. Perché lo screening melanoma è così efficace?

---

## 💡 Riflessioni Educative

Questo esercizio ci porta a riflettere su:

- **Responsabilità individuale**: Le vaccinazioni proteggono sé e gli altri (solidarietà)
- **Equità territoriale**: Diritto alla salute uguale per tutti
- **Valore prevenzione**: Meglio prevenire che curare
- **Scelte informate**: Dati oggettivi vs fake news
- **Investimento pubblico**: Dove allocare risorse sanitarie

---

<details>
<summary><strong>📝 Soluzione Completa</strong></summary>

## Grafico 1: Copertura Vaccinale

### Passi Creazione

1. Seleziona A1:D7
2. Inserisci → Grafico → Linee
3. **Personalizza**:

**Serie Morbillo**:
- Colore: Rosso (#EA4335)
- Spessore: 3px
- Marcatori: Cerchi piccoli

**Serie Polio**:
- Colore: Blu (#4285F4)
- Spessore: 3px
- Marcatori: Cerchi piccoli

**Serie HPV**:
- Colore: Verde (#34A853)
- Spessore: 3px
- Marcatori: Cerchi grandi (più visibili dato meno punti)

**Linea 95% (soglia)**:
Aggiungi serie helper:
```
Colonna E: 95 per tutte le righe
```
Serie "Soglia 95%": Linea rossa tratteggiata sottile

**Titolo**: `Copertura Vaccinale per Fascia d'Età - Italia 2026`
**Sottotitolo**: `Linea rossa = soglia immunità di gregge (95%)`

### Risultato Atteso

```
Copertura %
100 ├─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ 95% (soglia)
 95 │○──○──
 90 │   ╲──○──○            (Morbillo/Polio)
 85 │         ╲──○──
 80 │               ○        (HPV inizia a 13-17)
    │                  ○──
 60 │                     ○
    └────────────────────────→ Età
     0-2  6-12  18-24  25-40
```

**Insight visivo**: Calo progressivo, sotto soglia dai 13 anni

## Grafico 2: Scatter Spesa-Salute

### Passi Creazione

1. Seleziona F1:H6
2. Inserisci → Grafico → Dispersione
3. **Configurazione**:
   - X: Spesa_ProCapite
   - Y: Aspettativa_Vita
   - Etichetta: Regione

4. **Linea di tendenza**:
   - Tipo: Lineare
   - Mostra R²
   - Colore: Grigio tratteggiato

5. **Personalizza punti**:
   - Dimensione: 10px
   - Colore: Blu
   - Bordo: Nero 2px
   - Etichette: Nome regione sopra punto

### Risultato e Analisi

```
Aspettativa
    ▲
84  │     ○ Toscana
    │
83  │ ○ Lombardia
    │           ╱
82  │       ○ Lazio    R² = 0,68
    │     ╱
81  │  ╱  ○ Sicilia
    │╱
80  │○ Campania
    └─────────────────────→ Spesa
     1800  2200  2600 €/capita
```

**R² ≈ 0,68**: Correlazione moderata-forte
- Più spesa generalmente → più longevità
- Ma: Toscana (2420€) batte Lazio (2680€)!
- **Insight**: Efficienza conta più del budget

## Grafico 3: Efficacia Screening

### Passi Creazione

1. Seleziona J1:L6
2. Inserisci → Grafico → Combinato

**Configurazione**:
- Diagnosi_Precoci: Colonne, asse sinistro
- Mortalità_Evitata%: Linea, asse destro

**Colonne (Diagnosi)**:
- Colore: Verde (#34A853)
- Etichette: Valore numerico sopra

**Linea (Mortalità)**:
- Colore: Arancione (#FBBC04)
- Spessore: 3px
- Marcatori: Rombi grandi
- Etichette: Percentuale

**Assi**:
- Sx: "Diagnosi Precoci (n°)", 0-10.000
- Dx: "Mortalità Evitata (%)", 0-70%

### Risultato Atteso

```
Diagnosi          Mortalità%
10k│                          │70%
   │                          │
8k │┌──┐                ◇     │60%
   ││  │           ─◇──       │50%
6k ││  │┌──┐  ─◇──      ◇    │40%
   ││  ││  │◇─              ◇ │30%
4k ││  ││  │┌─┐  ┌─┐  ┌─┐    │20%
   │└──┴└──┴└─┴┘└──┴┘└──┘ │
   └────────────────────────────
    Mam Pap Col PSA Mel
```

**Insight**: Melanoma ha meno diagnosi ma salva più vite (60%)!
- Precocità è cruciale
- Rapporto costo-beneficio screening

## Risposte Domande di Analisi

### Grafico 1 - Vaccinazioni

1. **Perché copertura cala con età?**
   - Generazioni più vecchie: campagne meno sistematiche
   - Richiami dimenticati
   - Scetticismo crescente (no-vax più diffuso adulti)
   - HPV: introdotto recentemente (2007), solo giovani coperti

2. **Sotto soglia 95%?**
   - Morbillo: da 6-12 anni in poi
   - Polio: da 13-17 anni in poi
   - HPV: tutte le fasce (max 65%)
   - **Rischio**: Epidemie possibili se sotto 95%

3. **Conseguenze calo collettivo?**
   - Perdita immunità di gregge
   - Rischio epidemie (vedi focolai morbillo 2017-2019)
   - Persone fragili (immunodepressi) non protette
   - Costi sanitari malattie evitabili

4. **HPV bassa copertura - cause?**
   - Vaccino relativamente nuovo
   - Controversie mediatiche infondate
   - Imbarazzo tema (HPV = sessualmente trasmesso)
   - Mancata sensibilizzazione genitori
   - **Problema**: HPV previene tumori (cervice, orofaringe)

### Grafico 2 - Spesa e Longevità

1. **Correlazione presente?**
   - Sì, R² = 0,68 (moderata-forte)
   - Tendenza: più spesa → più longevità
   - Ma non lineare perfetta (efficienza varia)

2. **Miglior rapporto qualità-prezzo?**
   - **Toscana**: 83,9 anni con €2.420
   - Lombardia: 83,5 anni con €2.580 (spende +7% per -0,4 anni)
   - **Toscana modello**: Efficienza + prevenzione territoriale

3. **Lazio anomalia?**
   - Spende di più (€2.680) ma aspettativa 82,8 anni
   - Possibili cause:
     - Roma concentra spesa ospedali ricerca (non solo cure)
     - Immigrazione (popolazione più giovane, diversa)
     - Inefficienze strutturali
     - Stili vita urbani (stress, inquinamento)

4. **Cosa suggerisce sull'efficienza?**
   - Più soldi ≠ automaticamente più salute
   - **Conta**: Organizzazione, prevenzione, territorio
   - Divari Nord-Sud persistono (Campania/Sicilia)
   - Investire in **prevenzione** più efficace che curare

### Grafico 3 - Screening

1. **Screening più efficace?**
   - **Melanoma**: 60% mortalità evitata
   - Seguito da Pap test (45%) e Colonscopia (40%)
   - Melanoma: se preso in fase iniziale, curabile al 98%

2. **Correlazione diagnosi-mortalità?**
   - **No correlazione diretta**
   - Mammografia: 8.500 diagnosi, 35% riduzione
   - Melanoma: 2.400 diagnosi, 60% riduzione
   - **Conta**: Precocità stadio, tipo tumore, terapie

3. **Valore economico prevenzione?**
   - **Costi screening**: €50-200 per test
   - **Costi terapia avanzata**: €50.000-500.000
   - **Rapporto**: 1:250 a favore screening
   - **Sociale**: Anni vita salvati, qualità vita, produttività

4. **Melanoma così efficace perché?**
   - Esame visivo (dermatologo) economico
   - Stadio iniziale: asportazione chirurgica semplice
   - Stadio avanzato: metastasi, prognosi infausta
   - **Finestra terapeutica** molto chiara
   - Sensibilizzazione pubblica (nei, sole) cresciuta

## Riflessioni Finali

**Messaggi chiave**:
1. 🩹 **Prevenzione salva vite**: Screening riduce mortalità 25-60%
2. 💉 **Vaccinazioni proteggono tutti**: Immunità gregge = solidarietà
3. 💰 **Efficienza > Budget**: Toscana modello virtuoso
4. ⚠️ **Allarme giovani**: Copertura sotto soglia = rischio epidemie
5. 📊 **Dati guidano scelte**: Evidenze scientifiche vs opinioni

**Azioni concrete**:
- Vaccinarsi e fare richiami
- Aderire a screening offerti (gratuiti SSN)
- Informarsi da fonti affidabili (ISS, Ministero Salute)
- Promuovere salute pubblica come bene comune

</details>

---

## 🚀 Varianti e Approfondimenti

### Variante A: Confronto Internazionale
Aggiungi dati altri Paesi europei per Grafico 2:
```
Germania	83,2	3850
Francia	83,7	3250
UK	82,5	2990
```
Osserva: più spesa non sempre = più salute (stili vita, alimentazione contano).

### Variante B: Costi Vaccini vs Costi Malattie
Crea grafico:
```
Malattia	Costo_Vaccino	Costo_Cura	Risparmio
Morbillo	€50	€5.000	€4.950
Polio	€60	€250.000	€249.940
HPV	€180	€80.000	€79.820
```
Evidenzia ROI economico vaccinazioni.

### Variante C: Dashboard Integrata
Combina i 3 grafici in dashboard con:
- KPI: Copertura media (89%), Aspettativa Italia (82,5 anni), Screening attivi (5)
- Layout 2x2: 3 grafici + 1 card riepilogo

---

## 🔗 Risorse Approfondimento

- **ISS** (Istituto Superiore Sanità): www.iss.it
- **Ministero Salute**: www.salute.gov.it
- **AIFA** (Farmaci): www.aifa.gov.it
- **OMS** dati internazionali: www.who.int

---

**Esercizio Precedente**: Esercizio 12 - Portfolio Prodotti  
**Prossimo Esercizio**: [Esercizio 14 - Alimentazione](esercizio_14_alimentazione.md)
