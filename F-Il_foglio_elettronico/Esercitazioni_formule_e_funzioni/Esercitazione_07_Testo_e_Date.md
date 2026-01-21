# Esercitazione 7: Elaborazione Testi e Date

**Livello:** 📚 AVANZATO  
**Tempo stimato:** 60 minuti

---

## Obiettivi

- Manipolare stringhe di testo con funzioni avanzate
- Lavorare con funzioni di data
- Estrarre informazioni da codici strutturati
- Formattare testo automaticamente

---

## Dati di Partenza

```
A                      B              C
Codice Completo        Data Ordine    Cliente
PRD-2026-001-ROSSI     15/01/2026     Mario Rossi
PRD-2026-002-BIANCHI   18/01/2026     anna bianchi
PRD-2026-003-VERDI     20/01/2026     LUCA VERDI
PRD-2026-004-NERI      21/01/2026     giulia neri
```

---

## Compiti da Svolgere

### 1. Colonna D - Estrai Numero Ordine

Dal codice "PRD-2026-001-ROSSI", estrai "001".

**Formula in D2:**
```
=STRINGA.ESTRAI(A2;10;3)
```

**Spiegazione:**
- Inizia dalla posizione 10 (dopo "PRD-2026-")
- Estrai 3 caratteri

**Alternativa con TESTO.DIVIDI (Google Sheets):**
```
=TESTO.DIVIDI(A2;"-";3)
```
(restituisce la terza parte dopo lo split)

### 2. Colonna E - Estrai Cognome

Dal codice "PRD-2026-001-ROSSI", estrai "ROSSI".

**Formula in E2:**
```
=STRINGA.ESTRAI(A2;14;100)
```

**Spiegazione:**
- Inizia dalla posizione 14
- Estrai 100 caratteri (più che abbastanza)

**Alternativa dinamica:**
```
=DESTRA(A2;LUNGHEZZA(A2)-13)
```
(prende tutto dalla posizione 14 in poi)

### 3. Colonna F - Formatta Nome

Trasforma "anna bianchi" in "Anna Bianchi".

**Formula in F2:**
```
=MAIUSC.INIZ(C2)
```

Questa funzione mette in maiuscolo la prima lettera di ogni parola.

### 4. Colonna G - Giorni Trascorsi

Calcola quanti giorni sono passati dalla data ordine.

**Formula in G2:**
```
=OGGI()-B2
```

**Alternativa con DATA.DIFF:**
```
=DATA.DIFF(B2;OGGI();"D")
```

### 5. Colonna H - Alert Sollecito

Mostra "SOLLECITO" se sono passati più di 5 giorni.

**Formula in H2:**
```
=SE(G2>5;"SOLLECITO";"")
```

### 6. Colonna I - Codice Spedizione

Crea codice: "SPED-001-ROS"

**Formula in I2:**
```
=CONCATENA("SPED-";D2;"-";SINISTRA(E2;3))
```

**Alternativa con & (più semplice):**
```
="SPED-"&D2&"-"&SINISTRA(E2;3)
```

---

## Risultati Attesi

| Codice | Data | Cliente | Num | Cognome | Nome Form. | Giorni | Alert | Cod. Sped. |
|--------|------|---------|-----|---------|------------|--------|-------|------------|
| PRD-2026-001-ROSSI | 15/01/26 | Mario Rossi | 001 | ROSSI | Mario Rossi | X | (SOLLECITO) | SPED-001-ROS |
| PRD-2026-002-BIANCHI | 18/01/26 | anna bianchi | 002 | BIANCHI | Anna Bianchi | X | | SPED-002-BIA |
| PRD-2026-003-VERDI | 20/01/26 | LUCA VERDI | 003 | VERDI | Luca Verdi | X | | SPED-003-VER |
| PRD-2026-004-NERI | 21/01/26 | giulia neri | 004 | NERI | Giulia Neri | X | | SPED-004-NER |

*(I giorni dipendono dalla data corrente)*

---

## Funzioni di Testo Utilizzate

| Funzione | Scopo | Esempio |
|----------|-------|---------|
| `STRINGA.ESTRAI(testo;inizio;lunghezza)` | Estrae sottostringa | `=STRINGA.ESTRAI("ABCDEF";2;3)` → "BCD" |
| `SINISTRA(testo;num_car)` | Primi N caratteri | `=SINISTRA("Ciao";2)` → "Ci" |
| `DESTRA(testo;num_car)` | Ultimi N caratteri | `=DESTRA("Ciao";2)` → "ao" |
| `LUNGHEZZA(testo)` | Conta caratteri | `=LUNGHEZZA("Ciao")` → 4 |
| `MAIUSC(testo)` | Tutto maiuscolo | `=MAIUSC("ciao")` → "CIAO" |
| `MINUSC(testo)` | Tutto minuscolo | `=MINUSC("CIAO")` → "ciao" |
| `MAIUSC.INIZ(testo)` | Iniziali maiuscole | `=MAIUSC.INIZ("mario rossi")` → "Mario Rossi" |
| `CONCATENA(t1;t2;...)` | Unisce testi | `=CONCATENA("A";"B")` → "AB" |
| `&` | Operatore concatenazione | `="A"&"B"` → "AB" |

