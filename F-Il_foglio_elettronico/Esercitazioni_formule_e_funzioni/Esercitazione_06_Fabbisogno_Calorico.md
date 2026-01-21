# Esercitazione 6: Calcolo Fabbisogno Calorico e Analisi Menu

**Livello:** 📚 INTERMEDIO-AVANZATO  
**Tempo stimato:** 90-120 minuti

---

## Obiettivi

- Calcolare il fabbisogno calorico giornaliero in base a parametri personali
- Analizzare le calorie di un menu giornaliero
- Confrontare fabbisogno e consumo calorico
- Utilizzare formule condizionali per valutazioni nutrizionali
- Collegare dati tra fogli multipli

---

## Scenario

Creare un sistema per calcolare il fabbisogno calorico personale e confrontarlo con l'apporto calorico di un menu giornaliero, fornendo feedback nutrizionali basati su dati scientifici.

---

## 📖 CONCETTI TEORICI ESSENZIALI

### 1. BMI - Indice di Massa Corporea

**Formula:**
```
BMI = Peso (kg) / [Altezza (m)]²
```

**Classificazione WHO:**
- BMI < 18,5: Sottopeso
- BMI 18,5-25: Normopeso
- BMI 25-30: Sovrappeso
- BMI > 30: Obesità

### 2. Metabolismo Basale (MB)

Il MB è la quantità di energia che il corpo consuma a riposo per mantenere le funzioni vitali.

**Formula di Harris-Benedict (rivista 1984):**

**Uomini:**
```
MB = 88,362 + (13,397 × Peso kg) + (4,799 × Altezza cm) - (5,677 × Età anni)
```

**Donne:**
```
MB = 447,593 + (9,247 × Peso kg) + (3,098 × Altezza cm) - (4,330 × Età anni)
```

### 3. Livelli di Attività Fisica (PAL)

| Livello | Fattore | Descrizione |
|---------|---------|-------------|
| Sedentario | 1,2 | Lavoro d'ufficio, no esercizio |
| Leggero | 1,375 | Esercizio leggero 1-3 giorni/settimana |
| Moderato | 1,55 | Esercizio moderato 3-5 giorni/settimana |
| Intenso | 1,725 | Esercizio intenso 6-7 giorni/settimana |
| Molto Intenso | 1,9 | Atleti, lavoro fisico pesante |

**Fabbisogno Totale = MB × PAL**

---

## 📋 STRUTTURA DEL PROGETTO - 3 FOGLI

1. **Profilo** - Dati personali e calcolo fabbisogno
2. **Menu Giornaliero** - Registro pasti e calorie
3. **Analisi** - Confronto e valutazione

---

## FOGLIO 1: PROFILO

### Struttura

```
A                          B
--- DATI PERSONALI ---
Nome                       Mario Rossi
Sesso                      M
Età (anni)                 35
Peso (kg)                  75
Altezza (cm)               175
Livello Attività           Moderato

--- CALCOLI AUTOMATICI ---
BMI                        [formula]
Categoria BMI              [formula]
Metabolismo Basale (kcal)  [formula]
Fabbisogno Totale (kcal)   [formula]
```

### Compiti

**1. Calcolare il BMI (in B10):**
```
=B5/(B6/100)^2
```

**2. Determinare Categoria BMI (in B11):**
```
=SE(B10<18,5;"Sottopeso";SE(B10<25;"Normopeso";SE(B10<30;"Sovrappeso";"Obesità")))
```

**3. Calcolare Metabolismo Basale (in B12):**
```
=SE(B3="M";
  88,362+(13,397*B5)+(4,799*B6)-(5,677*B4);
  447,593+(9,247*B5)+(3,098*B6)-(4,330*B4)
)
```

**4. Fabbisogno Totale (in B13):**

Prima crea una tabella di lookup per i fattori PAL:

```
   H                I
1  Livello          Fattore
2  Sedentario       1,2
3  Leggero          1,375
4  Moderato         1,55
5  Intenso          1,725
6  Molto Intenso    1,9
```

Poi usa CERCA.VERT:
```
=B12*CERCA.VERT(B7;H2:I6;2;FALSO)
```

---

## FOGLIO 2: MENU GIORNALIERO

### Struttura

```
A          B              C          D         E         F
Pasto      Alimento       Quantità   Unità     Cal/100g  Calorie
```

### Dati di Esempio

**COLAZIONE:**
```
COLAZIONE  Latte          200        ml        64        128
COLAZIONE  Fette bisc.    40         g         410       164
COLAZIONE  Marmellata     20         g         250       50
COLAZIONE  Caffè          1          tazza     2         2
```

