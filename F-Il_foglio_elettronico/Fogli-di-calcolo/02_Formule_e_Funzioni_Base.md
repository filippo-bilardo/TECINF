# Modulo 2: Formule e Funzioni Base

## 2.1 Operatori Aritmetici

### Introduzione
Le formule in Google Fogli iniziano sempre con il simbolo `=`. Gli operatori aritmetici permettono di eseguire calcoli matematici base.

### Operatori disponibili
- **Addizione (+)**: `=A1+B1` somma i valori delle celle A1 e B1
- **Sottrazione (-)**: `=A1-B1` sottrae B1 da A1
- **Moltiplicazione (*)**: `=A1*B1` moltiplica A1 per B1
- **Divisione (/)**: `=A1/B1` divide A1 per B1
- **Elevamento a potenza (^)**: `=A1^2` eleva A1 al quadrato
- **Percentuale (%)**: `=A1*10%` calcola il 10% di A1

### Ordine delle operazioni
Google Fogli segue l'ordine matematico standard (PEMDAS):
1. Parentesi
2. Esponenti
3. Moltiplicazione e Divisione (da sinistra a destra)
4. Addizione e Sottrazione (da sinistra a destra)

**Esempio**:
```
=5+3*2       → Risultato: 11 (prima 3*2=6, poi 5+6=11)
=(5+3)*2     → Risultato: 16 (prima 5+3=8, poi 8*2=16)
```

### Esercizi pratici
1. Calcolare il totale di una spesa: `=10+15+20+5`
2. Calcolare il prezzo scontato: `=100-(100*20%)`
3. Calcolare l'area di un rettangolo: `=base*altezza`

---

## 2.2 Riferimenti di Cella

### Riferimenti Relativi
Quando copi una formula, i riferimenti si adattano automaticamente.

**Esempio**:
- Formula in C1: `=A1+B1`
- Copiata in C2 diventa: `=A2+B2`
- Copiata in C3 diventa: `=A3+B3`

### Riferimenti Assoluti
Usa il simbolo `$` per bloccare riga e/o colonna. I riferimenti assoluti non cambiano quando copi la formula.

**Sintassi**:
- `$A$1` - Blocca sia colonna che riga
- `$A1` - Blocca solo la colonna
- `A$1` - Blocca solo la riga

**Esempio pratico**: Calcolo con IVA
```
     A          B           C
1   Prezzo     IVA(22%)    Totale
2   100        0,22        =A2+(A2*$B$1)
3   200        0,22        =A3+(A3*$B$1)
```
Copiando la formula da C2 a C3, `$B$1` rimane fisso.

### Riferimenti a intervalli
- `A1:A10` - Intervallo verticale (colonna A, righe 1-10)
- `A1:C1` - Intervallo orizzontale (riga 1, colonne A-C)
- `A1:C10` - Intervallo rettangolare (blocco di celle)

### Tasti rapidi
- **F4**: Cicla tra i tipi di riferimento (relativo → assoluto → misto)

---

## 2.3 Funzioni Matematiche Base

### SOMMA
Somma un intervallo di celle.

**Sintassi**: `=SOMMA(intervallo)`

**Esempi**:
```
=SOMMA(A1:A10)           → Somma le celle da A1 a A10
=SOMMA(A1:A5, C1:C5)     → Somma due intervalli separati
=SOMMA(A1, B1, C1, 100)  → Somma celle e valori diretti
```

**Casi d'uso**:
- Totale vendite mensili
- Somma spese
- Calcolo subtotali

### MEDIA
Calcola la media aritmetica di un intervallo.

**Sintassi**: `=MEDIA(intervallo)`

**Esempi**:
```
=MEDIA(A1:A10)           → Media dei valori da A1 a A10
=MEDIA(A1:A5, C1:C5)     → Media di due intervalli
```

**Nota**: La funzione MEDIA ignora automaticamente le celle vuote e quelle con testo.

### MIN
Trova il valore minimo in un intervallo.

**Sintassi**: `=MIN(intervallo)`

**Esempi**:
```
=MIN(A1:A10)             → Valore minimo nell'intervallo
=MIN(A1:A10, B1:B10)     → Minimo tra due intervalli
```

**Casi d'uso**:
- Temperatura minima registrata
- Prezzo più basso
- Punteggio minimo

### MAX
Trova il valore massimo in un intervallo.

**Sintassi**: `=MAX(intervallo)`

**Esempi**:
```
=MAX(A1:A10)             → Valore massimo nell'intervallo
=MAX(A1:A10, B1:B10)     → Massimo tra due intervalli
```

### Altre funzioni matematiche utili
- `ARROTONDA(numero; decimali)` - Arrotonda a n decimali
  - Esempio: `=ARROTONDA(3,14159; 2)` → 3,14
- `ARROTONDA.PER.DIF(numero; multiplo)` - Arrotonda al multiplo specificato
  - Esempio: `=ARROTONDA.PER.DIF(23; 5)` → 25
