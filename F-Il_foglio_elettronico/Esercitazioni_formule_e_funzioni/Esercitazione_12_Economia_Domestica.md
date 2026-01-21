# Esercitazione 12: Economia Domestica - Gestione Familiare Completa

**Livello:** 📚 INTERMEDIO  
**Tempo stimato:** 120 minuti  
**Disciplina:** Economia Domestica + Matematica Applicata

---

## Obiettivi

- Applicare i fogli di calcolo alla gestione economica familiare
- Calcolare costi di gestione casa (bollette, spesa, manutenzione)
- Analizzare consumi e sprechi
- Pianificare budget familiare mensile/annuale
- Confrontare costi e ottimizzare spese

---

## Scenario

Una famiglia di 4 persone (2 adulti, 2 figli) vuole ottimizzare la gestione economica domestica. Devi creare un sistema completo che permetta di monitorare spese, consumi e pianificare il budget familiare.

---

## 📊 STRUTTURA DEL PROGETTO - 6 FOGLI

1. **Budget Familiare** - Entrate, uscite fisse e variabili
2. **Spesa Alimentare** - Gestione spesa settimanale
3. **Bollette e Utenze** - Monitoraggio consumi energetici
4. **Manutenzione Casa** - Spese straordinarie e ordinarie
5. **Analisi Costi** - Confronti e ottimizzazioni
6. **Dashboard** - Vista d'insieme e KPI

---

## FOGLIO 1: BUDGET FAMILIARE MENSILE

### SEZIONE A - ENTRATE

```
A                          B          C
=== ENTRATE MENSILI ===
Stipendio Genitore 1      2.200 €
Stipendio Genitore 2      1.800 €
Assegni familiari         200 €
Affitti percepiti         0 €
Altre entrate             150 €

TOTALE ENTRATE           [=SOMMA(B3:B7)]
```

### SEZIONE B - USCITE FISSE

```
A                          B          C
=== USCITE FISSE ===
Affitto/Mutuo             800 €
Condominio                100 €
Assicurazioni             150 €
Trasporti (abbonamenti)   120 €
Scuola/Università         200 €
Rate prestiti             250 €
Palestra/Sport            80 €
Telefonia/Internet        50 €

TOTALE FISSO             [=SOMMA(B12:B19)]
```

### SEZIONE C - USCITE VARIABILI (STIMATE)

```
A                          B              C
=== USCITE VARIABILI ===
Spesa alimentare          600 €          [da Foglio Spesa]
Bollette (luce)           80 €           [da Foglio Bollette]
Bollette (gas)            100 €          [da Foglio Bollette]
Bollette (acqua)          40 €           [da Foglio Bollette]
Carburante                200 €
Vestiario                 150 €
Salute/Farmaci            80 €
Svago/Tempo libero        150 €
Regali/Occasioni          50 €
Manutenzione casa         100 €          [da Foglio Manutenzione]
Altro                     50 €

TOTALE VARIABILE         [=SOMMA(B24:B34)]
```

### SEZIONE D - RIEPILOGO

```
A                          B
=== RIEPILOGO MENSILE ===
Totale Entrate            [=B8]
Totale Uscite Fisse       [=B20]
Totale Uscite Variabili   [=B35]
Totale Uscite             [=B38+B39]

SALDO MENSILE             [=B37-B40]
% Risparmio               [=(B41/B37)*100]

=== VALUTAZIONE ===
Stato                     [=SE(B41>0;"✅ POSITIVO";"❌ NEGATIVO")]
Capacità risparmio        [=SE(B42>10%;"🟢 OTTIMA";SE(B42>5%;"🟡 BUONA";"🔴 SCARSA"))]
```

---

## FOGLIO 2: SPESA ALIMENTARE

### SEZIONE A - SPESA SETTIMANALE

```
A            B          C        D         E          F
Settimana    Data       Negozio  Importo   Persone    €/Persona
1            06/01/26   Coop     142,50    4          35,63
2            13/01/26   Coop     138,20    4          34,55
3            20/01/26   Lidl     128,90    4          32,23
4            27/01/26   Coop     145,80    4          36,45
```