**SPUNTINO MATTINA:**
```
SPUNTINO   Mela           150        g         52        78
SPUNTINO   Noci           30         g         654       196
```

**PRANZO:**
```
PRANZO     Pasta          80         g         350       280
PRANZO     Sugo pomod.    100        g         24        24
PRANZO     Parmigiano     10         g         431       43
PRANZO     Insalata       100        g         15        15
PRANZO     Olio oliva     10         ml        884       88
PRANZO     Pane           50         g         265       133
```

**SPUNTINO POMERIGGIO:**
```
SPUNTINO   Yogurt         125        g         61        76
```

**CENA:**
```
CENA       Petto pollo    150        g         110       165
CENA       Patate         200        g         77        154
CENA       Zucchine       150        g         17        26
CENA       Olio oliva     10         ml        884       88
CENA       Pane           30         g         265       80
```

### Compiti

**1. Colonna F - Calcolare Calorie Effettive:**

Formula in F2:
```
=SE(D2="g";(E2*C2)/100;SE(D2="ml";(E2*C2)/100;E2))
```

Copia fino alla fine del menu.

**2. Totali per Pasto:**

Dopo ogni pasto, aggiungi una riga di totale:
- Dopo ultima riga COLAZIONE: `=SOMMA(F2:F5)` (es.)
- Dopo SPUNTINO 1: `=SOMMA(F7:F8)` (es.)
- Dopo PRANZO: `=SOMMA(F10:F15)` (es.)
- E così via...

**3. Totale Giornaliero:**

Alla fine del menu:
```
Totale Giornaliero: =SOMMA(F2:F26)  [adatta intervallo]
```

---

## FOGLIO 3: ANALISI E CONFRONTO

### Struttura

```
A                                  B
--- RIEPILOGO ---
Fabbisogno Calorico               [da Profilo]
Calorie Consumate                 [da Menu]
Differenza (consumo - fabbisogno) [formula]
Differenza %                      [formula]

--- VALUTAZIONE ---
Stato                             [formula]
Consiglio                         [formula]

--- DISTRIBUZIONE PASTI ---
Calorie Colazione                 [da Menu]
% Colazione                       [formula]
Calorie Pranzo                    [da Menu]
% Pranzo                          [formula]
Calorie Cena                      [da Menu]
% Cena                            [formula]
Calorie Spuntini                  [da Menu]
% Spuntini                        [formula]

--- VALORI IDEALI ---
Colazione: 20-25%
Pranzo: 35-40%
Cena: 25-30%
Spuntini: 10-15%
```

### Compiti

**1. Collegamenti tra Fogli:**

```
B2: =Profilo!B13                    (Fabbisogno)
B3: =Menu!B30                       (Totale giornaliero)
B4: =B3-B2                          (Differenza)
B5: =(B4/B2)*100                    (Differenza %)
```

**2. Valutazione Stato (B8):**
```
=SE(B5>10;"ECCESSO";SE(B5<-10;"DEFICIT";"ADEGUATO"))
```

**3. Consiglio Personalizzato (B9):**
```
=SE(B8="ECCESSO";"Ridurre apporto calorico o aumentare attività fisica";
  SE(B8="DEFICIT";"Aumentare apporto calorico per evitare carenze";
  "Alimentazione bilanciata, continua così!"))
```

**4. Distribuzione Pasti:**

```
B12: =Menu!F6                       (Totale COLAZIONE)
B13: =(B12/B3)*100                  (% Colazione)
B14: =Menu!F16                      (Totale PRANZO)
B15: =(B14/B3)*100                  (% Pranzo)
B16: =Menu!F27                      (Totale CENA)
B17: =(B16/B3)*100                  (% Cena)
```

---

## ESEMPIO COMPLETO DI RISULTATI

**Profilo:**
- Nome: Mario Rossi
- Sesso: M
- Età: 35 anni
- Peso: 75 kg
- Altezza: 175 cm
- Attività: Moderato

**Calcoli:**
- BMI: 24,5 (Normopeso)
- MB: 1.734 kcal
- Fabbisogno: 2.688 kcal

**Menu Giornaliero:**
- Colazione: 344 kcal
- Spuntino 1: 274 kcal
- Pranzo: 583 kcal
- Spuntino 2: 76 kcal
- Cena: 513 kcal
- **Totale: 1.790 kcal**

**Analisi:**
- Differenza: -898 kcal
- Differenza %: -33,4%
- Stato: **DEFICIT**
- Consiglio: "Aumentare apporto calorico per evitare carenze"

