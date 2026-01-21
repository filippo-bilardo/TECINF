# Esercitazione 13: Chimica Computazionale - Calcoli e Analisi per Laboratorio

**Livello:** 📚 INTERMEDIO-AVANZATO  
**Tempo stimato:** 120-150 minuti  
**Disciplina:** Chimica Generale + Matematica + Analisi Dati

---

## Obiettivi

- Applicare i fogli di calcolo ai calcoli chimici fondamentali
- Analizzare dati sperimentali di laboratorio
- Calcolare concentrazioni, diluizioni e stechiometria
- Creare grafici per curve di titolazione e calibrazione
- Gestire inventario reagenti e sicurezza in laboratorio

---

## Scenario

Sei uno studente del primo anno di Chimica che deve:
1. Preparare soluzioni per esperimenti di laboratorio
2. Analizzare dati sperimentali raccolti
3. Calcolare rese di reazione
4. Gestire l'inventario dei reagenti del laboratorio

---

## 📊 STRUTTURA DEL PROGETTO - 6 FOGLI

1. **Soluzioni e Diluizioni** - Calcoli molarità e preparazione
2. **Stechiometria** - Calcoli reagenti e prodotti
3. **Analisi Titolazioni** - Curve titolazione acido-base
4. **Legge dei Gas** - PV=nRT e applicazioni
5. **Inventario Reagenti** - Gestione laboratorio
6. **Analisi Dati** - Regressione lineare e curve calibrazione

---

## FOGLIO 1: SOLUZIONI E DILUIZIONI

### 📖 TEORIA: Concetti Fondamentali

**Molarità (M):**
```
M = moli di soluto / litri di soluzione
M = (grammi / peso molecolare) / litri
```

**Diluizione:**
```
M₁V₁ = M₂V₂
(concentrazione iniziale × volume iniziale = concentrazione finale × volume finale)
```

**Massa molare (PM):**
Somma delle masse atomiche degli elementi nella molecola.

---

### SEZIONE A - PREPARAZIONE SOLUZIONI

```
A                  B        C      D       E        F         G
Composto           Formula  PM     Moli    Volume   Molarità  Massa
                            g/mol  mol     L        M         g
```

**Esempio 1 - Preparare NaCl 0,5 M (500 mL):**

```
NaCl               NaCl     58,44  [calc]  0,500    0,5      [calc]
KCl                KCl      74,55  [calc]  0,250    1,0      [calc]
HCl                HCl      36,46  [calc]  1,000    0,1      [calc]
NaOH               NaOH     40,00  [calc]  0,500    2,0      [calc]
H₂SO₄              H₂SO₄    98,08  [calc]  1,000    0,25     [calc]
```

**Formule:**

**Moli richieste (D2):**
```
=F2*E2
```

**Massa da pesare (G2):**
```
=D2*C2
```

**Risultati attesi:**
- NaCl 0,5 M in 500 mL: pesare **14,61 g**
- KCl 1,0 M in 250 mL: pesare **18,64 g**
- HCl 0,1 M in 1000 mL: pesare **3,65 g**

---

### SEZIONE B - CALCOLO DILUIZIONI

**Formula base: M₁V₁ = M₂V₂**

```
A                    B          C          D          E
Soluzione            M iniziale V iniziale M finale   V finale
                     (M₁)       (mL)       (M₂)       (mL)
HCl                  12,0       [calc]     1,0        100
NaOH                 10,0       [calc]     0,5        250
H₂SO₄                18,0       [calc]     2,0        500
```

**Formula per V₁ (C2):**
```
=(D2*E2)/B2
```

**Esempio:**
Per preparare HCl 1,0 M partendo da HCl 12,0 M:
- V₁ = (1,0 × 100) / 12,0 = **8,33 mL**
- Prelevare 8,33 mL di HCl 12 M e portare a 100 mL con acqua

---

### SEZIONE C - DILUIZIONI SERIALI