- `RADQ(numero)` - Radice quadrata
  - Esempio: `=RADQ(16)` → 4
- `POTENZA(base; esponente)` - Elevamento a potenza
  - Esempio: `=POTENZA(2; 3)` → 8
- `ABS(numero)` - Valore assoluto
  - Esempio: `=ABS(-10)` → 10

---

## 2.4 Funzioni di Conteggio

### CONTA.NUMERI
Conta solo le celle che contengono numeri.

**Sintassi**: `=CONTA.NUMERI(intervallo)`

**Esempi**:
```
=CONTA.NUMERI(A1:A10)    → Conta quante celle contengono numeri
```

**Risultato con dati misti**:
```
A1: 10        → Contato
A2: Testo     → Ignorato
A3: 20        → Contato
A4: (vuota)   → Ignorato
Risultato: 2
```

### CONTA.VALORI
Conta le celle non vuote (numeri, testo, date, valori logici).

**Sintassi**: `=CONTA.VALORI(intervallo)`

**Esempi**:
```
=CONTA.VALORI(A1:A10)    → Conta tutte le celle non vuote
```

**Differenza tra CONTA.NUMERI e CONTA.VALORI**:
```
     A              CONTA.NUMERI    CONTA.VALORI
1    100            1               1
2    Testo          0               1
3    15/03/2026     1               1
4    (vuota)        0               0
5    VERO           0               1
```

### CONTA.VUOTE
Conta le celle vuote in un intervallo.

**Sintassi**: `=CONTA.VUOTE(intervallo)`

**Esempio**:
```
=CONTA.VUOTE(A1:A10)     → Conta quante celle sono vuote
```

### CONTA.SE
Conta le celle che soddisfano un criterio specifico.

**Sintassi**: `=CONTA.SE(intervallo; criterio)`

**Esempi**:
```
=CONTA.SE(A1:A10; ">50")         → Conta valori maggiori di 50
=CONTA.SE(A1:A10; "Completato")  → Conta celle con testo "Completato"
=CONTA.SE(A1:A10; ">=100")       → Conta valori >= 100
=CONTA.SE(A1:A10; "<>0")         → Conta valori diversi da 0
=CONTA.SE(A1:A10; A1)            → Conta celle uguali ad A1
```

**Criteri disponibili**:
- `"=valore"` - Uguale a
- `">valore"` - Maggiore di
- `"<valore"` - Minore di
- `">=valore"` - Maggiore o uguale
- `"<=valore"` - Minore o uguale
- `"<>valore"` - Diverso da
- `"*testo*"` - Contiene testo (usa i caratteri jolly)

**Casi d'uso pratici**:
- Contare quanti prodotti hanno prezzo superiore a 100€
- Contare quanti compiti sono stati completati
- Contare quante vendite superano l'obiettivo

---

## 2.5 Funzione SE (Condizioni Semplici)

### Introduzione
La funzione SE permette di eseguire test logici e restituire valori diversi in base al risultato.

**Sintassi**: `=SE(test; valore_se_vero; valore_se_falso)`

### Componenti
1. **test**: Condizione da verificare (restituisce VERO o FALSO)
2. **valore_se_vero**: Valore restituito se il test è vero
3. **valore_se_falso**: Valore restituito se il test è falso

### Esempi base
```
=SE(A1>10; "Alto"; "Basso")
→ Se A1 è maggiore di 10, mostra "Alto", altrimenti "Basso"

=SE(B1="Pagato"; "OK"; "Da incassare")
→ Se B1 contiene "Pagato", mostra "OK", altrimenti "Da incassare"

=SE(C1>=18; "Maggiorenne"; "Minorenne")
→ Verifica la maggiore età
```

### Operatori di confronto
- `=` - Uguale
- `>` - Maggiore di
- `<` - Minore di
- `>=` - Maggiore o uguale
- `<=` - Minore o uguale
- `<>` - Diverso da

### SE annidati (condizioni multiple)
Puoi inserire una funzione SE dentro un'altra per gestire più condizioni.

**Esempio**: Voti scolastici
```
=SE(A1>=90; "Ottimo"; SE(A1>=70; "Buono"; SE(A1>=60; "Sufficiente"; "Insufficiente")))
```

**Spiegazione**:
- Se voto ≥ 90 → Ottimo
- Altrimenti, se voto ≥ 70 → Buono
- Altrimenti, se voto ≥ 60 → Sufficiente
- Altrimenti → Insufficiente

### SE con calcoli
Puoi usare calcoli sia nel test che nei risultati.

**Esempi**:
```
=SE(A1*B1>1000; A1*B1*0,9; A1*B1)
→ Applica uno sconto del 10% se il totale supera 1000

=SE(B1<>0; A1/B1; "Errore divisione")
→ Evita la divisione per zero

=SE(MEDIA(A1:A10)>=6; "Promosso"; "Bocciato")
→ Usa la media per decidere
```