**Formule:**

**€/Persona (F2):**
```
=D2/E2
```

**Totale mese:**
```
Totale spesa mese: =SOMMA(D2:D5)
Media settimanale: =MEDIA(D2:D5)
Media per persona: =MEDIA(F2:F5)
```

### SEZIONE B - CATEGORIE SPESA

```
A                    B
=== SPESA TIPO SETTIMANALE ===
Frutta e verdura     35,00 €
Carne e pesce        40,00 €
Pane e cereali       20,00 €
Latte e derivati     18,00 €
Bevande              12,00 €
Prodotti pulizia     10,00 €
Altro                7,50 €

TOTALE               [=SOMMA(B2:B8)]
```

### SEZIONE C - ANALISI CONSUMI

```
=== ANALISI PRO CAPITE ===

Spesa giornaliera per persona    [=TotaleSettimanale/7/4]
Spesa mensile per persona        [=TotaleMensile/4]

Colazione (stimata)              2,50 €
Pranzo (stimata)                 5,00 €
Cena (stimata)                   4,50 €
Spuntini                         1,00 €

TOTALE GIORNALIERO               13,00 €
TOTALE MENSILE/PERSONA           390,00 €
```

### SEZIONE D - CONFRONTO NEGOZI

```
Negozio    Spesa Media    N° Spese    Totale    Convenienza
Coop       142,17 €       3           426,50    Base
Lidl       128,90 €       1           128,90    -9,3%
Esselunga  [dati]         [dati]      [dati]    [calc]
```

**Convenienza formula:**
```
=((D2-$D$2)/$D$2)*100
```

### SEZIONE E - RIDUZIONE SPRECHI

```
=== PIANO ANTI-SPRECO ===

Stima sprechi attuali (%)        15%
Valore sprechi mensili           [=TotaleMensile*15%]
Obiettivo riduzione              5%
Risparmio potenziale mensile     [=TotaleMensile*10%]
Risparmio potenziale annuo       [=RisparmioMese*12]

AZIONI:
- Lista spesa precisa
- Verifica scadenze settimanale
- Riutilizzo avanzi
- Congelamento eccedenze
```

---

## FOGLIO 3: BOLLETTE E UTENZE

### SEZIONE A - ELETTRICITÀ

```
A        B          C          D          E         F         G
Mese     Lettura    Consumo    €/kWh      Importo   Persone   €/Pers
Gen      2580       280 kWh    0,28       78,40     4         19,60
Feb      2840       260 kWh    0,28       72,80     4         18,20
Mar      3090       250 kWh    0,28       70,00     4         17,50
Apr      3320       230 kWh    0,28       64,40     4         16,10
```

**Formule:**

**Consumo (C2):**
```
=B2-B1  (lettura attuale - lettura precedente)
```

**Importo (E2):**
```
=C2*D2
```

**€/Persona (G2):**
```
=E2/F2
```

**Statistiche:**
```
Consumo medio mensile:    265 kWh
Costo medio mensile:      71,40 €
Consumo per persona:      66,25 kWh
Costo per persona:        17,85 €
```

### SEZIONE B - GAS

```
Mese     Lettura    Consumo    €/m³       Importo   m³/Persona
Gen      1250       120 m³     0,85       102,00    30,00
Feb      1360       110 m³     0,85       93,50     27,50
Mar      1460       100 m³     0,85       85,00     25,00
Apr      1550       90 m³      0,85       76,50     22,50
```

**Analisi stagionale:**
```
=== CONSUMI STAGIONALI GAS ===

Inverno (Gen-Mar)        110 m³/mese
Primavera (Apr-Giu)      70 m³/mese
Estate (Lug-Set)         40 m³/mese
Autunno (Ott-Dic)        90 m³/mese

Media annuale            77,5 m³/mese
Costo annuale stimato    790,00 €
```

### SEZIONE C - ACQUA

```
Mese     Lettura    Consumo    €/m³       Importo
Gen      245        15 m³      2,50       37,50
Feb      260        15 m³      2,50       37,50
Mar      275        15 m³      2,50       37,50
Apr      290        15 m³      2,50       37,50
```