```
Diluizione    Fattore    M iniziale    M finale    
1             1:10       1,000         0,100
2             1:10       0,100         0,010
3             1:10       0,010         0,001
4             1:10       0,001         0,0001
```

**Formula M finale (D2):**
```
=C2/B2
```
(dove B2 contiene il numero 10 per diluizione 1:10)

---

### SEZIONE D - PERCENTUALI IN PESO/VOLUME

```
=== SOLUZIONI % P/V ===

NaCl 5% (p/v) in 200 mL
Massa NaCl necessaria:    [=5*200/100] = 10 g

Glucosio 10% (p/v) in 500 mL
Massa glucosio:           [=10*500/100] = 50 g

Etanolo 70% (v/v) in 1000 mL
Volume etanolo puro:      [=70*1000/100] = 700 mL
```

---

## FOGLIO 2: STECHIOMETRIA E RESE DI REAZIONE

### 📖 TEORIA: Calcoli Stechiometrici

**Reazione generica:**
```
aA + bB → cC + dD
```

**Rapporti stechiometrici:**
- I coefficienti indicano i rapporti molari
- Il reagente limitante determina la quantità di prodotto

**Resa di reazione:**
```
Resa % = (quantità ottenuta / quantità teorica) × 100
```

---

### SEZIONE A - ESEMPIO: SINTESI ASPIRINA

**Reazione:**
```
C₇H₆O₃ + C₄H₆O₃ → C₉H₈O₄ + CH₃COOH
(Ac. salicilico) + (Anidr. acetica) → (Aspirina) + (Ac. acetico)
```

**Rapporto stechiometrico: 1:1:1:1**

```
A                      B        C        D        E         F
Composto               Formula  PM       Massa    Moli      Ruolo
                                g/mol    g        mol
Acido salicilico       C₇H₆O₃   138,12   2,00     [calc]    Reagente
Anidride acetica       C₄H₆O₃   102,09   3,00     [calc]    Reagente
Aspirina (teorica)     C₉H₈O₄   180,16   [calc]   [calc]    Prodotto
Aspirina (ottenuta)    C₉H₈O₄   180,16   2,35     [calc]    Reale
```

**Formule:**

**Moli (E2):**
```
=D2/C2
```

**Moli acido salicilico:** 2,00 / 138,12 = **0,0145 mol**
**Moli anidride acetica:** 3,00 / 102,09 = **0,0294 mol**

**Reagente limitante:** Acido salicilico (meno moli)

**Aspirina teorica (moli E4):**
```
=E2  (stessa quantità del reagente limitante)
```

**Aspirina teorica (massa D4):**
```
=E4*C4
```
= 0,0145 × 180,16 = **2,61 g**

**Resa % (G4):**
```
=(D5/D4)*100
```
= (2,35 / 2,61) × 100 = **90,0%**

---

### SEZIONE B - TABELLA STECHIOMETRIA MULTIPLA

```
Esperim.  Reagente1  Reagente2  Prod.Teorico  Prod.Ottenuto  Resa%
1         2,00 g     3,00 g     2,61 g        2,35 g         90,0%
2         5,00 g     6,00 g     6,52 g        5,80 g         89,0%
3         1,50 g     2,50 g     1,96 g        1,65 g         84,2%

Media resa:                                                   87,7%
Dev.standard:                                                 3,1%
```

**Formula deviazione standard:**
```
=DEV.ST(F2:F4)
```

---

### SEZIONE C - REAGENTE IN ECCESSO

```
=== CALCOLO ECCESSO ===

Moli reagente 1 necessarie:     0,0145 mol
Moli reagente 2 disponibili:    0,0294 mol
Moli reagente 2 necessarie:     0,0145 mol (rapporto 1:1)

Eccesso reagente 2 (moli):      [=0,0294-0,0145] = 0,0149 mol
Eccesso reagente 2 (grammi):    [=0,0149*PM] = 1,52 g
% Eccesso:                      [=(0,0149/0,0145)*100] = 102,8%
```