### Casi d'uso pratici
1. **Controllo stock**: `=SE(A1<10; "Riordinare"; "OK")`
2. **Calcolo commissioni**: `=SE(B1>5000; B1*0,05; B1*0,03)`
3. **Verifica scadenze**: `=SE(A1<OGGI(); "Scaduto"; "Valido")`
4. **Calcolo bonus**: `=SE(Vendite>=Obiettivo; Stipendio*1,1; Stipendio)`

---

## 2.6 Gestione Errori Comuni nelle Formule

### Tipi di errori

#### #DIV/0!
**Significato**: Divisione per zero

**Cause**:
- Divisione per una cella vuota
- Divisione per zero esplicito

**Esempio**:
```
=A1/B1  dove B1 è vuoto o contiene 0
```

**Soluzione**:
```
=SE(B1=0; "N/D"; A1/B1)
oppure
=SE.ERRORE(A1/B1; "N/D")
```

#### #VALORE!
**Significato**: Tipo di dato errato

**Cause**:
- Operazione matematica su testo
- Formato non riconosciuto

**Esempio**:
```
=A1+B1  dove A1 contiene "Testo"
```

**Soluzione**:
- Verificare che le celle contengano numeri
- Usare VAL() per convertire testo in numero: `=VAL(A1)+B1`

#### #RIF!
**Significato**: Riferimento non valido

**Cause**:
- Celle referenziate eliminate
- Riferimenti a celle inesistenti

**Esempio**:
```
=A1+B1  dove la colonna B è stata eliminata
```

**Soluzione**:
- Verificare i riferimenti delle celle
- Ripristinare le celle eliminate o aggiornare la formula

#### #NOME?
**Significato**: Nome funzione non riconosciuto

**Cause**:
- Errore di battitura nel nome della funzione
- Uso di una funzione non esistente

**Esempio**:
```
=SOMA(A1:A10)  invece di =SOMMA(A1:A10)
```

**Soluzione**:
- Controllare l'ortografia della funzione
- Verificare che la funzione esista in Google Fogli

#### #N/D
**Significato**: Valore non disponibile

**Cause**:
- Valore non trovato in una ricerca (CERCA.VERT)
- Celle vuote in calcoli specifici

**Esempio**:
```
=CERCA.VERT("Rossi"; A1:B10; 2; FALSO)  → "Rossi" non trovato
```

**Soluzione**:
```
=SE.ERRORE(CERCA.VERT("Rossi"; A1:B10; 2; FALSO); "Non trovato")
```

#### #NUM!
**Significato**: Problema numerico

**Cause**:
- Numero troppo grande o troppo piccolo
- Calcolo impossibile (es. radice quadrata di numero negativo)

**Esempio**:
```
=RADQ(-4)  → Errore #NUM!
```

### Funzione SE.ERRORE
La funzione SE.ERRORE gestisce tutti gli errori in modo elegante.

**Sintassi**: `=SE.ERRORE(formula; valore_se_errore)`

**Esempi**:
```
=SE.ERRORE(A1/B1; 0)
→ Se c'è un errore, mostra 0

=SE.ERRORE(CERCA.VERT(A1; Tabella; 2; FALSO); "Non trovato")
→ Gestisce errori di ricerca

=SE.ERRORE(A1+B1; "Verifica i dati")
→ Messaggio personalizzato in caso di errore
```

### Best practices
1. **Prevenire è meglio che curare**: Usa SE per controllare le condizioni prima di calcolare
2. **Messaggi chiari**: Usa SE.ERRORE con messaggi descrittivi
3. **Verifica dati**: Controlla che i dati di input siano del tipo corretto
4. **Riferimenti corretti**: Usa riferimenti assoluti quando necessario
5. **Test formule**: Prova le formule con diversi scenari, inclusi casi limite

### Esercizio di riepilogo
Crea una formula che:
- Divide A1 per B1
- Gestisce la divisione per zero
- Arrotonda il risultato a 2 decimali
- Mostra "Errore" se ci sono problemi

**Soluzione**:
```
=SE.ERRORE(ARROTONDA(A1/B1; 2); "Errore")
```

---

## Riepilogo Modulo 2

### Concetti chiave appresi
✓ Operatori aritmetici e ordine delle operazioni  
✓ Differenza tra riferimenti relativi e assoluti  
✓ Funzioni matematiche base (SOMMA, MEDIA, MIN, MAX)  
✓ Funzioni di conteggio (CONTA.NUMERI, CONTA.VALORI, CONTA.SE)  
✓ Logica condizionale con la funzione SE  
✓ Gestione e prevenzione degli errori  

### Formule essenziali da ricordare
```
=SOMMA(A1:A10)
=MEDIA(A1:A10)
=CONTA.SE(A1:A10; ">50")
=SE(A1>10; "Alto"; "Basso")
=SE.ERRORE(A1/B1; 0)
```

### Prossimi passi
Nel Modulo 3 esploreremo la formattazione avanzata per rendere i fogli più leggibili e professionali.
