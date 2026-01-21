# Esercitazione 8: Database Dipendenti con CERCA.VERT

**Livello:** 🎯 AVANZATO  
**Tempo stimato:** 70 minuti

---

## Obiettivi

- Utilizzare CERCA.VERT per cercare informazioni tra tabelle
- Creare sistemi di lookup automatici
- Gestire errori con SE.ERRORE
- Collegare dati da tabelle multiple

---

## Concetto Teorico: CERCA.VERT

**CERCA.VERT** (o VLOOKUP in inglese) cerca un valore nella prima colonna di una tabella e restituisce un valore dalla stessa riga in una colonna specificata.

**Sintassi:**
```
=CERCA.VERT(valore_cercato; intervallo_tabella; numero_colonna; [corrispondenza_esatta])
```

**Parametri:**
1. **valore_cercato**: Il valore da cercare (es. codice dipendente)
2. **intervallo_tabella**: La tabella dove cercare (es. A2:D10)
3. **numero_colonna**: Quale colonna restituire (1=prima, 2=seconda, ecc.)
4. **corrispondenza_esatta**: FALSO (o 0) per corrispondenza esatta, VERO (o 1) per approssimata

**Esempio:**
```
=CERCA.VERT("D001";A2:D6;2;FALSO)
```
Cerca "D001" nella colonna A e restituisce il valore dalla colonna 2 (colonna B).

---

## Dati di Partenza

### Tabella 1 - Anagrafica Dipendenti (A1:D6)

```
A       B              C          D
Codice  Nome           Reparto    Livello
D001    Marco Rossi    Vendite    3
D002    Anna Verdi     IT         4
D003    Luca Bianchi   Vendite    2
D004    Sara Neri      HR         3
D005    Paolo Gialli   IT         5
```

### Tabella 2 - Livelli Retributivi (F1:G6)

```
F        G
Livello  Stipendio Base
1        1200
2        1500
3        1800
4        2200
5        2800
```

---

## Compiti da Svolgere

### PARTE 1: Calcolo Stipendi

Crea una sezione "Calcolo Stipendi" (inizia da colonna I):

```
I       J       K        L           M            N            O
Codice  Nome    Reparto  Livello    Stip.Base    Bonus        Totale
D001
D002
D003
D004
D005
```

**1. Colonna J - Nome (J2):**
```
=CERCA.VERT(I2;$A$2:$D$6;2;FALSO)
```

**2. Colonna K - Reparto (K2):**
```
=CERCA.VERT(I2;$A$2:$D$6;3;FALSO)
```

**3. Colonna L - Livello (L2):**
```
=CERCA.VERT(I2;$A$2:$D$6;4;FALSO)
```

**4. Colonna M - Stipendio Base (M2):**
```
=CERCA.VERT(L2;$F$2:$G$6;2;FALSO)
```

**5. Colonna N - Bonus (N2):**
Calcola bonus in base al reparto:
- Vendite: 15%
- IT: 10%
- Altri: 5%

```
=SE(K2="Vendite";M2*0,15;SE(K2="IT";M2*0,10;M2*0,05))
```

**6. Colonna O - Stipendio Totale (O2):**
```
=M2+N2
```

**Copia tutte le formule da riga 2 a riga 6.**

---

### PARTE 2: Gestione Errori

**Problema:** Se inserisci un codice dipendente inesistente (es. "D999"), CERCA.VERT restituisce #N/D (errore).

**Soluzione:** Usa SE.ERRORE per gestire l'errore.

**Formula migliorata per Nome (J2):**
```
=SE.ERRORE(CERCA.VERT(I2;$A$2:$D$6;2;FALSO);"Codice non trovato")
```

Applica SE.ERRORE a tutte le colonne che usano CERCA.VERT.

**Test:** Inserisci "D999" in I7 e verifica che mostri "Codice non trovato".

---

### PARTE 3: Analisi per Reparto

Crea tabella riassuntiva (inizia da Q1):

```
Q                    R
Reparto              Costo Totale
Vendite              [formula]
IT                   [formula]
HR                   [formula]

TOTALE GENERALE      [formula]
```

**Formule:**

**Costo Vendite (R2):**
```
=SOMMA.SE(K2:K6;"Vendite";O2:O6)
```

**Costo IT (R3):**
```
=SOMMA.SE(K2:K6;"IT";O2:O6)
```

**Costo HR (R4):**
```
=SOMMA.SE(K2:K6;"HR";O2:O6)
```

**Totale Generale (R6):**
```
=SOMMA(R2:R4)
```

---

## Risultati Attesi

### Tabella Stipendi

| Codice | Nome | Reparto | Livello | Stip.Base | Bonus | Totale |
|--------|------|---------|---------|-----------|-------|--------|
| D001 | Marco Rossi | Vendite | 3 | 1800 | 270 | 2070 |
| D002 | Anna Verdi | IT | 4 | 2200 | 220 | 2420 |
| D003 | Luca Bianchi | Vendite | 2 | 1500 | 225 | 1725 |
| D004 | Sara Neri | HR | 3 | 1800 | 90 | 1890 |
| D005 | Paolo Gialli | IT | 5 | 2800 | 280 | 3080 |