**Analisi consumo:**
```
=== ANALISI ACQUA ===

Consumo medio giornaliero        500 litri (15m³/30giorni)
Consumo per persona/giorno       125 litri
Costo giornaliero                1,25 €
Costo per persona/giorno         0,31 €

BENCHMARK:
Media nazionale:                 220 litri/persona
Situazione:                      [=SE(125<220;"✅ SOTTO MEDIA";"⚠️ SOPRA MEDIA")]
```

### SEZIONE D - RIEPILOGO BOLLETTE

```
=== TOTALE BOLLETTE MENSILI ===

Elettricità              71,40 €
Gas                      89,25 €
Acqua                    37,50 €

TOTALE                   198,15 €
% su budget              [=198,15/EntrateMensili*100]

=== OBIETTIVI RISPARMIO ===

Target riduzione         10%
Risparmio obiettivo      19,82 €/mese
Risparmio annuo          237,84 €
```

---

## FOGLIO 4: MANUTENZIONE CASA

### SEZIONE A - MANUTENZIONE ORDINARIA

```
A                      B          C              D
Voce                   Freq.      Costo/volta    Costo/anno
Pulizie profonde       Mensile    50 €           600 €
Caldaia controllo      Annuale    80 €           80 €
Climatizzatore pulizia Annuale    60 €           60 €
Elettrodomestici       Annuale    40 €           40 €
Imbiancatura           Ogni 3y    800 €          267 €
Infissi manutenzione   Annuale    100 €          100 €

TOTALE ANNUO                                     [=SOMMA(D2:D7)]
MEDIA MENSILE                                    [=D8/12]
```

### SEZIONE B - MANUTENZIONE STRAORDINARIA

```
Data       Intervento           Fornitore    Importo    Categoria
15/01/26   Riparaz. lavatrice   TecnoCasa    120 €      Elettrodom.
22/01/26   Idraulico perdita    IdroService  180 €      Idraulica
[futuro]   [preventivato]       [fornitore]  [stima]    [categoria]

TOTALE STRAORDINARIE ANNO                     [=SOMMA(D2:D10)]
```

### SEZIONE C - FONDO EMERGENZE

```
=== FONDO MANUTENZIONI ===

Versamento mensile consigliato   100 €
Saldo fondo attuale              850 €
Spese anno corrente              300 €
Disponibilità residua            550 €

Target fondo emergenze           2.000 €
Mancano                          1.150 €
Mesi per raggiungere obiettivo   12 mesi
```

### SEZIONE D - ELETTRODOMESTICI

```
Elettrodom.    Anno acq.  Età   Vita media  Sostituz.  Costo stim.
Frigorifero    2018       8y    12y         2030       600 €
Lavatrice      2020       6y    10y         2030       450 €
Lavastoviglie  2019       7y    10y         2029       500 €
Forno          2016       10y   15y         2031       400 €
TV             2021       5y    8y          2029       600 €

=== PIANIFICAZIONE SOSTITUZIONI ===

2029: Lavastoviglie + TV                     1.100 €
2030: Frigorifero + Lavatrice                1.050 €
2031: Forno                                  400 €

TOTALE PROSSIMI 5 ANNI                       2.550 €
Accantonamento mensile consigliato           43 €/mese
```

---

## FOGLIO 5: ANALISI COSTI E OTTIMIZZAZIONI

### SEZIONE A - DISTRIBUZIONE SPESE

```
=== DISTRIBUZIONE PERCENTUALE ===

Categoria              Importo     % su totale
Abitazione (affitto)   800 €       [calc]
Spesa alimentare       600 €       [calc]
Bollette utenze        200 €       [calc]
Trasporti              320 €       [calc]
Scuola/Formazione      200 €       [calc]
Assicurazioni          150 €       [calc]
Salute                 80 €        [calc]
Svago                  150 €       [calc]
Altro                  300 €       [calc]

TOTALE                 2.800 €     100%
```

