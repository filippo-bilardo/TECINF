# Esercizio 15: Ambiente e Sostenibilità

**Livello**: 🟡 Intermedio  
**Tipo grafico**: Multiplo (Colonne+Linea + Torta+Barre + Area in pila)  
**Tempo stimato**: 40 minuti  
**Tema**: Ambiente, riciclo, emissioni, energie rinnovabili  
**Competenze**: Grafici combinati, analisi trend, sensibilizzazione ambientale

---

## 🎯 Obiettivo

Analizzare tre dimensioni della sostenibilità ambientale: efficacia della raccolta differenziata, emissioni CO2 per settore, e transizione verso energie rinnovabili, per comprendere progressi e sfide nella lotta al cambiamento climatico.

## 📖 Scenario

Lavori per l'Agenzia Regionale per l'Ambiente e devi preparare un report per amministratori locali e cittadini. Il tuo compito è mostrare dove stiamo facendo progressi e dove serve maggiore impegno per raggiungere gli obiettivi di sostenibilità 2030.

## 📊 Dati Forniti

### Dataset 1: Raccolta Differenziata per Materiale

Copia in celle A1:D7:

```
Materiale	Quantità_Ton	Tasso_Riciclo%	Risparmio_CO2_Ton
Carta	450000	82	675000
Plastica	280000	45	420000
Vetro	320000	76	480000
Alluminio	85000	68	127500
Organico	620000	55	930000
Altro	145000	32	72500
```

**Note**: 
- Quantità in tonnellate/anno
- Risparmio CO2 vs produzione da materie prime vergini

### Dataset 2: Emissioni CO2 per Settore (Mt/anno)

Copia in celle F1:J7:

```
Anno	Trasporti	Industria	Residenziale	Energia	Agricoltura
2015	112,5	98,2	72,8	64,5	45,2
2018	108,3	95,5	70,2	61,8	44,5
2021	106,8	93,8	69,1	59,2	43,8
2023	105,9	93,1	68,8	58,7	43,2
2026	105,2	92,8	68,5	58,3	42,7
```

**Totale 2026**: 367,5 Mt CO2  
**Obiettivo 2030**: -40% vs 2015 (= 248 Mt)

### Dataset 3: Energie Rinnovabili - Evoluzione 2015-2030

Copia in celle L1:P6:

```
Anno	Solare_GW	Eolico_GW	Idroelettrico_GW	Biomasse_GW
2015	18,5	9,1	18,3	4,2
2020	21,6	10,9	18,5	4,8
2025	28,2	15,3	19,1	5,6
2030	42,5	25,8	19,8	7,2
2035	58,0	38,5	20,2	8,5
```

**Capacità totale 2030**: 95,3 GW (vs 50,1 GW nel 2015)

---

## ✅ Requisiti

### Grafico 1: Efficacia Riciclo per Materiale