**Distribuzione:**
- Colazione: 19,2% (ideale 20-25%) ✅
- Pranzo: 32,6% (ideale 35-40%) ⚠️
- Cena: 28,7% (ideale 25-30%) ✅
- Spuntini: 19,5% (ideale 10-15%) ⚠️

---

## FUNZIONALITÀ AVANZATE (BONUS)

### 1. Grafico a Torta

Crea un grafico che mostri la distribuzione calorica tra i pasti.

### 2. Formattazione Condizionale

Applica colori:
- **Verde:** Valori nella norma
- **Giallo:** Lieve scostamento (+/-10%)
- **Rosso:** Scostamento significativo (+/-20%)

### 3. Macronutrienti

Aggiungi colonne per:
- Proteine (g)
- Carboidrati (g)
- Grassi (g)

Calcola distribuzione %:
- Proteine: 4 kcal/g
- Carboidrati: 4 kcal/g
- Grassi: 9 kcal/g

Valori ideali:
- Carboidrati: 50%
- Proteine: 20%
- Grassi: 30%

### 4. Tracker Settimanale

Crea un foglio per tracciare 7 giorni:
- Media settimanale
- Trend con grafico a linee
- Giorni in deficit/eccesso

### 5. Database Alimenti

Crea foglio separato con tabella completa:

```
A              B           C           D           E
Alimento       Cal/100g    Proteine    Carbo       Grassi
Pasta          350         12          70          1,5
Pollo          110         23          0           1,2
...
```

Usa CERCA.VERT in Menu per cercare automaticamente i valori.

---

## ERRORI COMUNI DA EVITARE

❌ **Unità di misura sbagliate**
- Altezza in metri invece che cm
- Peso in grammi invece che kg

❌ **Riferimenti errati tra fogli**
- `=Profilo!B13` non `=B13`
- Maiuscole/minuscole nei nomi fogli

❌ **Dimenticare le parentesi**
- `=B12*CERCA.VERT(...)` chiudi tutte le parentesi

❌ **Divisione per 100**
- Calorie per 100g, devi moltiplicare per quantità e dividere per 100

---

## CRITERI DI VALUTAZIONE

| Criterio | Peso | Descrizione |
|----------|------|-------------|
| **Calcoli Profilo** | 25% | BMI, MB, Fabbisogno corretti |
| **Menu Giornaliero** | 20% | Calorie calcolate correttamente |
| **Analisi e Confronto** | 20% | Collegamenti e valutazioni |
| **Collegamenti Fogli** | 15% | Riferimenti tra fogli corretti |
| **Presentazione** | 10% | Chiaro e professionale |
| **Funzionalità Bonus** | 10% | Grafici, formattazione, extra |

---

## ESTENSIONI POSSIBILI

1. **Obiettivi Peso:** Calcolare deficit per dimagrire o surplus per aumentare massa
2. **Idratazione:** Tracciare assunzione acqua (30ml × kg peso)
3. **Micronutrienti:** Vitamine e minerali
4. **Sport:** Calcolare calorie bruciate con attività specifiche
5. **Storia:** Tracciare peso nel tempo e progressi

---

## RIFERIMENTI TEORICI

**Concetti approfonditi nel materiale supplementare:**
- Calorie e unità di misura (kcal, kJ)
- Metabolismo basale e fattori che lo influenzano
- Macronutrienti (carboidrati, proteine, grassi)
- Micronutrienti (vitamine e minerali)
- Idratazione e bilancio idrico
- Distribuzione pasti nella giornata
- Bilancio energetico (surplus, deficit, mantenimento)

---

## PROFILI DI TEST AGGIUNTIVI

### Profilo 2 - Donna Attiva
- Sesso: F
- Età: 28 anni
- Peso: 58 kg
- Altezza: 165 cm
- Attività: Intenso

**Risultati attesi:**
- BMI: 21,3 (Normopeso)
- MB: ~1.340 kcal
- Fabbisogno: ~2.310 kcal

### Profilo 3 - Uomo Sedentario
- Sesso: M
- Età: 45 anni
- Peso: 92 kg
- Altezza: 178 cm
- Attività: Sedentario

**Risultati attesi:**
- BMI: 29,0 (Sovrappeso)
- MB: ~1.935 kcal
- Fabbisogno: ~2.322 kcal

---

*Tempo totale: 90-120 minuti*  
*Difficoltà: ⭐⭐⭐⭐ (4/5)*  
*Utilità pratica: ⭐⭐⭐⭐⭐ (5/5)*  
*Multidisciplinare: Informatica + Scienze + Educazione alla salute*