**Formula % (C2):**
```
=(B2/$B$11)*100
```

### SEZIONE B - CONFRONTO CON PARAMETRI IDEALI

```
Categoria              Reale    Ideale    Diff      Azione
Abitazione            28,6%    30%       -1,4%     ✅ OK
Alimentazione         21,4%    15-20%    +1,4%     ⚠️ Ridurre
Bollette              7,1%     5-8%      0%        ✅ OK
Trasporti             11,4%    10-15%    0%        ✅ OK
Risparmio             14,3%    >10%      +4,3%     ✅ OTTIMO
```

### SEZIONE C - PROPOSTE DI RISPARMIO

```
=== OPPORTUNITÀ DI RISPARMIO ===

Azione                          Risparmio/mese    Risparmio/anno
Cambio fornitore energia        10 €              120 €
Spesa con lista (no sprechi)    60 €              720 €
Preparare pranzi lavoro         80 €              960 €
Riduci uscite bar/caffè         40 €              480 €
Cambio operatore telefonico     15 €              180 €
Prodotti marca supermercato     30 €              360 €
Riciclo acqua lavatrice         5 €               60 €
LED e risparmio energetico      10 €              120 €

TOTALE RISPARMIO POTENZIALE     250 €             3.000 €/anno
```

### SEZIONE D - SIMULAZIONI SCENARI

```
=== SCENARIO 1: RISPARMIO AGGRESSIVO ===

Riduzione spesa alimentare      -15%    -90 €/mese
Riduzione svago                 -30%    -45 €/mese
Ottimizzazione bollette         -10%    -20 €/mese

Risparmio totale mensile                155 €/mese
Risparmio annuale                       1.860 €
Nuovo saldo mensile                     715 € (+155)

=== SCENARIO 2: AUMENTO ENTRATE ===

Lavoro extra (baby sitting)     +200 €/mese
Affitto camera studente         +300 €/mese

Nuovo saldo mensile                     1.060 €
Capacità risparmio annuale              12.720 €
```

---

## FOGLIO 6: DASHBOARD FAMILIARE

### KPI PRINCIPALI

```
=== SITUAZIONE MENSILE ===

💰 Saldo Mensile                 560 €
📊 % Risparmio                   14,3%
📈 Trend vs mese scorso          +2,5%

=== INDICATORI ===

✅ Budget sotto controllo        SÌ
⚠️ Categorie in eccesso          1 (Alimentari)
🎯 Obiettivo risparmio           Raggiunto
🔴 Alert spese                   Nessuno

=== OBIETTIVI ANNUALI ===

Risparmio target anno            6.000 €
Risparmio attuale (3 mesi)       1.680 €
% raggiungimento                 28%
Proiezione fine anno             6.720 €   ✅
```

### GRAFICI DA CREARE

1. **Grafico a torta**: Distribuzione spese per categoria
2. **Grafico a barre**: Spesa alimentare settimanale (4 settimane)
3. **Grafico a linee**: Trend bollette ultimi 6 mesi
4. **Grafico a colonne**: Entrate vs Uscite mensili

---

## COMPITI DA SVOLGERE

### Livello Base (40 punti)

1. ✅ Completa Foglio 1 con tutte le formule (10 pt)
2. ✅ Calcola spesa alimentare mensile e per persona (10 pt)
3. ✅ Inserisci consumi bollette e calcola totali (10 pt)
4. ✅ Crea grafico distribuzione spese (10 pt)

### Livello Intermedio (30 punti)

5. ✅ Analizza convenienza negozi con % (10 pt)
6. ✅ Calcola consumo energetico per persona (10 pt)
7. ✅ Pianifica sostituzioni elettrodomestici (10 pt)

### Livello Avanzato (30 punti)

8. ✅ Confronta reale vs ideale con formattazione (10 pt)
9. ✅ Crea simulazioni scenari risparmio (10 pt)
10. ✅ Dashboard completa con tutti i KPI (10 pt)

**BONUS (+10 pt):** Piano risparmio personalizzato per obiettivo specifico (es. vacanza, auto, ristrutturazione)