### Costi per Reparto

| Reparto | Costo Totale |
|---------|--------------|
| Vendite | 3.795 € |
| IT | 5.500 € |
| HR | 1.890 € |
| **TOTALE** | **11.185 €** |

---

## Sfide Avanzate

### Challenge 1: Livello Carriera

Aggiungi colonna P "Descrizione Livello":
- Livello 1-2: "Junior"
- Livello 3-4: "Senior"
- Livello 5: "Manager"

**Formula:**
```
=SE(L2<=2;"Junior";SE(L2<=4;"Senior";"Manager"))
```

### Challenge 2: Aumento Automatico

Crea colonna Q "Nuovo Stipendio" con aumento del:
- 10% per livello 1-2
- 5% per livello 3-4
- 3% per livello 5

**Formula:**
```
=SE(L2<=2;O2*1,10;SE(L2<=4;O2*1,05;O2*1,03))
```

### Challenge 3: Ricerca Bidirezionale

Aggiungi funzionalità per cercare dipendente per nome (non solo codice).

**Usa CONFRONTA + INDICE invece di CERCA.VERT:**
```
=INDICE($A$2:$A$6;CONFRONTA("Marco Rossi";$B$2:$B$6;0))
```
Restituisce il codice del dipendente cercando per nome.

### Challenge 4: Tabella Dinamica

Crea conteggio dipendenti per livello:

```
Livello  Numero Dipendenti
1        [formula]
2        [formula]
3        [formula]
4        [formula]
5        [formula]
```

**Formula:**
```
=CONTA.SE($L$2:$L$6;1)
```

---

## Confronto CERCA.VERT vs Altre Funzioni

### CERCA.VERT
**Pro:**
- Semplice da usare
- Intuitivo
- Sufficiente per la maggior parte dei casi

**Contro:**
- Cerca solo verso destra (colonne successive)
- Numero colonna fisso (problemi se aggiungi colonne)
- Meno flessibile

### INDICE + CONFRONTA
**Pro:**
- Più flessibile (cerca in ogni direzione)
- Indipendente da posizione colonne
- Più veloce su grandi dataset

**Contro:**
- Sintassi più complessa
- Richiede due funzioni

**Esempio equivalente:**
```
CERCA.VERT:     =CERCA.VERT(I2;$A$2:$D$6;2;FALSO)
INDICE+CONF:    =INDICE($B$2:$B$6;CONFRONTA(I2;$A$2:$A$6;0))
```

### CERCA.X (Excel 365/Google Sheets moderni)
Evoluzione moderna di CERCA.VERT:
```
=CERCA.X(valore;array_ricerca;array_restituzione)
```

---

## Errori Comuni da Evitare

❌ **Errore 1: Dimenticare $**
```
=CERCA.VERT(I2;A2:D6;2;FALSO)  ❌ Copiando cambia il riferimento!
=CERCA.VERT(I2;$A$2:$D$6;2;FALSO)  ✅ Riferimento fisso
```

❌ **Errore 2: Numero colonna sbagliato**
```
Tabella: A=Cod, B=Nome, C=Rep, D=Livello
=CERCA.VERT(I2;$A$2:$D$6;5;FALSO)  ❌ Colonna 5 non esiste!
```

❌ **Errore 3: Corrispondenza VERO invece di FALSO**
```
=CERCA.VERT(I2;$A$2:$D$6;2;VERO)  ❌ Cerca approssimata!
=CERCA.VERT(I2;$A$2:$D$6;2;FALSO)  ✅ Cerca esatta
```

❌ **Errore 4: Valore cercato non in prima colonna**
```
Se cerchi il Nome (colonna B), CERCA.VERT non funziona!
Devi usare INDICE+CONFRONTA
```

---

## Casi d'Uso Reali

CERCA.VERT è usato per:

- 💼 **HR:** Calcolo stipendi, benefit, gestione ferie
- 📦 **Magazzino:** Prezzi prodotti, giacenze, fornitori
- 🏦 **Finanza:** Tassi cambio, commissioni, categorie spese
- 🎓 **Scuola:** Calcolo voti, assenze, medie
- 🛒 **E-commerce:** Catalogo prodotti, sconti, spedizioni
- 📊 **Reporting:** Aggregazione dati da fonti multiple

---

## Prossimi Passi

- ✅ Esercitazione 9: Dashboard Vendite Interattiva
- 📚 Approfondisci: CERCA.X, INDICE, CONFRONTA
- 💡 Esplora: Query e Filter (Google Sheets)

---

*Tempo medio di completamento: 60-70 minuti*  
*Difficoltà: ⭐⭐⭐⭐ (4/5)*  
*Concetto chiave: Lookup e relazioni tra tabelle*