---

## FOGLIO 3: TITOLAZIONI ACIDO-BASE

### 📖 TEORIA: Titolazione

**Punto di equivalenza:**
```
n(acido) = n(base)
M_acido × V_acido = M_base × V_base
```

**pH durante titolazione:**
- Prima del punto eq.: pH dipende dall'acido
- Al punto eq.: pH = 7 (acidi/basi forti)
- Dopo il punto eq.: pH dipende dalla base

---

### SEZIONE A - DATI SPERIMENTALI TITOLAZIONE

**Titolazione: HCl 0,1 M con NaOH 0,1 M**

```
A              B              C           D
Vol NaOH (mL)  pH misurato    pH teorico  Derivata
0              1,00           [calc]      -
5              1,18           [calc]      [calc]
10             1,37           [calc]      [calc]
15             1,60           [calc]      [calc]
20             1,95           [calc]      [calc]
23             2,60           [calc]      [calc]
24             3,00           [calc]      [calc]
24,5           3,30           [calc]      [calc]
25             7,00           [calc]      [calc]  ← Punto equivalenza
25,5           10,70          [calc]      [calc]
26             11,00          [calc]      [calc]
27             11,40          [calc]      [calc]
30             11,96          [calc]      [calc]
```

**Formula derivata (approssimata) D3:**
```
=(B3-B2)/(A3-A2)
```

**Punto di equivalenza:** Massimo della derivata

---

### SEZIONE B - CALCOLI CONCENTRAZIONE INCOGNITA

```
=== DETERMINAZIONE CONCENTRAZIONE ===

Titolante: NaOH               M = 0,1000 M
Volume usato al p.eq.:        V = 25,35 mL
Titolando: HCl                V = 25,00 mL
Concentrazione HCl:           M = ?

Formula: M₁V₁ = M₂V₂

M(HCl) = [M(NaOH) × V(NaOH)] / V(HCl)
M(HCl) = (0,1000 × 25,35) / 25,00
M(HCl) = 0,1014 M

Errore % rispetto a nominale (0,1000 M):
Errore = [(0,1014 - 0,1000) / 0,1000] × 100 = +1,4%
```

---

### SEZIONE C - SERIE DI TITOLAZIONI

```
Esperim.  Vol NaOH (mL)  M(HCl) calc  Errore%
1         25,35          0,1014       +1,4%
2         25,28          0,1011       +1,1%
3         25,42          0,1017       +1,7%
4         25,31          0,1012       +1,2%
5         25,38          0,1015       +1,5%

Media M(HCl):            0,1014 M
Dev.standard:            0,0002 M
CV% (coeff.variaz):      0,2%
```

**Coefficiente di variazione (CV%):**
```
=(DEV.ST(C2:C6)/MEDIA(C2:C6))*100
```

---

### SEZIONE D - GRAFICO DA CREARE

**Curva di titolazione:**
- Asse X: Volume NaOH (mL)
- Asse Y: pH
- Tipo: Grafico a dispersione con linee smussate
- Evidenziare punto di equivalenza (pH ≈ 7)

---

## FOGLIO 4: LEGGE DEI GAS IDEALI

### 📖 TEORIA: Equazione di Stato

**Legge dei gas ideali:**
```
PV = nRT

P = pressione (atm)
V = volume (L)
n = moli (mol)
R = 0,0821 atm·L/(mol·K)
T = temperatura (K)
```

**Conversioni:**
- K = °C + 273,15
- 1 atm = 101325 Pa = 760 mmHg

---

### SEZIONE A - CALCOLI BASE

```
A                  B         C       D       E        F
Dato               P (atm)   V (L)   n (mol) T (K)    Valore
```

**Esempio 1: Calcolare volume**
```
1 mol gas, 1 atm, 273 K
V = nRT/P
V = (1 × 0,0821 × 273) / 1 = 22,4 L  ← Condizioni standard!
```

