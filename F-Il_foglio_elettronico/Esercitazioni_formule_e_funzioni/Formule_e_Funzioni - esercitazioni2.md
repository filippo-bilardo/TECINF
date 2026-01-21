### FOGLIO 1: DASHBOARD PRODUTTIVITÀ

**Obiettivo:** Creare una vista generale con indicatori chiave di performance personali.

**Struttura del foglio:**

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

**Formule da implementare:**

1. **Budget Disponibile:**
```
=BudgetMensile!B2-SOMMA(BudgetMensile!C8:C50)
```

2. **% Budget Utilizzato:**
```
=SOMMA(BudgetMensile!C8:C50)/BudgetMensile!B2
```

3. **Stato Budget:**
```
=SE(B2>90%;"🔴 ATTENZIONE";SE(B2>75%;"🟡 CONTROLLARE";"🟢 OK"))
```

4. **Ore Produttive Oggi:**
```
=SOMMA.SE(TimeTracker!A:A;OGGI();TimeTracker!C:C)
```

---

### FOGLIO 2: BUDGET MENSILE

**Obiettivo:** Gestire entrate e uscite con analisi automatica delle spese.

**SEZIONE A - ENTRATE:**

```
A                    B
=== ENTRATE MENSILI ===
Stipendio            1800
Freelance            200
Altro                50
TOTALE ENTRATE       =SOMMA(B3:B5)
```

**SEZIONE B - CATEGORIE BUDGET:**

```
A                    B          C              D
=== BUDGET CATEGORIE ===
Categoria            Budget     Speso          Rimanente
Alimentari           400        =SOMMA.SE()    =B9-C9
Trasporti            100        =SOMMA.SE()    =B10-C10
Casa (affitto)       600        =SOMMA.SE()    =B11-C11
Utenze               120        =SOMMA.SE()    =B12-C12
Svago               150        =SOMMA.SE()    =B13-C13
Salute              80         =SOMMA.SE()    =B14-C14
Risparmi            500        =SOMMA.SE()    =B15-C15
Altro               100        =SOMMA.SE()    =B16-C16

TOTALE              =SOMMA()   =SOMMA()       =SOMMA()
```

**SEZIONE C - REGISTRO SPESE:**

```
A          B              C          D              E
Data       Categoria      Importo    Descrizione    Tipo
01/01      Alimentari     -45,50     Supermercato   Necessario
02/01      Svago          -15,00     Cinema         Voluttuario
03/01      Trasporti      -30,00     Benzina        Necessario
```

**Formule avanzate:**

1. **Speso per categoria (in Sezione B):**
```
=SOMMA.SE($B$20:$B$100;A9;$C$20:$C$100)
```

2. **Alert budget categoria:**
```
=SE(C9>B9*0.9;"⚠️ ATTENZIONE";SE(C9>B9;"❌ SUPERATO";"✅"))
```

3. **Analisi tipo spesa:**
```
Necessarie: =SOMMA.SE(E:E;"Necessario";C:C)
Voluttuarie: =SOMMA.SE(E:E;"Voluttuario";C:C)
```

4. **Grafico a torta automatico:**
Crea grafico che mostra distribuzione spese per categoria.

**SEZIONE D - ANALISI:**

```
=== ANALISI MENSILE ===

Totale Entrate              =B6
Totale Spese               =-SOMMA(C20:C100)
Bilancio                   =Entrate+Spese
% Risparmio Effettivo      =Bilancio/Entrate

Media Spesa Giornaliera    =Spese/GIORNO(FINE.MESE(OGGI();0))
Proiezione Fine Mese       =MediaGiornaliera*30

Categoria più cara         =INDICE(A9:A16;CONFRONTA(MAX(C9:C16);C9:C16;0))
% sul totale               =MAX(C9:C16)/SOMMA(C9:C16)

Spese necessarie           =SOMMA.SE(E:E;"Necessario";C:C)
Spese voluttuarie          =SOMMA.SE(E:E;"Voluttuario";C:C)
Rapporto N/V               =Necessarie/Voluttuarie
```

---

### FOGLIO 3: TIME TRACKER

**Obiettivo:** Analizzare come si utilizza il tempo durante la giornata.

