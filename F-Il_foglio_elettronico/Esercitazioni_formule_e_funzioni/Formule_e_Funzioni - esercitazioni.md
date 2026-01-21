# Guida alle Formule e Funzioni nei Fogli di Calcolo

## Esempi Pratici

### Esempio 1: Calcolo Stipendio con Bonus

```
   A           B          C                D
1  Dipendente  Stipendio  Vendite         Bonus
2  Mario       2000       150000          =SE(C2>100000;B2*0.1;0)
3  Luigi       2500       80000           =SE(C3>100000;B3*0.1;0)
4  Anna        2200       120000          =SE(C4>100000;B4*0.1;0)

// Stipendio Totale
5  TOTALE                                 =SOMMA(B2:B4)+SOMMA(D2:D4)
```

### Esempio 2: Analisi Vendite

```
   A           B          C               D
1  Prodotto    Q.tà       Prezzo         Totale
2  Mele        10         1,50           =B2*C2
3  Banane      15         2,00           =B3*C3
4  Arance      8          1,80           =B4*C4
5
6  TOTALE                                =SOMMA(D2:D4)
7  MEDIA VENDITA                         =MEDIA(D2:D4)
8  MAX VENDITA                           =MAX(D2:D4)
9  MIN VENDITA                           =MIN(D2:D4)
```

### Esempio 3: Valutazione Studenti

```
   A           B          C          D          E
1  Studente    Voto1      Voto2      Media      Risultato
2  Marco       75         82         =MEDIA(B2:C2)  =SE(D2>=60;"PROMOSSO";"BOCCIATO")
3  Sara        58         63         =MEDIA(B3:C3)  =SE(D3>=60;"PROMOSSO";"BOCCIATO")
4  Luca        90         88         =MEDIA(B4:C4)  =SE(D4>=60;"PROMOSSO";"BOCCIATO")
```

### Esempio 4: Gestione Inventario

```
   A           B          C          D              E
1  Prodotto    Stock      Minimo     Stato         Azione
2  Item A      50         20         =SE(B2<C2;"BASSO";"OK")  =SE(D2="BASSO";"RIORDINA";"")
3  Item B      15         20         =SE(B3<C3;"BASSO";"OK")  =SE(D3="BASSO";"RIORDINA";"")
4  Item C      100        50         =SE(B4<C4;"BASSO";"OK")  =SE(D4="BASSO";"RIORDINA";"")
```

### Esempio 5: Calcolo IVA e Totali

```
   A           B          C              D
1  Descrizione Imponibile IVA (22%)      Totale
2  Servizio 1  1000       =B2*0.22       =B2+C2
3  Servizio 2  1500       =B3*0.22       =B3+C3
4  Servizio 3  2000       =B4*0.22       =B4+C4
5
6  SUBTOTALE   =SOMMA(B2:B4)  =SOMMA(C2:C4)  =SOMMA(D2:D4)
```

### Esempio 6: Ricerca con CERCA.VERT

**Tabella Prezzi (A:B):**
```
   A           B
1  Codice      Prezzo
2  P001        15,00
3  P002        22,50
4  P003        18,00
```

**Fattura (D:F):**
```
   D           E                              F
1  Codice      Quantità                       Totale
2  P002        3                              =CERCA.VERT(D2;$A$2:$B$4;2;FALSO)*E2
3  P001        5                              =CERCA.VERT(D3;$A$2:$B$4;2;FALSO)*E3
```

### Esempio 7: Analisi Date

```
   A               B                      C
1  Data Ordine     Giorni Trascorsi      Stato
2  15/01/2026      =OGGI()-A2            =SE(B2>7;"RITARDO";"OK")
3  10/01/2026      =OGGI()-A3            =SE(B3>7;"RITARDO";"OK")
4  20/01/2026      =OGGI()-A4            =SE(B4>7;"RITARDO";"OK")
```

### Esempio 8: Formattazione Condizionale con Formule

**Formula per evidenziare valori sopra la media:**
```
=A1>MEDIA($A$1:$A$10)
```

**Formula per evidenziare duplicati:**
```
=CONTA.SE($A$1:$A$10;A1)>1
```

### Esempio 9: QUERY Avanzata