**Formula V (C2):**
```
=(D2*0,0821*E2)/B2
```

**Esempio 2: Calcolare pressione**
```
2 mol gas, 10 L, 300 K
P = nRT/V
P = (2 × 0,0821 × 300) / 10 = 4,93 atm
```

**Formula P (B3):**
```
=(D3*0,0821*E3)/C3
```

---

### SEZIONE B - PROBLEMI APPLICATIVI

**Problema 1: Raccolta gas su acqua**

```
=== RACCOLTA H₂ SU ACQUA ===

Reazione: Zn + 2HCl → ZnCl₂ + H₂

Massa Zn usata:              1,50 g
PM Zn:                       65,38 g/mol
Moli Zn:                     [=1,50/65,38] = 0,0229 mol
Moli H₂ prodotte:            [=0,0229] = 0,0229 mol (rapporto 1:1)

Pressione totale:            748 mmHg = 0,984 atm
Pressione vapor acqueo 25°C: 24 mmHg = 0,032 atm
Pressione H₂:                [=0,984-0,032] = 0,952 atm

Temperatura:                 25°C = 298 K

Volume H₂ raccolto:
V = nRT/P = (0,0229 × 0,0821 × 298) / 0,952
V = 0,589 L = 589 mL
```

---

### SEZIONE C - TABELLA DENSITÀ GAS

```
Gas      PM(g/mol)  P(atm)  T(K)   Densità(g/L)
H₂       2,016      1,00    273    [calc]
N₂       28,014     1,00    273    [calc]
O₂       31,998     1,00    273    [calc]
CO₂      44,010     1,00    273    [calc]
```

**Formula densità:**
```
Densità = (P × PM) / (R × T)
```

**Formula per H₂ (E2):**
```
=(C2*B2)/(0,0821*D2)
```

**Risultati attesi (STP):**
- H₂: 0,090 g/L
- N₂: 1,25 g/L
- O₂: 1,43 g/L
- CO₂: 1,96 g/L

---

### SEZIONE D - LEGGE DI DALTON (MISCELE)

```
=== PRESSIONI PARZIALI ===

Contenitore 10 L a 300 K contiene:
- 0,5 mol N₂
- 0,3 mol O₂
- 0,2 mol CO₂

Pressione parziale N₂:  P = nRT/V = (0,5×0,0821×300)/10 = 1,23 atm
Pressione parziale O₂:  P = (0,3×0,0821×300)/10 = 0,74 atm
Pressione parziale CO₂: P = (0,2×0,0821×300)/10 = 0,49 atm

Pressione totale:       P_tot = 1,23 + 0,74 + 0,49 = 2,46 atm

Frazione molare N₂:     X = 0,5/1,0 = 0,50 (50%)
Frazione molare O₂:     X = 0,3/1,0 = 0,30 (30%)
Frazione molare CO₂:    X = 0,2/1,0 = 0,20 (20%)
```

---

## FOGLIO 5: INVENTARIO REAGENTI LABORATORIO

### SEZIONE A - CATALOGO REAGENTI

```
A          B              C         D        E        F         G          H
Codice     Nome           Formula   PM       Classe   Quantità  Scadenza   CAS
R001       NaCl           NaCl      58,44    Neutra   500 g     12/2027    7647-14-5
R002       HCl 37%        HCl       36,46    Acido    1 L       06/2026    7647-01-0
R003       NaOH           NaOH      40,00    Base     250 g     09/2026    1310-73-2
R004       H₂SO₄ 98%     H₂SO₄     98,08    Acido    500 mL    03/2027    7664-93-9
R005       Etanolo 99%    C₂H₅OH    46,07    Solv.    2 L       08/2026    64-17-5
R006       Acetone        C₃H₆O     58,08    Solv.    1 L       05/2026    67-64-1
R007       KMnO₄          KMnO₄     158,03   Ossid.   100 g     12/2028    7722-64-7
R008       AgNO₃          AgNO₃     169,87   Sali     50 g      11/2026    7761-88-8
```