---

## FORMULE CHIAVE

### Collegamenti tra Fogli

```
// Nel Budget, leggi spesa da Foglio Spesa
=SpesaAlimentare!B50

// Nel Budget, leggi bollette da Foglio Bollette
=Bollette!D15

// Nella Dashboard, leggi saldo da Budget
=BudgetFamiliare!B41
```

### Formule Condizionali Utili

```
// Alert bolletta alta
=SE(BollettaLuce>100;"⚠️ CONSUMO ALTO";"✅ OK")

// Valutazione risparmio
=SE(Risparmio%>15%;"🟢 OTTIMO";SE(Risparmio%>10%;"🟡 BUONO";"🔴 INSUFFICIENTE"))

// Categoria spesa
=SE(SpesaMensile>Budget*1,1;"❌ FUORI BUDGET";SE(SpesaMensile>Budget*0,95;"⚠️ ATTENZIONE";"✅ OK"))
```

---

## CRITERI DI VALUTAZIONE

| Criterio | Punti | Descrizione |
|----------|-------|-------------|
| **Formule corrette** | 30 | Tutti i calcoli funzionanti |
| **Collegamenti fogli** | 20 | Dati collegati correttamente |
| **Analisi e confronti** | 20 | Valutazioni e proposte |
| **Grafici e dashboard** | 15 | Visualizzazioni chiare |
| **Presentazione** | 10 | Organizzazione e usabilità |
| **Funzionalità bonus** | 5 | Creatività e approfondimenti |

---

## ESTENSIONI POSSIBILI

### 1. Gestione Abbigliamento
- Inventario vestiti per persona
- Spesa annuale vestiario
- Pianificazione acquisti stagionali

### 2. Gestione Farmacia
- Inventario farmaci domestici
- Scadenze medicinali
- Spese sanitarie per persona

### 3. Gestione Auto
- Carburante (km, litri, €/km)
- Manutenzioni programmate
- Bollo, assicurazione, revisione

### 4. Pianificazione Vacanze
- Budget vacanze annuale
- Accantonamento mensile
- Preventivi e prenotazioni

### 5. Investimenti e Risparmi
- Conti deposito
- Investimenti mensili
- Proiezioni lungo termine

---

## 💡 CONSIGLI PRATICI

### Regole d'Oro Economia Domestica

1. **Regola 50/30/20:**
   - 50% necessità (casa, spesa, bollette)
   - 30% desideri (svago, hobby)
   - 20% risparmio/investimenti

2. **Fondo emergenze:**
   - Mantieni 3-6 mesi di spese come riserva
   - Accantonamento minimo 10% entrate

3. **Pianificazione:**
   - Rivedi budget ogni mese
   - Adatta in base a cambiamenti
   - Festeggia obiettivi raggiunti

4. **Consapevolezza:**
   - Annota ogni spesa per 1 mese
   - Identifica sprechi nascosti
   - Elimina spese inutili

---

## RIFLESSIONI FINALI

**Perché questa esercitazione è importante:**

- 🎯 **Competenza di vita**: Essenziale per autonomia economica
- 📊 **Consapevolezza finanziaria**: Capire dove vanno i soldi
- 💰 **Risparmio reale**: Identificare opportunità concrete
- 👨‍👩‍👧‍👦 **Gestione familiare**: Coinvolgere tutta la famiglia
- 📈 **Pianificazione futuro**: Obiettivi a medio-lungo termine

**Testimonianze:**

> "Dopo 3 mesi di tracciamento, abbiamo risparmiato 400€/mese solo eliminando sprechi che non vedevamo!" - Famiglia Rossi

> "Il foglio ci ha fatto capire che spendavamo troppo in uscite bar/ristorante. Ora cuciniamo più spesso e risparmiamo 200€/mese." - Famiglia Bianchi

---

*Tempo totale: 100-120 minuti*  
*Difficoltà: ⭐⭐⭐ (3/5)*  
*Utilità pratica: ⭐⭐⭐⭐⭐ (5/5)*  
*Competenza: Life skill fondamentale per tutti*