```
=QUERY(A1:D100;"SELECT A, SUM(C), AVG(D) WHERE B = 'Venduto' GROUP BY A ORDER BY SUM(C) DESC")
```
Questa query:
- Seleziona la colonna A
- Calcola la somma della colonna C
- Calcola la media della colonna D
- Filtra dove colonna B = "Venduto"
- Raggruppa per colonna A
- Ordina per somma decrescente

### Esempio 10: Dashboard Dinamica

```
// Contatori
=CONTA.SE(Stato;"Completato")
=CONTA.SE(Stato;"In Corso")
=CONTA.SE(Stato;"Da Fare")

// Percentuali
=CONTA.SE(Stato;"Completato")/CONTA.VALORI(Stato)

// Grafici SPARKLINE
=SPARKLINE(B2:B10;{"charttype"\"column";"color1"\"green"})
```

---


## Esercitazioni per Studenti

Questa sezione contiene esercitazioni pratiche organizzate per livello di difficoltà. Ogni esercitazione include obiettivi, dati da utilizzare e compiti da svolgere.

---

### 📚 LIVELLO BASE

#### Esercitazione 1: Primi Passi con le Formule

**Obiettivi:**
- Scrivere formule semplici con operatori aritmetici
- Utilizzare riferimenti di cella
- Creare somme e medie

**Dati di partenza:**
Crea un foglio con questi dati nella colonna A (Prodotto), B (Quantità), C (Prezzo Unitario):

```
A              B          C
Mele           50         1,50
Banane         30         2,00
Arance         40         1,80
Pere           25         2,50
Kiwi           35         3,00
```

**Compiti:**
1. Nella colonna D (Totale), calcola il totale per ogni prodotto (Quantità × Prezzo)
2. Alla fine della colonna B, calcola la quantità totale di tutti i prodotti
3. Alla fine della colonna D, calcola il valore totale di tutta la merce
4. Calcola il prezzo medio dei prodotti
5. Trova il prezzo più alto e quello più basso

**Formule da utilizzare:** Operatori base, SOMMA, MEDIA, MAX, MIN

---

#### Esercitazione 2: Gestione Registro Voti

**Obiettivi:**
- Calcolare medie
- Utilizzare funzioni statistiche
- Applicare formule a più studenti

**Dati di partenza:**
Crea una tabella con studenti e voti:

```
A          B       C       D       E
Studente   Voto1   Voto2   Voto3   Media
Marco      7       8       7
Anna       9       8       9
Luca       6       7       6
Giulia     8       9       8
Paolo      5       6       5
```

**Compiti:**
1. Calcola la media per ogni studente nella colonna E
2. Aggiungi una riga finale con:
   - Media della classe per ogni verifica
   - Media generale della classe
3. Trova il voto massimo e minimo per ogni verifica
4. Conta quanti studenti hanno media >= 7
5. Conta quanti studenti hanno media < 6

**Formule da utilizzare:** MEDIA, MAX, MIN, CONTA.SE

---

#### Esercitazione 3: Riferimenti Assoluti e Relativi

**Obiettivi:**
- Comprendere la differenza tra riferimenti relativi e assoluti
- Applicare il cambio valuta
- Usare riferimenti misti

**Dati di partenza:**
```
A              B          C (Tasso cambio: 1,10)
Prodotto       Euro       Dollari
Laptop         800
Mouse          25
Tastiera       45
Monitor        350
Webcam         80
```

**Compiti:**
1. Inserisci il tasso di cambio Euro/Dollaro in una cella (es. D1 = 1,10)
2. Nella colonna C, calcola il prezzo in dollari usando un riferimento assoluto al tasso
3. Copia la formula verso il basso per tutti i prodotti
4. Prova a cambiare il tasso di cambio e verifica che tutti i prezzi si aggiornino
5. Aggiungi una colonna D per convertire da Dollari a Sterline (tasso 0,85)

**Formule da utilizzare:** Riferimenti assoluti ($), moltiplicazione

---

### 📊 LIVELLO INTERMEDIO

#### Esercitazione 4: Gestione Magazzino con Logica

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

#### Esercitazione 6: Elaborazione Testi e Date

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