---

### SEZIONE B - PITTOGRAMMI DI PERICOLO

```
Codice  Nome         Pittogrammi                 Note sicurezza
R002    HCl 37%      ⚠️ Corrosivo, Irritante    Indossare guanti, occhiali
R003    NaOH         ⚠️ Corrosivo               Protezione occhi obbligatoria
R004    H₂SO₄ 98%   ☠️ Corrosivo, Reattivo     Cappa aspirante, DPI completi
R005    Etanolo      🔥 Infiammabile            Lontano da fiamme
R006    Acetone      🔥 Infiammabile            Cappa, no fiamme
R007    KMnO₄        ⚠️ Ossidante, Irritante   Evitare contatto pelle
R008    AgNO₃        ⚠️ Corrosivo, Ecotossico  Guanti, smaltimento speciale
```

---

### SEZIONE C - REGISTRO USI

```
Data       Codice  Utente    Esperimento        Quantità  Residuo
15/01/26   R002    Mario R.  Titolazione        50 mL     950 mL
16/01/26   R003    Anna V.   Preparaz. sol.     10 g      240 g
17/01/26   R005    Luca B.   Estrazione         100 mL    1900 mL
18/01/26   R007    Sara N.   Redox              5 g       95 g
```

**Formula residuo (F2):**
```
=F1-E2
```
(F1 è il residuo precedente o la quantità iniziale)

---

### SEZIONE D - ALERT E RIORDINI

```
=== ALERT AUTOMATICI ===

Codice  Nome        Residuo   Minimo    Alert           Riordino
R002    HCl 37%     950 mL    500 mL    ✅ OK          No
R003    NaOH        240 g     200 g     ⚠️ BASSO       Presto
R005    Etanolo     1900 mL   1000 mL   ✅ OK          No
R006    Acetone     150 mL    500 mL    🔴 CRITICO     Urgente
R007    KMnO₄       95 g      50 g      ✅ OK          No
R008    AgNO₃       12 g      20 g      🔴 CRITICO     Urgente
```

**Formula alert (E2):**
```
=SE(C2<D2*0,5;"🔴 CRITICO";SE(C2<D2*1,2;"⚠️ BASSO";"✅ OK"))
```

**Formula riordino (F2):**
```
=SE(E2="🔴 CRITICO";"Urgente";SE(E2="⚠️ BASSO";"Presto";"No"))
```

---

### SEZIONE E - COSTI E BUDGET

```
Reagente     Prezzo/unità   Quantità riordino   Costo tot   Fornitore
HCl 37%      25 €/L         2 L                 50 €        Sigma-Aldrich
NaOH         18 €/kg        1 kg                18 €        Merck
Acetone      22 €/L         2 L                 44 €        Carlo Erba
AgNO₃        180 €/100g     100 g               180 €       Sigma-Aldrich

TOTALE ORDINE                                    292 €
Budget disponibile                               500 €
Residuo budget                                   208 €
```

---

## FOGLIO 6: ANALISI DATI E CURVE DI CALIBRAZIONE

### 📖 TEORIA: Regressione Lineare

**Equazione retta:**
```
y = mx + q

m = pendenza
q = intercetta
R² = coefficiente di determinazione (0-1, vicino a 1 = buona correlazione)
```

---

### SEZIONE A - CURVA DI CALIBRAZIONE SPETTROFOTOMETRO

**Legge di Beer-Lambert:**
```
A = ε × c × l

A = assorbanza
ε = coefficiente di estinzione molare
c = concentrazione (M)
l = cammino ottico (cm)
```

**Dati sperimentali:**

```
A                B              C              D
Concentr.(mg/L)  Assorbanza     Abs.teorica    Residuo
0                0,000          [calc]         [calc]
2                0,095          [calc]         [calc]
4                0,188          [calc]         [calc]
6                0,285          [calc]         [calc]
8                0,378          [calc]         [calc]
10               0,472          [calc]         [calc]
```