**SEZIONE A - LOG ATTIVITÀ:**

```
A          B              C          D              E
Data       Attività       Ore        Categoria      Produttivo
21/01      Studio         2,5        Formazione     Sì
21/01      Social Media   1,0        Svago          No
21/01      Lavoro         4,0        Carriera       Sì
21/01      Sport          1,0        Salute         Sì
21/01      Serie TV       2,0        Svago          No
```

**SEZIONE B - CATEGORIE TEMPO:**

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

**Formule:**

1. **Ore per categoria (settimana corrente):**
```
=SOMMA.PIÙ.SE(C:C;A:A;">="&OGGI()-GIORNO.SETTIMANA(OGGI())+1;D:D;A2)
```

2. **% Tempo produttivo:**
```
=SOMMA.SE(E:E;"Sì";C:C)/SOMMA(C:C)
```

3. **Media ore/giorno per categoria:**
```
=B2/7
```

4. **Differenza da target:**
```
=B2-E2
```

5. **Alert produttività:**
```
=SE(PercentualeProduttivo<60%;"🔴 BASSO";SE(<75%;"🟡 MEDIO";"🟢 ALTO"))
```

**SEZIONE C - ANALISI GIORNALIERA:**

```
=== OGGI: 21/01/2026 ===

Ore produttive              7,5 / 16 ore disponibili
% Produttività              47%
Valutazione                 🟡 BUONO

Attività principale         Lavoro (4 ore)
Tempo perso                 3 ore (social, TV)
Potenziale risparmio        Se riduci tempo perso del 50% → +1,5 ore produttive

=== QUESTA SETTIMANA ===

Giorni tracciati            5/7
Media produttività          52%
Trend                       ↗️ +5% vs scorsa settimana
Miglior giorno              Lunedì (8 ore produttive)
Peggior giorno              Sabato (2 ore produttive)
```

---

### FOGLIO 4: HABIT TRACKER

**Obiettivo:** Monitorare abitudini quotidiane e visualizzare progressi.

**STRUTTURA:**

```
A              B  C  D  E  F  G  H  I  J  K  L  M ... (31 giorni)
Abitudine      1  2  3  4  5  6  7  8  9 10 11 12 ...  Totale  %   Streak

Bere 2L acqua  ✓  ✓  ✓  ✗  ✓  ✓  ✓  ✓           8/10  80%   3
Meditazione    ✓  ✗  ✓  ✓  ✓  ✓  ✓  ✓           7/10  70%   5
Esercizio      ✓  ✓  ✗  ✗  ✓  ✓  ✗  ✓           5/10  50%   1
Leggere        ✓  ✓  ✓  ✓  ✓  ✓  ✓  ✓           8/10  80%   8
No junk food   ✓  ✓  ✗  ✓  ✓  ✓  ✓  ✓           7/10  70%   5
```

**Formule avanzate:**

1. **Totale completamenti:**
```
=CONTA.SE(B2:L2;"✓")
```

2. **Percentuale:**
```
=M2/CONTA.VALORI(B2:L2)
```

3. **Streak corrente (serie consecutiva):**
```
=SE(L2="✓";SE(K2="✓";[precedente]+1;1);0)
```

4. **Migliore streak del mese:**
```
=MAX([tutti gli streak della riga])
```

5. **Formattazione condizionale:**
- Verde: ✓ (completato)
- Rosso: ✗ (non completato)
- Grigio: celle future

**SEZIONE ANALISI:**

```
=== RIEPILOGO MENSILE ===

Abitudine più costante      Leggere (80%)
Abitudine da migliorare     Esercizio (50%)
Streak più lungo            Leggere (8 giorni)

Media completamento         70%
Giorni perfetti (tutti ✓)   3
Giorni critici (nessuno ✓)  0

=== OBIETTIVI ===

Target: completare almeno 4/5 abitudini al giorno
Giorni target raggiunto:    8/10 giorni
% successo:                 80%
```

**VISUALIZZAZIONE:**
Crea heatmap con formattazione condizionale:
- Verde scuro: 100% abitudini
- Verde chiaro: 75-99%
- Giallo: 50-74%
- Arancione: 25-49%
- Rosso: 0-24%

