# Esercitazione 4: Sistema di Produttività Personale

**Livello:** 📚 BASE-INTERMEDIO  
**Tempo stimato:** 3-4 ore (progetto multi-sessione)

---

## Obiettivi

- Creare un sistema integrato per gestire tempo, obiettivi e abitudini
- Utilizzare formule per automatizzare tracking e analisi
- Sviluppare competenze pratiche per la vita quotidiana
- Implementare dashboard personale con KPI
- Collegare dati tra fogli multipli

---

## Scenario

Creare un sistema completo di produttività personale che include gestione del tempo, budget mensile, tracker abitudini, to-do list intelligente e pianificazione settimanale. Questo sistema aiuterà a organizzare la vita quotidiana in modo efficiente.

---

## 📊 STRUTTURA DEL PROGETTO - 5 FOGLI INTERCONNESSI

1. **Dashboard** - Vista generale e KPI
2. **Budget Mensile** - Gestione finanze personali
3. **Time Tracker** - Analisi utilizzo del tempo
4. **Habit Tracker** - Monitoraggio abitudini
5. **Weekly Planner** - Pianificazione settimanale

---

## FOGLIO 1: DASHBOARD PRODUTTIVITÀ

### Obiettivo
Creare una vista generale con indicatori chiave di performance personali.

### Struttura

```
=== KPI MENSILI ===

A                          B           C
Budget Disponibile         €XXXX       [formula]
% Budget Utilizzato        XX%         [formula]
Stato Budget              [OK/ALERT]   [formula]

Ore Produttive Oggi       X ore        [formula]
Ore Produttive Settimana  XX ore       [formula]
Media Giornaliera         X ore        [formula]

Abitudini Completate      X/Y          [formula]
Streak Corrente          X giorni      [formula]
% Completamento          XX%           [formula]

Task Completati Oggi      X/Y          [formula]
Task in Ritardo          X             [formula]

=== OBIETTIVI MENSILI ===

Obiettivo 1: Risparmio          Target: €500    Attuale: €XXX    %: XX%
Obiettivo 2: Studio             Target: 60 ore  Attuale: XX ore  %: XX%
Obiettivo 3: Esercizio          Target: 20 gg   Attuale: XX gg   %: XX%
```

### Formule da Implementare

**1. Budget Disponibile:**
```
=BudgetMensile!B6-SOMMA(BudgetMensile!C20:C50)
```

**2. % Budget Utilizzato:**
```
=SOMMA(BudgetMensile!C20:C50)/BudgetMensile!B6
```

**3. Stato Budget:**
```
=SE(B2>0,9;"🔴 ATTENZIONE";SE(B2>0,75;"🟡 CONTROLLARE";"🟢 OK"))
```

**4. Ore Produttive Oggi:**
```
=SOMMA.SE(TimeTracker!A:A;OGGI();TimeTracker!C:C)
```

---

## FOGLIO 2: BUDGET MENSILE

### Obiettivo
Gestire entrate e uscite con analisi automatica delle spese.

### SEZIONE A - ENTRATE

```
A                    B
=== ENTRATE MENSILI ===
Stipendio            1800
Freelance            200
Altro                50
TOTALE ENTRATE       [=SOMMA(B3:B5)]
```

### SEZIONE B - CATEGORIE BUDGET

```
A                    B          C              D
=== BUDGET CATEGORIE ===
Categoria            Budget     Speso          Rimanente
Alimentari           400        [=SOMMA.SE()]  [=B9-C9]
Trasporti            100        [=SOMMA.SE()]  [=B10-C10]
Casa (affitto)       600        [=SOMMA.SE()]  [=B11-C11]
Utenze               120        [=SOMMA.SE()]  [=B12-C12]
Svago               150        [=SOMMA.SE()]  [=B13-C13]
Salute              80         [=SOMMA.SE()]  [=B14-C14]
Risparmi            500        [=SOMMA.SE()]  [=B15-C15]
Altro               100        [=SOMMA.SE()]  [=B16-C16]

TOTALE              [=SOMMA()] [=SOMMA()]     [=SOMMA()]
```