---

### SEZIONE B - CALCOLI REGRESSIONE

```
=== PARAMETRI REGRESSIONE ===

Pendenza (m):           [=PENDENZA(B2:B7;A2:A7)] = 0,0472
Intercetta (q):         [=INTERCETTA(B2:B7;A2:A7)] = 0,0005
R²:                     [=RQ(B2:B7;A2:A7)] = 0,9998

Equazione retta:        y = 0,0472x + 0,0005
```

**Formule Google Sheets:**
- `=SLOPE(B2:B7;A2:A7)` per pendenza
- `=INTERCEPT(B2:B7;A2:A7)` per intercetta
- `=RSQ(B2:B7;A2:A7)` per R²

---

### SEZIONE C - DETERMINAZIONE INCOGNITA

```
=== CAMPIONE INCOGNITO ===

Assorbanza misurata:    0,336

Concentrazione = (Abs - q) / m
Concentrazione = (0,336 - 0,0005) / 0,0472
Concentrazione = 7,11 mg/L
```

**Formula:**
```
=(0,336-Intercetta)/Pendenza
```

---

### SEZIONE D - LIMITE DI RILEVABILITÀ (LOD)

```
=== ANALISI QUALITÀ ===

Deviazione std. bianco: σ = 0,003
LOD = 3,3 × σ / m
LOD = 3,3 × 0,003 / 0,0472
LOD = 0,21 mg/L

LOQ (limite quantificaz.):
LOQ = 10 × σ / m
LOQ = 10 × 0,003 / 0,0472
LOQ = 0,64 mg/L
```

---

### SEZIONE E - GRAFICI DA CREARE

**1. Curva di calibrazione:**
- X: Concentrazione (mg/L)
- Y: Assorbanza
- Tipo: Dispersione XY
- Aggiungi linea di tendenza lineare
- Mostra equazione e R²

**2. Grafico residui:**
- X: Concentrazione
- Y: Residuo (Abs.misurata - Abs.teorica)
- Verifica distribuzione casuale intorno a zero

---

## COMPITI DA SVOLGERE

### Livello Base (30 punti)

1. ✅ Calcola masse per preparare 5 soluzioni (10 pt)
2. ✅ Esegui 3 calcoli di diluizione (10 pt)
3. ✅ Calcola resa % in reazione stechiometrica (10 pt)

### Livello Intermedio (40 punti)

4. ✅ Analizza dati titolazione, trova punto equivalenza (10 pt)
5. ✅ Risolvi 3 problemi con legge gas ideali (10 pt)
6. ✅ Crea inventario con alert automatici (10 pt)
7. ✅ Costruisci curva calibrazione con regressione (10 pt)

### Livello Avanzato (30 punti)

8. ✅ Crea grafico curva titolazione con derivata (10 pt)
9. ✅ Analizza errori sperimentali con dev.std (10 pt)
10. ✅ Sistema completo con collegamenti tra fogli (10 pt)

---

## FORMULE CHIMICHE ESSENZIALI

### Concentrazioni

```
Molarità:           M = moli / litri
Molalità:           m = moli / kg solvente
Frazione molare:    X = moli_A / moli_totali
% p/p:              (massa_soluto / massa_soluzione) × 100
% p/v:              (massa_soluto_g / volume_soluz_mL) × 100
ppm:                (massa_soluto / massa_soluzione) × 10⁶
```

### pH e pOH

```
pH:                 pH = -log[H⁺]
pOH:                pOH = -log[OH⁻]
Relazione:          pH + pOH = 14 (a 25°C)
[H⁺]:               [H⁺] = 10^(-pH)
```

### Termodinamica

```
ΔH = Entalpia
ΔS = Entropia
ΔG = Energia libera di Gibbs
ΔG = ΔH - TΔS
```

---

## COSTANTI UTILI