---

### FOGLIO 5: WEEKLY PLANNER

**Obiettivo:** Pianificare la settimana con to-do list intelligente.

**STRUTTURA:**

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

...
```

**Legend status:**
- ✅ Completato
- 🔄 In corso
- 📅 Pianificato
- ⏸️ In pausa
- ❌ Cancellato

**SEZIONE PRIORITÀ:**

```
=== MATRICE EISENHOWER ===

                URGENTE         NON URGENTE
IMPORTANTE      [Task lista]    [Task lista]
                FARE SUBITO     PIANIFICARE

NON IMPORTANTE  [Task lista]    [Task lista]
                DELEGARE        ELIMINARE
```

**Formule:**

1. **Task completati per giorno:**
```
=CONTA.SE($F$2:$F$50;"✅")
```

2. **Ore pianificate vs disponibili:**
```
Pianificate: =SOMMA.SE(A:A;A2;E:E)
Alert: =SE(Pianificate>12;"⚠️ SOVRACCARICO";"✅")
```

3. **Task in ritardo:**
```
=CONTA.PIÙ.SE(A:A;"<"&OGGI();F:F;"<>"&"✅")
```

4. **Distribuzione tempo per categoria:**
```
=SOMMA.SE(C:C;"Lavoro";E:E)
```

**SEZIONE ANALISI:**

```
=== QUESTA SETTIMANA ===

Task totali                 25
Completati                  18
In corso                    4
Da fare                     3

% Completamento             72%
Valutazione                 🟢 BUONA SETTIMANA

Ore pianificate totali      45
Media ore/giorno            6,4
Giorno più carico           Martedì (9 ore)

Priorità alta completata    5/6 (83%)
Priorità media completata   8/12 (67%)
Priorità bassa completata   5/7 (71%)

=== PROSSIMA SETTIMANA ===

Task riportati              3
Nuovi task da pianificare   [input manuale]
Carico previsto            [calcolo automatico]
```

---

### FUNZIONALITÀ AVANZATE E AUTOMAZIONI

**1. COLLEGAMENTI TRA FOGLI:**

Dashboard richiama automaticamente dati da tutti gli altri fogli:

```
// Budget disponibile
=BudgetMensile!B17-SOMMA(BudgetMensile!C20:C100)

// Ore produttive oggi
=SOMMA.SE(TimeTracker!A:A;OGGI();TimeTracker!C:C)

// Abitudini completate oggi
=CONTA.SE(HabitTracker!B2:B6;"✓")

// Task completati oggi
=CONTA.PIÙ.SE(WeeklyPlanner!A:A;OGGI();WeeklyPlanner!F:F;"✅")
```

**2. NOTIFICHE E ALERT:**

Crea sezione "ALERT" nella Dashboard:

```
=== ⚠️ ALERT E NOTIFICHE ===