### SEZIONE C - REGISTRO SPESE

```
A          B              C          D              E
Data       Categoria      Importo    Descrizione    Tipo
01/01      Alimentari     -45,50     Supermercato   Necessario
02/01      Svago          -15,00     Cinema         Voluttuario
03/01      Trasporti      -30,00     Benzina        Necessario
```

### Formule Chiave

**1. Speso per categoria:**
```
=SOMMA.SE($B$20:$B$100;A9;$C$20:$C$100)
```

**2. Alert budget categoria:**
```
=SE(C9>B9*0,9;"⚠️ ATTENZIONE";SE(C9>B9;"❌ SUPERATO";"✅"))
```

**3. Analisi tipo spesa:**
```
Necessarie: =SOMMA.SE(E:E;"Necessario";C:C)
Voluttuarie: =SOMMA.SE(E:E;"Voluttuario";C:C)
```

---

## FOGLIO 3: TIME TRACKER

### Obiettivo
Analizzare come si utilizza il tempo durante la giornata.

### SEZIONE A - LOG ATTIVITÀ

```
A          B              C          D              E
Data       Attività       Ore        Categoria      Produttivo
21/01      Studio         2,5        Formazione     Sì
21/01      Social Media   1,0        Svago          No
21/01      Lavoro         4,0        Carriera       Sì
21/01      Sport          1,0        Salute         Sì
21/01      Serie TV       2,0        Svago          No
```

### SEZIONE B - ANALISI SETTIMANALE

```
=== ANALISI SETTIMANALE ===

Categoria          Ore Settimana    Ore/Giorno    % Tempo    Target    Diff
Lavoro/Studio      35               5,0           29%        40        -5
Salute/Sport       7                1,0           6%         10        -3
Famiglia          14               2,0           12%        14         0
Svago             21               3,0           18%        15        +6
Sonno             56               8,0           47%        56         0
Altro             7                1,0           6%         5         +2

TOTALE            168              24,0          100%       168        0
```

### Formule

**1. Ore per categoria (settimana corrente):**
```
=SOMMA.PIÙ.SE(C:C;A:A;">="&OGGI()-GIORNO.SETTIMANA(OGGI())+1;D:D;A2)
```

**2. % Tempo produttivo:**
```
=SOMMA.SE(E:E;"Sì";C:C)/SOMMA(C:C)
```

**3. Media ore/giorno:**
```
=B2/7
```

---

## FOGLIO 4: HABIT TRACKER

### Obiettivo
Monitorare abitudini quotidiane e visualizzare progressi.

### Struttura

```
A              B  C  D  E  F  G  H  I  J  K  L  M ... (31 giorni)
Abitudine      1  2  3  4  5  6  7  8  9 10 11 12 ...  Totale  %   Streak

Bere 2L acqua  ✓  ✓  ✓  ✗  ✓  ✓  ✓  ✓           8/10  80%   3
Meditazione    ✓  ✗  ✓  ✓  ✓  ✓  ✓  ✓           7/10  70%   5
Esercizio      ✓  ✓  ✗  ✗  ✓  ✓  ✗  ✓           5/10  50%   1
Leggere        ✓  ✓  ✓  ✓  ✓  ✓  ✓  ✓           8/10  80%   8
No junk food   ✓  ✓  ✗  ✓  ✓  ✓  ✓  ✓           7/10  70%   5
```

### Formule

**1. Totale completamenti:**
```
=CONTA.SE(B2:L2;"✓")
```

**2. Percentuale:**
```
=M2/CONTA.VALORI(B2:L2)
```

**3. Streak corrente:**
```
=SE(L2="✓";SE(K2="✓";1+[precedente];1);0)
```

---

## FOGLIO 5: WEEKLY PLANNER

### Obiettivo
Pianificare la settimana con to-do list intelligente.

### Struttura