---

## Funzioni di Data Utilizzate

| Funzione | Scopo | Esempio |
|----------|-------|---------|
| `OGGI()` | Data corrente | `=OGGI()` → 21/01/2026 |
| `ADESSO()` | Data e ora corrente | `=ADESSO()` → 21/01/2026 15:30 |
| `ANNO(data)` | Estrae anno | `=ANNO(DATA(2026;1;15))` → 2026 |
| `MESE(data)` | Estrae mese | `=MESE(DATA(2026;1;15))` → 1 |
| `GIORNO(data)` | Estrae giorno | `=GIORNO(DATA(2026;1;15))` → 15 |
| `DATA(anno;mese;giorno)` | Crea data | `=DATA(2026;1;15)` → 15/01/2026 |
| `DATA.DIFF(inizio;fine;unità)` | Differenza date | `=DATA.DIFF(DATA(2026;1;1);DATA(2026;1;15);"D")` → 14 |

**Unità DATA.DIFF:**
- "D": giorni
- "M": mesi
- "Y": anni
- "MD": giorni ignorando mesi/anni
- "YM": mesi ignorando anni

---

## Sfide Avanzate

### Challenge 1: Email Automatica

Genera email aziendale: `nome.cognome@azienda.it`

**Formula:**
```
=MINUSC(SOSTITUISCI(ANNULLA.SPAZI(F2);" ";"."))&"@azienda.it"
```

**Risultato:** `mario.rossi@azienda.it`

### Challenge 2: Età da Data di Nascita

Dati:
```
Data Nascita    Età
15/03/1990
22/07/1985
10/12/2000
```

**Formula:**
```
=DATA.DIFF(A2;OGGI();"Y")
```

### Challenge 3: Codice Fiscale Parziale

Estrai prime 3 lettere cognome + prime 3 lettere nome + anno nascita:

```
Nome: Mario Rossi
Nato: 15/03/1990
```

**Formula:**
```
=MAIUSC(SINISTRA(E2;3))&MAIUSC(SINISTRA(C2;3))&ANNO(D2)
```

**Risultato:** `ROSMAR1990`

### Challenge 4: Formattazione Telefono

Trasforma "3331234567" in "+39 333 123 4567"

**Formula:**
```
="+39 "&STRINGA.ESTRAI(A2;1;3)&" "&STRINGA.ESTRAI(A2;4;3)&" "&DESTRA(A2;4)
```

---

## Casi d'Uso Reali

Queste tecniche sono utilizzate per:

- 📧 **Generazione email automatiche** da nome e cognome
- 🏷️ **Creazione codici identificativi** (ordini, prodotti, clienti)
- 📊 **Pulizia dati importati** (maiuscole/minuscole, spazi)
- 📅 **Calcolo scadenze** (giorni rimanenti, età, durata)
- 🔍 **Estrazione informazioni** da codici strutturati
- 📝 **Formattazione report** automatici

---

## Errori Comuni da Evitare

❌ **Errore 1: Posizioni sbagliate in STRINGA.ESTRAI**
```
="ABCDEF"
=STRINGA.ESTRAI(A1;1;3)  → "ABC" ✅ (parte da 1)
=STRINGA.ESTRAI(A1;0;3)  → Errore! (non esiste pos. 0)
```

❌ **Errore 2: Dimenticare di convertire formato date**
```
="15/01/2026"            → Testo, non data!
=DATA(2026;1;15)         → Data vera ✅
```

❌ **Errore 3: Spazi extra nei testi**
```
="Mario Rossi "          → Ha uno spazio alla fine
=ANNULLA.SPAZI(A1)       → Rimuove spazi extra ✅
```

---

## Funzioni Bonus

### SOSTITUISCI

Sostituisce testo dentro una stringa:
```
=SOSTITUISCI("mario.rossi@old.com";"old";"new")
```
→ "mario.rossi@new.com"

### TROVA

Trova posizione di un testo:
```
=TROVA("-";"PRD-2026-001")
```
→ 4 (posizione del primo "-")

### RIPETI

Ripete un testo N volte:
```
=RIPETI("*";5)
```
→ "*****"

---

## Prossimi Passi

- ✅ Esercitazione 8: Database Dipendenti con CERCA.VERT
- 📚 Approfondisci: Espressioni regolari (REGEX in Google Sheets)
- 💡 Esplora: Funzioni di data avanzate (GIORNO.LAVORATIVO, FINE.MESE)

---

*Tempo medio di completamento: 50-60 minuti*  
*Difficoltà: ⭐⭐⭐⭐ (4/5)*  
*Concetto chiave: Manipolazione dati testuali e temporali*