```
R (gas):                0,0821 atm·L/(mol·K)
R (SI):                 8,314 J/(mol·K)
Costante Avogadro:      6,022 × 10²³ mol⁻¹
Carica elettrone:       1,602 × 10⁻¹⁹ C
Costante Faraday:       96485 C/mol
Volume molare (STP):    22,4 L/mol
Zero assoluto:          -273,15°C = 0 K
```

---

## CRITERI DI VALUTAZIONE

| Criterio | Punti | Descrizione |
|----------|-------|-------------|
| **Calcoli chimici corretti** | 30 | Formule e risultati accurati |
| **Analisi dati** | 25 | Regressioni, statistiche, errori |
| **Grafici scientifici** | 20 | Assi, unità, titoli, legenda |
| **Organizzazione** | 15 | Struttura chiara e logica |
| **Presentazione** | 10 | Formattazione professionale |

---

## SICUREZZA IN LABORATORIO

### Pittogrammi GHS (Sistema Globale Armonizzato)

```
🔥 GHS02: Infiammabile
☠️ GHS06: Tossico acuto
⚠️ GHS07: Nocivo, irritante
⚗️ GHS05: Corrosivo
💣 GHS01: Esplosivo
🌳 GHS09: Pericoloso per ambiente
```

### Frase H (Hazard) comuni

```
H314: Provoca gravi ustioni cutanee
H318: Provoca gravi lesioni oculari
H225: Liquido e vapori facilmente infiammabili
H302: Nocivo se ingerito
H400: Molto tossico per organismi acquatici
```

---

## RISORSE E APPROFONDIMENTI

### Database Online

- **PubChem** - Proprietà chimiche composti
- **ChemSpider** - Ricerca strutture chimiche
- **NIST Chemistry WebBook** - Dati termodinamici
- **Sigma-Aldrich** - Schede sicurezza (MSDS/SDS)

### Software Complementari

- **ChemDraw** - Strutture molecolari
- **PyMOL** - Visualizzazione 3D molecole
- **Origin/GraphPad** - Analisi dati avanzata
- **Python (NumPy, SciPy, Matplotlib)** - Calcoli scientifici

---

## RIFLESSIONI FINALI

**Perché questa esercitazione è fondamentale:**

- 🧪 **Calcoli accurati**: Evita sprechi e rischi in laboratorio
- 📊 **Analisi dati**: Competenza essenziale per ogni chimico
- 🔬 **Metodo scientifico**: Riproducibilità e documentazione
- ⚗️ **Sicurezza**: Gestione consapevole reagenti pericolosi
- 💾 **Automazione**: Risparmio tempo nei calcoli ripetitivi

**Testimonianze studenti:**

> "Prima perdevo ore a calcolare manualmente molarità e diluizioni. Ora con il foglio verifico tutto in pochi secondi!" - Marco, Chimica I anno

> "Le curve di calibrazione automatiche mi hanno fatto risparmiare giorni di lavoro nella tesi!" - Anna, Chimica Analitica

> "L'inventario reagenti ha evitato che rimanessimo senza HCl nel mezzo di un esperimento!" - Luca, Responsabile laboratorio

---

## ESTENSIONI POSSIBILI

1. **Elettrochimica** - Calcoli celle galvaniche, leggi Faraday
2. **Cinetica** - Costanti velocità, ordini reazione, tempo emivita
3. **Equilibrio chimico** - K_eq, Q, principio Le Chatelier
4. **Termochimica** - ΔH reazione, legge Hess, cicli Born-Haber
5. **Chimica organica** - Calcolo resa sintesi, purificazioni

---

*Tempo totale: 120-150 minuti*  
*Difficoltà: ⭐⭐⭐⭐ (4/5)*  
*Utilità: ⭐⭐⭐⭐⭐ (5/5) - Essenziale per ogni studente di chimica*  
*Competenze: Calcoli chimici + Analisi dati + Laboratorio*