1. **Tipo**: Grafico combinato (colonne + linea)
2. **Titolo**: "Raccolta Differenziata - Quantità e Efficienza Riciclo"
3. **Colonne**: Quantità_Ton (asse sinistro)
4. **Linea**: Tasso_Riciclo% (asse destro)
5. **Colori**:
   - Colonne: Verde (#34A853)
   - Linea: Arancione (#FBBC04), spessore 3px
   - Marcatori: Cerchi grandi
6. **Annotazione**: Linea obiettivo 70% riciclo
7. **Etichette**: Valori su entrambe le serie
8. **Ordina**: Per quantità decrescente

### Grafico 2: Emissioni per Settore - Composizione e Trend

1. **Tipo**: Grafico a torta + istogramma affiancato
2. **Torta** (dati 2026):
   - Titolo: "Emissioni CO2 2026 - 367,5 Mt per Settore"
   - Fette con percentuali ed etichette
   - Esplodi fetta "Trasporti" (maggior contributo)
   - Colori palette caldi (rossi/arancioni)
3. **Istogramma trend** (tutti gli anni):
   - Titolo: "Trend Emissioni 2015-2026 per Settore"
   - 5 serie sovrapposte
   - Legenda visibile

### Grafico 3: Transizione Energetica - Area in Pila

1. **Tipo**: Grafico ad area in pila
2. **Titolo**: "Crescita Energie Rinnovabili 2015-2035"
3. **Sottotitolo**: "Obiettivo: raddoppio capacità entro 2030"
4. **Aree**: 4 strati colorati
5. **Colori**:
   - Solare: Giallo (#FBBC04)
   - Eolico: Azzurro (#4285F4)
   - Idroelettrico: Blu scuro (#1976D2)
   - Biomasse: Verde (#34A853)
6. **Trasparenza**: 80% per vedere sovrapposizioni
7. **Etichette**: Totale su ogni anno
8. **Asse Y**: "Capacità (GW)"

---

## 🤔 Domande di Analisi Critica

### Grafico 1 - Riciclo:
1. Quale materiale ha il tasso di riciclo più alto e più basso? Perché?
2. L'organico ha 620k ton ma solo 55% riciclo: che opportunità perdiamo?
3. Calcola il risparmio CO2 totale della raccolta differenziata
4. Quali materiali dovrebbero essere priorità per migliorare il riciclo?

### Grafico 2 - Emissioni:
1. Quale settore contribuisce di più alle emissioni? Quanto in percentuale?
2. Dal 2015 al 2026, quale settore ha ridotto di più? E di meno?
3. Con trend attuale, raggiungeremo l'obiettivo 2030 (-40%)?
4. Cosa può fare ciascuno di noi per ridurre emissioni nei 3 settori principali?

### Grafico 3 - Rinnovabili:
1. Quale fonte rinnovabile cresce più velocemente? Calcola la crescita %
2. L'idroelettrico è quasi stabile: perché? È un problema?
3. Nel 2030 avremo raddoppiato la capacità del 2015?
4. Quale mix energetico è più sostenibile: perché diversificare?

---

## 💡 Riflessioni Educative

Questo esercizio ci porta a riflettere su:

- **Responsabilità individuale**: Ogni cittadino contribuisce con raccolta differenziata e scelte di mobilità
- **Economia circolare**: Riciclare significa meno materie prime, meno energia, meno CO2
- **Urgenza climatica**: Obiettivi 2030 ambiziosi ma necessari per limitare riscaldamento +1,5°C
- **Transizione energetica**: Rinnovabili sono la soluzione, ma serve accelerare investimenti
- **Equità intergenerazionale**: Oggi decidiamo il pianeta che lasciamo a figli e nipoti

---

<details>
<summary><strong>📝 Soluzione Completa</strong></summary>

## Grafico 1: Efficacia Riciclo

### Preparazione Dati

**Ordina per quantità decrescente**:
1. Seleziona A1:D7
2. Dati → Ordina intervallo
3. Colonna: Quantità_Ton, Decrescente

Risultato:
```
Organico	620000	55	930000
Carta	450000	82	675000
Vetro	320000	76	480000
Plastica	280000	45	420000
Altro	145000	32	72500
Alluminio	85000	68	127500
```

### Creazione Grafico

1. Seleziona A1:C7 (Materiale, Quantità, Tasso)
2. Inserisci → Grafico → Combinato
3. **Configurazione**:
   - Quantità_Ton: Colonne, asse sinistro
   - Tasso_Riciclo%: Linea, asse destro

**Personalizza Colonne**:
- Colore: Verde #34A853
- Etichette: Valori numerici con "k" (es: 620k)
- Spaziatura: 40%

**Personalizza Linea**:
- Colore: Arancione #FBBC04
- Spessore: 3px
- Marcatori: Cerchi 8px, bordo bianco
- Etichette: Percentuale (es: 82%)

**Linea Obiettivo 70%**:
Crea colonna helper con valore 70 per ogni riga.
Aggiungi come serie linea:
- Colore: Rosso #EA4335
- Stile: Tratteggiata
- Spessore: 2px
- Etichetta: "Obiettivo 70%"

**Assi**:
- Sinistro: "Quantità (tonnellate)", 0-700.000
- Destro: "Tasso Riciclo (%)", 0-100%

**Titolo**: `Raccolta Differenziata - Quantità e Efficienza Riciclo`
**Sottotitolo**: `Dati 2026 - Risparmio totale 2,7 milioni tonnellate CO2`

### Risultato Atteso

```
Tonnellate          Tasso %
700k│┌──┐                       │100%
    ││Or│
600k││ga│                       │90%
    ││ni│           ─ ─ ─ ─ ─  │80% (obiettivo)
500k││co│     ○────             │70%
    │└──┘┌──┐ │┌──┐             │60%
400k│    │Ca││ ││Ve│             │50%
    │    │rt││ ││tr│○            │40%
300k│    │a │└┐││o │             │30%
    │    └───┘│└───┘ ○           │20%
200k│         └─┐┌──┐            │10%
    │           ││Pl│ ○           │
100k│           ││as│             │
    └───────────┴└──┴────────────┘
     Org Car Vet Pla Alt All
```

**Insight visivi**:
- Organico: Maggior quantità ma sotto obiettivo (55%)
- Carta: Eccellenza (82%, sopra obiettivo)
- Plastica e Altro: Criticità (45% e 32%)
- Opportunità: Migliorare organico e plastica = massimo impatto

## Grafico 2: Emissioni CO2

### Parte A: Torta Composizione 2026

1. Estrai riga 2026 (F6:J6) in nuovo range
2. Calcola totali e percentuali:

```
Settore	Mt_CO2	Percentuale
Trasporti	105,2	28,6%
Industria	92,8	25,3%
Residenziale	68,5	18,6%
Energia	58,3	15,9%
Agricoltura	42,7	11,6%
Totale	367,5	100%
```

**Crea Torta**:
- Seleziona Settore + Mt_CO2
- Inserisci → Torta
- **Titolo**: `Emissioni CO2 2026 - 367,5 Mt per Settore`
- **Sottotitolo**: `Obiettivo 2030: riduzione a 248 Mt (-32% attuale)`

**Personalizza**:
- Esplodi "Trasporti": 0,15 (evidenzia principale)
- Etichette: `Settore: % (Mt CO2)`
- Esempio: `Trasporti: 28,6% (105,2 Mt)`

**Colori palette caldi**:
- Trasporti: Rosso scuro #B71C1C
- Industria: Rosso #EA4335
- Residenziale: Arancione #FF6D01
- Energia: Arancione chiaro #FBBC04
- Agricoltura: Giallo #F4B400

### Risultato Torta

```
              Agricoltura
               11,6%
                 ╱
    Energia ╱╱╱╱  ─────╲
     15,9%               ╲
         ╱   ╱─────────╲  ╲
        │   │ Trasporti │ │ ← Esplosa
        │   │   28,6%   │ │
        │   │ (105,2Mt) │ │
         ╲  ╲─────────╱  ╱
          ╲              ╱  Industria
           ╲───────────╱     25,3%
          Residenziale
            18,6%
```

### Parte B: Trend Emissioni

1. Seleziona F1:J6 (tutti gli anni)
2. Inserisci → Linee multiple
3. **5 serie** (una per settore)

**Personalizza serie** (stessi colori torta):
- Tutte: Spessore 3px, marcatori cerchi

**Annotazioni**:
- Linea orizzontale a 248 Mt: "Obiettivo 2030"
- Colore verde tratteggiato

**Titolo**: `Trend Emissioni CO2 2015-2026 per Settore`

### Risultato Trend

```
Mt CO2
120│○──────
   │  ○────── Trasporti (calo lento)
110│    ○────
   │      ○──○
100│○────────
   │  ○────── Industria
 90│    ○──○─○
   │
 80│
   │
 70│○────
   │  ○──── Residenziale
 60│    ○──○─○
   │○────────
 50│  ○────── Energia
   │    ○──○─○
 40│○──○──○──○─○ Agricoltura (quasi stabile)
   └────────────────────→
    2015 2018 2021 2023 2026
```

**Analisi visiva**:
- Tutti i settori in calo, ma **troppo lento**
- Trasporti: -6,5% in 11 anni (serve -20% entro 2030!)
- Agricoltura: Quasi piatta (-5,5%)
- Totale 2026 = 367,5 Mt vs obiettivo 248 Mt
- **Gap**: 119,5 Mt da tagliare in 4 anni! (Irrealistico con trend attuale)

## Grafico 3: Energie Rinnovabili

### Creazione Area in Pila

1. Seleziona L1:P6
2. Inserisci → Grafico → Area in pila
3. **4 serie** impilate

**Personalizza aree**:

**Solare** (base):
- Colore: Giallo #FBBC04
- Trasparenza: 80%

**Eolico**:
- Colore: Azzurro #4285F4
- Trasparenza: 80%

**Idroelettrico**:
- Colore: Blu scuro #1976D2
- Trasparenza: 80%

**Biomasse** (top):
- Colore: Verde #34A853
- Trasparenza: 80%

**Bordi**: Spessore 1px, colore più scuro

**Etichette**: Totale capacità su ogni anno

**Titolo**: `Crescita Energie Rinnovabili 2015-2035`
**Sottotitolo**: `Obiettivo 2030: raddoppio capacità (50 → 95 GW)`

**Asse Y**: "Capacità Installata (GigaWatt)", 0-140 GW

### Risultato Atteso

```
GW
140│                             ┌────── Biomasse
   │                         ┌───┴─────
120│                     ┌───┴─────
   │                 ┌───┴───────── Idroelettrico
100│             ┌───┴─────
   │         ┌───┴───────────────── Eolico
 80│     ┌───┴─────
   │ ┌───┴─────
 60│┌┴───────────────────────────── Solare
   ││
 40││
   ││
 20││
   ││
   └┴────────────────────────────→
    2015  2020  2025  2030  2035
    50GW        95GW  125GW
```

**Insight visivi**:
- **Solare**: Crescita esplosiva (18,5 → 58 GW, +214%!)
- **Eolico**: Forte crescita (9,1 → 38,5 GW, +323%!)
- **Idroelettrico**: Quasi saturo (+10%, risorse limitate)
- **Biomasse**: Crescita moderata (raddoppio)
- **Totale 2030**: 95,3 GW = +90% vs 2015 ✅ Obiettivo centrato!

## Risposte Domande di Analisi

### Grafico 1 - Riciclo

1. **Tasso più alto e più basso?**
   - **Più alto**: Carta 82%
     - Filiera consolidata da decenni
     - Separazione semplice (cestini blu)
     - Alto valore economico carta riciclata
     - Sensibilizzazione diffusa
   - **Più basso**: Altro 32%
     - Categoria eterogenea (tessuti, elettronica, ingombranti)
     - Difficile trattamento
     - Manca infrastruttura specifica

2. **Organico 620k ton ma 55% - opportunità?**
   - **Quantità persa**: 279.000 tonnellate/anno (45%)
   - **Potenziale**:
     - Compost di qualità per agricoltura
     - Biogas per energia (biometano)
     - Risparmio CO2 extra: 418.500 ton
   - **Perché solo 55%?**
     - Mancano impianti compostaggio/biogas in molte zone
     - Cittadini confondono (es: carne, olio nell'organico)
     - Sacchetti non conformi
   - **Soluzione**: Investire impianti + educazione capillare

3. **Risparmio CO2 totale?**
   - Somma colonna Risparmio_CO2_Ton:
   - Carta: 675.000
   - Plastica: 420.000
   - Vetro: 480.000
   - Alluminio: 127.500
   - Organico: 930.000
   - Altro: 72.500
   - **Totale: 2.705.000 tonnellate CO2/anno**
   - Equivalente: Togliere dalla strada 1,3 milioni auto!

4. **Priorità miglioramento?**
   - **1. Organico** (55% → 75%): +186k ton CO2 risparmiate
   - **2. Plastica** (45% → 70%): +210k ton CO2
   - **3. Altro** (32% → 50%): +40k ton CO2
   - **Perché**: Impatto massimo con investimenti mirati

### Grafico 2 - Emissioni

1. **Settore maggiore e percentuale?**
   - **Trasporti: 105,2 Mt = 28,6%** del totale
   - Cause:
     - Dipendenza auto privata (60% spostamenti)
     - Trasporto merci su gomma (vs treno)
     - Scarsa rete trasporto pubblico fuori città
     - Auto vecchie inquinanti (età media 12 anni)

2. **Maggior e minor riduzione 2015-2026?**
   - **Maggior riduzione**: Energia -9,6% (64,5 → 58,3 Mt)
     - Crescita rinnovabili
     - Chiusura centrali a carbone
     - Efficienza energetica
   - **Minor riduzione**: Agricoltura -5,5% (45,2 → 42,7 Mt)
     - Allevamenti intensivi (metano)
     - Fertilizzanti chimici (N2O)
     - Difficile decarbonizzare agricoltura

3. **Raggiungeremo obiettivo 2030?**
   - **NO**, con trend attuale è **impossibile**
   - Calcoli:
     - 2015: 393,2 Mt totale
     - Obiettivo 2030: -40% = 235,9 Mt
     - 2026 attuale: 367,5 Mt
     - Riduzione 2015-2026: -6,5%/11 anni = -0,6%/anno
     - Serve: -8,7%/anno nei prossimi 4 anni!
   - **Necessario**: Interventi drastici (elettrificazione trasporti, ristrutturazioni edifici, industria verde)

4. **Cosa fare individualmente?**
   - **Trasporti** (28,6%):
     - Bici/piedi per distanze <5 km
     - Mezzi pubblici quando possibile
     - Car sharing/pooling
     - Auto elettrica/ibrida al prossimo cambio
   - **Residenziale** (18,6%):
     - Isolamento termico casa
     - Termostato a 19°C inverno, 26°C estate
     - Elettrodomestici efficienti (A+++)
     - Pannelli solari se possibile
   - **Industria** (25,3%):
     - Scegliere prodotti locali (meno trasporti)
     - Economia circolare (riparare, riusare)
     - Supportare aziende green

### Grafico 3 - Rinnovabili

1. **Crescita più veloce e percentuale?**
   - **Eolico**: 9,1 → 38,5 GW (2015-2035)
     - Crescita: **+323%**
     - +29,4 GW in 20 anni = +1,47 GW/anno
   - **Perché così veloce?**
     - Tecnologia matura e competitiva
     - Costi turbine crollati (-70% dal 2010)
     - Italia ha venti favorevoli (coste, Appennini)
     - Offshore in espansione (mare)

2. **Idroelettrico stabile - problema?**
   - 2015: 18,3 GW → 2035: 20,2 GW (+10%)
   - **Perché stabile?**
     - Fiumi/laghi sfruttati quasi al massimo
     - Nuovi impianti: micro-hydro, ammodernamenti
     - Vincoli ambientali (ecosistemi fluviali)
   - **È problema?**
     - **No**: Idro è "batteria naturale" (pompaggio)
     - Regola produzione intermittente (solare/eolico)
     - Ruolo complementare essenziale
   - **Pro**: Stabile, affidabile, flessibile

3. **Raddoppio 2030 vs 2015?**
   - 2015: 50,1 GW (18,5+9,1+18,3+4,2)
   - 2030: 95,3 GW (42,5+25,8+19,8+7,2)
   - Crescita: **+90%** → Quasi raddoppio! ✅
   - **Obiettivo centrato** (grazie a solare ed eolico)
   - Ma serve anche: Reti intelligenti, accumuli, demand response

4. **Perché diversificare mix?**
   - **Complementarità temporale**:
     - Solare: Giorno, estate
     - Eolico: Anche notte, inverno
     - Idro: Regolazione rapida
     - Biomasse: Programmabile
   - **Sicurezza energetica**: Non dipendere da una fonte
   - **Resilienza**: Meteo varia, diversificare copre rischi
   - **Territoriale**: Sfruttare risorse locali (sole Sud, vento coste, idro Alpi)

## Riflessioni Finali

**Messaggi chiave**:
1. ♻️ **Riciclo funziona**: 2,7 Mt CO2 risparmiate, ma margini miglioramento enormi
2. 🚗 **Trasporti emergenza**: 28,6% emissioni, serve rivoluzione mobilità
3. ⚡ **Rinnovabili vincono**: Raddoppio capacità, costi competitivi
4. ⏰ **Tempo scadenza**: Obiettivi 2030 a rischio senza accelerazione
5. 🌍 **Responsabilità condivisa**: Cittadini + imprese + politica

**Azioni concrete individuali**:
- ♻️ Ricicla correttamente (separa, pulisci, informati)
- 🚲 Privilegia mobilità sostenibile (bici, piedi, mezzi)
- 💡 Riduci consumi energetici casa (led, isolamento)
- 🥗 Dieta plant-based riduce impronta (meno carne)
- 🛒 Consuma locale e stagionale (meno trasporti)
- 🗳️ Vota politiche ambientali ambiziose

**Azioni concrete collettive**:
- 🏗️ Investire massicciamente in rinnovabili
- 🚊 Potenziare trasporto pubblico e ferrovie
- 🏠 Incentivi ristrutturazione energetica edifici
- 🏭 Tassare emissioni (carbon tax), premiare green
- 📚 Educazione ambientale obbligatoria scuole

</details>

---

## 🚀 Varianti e Approfondimenti

### Variante A: Footprint Personale
Calcola la tua impronta CO2 annuale:
```
Categoria	Azione	CO2_Annua_Kg
Trasporti	10.000 km auto	2.400
Energia	Elettricità casa	1.200
Cibo	Dieta media italiana	2.800
Consumi	Acquisti vari	1.600
Totale	Media italiana	8.000
```
Grafico a barre: Identifica dove tagliare.

### Variante B: Costo Rinnovabili vs Fossili
```
Fonte	Costo_kWh_2015	Costo_kWh_2025	Riduzione%
Solare	€0,25	€0,04	-84%
Eolico	€0,18	€0,05	-72%
Carbone	€0,08	€0,09	+13%
Gas	€0,06	€0,12	+100%
```
Linee incrociate: Rinnovabili ora più convenienti!

### Variante C: Dashboard Città Sostenibile
KPI città ideale 2030:
- 🚲 Mobilità dolce: 60% spostamenti
- ♻️ Rifiuti: 80% differenziata
- 🏠 Edifici: 90% classe A+
- 🌳 Verde: 40 m²/abitante
- ⚡ Energia: 100% rinnovabile

Crea dashboard confronto città reali vs target.

### Variante D: Scenari Climatici
```
Scenario	Emissioni_2030	Riscaldamento_2100
Business-as-usual	420 Mt	+3,5°C
Politiche attuali	330 Mt	+2,7°C
Obiettivo Parigi	250 Mt	+1,8°C
Net-Zero 2050	180 Mt	+1,5°C
```
Grafico a linee con zone rosse/verdi: Urgenza visiva.

---

## 🔗 Risorse Approfondimento

- **ISPRA** (Ambiente Italia): www.isprambiente.gov.it
- **GSE** (Energia Rinnovabili): www.gse.it
- **Ministero Transizione Ecologica**: www.mite.gov.it
- **IPCC** (ONU Clima): www.ipcc.ch
- **Legambiente**: www.legambiente.it
- **Calcolatori impronta CO2**: 
  - www.footprintcalculator.org
  - www.improntawwf.it

---

**Esercizio Precedente**: [Esercizio 14 - Alimentazione](esercizio_14_alimentazione.md)  
**Prossimo Esercizio**: [Esercizio 16 - Educazione Civica](esercizio_16_educazione_civica.md)