Budget:     =SE(BudgetUtilizzato>90%;"🔴 Budget quasi esaurito!";"-")
Abitudini:  =SE(AbitudiniOggi<3;"🟡 Completa almeno 3 abitudini oggi";"-")
Task:       =SE(TaskInRitardo>0;"🔴 Hai "&TaskInRitardo&" task in ritardo";"-")
Tempo:      =SE(OreProduttiveOggi<4;"🟡 Solo "&Ore&" ore produttive oggi";"-")
```

**3. GRAFICI INTERATTIVI:**

Crea nella Dashboard:

1. **Grafico a torta:** Distribuzione budget per categoria
2. **Grafico a barre:** Ore per categoria settimanali
3. **Grafico a linee:** Trend % abitudini completate
4. **Grafico Gantt:** Task della settimana su timeline

**4. FORMATTAZIONE CONDIZIONALE:**

Applica colori automatici:

**Budget:**
- Verde: speso < 70% budget
- Giallo: speso 70-90%
- Rosso: speso > 90%

**Task:**
- Rosso: priorità alta
- Giallo: priorità media
- Verde: priorità bassa

**Abitudini:**
- Verde: ✓
- Rosso: ✗
- Grigio: non ancora

**5. VALIDAZIONE DATI:**

Imposta menu a tendina per:
- Categorie budget (elenco predefinito)
- Categorie tempo (elenco predefinito)
- Priorità task (Alta/Media/Bassa)
- Status task (elenco simboli)

---

### COMPITI DA SVOLGERE

**LIVELLO BASE (settimana 1-2):**

1. Crea il foglio Budget Mensile:
   - Inserisci 3 categorie di spesa
   - Registra almeno 10 transazioni
   - Calcola totali e rimanenti
   - Crea grafico a torta spese

2. Crea il foglio Habit Tracker:
   - Scegli 3 abitudini personali
   - Traccia per 7 giorni
   - Calcola percentuali
   - Identifica pattern

**LIVELLO INTERMEDIO (settimana 3-4):**

3. Crea il foglio Time Tracker:
   - Traccia attività per 3 giorni
   - Categorizza il tempo
   - Calcola % produttività
   - Identifica sprechi di tempo

4. Crea il foglio Weekly Planner:
   - Pianifica prossima settimana
   - Usa matrice Eisenhower
   - Calcola carico di lavoro
   - Monitora completamento

**LIVELLO AVANZATO (settimana 5-6):**

5. Crea la Dashboard:
   - Collegamenti a tutti i fogli
   - KPI automatici
   - Sistema di alert
   - Visualizzazioni grafiche

6. Implementa automazioni:
   - Formattazione condizionale
   - Validazione dati
   - Formule avanzate
   - Grafici dinamici

7. Personalizza il sistema:
   - Adatta categorie alle tue esigenze
   - Aggiungi nuovi KPI
   - Crea report mensili
   - Implementa obiettivi personali

---

### CRITERI DI VALUTAZIONE

**Completezza (30%):**
- Tutti i 5 fogli implementati
- Tutte le sezioni richieste
- Dati realistici e completi

**Formule (30%):**
- Correttezza calcoli
- Uso appropriato funzioni
- Collegamenti tra fogli
- Formule avanzate

**Automazione (20%):**
- Formattazione condizionale
- Validazione dati
- Alert automatici
- Aggiornamento dashboard

**Usabilità (10%):**
- Organizzazione chiara
- Facile da usare
- Design professionale
- Grafici efficaci

**Personalizzazione (10%):**
- Adattamento esigenze personali
- Funzionalità extra
- Creatività
- Utilità pratica

---

### ESTENSIONI E IDEE BONUS

**1. Fitness Tracker:**
- Log allenamenti
- Progressi peso
- Misurazioni corporee
- Grafici progressi

**2. Meal Planner:**
- Piano pasti settimanale
- Lista spesa automatica
- Calcolo calorie
- Rotazione ricette

**3. Learning Tracker:**
- Ore studio per materia
- Progressi competenze
- Certificazioni obiettivo
- Timeline apprendimento

**4. Social Battery:**
- Eventi sociali
- Livello energia sociale
- Bilanciamento intro/extro
- Tempo per sé

**5. Decision Tracker:**
- Decisioni importanti
- Pro/contro
- Outcome attesi vs reali
- Apprendimenti

**6. Gratitude Journal:**
- 3 gratitudini al giorno
- Highlight della giornata
- Riflessioni
- Mood tracker

**7. Book/Movie Tracker:**
- Lista libri/film
- Rating personale
- Tempo investito
- Statistiche annuali

**8. Project Tracker:**
- Progetti personali
- Milestone
- Progressi %
- Timeline

---

### 💡 RIFLESSIONI FINALI

**Perché questo esercizio è importante:**

1. **Applicazione pratica reale:** Non è un esercizio teorico, è un sistema che puoi usare davvero ogni giorno

2. **Sviluppa autodisciplina:** Tracciare dati richiede costanza, migliora l'accountability personale

3. **Data-driven decision making:** Impari a prendere decisioni basate su dati, non su sensazioni

4. **Competenze trasferibili:** Le tecniche imparate sono utili in qualsiasi lavoro

5. **Autoconsapevolezza:** Vedere i propri dati oggettivamente aiuta a identificare aree di miglioramento

**Come usare questo sistema dopo l'esercitazione:**

- Aggiorna quotidianamente (5-10 minuti)
- Rivedi settimanalmente la dashboard
- Analisi mensile approfondita
- Adatta e migliora continuamente
- Celebra i progressi!

**Testimonianze (simulate):**

> "Ho scoperto che spendevo 3 ore al giorno sui social. Ora sono 30 minuti e ho 2,5 ore in più per studiare!" - Marco, studente

> "Tracciando le abitudini ho mantenuto 87% di costanza. Prima non andavo oltre 3 giorni." - Sara, 17 anni

> "Il budget mi ha fatto risparmiare €200 al mese solo eliminando spese inutili." - Luca, studente universitario

---

### 📚 LIVELLO INTERMEDIO

#### Esercitazione 5: Gestione Magazzino con Logica

**Obiettivi:**
- Utilizzare la funzione SE
- Combinare funzioni logiche
- Gestire soglie e avvisi

**Dati di partenza:**
```
A          B          C          D              E
Prodotto   Giacenza   Minimo     Stato         Azione
Viti       150        100
Bulloni    45         50
Rondelle   200        80
Dadi       30         40
Chiodi     500        200
```

**Compiti:**
1. Nella colonna D, mostra "OK" se la giacenza >= minimo, "BASSO" altrimenti
2. Nella colonna E, mostra "RIORDINA" se lo stato è "BASSO", altrimenti lascia vuoto
3. Aggiungi una colonna F "Priorità" con:
   - "URGENTE" se giacenza < 50% del minimo
   - "NORMALE" se giacenza < minimo ma >= 50% del minimo
   - "OK" altrimenti
4. Conta quanti prodotti sono in stato "BASSO"
5. Calcola la percentuale di prodotti con giacenza sufficiente

**Formule da utilizzare:** SE, SE annidati o PIÙ.SE, CONTA.SE, CONTA.VALORI

---

#### Esercitazione 5: Analisi Vendite Mensili

**Obiettivi:**
- Utilizzare SOMMA.SE e MEDIA.SE
- Analizzare dati per categoria
- Creare report riassuntivi

**Dati di partenza:**
```
A          B          C          D
Data       Categoria  Prodotto   Importo
05/01      Elettr.    TV         450
08/01      Casa       Divano     800
12/01      Elettr.    Radio      80
15/01      Sport      Bici       350
18/01      Casa       Tavolo     250
22/01      Sport      Palla      25
25/01      Elettr.    PC         900
28/01      Casa       Lampada    45
```

**Compiti:**
1. Crea una tabella riassuntiva con:
   - Totale vendite per categoria (Elettronica, Casa, Sport)
   - Numero di vendite per categoria
   - Importo medio per categoria
2. Calcola il totale generale delle vendite
3. Trova la vendita di importo massimo
4. Conta quante vendite superano i 200€
5. Calcola la percentuale di vendite per ogni categoria sul totale

**Formule da utilizzare:** SOMMA.SE, CONTA.SE, MEDIA.SE, SOMMA, MAX

---

#### Esercitazione 7: Elaborazione Testi e Date

**Obiettivi:**
- Manipolare stringhe di testo
- Lavorare con funzioni di data
- Estrarre informazioni da codici

**Dati di partenza:**
```
A                      B              C
Codice Completo        Data Ordine    Cliente
PRD-2026-001-ROSSI     15/01/2026     Mario Rossi
PRD-2026-002-BIANCHI   18/01/2026     anna bianchi
PRD-2026-003-VERDI     20/01/2026     LUCA VERDI
PRD-2026-004-NERI      21/01/2026     giulia neri
```

**Compiti:**
1. Estrai il numero d'ordine (001, 002, ecc.) dal codice nella colonna D
2. Estrai il cognome dal codice nella colonna E
3. Nella colonna F, formatta il nome cliente con iniziali maiuscole (Mario Rossi)
4. Nella colonna G, calcola i giorni trascorsi dall'ordine
5. Nella colonna H, mostra "SOLLECITO" se sono passati più di 5 giorni
6. Crea un codice di spedizione concatenando: "SPED-" + numero ordine + "-" + prime 3 lettere cognome

**Formule da utilizzare:** STRINGA.ESTRAI, MAIUSC.INIZ, OGGI, CONCATENA o &, SE

---

### 🎯 LIVELLO AVANZATO

#### Esercitazione 7: Database Dipendenti con CERCA.VERT

**Obiettivi:**
- Utilizzare CERCA.VERT per cercare informazioni
- Creare un sistema di lookup tra tabelle
- Gestire errori con SE.ERRORE

**Dati di partenza:**

**Tabella 1 - Anagrafica Dipendenti (A:D):**
```
Codice  Nome           Reparto    Livello
D001    Marco Rossi    Vendite    3
D002    Anna Verdi     IT         4
D003    Luca Bianchi   Vendite    2
D004    Sara Neri      HR         3
D005    Paolo Gialli   IT         5
```

**Tabella 2 - Livelli Retributivi (F:G):**
```
Livello  Stipendio Base
1        1200
2        1500
3        1800
4        2200
5        2800
```

**Compiti:**
1. Crea una sezione "Calcolo Stipendi" con:
   - Colonna con codice dipendente
   - Cerca automaticamente nome, reparto e livello
   - Cerca lo stipendio base corrispondente al livello
2. Aggiungi una colonna "Bonus" che calcola:
   - 15% per reparto Vendite
   - 10% per reparto IT
   - 5% per altri reparti
3. Calcola lo stipendio totale (base + bonus)
4. Gestisci eventuali codici dipendente non trovati con SE.ERRORE
5. Calcola il costo totale del personale per reparto

**Formule da utilizzare:** CERCA.VERT, SE, SE.ERRORE, SOMMA.SE

---

#### Esercitazione 8: Dashboard Vendite Interattiva

**Obiettivi:**
- Creare un dashboard di riepilogo
- Utilizzare formule complesse combinate
- Implementare KPI (Key Performance Indicators)

**Dati di partenza:**
```
Data        Venditore  Regione  Prodotto    Quantità  Prezzo  
02/01/2026  Mario      Nord     Laptop      2         800
03/01/2026  Anna       Sud      Mouse       10        25
04/01/2026  Luca       Centro   Tastiera    5         45
05/01/2026  Mario      Nord     Monitor     3         350
06/01/2026  Sara       Sud      Laptop      1         800
...(continua con almeno 20 righe)
```

**Compiti:**
1. Crea una sezione "KPI GENERALI":
   - Totale vendite (importo)
   - Numero totale ordini
   - Valore medio ordine
   - Prodotto più venduto
   - Regione con più vendite
2. Crea una tabella "Performance Venditori":
   - Elenco venditori unici
   - Totale vendite per venditore
   - Numero ordini per venditore
   - Media per ordine
   - Ranking (1° migliore venditore, ecc.)
3. Crea una tabella "Analisi per Regione":
   - Totale vendite per regione
   - Percentuale sul totale
   - Numero ordini per regione
4. Aggiungi calcoli temporali:
   - Vendite settimanali
   - Crescita rispetto alla settimana precedente
5. Implementa un sistema di "Target":
   - Target mensile: 50.000€
   - Percentuale raggiungimento
   - Proiezione fine mese

**Formule da utilizzare:** SOMMA.SE, CONTA.SE, MEDIA.SE, MAX, CERCA.VERT, UNIQUE (Google Fogli), PERCENTUALE

---

#### Esercitazione 9: Sistema di Prenotazioni

**Obiettivi:**
- Gestire disponibilità e prenotazioni
- Utilizzare logica complessa con SE annidati
- Validazione automatica dei dati

**Dati di partenza:**

**Tabella Camere:**
```
Camera  Tipo      Posti  Prezzo/Notte
101     Singola   1      80
102     Doppia    2      120
103     Doppia    2      120
104     Suite     4      200
105     Singola   1      80
```

**Tabella Prenotazioni:**
```
ID   Camera  Check-in    Check-out   Ospiti  Nome Cliente
1    102     20/01/2026  23/01/2026  2       Mario Rossi
2    104     21/01/2026  25/01/2026  4       Anna Verdi
```

**Compiti:**
1. Nella tabella prenotazioni, aggiungi colonne:
   - Notti (calcola la differenza tra check-out e check-in)
   - Prezzo/Notte (cerca dalla tabella camere)
   - Totale prenotazione
2. Aggiungi una colonna "Validazione":
   - "OK" se numero ospiti <= posti camera
   - "ERRORE: Troppi ospiti" altrimenti
3. Crea una sezione "Disponibilità" che per ogni camera mostri:
   - Se è occupata oggi
   - Data fine occupazione
   - Stato: "Libera" o "Occupata"
4. Calcola statistiche:
   - Tasso di occupazione (% camere occupate)
   - Ricavo totale prenotazioni
   - Ricavo medio per camera
   - Camera più redditizia
5. Crea un calendario settimanale che mostri la disponibilità giornaliera

**Formule da utilizzare:** DATA.DIFF, CERCA.VERT, SE, E, O, CONTA.SE, SOMMA.SE

---

#### Esercitazione 10: Analisi Finanziaria Aziendale

**Obiettivi:**
- Creare bilancio aziendale
- Calcolare margini e KPI finanziari
- Analisi del punto di pareggio (break-even)

**Dati di partenza:**

**Costi Fissi Mensili:**
```
Voce           Importo
Affitto        2000
Stipendi       8000
Utenze         500
Assicurazioni  300
Altro          200
```

**Vendite Prodotti:**
```
Prodotto     Prezzo Vendita  Costo Unitario  Q.tà Venduta
Prodotto A   50              30              150
Prodotto B   80              45              100
Prodotto C   120             70              80
Prodotto D   35              20              200
```

**Compiti:**
1. Calcola per ogni prodotto:
   - Ricavo totale
   - Costo variabile totale
   - Margine di contribuzione unitario
   - Margine di contribuzione totale
   - Margine % sul prezzo
2. Calcola il totale:
   - Ricavi totali
   - Costi variabili totali
   - Costi fissi totali
   - Costi totali
   - Utile/Perdita
3. Calcola KPI:
   - Margine di contribuzione %
   - ROI (Return on Investment)
   - Break-even point in unità
   - Break-even point in valore
4. Crea scenari "What-if":
   - Cosa succede aumentando i prezzi del 10%?
   - Cosa succede riducendo i costi fissi del 15%?
   - Quante unità servono per raggiungere 5000€ di utile?
5. Analisi prodotti:
   - Quale prodotto è più redditizio?
   - Quale contribuisce maggiormente all'utile?
   - Quale ha il margine % migliore?

**Formule da utilizzare:** SOMMA, operatori matematici, SE, CERCA.VERT, percentuali, formule finanziarie

---

### 🏆 PROGETTO FINALE COMPLETO

#### Esercitazione 11: Sistema Gestionale E-commerce

**Obiettivi:**
- Integrare tutte le competenze acquisite
- Creare un sistema multi-foglio complesso
- Automatizzare processi aziendali

**Struttura del progetto:**

Il progetto deve includere minimo 5 fogli interconnessi:

**FOGLIO 1 - Prodotti (Catalogo):**
```
Codice  Nome           Categoria  Prezzo  Giacenza  Minimo  Fornitore
```

**FOGLIO 2 - Ordini Clienti:**
```
ID  Data  Cliente  Codice Prod  Quantità  Stato  Spedizione
```

**FOGLIO 3 - Clienti (Anagrafica):**
```
ID  Nome  Cognome  Email  Città  Sconto%  Totale Acquisti
```

**FOGLIO 4 - Dashboard:**
Riepilogo con KPI e grafici

**FOGLIO 5 - Ordini Fornitore:**
Ordini automatici da generare per prodotti sotto scorta

**Requisiti funzionali:**

1. **Gestione Ordini:**
   - Ricerca automatica prezzo prodotto
   - Calcolo totale ordine
   - Applicazione sconto cliente
   - Verifica disponibilità giacenza
   - Aggiornamento automatico giacenze
   - Stato ordine (In lavorazione, Spedito, Consegnato)

2. **Gestione Clienti:**
   - Calcolo totale storico acquisti
   - Categoria cliente (Bronzo <500€, Argento 500-1000€, Oro >1000€)
   - Sconto automatico in base alla categoria
   - Numero ordini effettuati

3. **Gestione Magazzino:**
   - Segnalazione prodotti sotto scorta minima
   - Generazione automatica ordini a fornitori
   - Valore magazzino totale
   - Rotazione prodotti (velocità vendita)

4. **Dashboard e Analisi:**
   - Totale vendite giornaliere/settimanali/mensili
   - Numero ordini per stato
   - Prodotti più venduti (Top 5)
   - Categorie più redditizie
   - Trend vendite (crescita %)
   - Clienti più importanti (Top 5 per acquisti)
   - Tasso di riordino (% prodotti sotto minimo)
   - Valore medio ordine
   - Previsione vendite prossimo mese

5. **Funzionalità Avanzate:**
   - Sistema di ricerca prodotti
   - Calcolo commissioni venditori (3% su ordini)
   - Gestione resi (stato "Reso")
   - Report spedizioni per corriere
   - Alert automatici (email da inviare)

**Formule richieste:**
- CERCA.VERT per lookup tra fogli
- SOMMA.SE e SOMMA.PIÙ.SE per aggregazioni
- SE annidati o PIÙ.SE per logica complessa
- CONTA.SE per conteggi condizionali
- Funzioni di testo per formattazione
- Funzioni di data per analisi temporali
- FILTER e QUERY (Google Fogli) per estrarre dati
- ARRAYFORMULA per applicare formule a intervalli

**Criteri di valutazione:**
1. Completezza (tutti i fogli implementati): 30%
2. Correttezza formule: 30%
3. Automazione e interconnessione fogli: 20%
4. Usabilità e presentazione: 10%
5. Funzionalità extra e creatività: 10%

**Bonus opzionali:**
- Formattazione condizionale per evidenziare dati
- Grafici interattivi nella dashboard
- Funzioni personalizzate (Google Apps Script)
- Pulsanti per azioni automatiche
- Sistema di login e permessi (simulato)

---

### 📝 Modalità di Svolgimento

#### Per gli Studenti

1. **Organizzazione:**
   - Crea un nuovo Google Foglio per ogni esercitazione
   - Rinomina il file con: "Esercitazione_X_NomeCognome"
   - Aggiungi un foglio "Note" per documentare difficoltà o domande

2. **Svolgimento:**
   - Leggi attentamente i requisiti
   - Inserisci i dati di partenza
   - Risolvi un compito alla volta
   - Testa ogni formula prima di procedere
   - Verifica i risultati per coerenza

3. **Consegna:**
   - Condividi il foglio con l'insegnante
   - Assicurati che le formule siano visibili (non solo i valori)
   - Aggiungi commenti nelle celle complesse

#### Per gli Insegnanti

1. **Assegnazione:**
   - Livello Base: settimane 1-2
   - Livello Intermedio: settimane 3-4
   - Livello Avanzato: settimane 5-7
   - Progetto Finale: settimane 8-10

2. **Supporto:**
   - Sessioni di tutoring per dubbi
   - Forum classe per domande comuni
   - Video tutorial per concetti complessi

3. **Valutazione:**
   - Esercizi base: 1 punto ciascuno
   - Esercizi intermedi: 2 punti ciascuno
   - Esercizi avanzati: 3 punti ciascuno
   - Progetto finale: 10 punti

4. **Feedback:**
   - Commenti diretti nel foglio Google
   - Evidenziare errori comuni
   - Suggerire ottimizzazioni

---

### 💡 Suggerimenti per il Successo

1. **Non aver paura di sperimentare**: Prova diverse formule, il foglio di calcolo non si rompe!

2. **Usa i riferimenti assoluti quando necessario**: Il simbolo $ è tuo amico.

3. **Testa con dati semplici**: Prima di applicare formule complesse, verifica con numeri semplici.

4. **Documenta il tuo lavoro**: Aggiungi note e commenti per ricordare la logica.

5. **Cerca aiuto**: Usa la documentazione di Google Fogli, forum e video tutorial.

6. **Pratica regolarmente**: 30 minuti al giorno sono meglio di 3 ore una volta a settimana.

7. **Impara dagli errori**: Ogni errore è un'opportunità per capire meglio.

8. **Condividi con i compagni**: Lavora in gruppo per discutere approcci diversi.

9. **Pensa prima di scrivere**: Pianifica la formula su carta prima di digitarla.

10. **Verifica sempre i risultati**: I numeri hanno senso logico?

---