```
=== SETTIMANA DEL 20-26 GENNAIO ===

A          B                      C         D          E           F
Giorno     Task                   Categoria Priorità   Tempo(h)    Status

LUN 20     Riunione team          Lavoro    Alta      2           ✅
LUN 20     Palestra               Salute    Media     1           ✅
LUN 20     Studio JavaScript      Formaz.   Alta      3           🔄
LUN 20     Spesa supermercato     Casa      Bassa     1           ⏸️

MAR 21     Presentazione cliente  Lavoro    Alta      4           📅
MAR 21     Dentista              Salute    Alta      1           📅
MAR 21     Leggere 50 pagine     Personal  Media     1           📅
```

**Legend status:**
- ✅ Completato
- 🔄 In corso
- 📅 Pianificato
- ⏸️ In pausa
- ❌ Cancellato

### Formule

**1. Task completati per giorno:**
```
=CONTA.SE($F$2:$F$50;"✅")
```

**2. Ore pianificate vs disponibili:**
```
Pianificate: =SOMMA.SE(A:A;A2;E:E)
Alert: =SE(Pianificate>12;"⚠️ SOVRACCARICO";"✅")
```

**3. Task in ritardo:**
```
=CONTA.PIÙ.SE(A:A;"<"&OGGI();F:F;"<>"&"✅")
```

---

## COMPITI DA SVOLGERE

### LIVELLO BASE (Settimana 1-2)

**1. Crea il foglio Budget Mensile:**
- Inserisci 3 categorie di spesa
- Registra almeno 10 transazioni
- Calcola totali e rimanenti
- Crea grafico a torta spese

**2. Crea il foglio Habit Tracker:**
- Scegli 3 abitudini personali
- Traccia per 7 giorni
- Calcola percentuali
- Identifica pattern

### LIVELLO INTERMEDIO (Settimana 3-4)

**3. Crea il foglio Time Tracker:**
- Traccia attività per 3 giorni
- Categorizza il tempo
- Calcola % produttività
- Identifica sprechi di tempo

**4. Crea il foglio Weekly Planner:**
- Pianifica prossima settimana
- Usa matrice Eisenhower
- Calcola carico di lavoro
- Monitora completamento

### LIVELLO AVANZATO (Settimana 5-6)

**5. Crea la Dashboard:**
- Collegamenti a tutti i fogli
- KPI automatici
- Sistema di alert
- Visualizzazioni grafiche

**6. Implementa automazioni:**
- Formattazione condizionale
- Validazione dati
- Formule avanzate
- Grafici dinamici

---

## CRITERI DI VALUTAZIONE

| Criterio | Peso | Descrizione |
|----------|------|-------------|
| **Completezza** | 30% | Tutti i 5 fogli implementati con sezioni richieste |
| **Formule** | 30% | Correttezza calcoli e collegamenti tra fogli |
| **Automazione** | 20% | Formattazione condizionale, validazione, alert |
| **Usabilità** | 10% | Organizzazione chiara e design professionale |
| **Personalizzazione** | 10% | Adattamento alle esigenze personali |

---

## 💡 ESTENSIONI E IDEE BONUS

1. **Fitness Tracker** - Log allenamenti e progressi peso
2. **Meal Planner** - Piano pasti settimanale con lista spesa
3. **Learning Tracker** - Ore studio per materia
4. **Gratitude Journal** - 3 gratitudini al giorno
5. **Book Tracker** - Lista libri/film con rating

---

## Riflessioni Finali

### Perché questo esercizio è importante

1. **Applicazione pratica reale:** Sistema utilizzabile quotidianamente
2. **Sviluppa autodisciplina:** Tracciare dati richiede costanza
3. **Data-driven decisions:** Decisioni basate su dati, non sensazioni
4. **Competenze trasferibili:** Tecniche utili in qualsiasi lavoro
5. **Autoconsapevolezza:** Identifica aree di miglioramento

### Come usare il sistema dopo l'esercitazione

- ✅ Aggiorna quotidianamente (5-10 minuti)
- 📊 Rivedi settimanalmente la dashboard
- 📈 Analisi mensile approfondita
- 🔄 Adatta e migliora continuamente
- 🎉 Celebra i progressi!

---

*Tempo totale: 3-4 ore distribuite su 6 settimane*  
*Difficoltà: ⭐⭐⭐ (3/5)*  
*Utilità pratica: ⭐⭐⭐⭐⭐ (5/5)*
