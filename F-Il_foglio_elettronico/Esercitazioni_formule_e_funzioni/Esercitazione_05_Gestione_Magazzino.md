# Esercitazione 5: Gestione Magazzino con Logica

**Livello:** 📚 INTERMEDIO  
**Tempo stimato:** 50 minuti

---

## Obiettivi

- Utilizzare la funzione SE per decisioni logiche
- Combinare funzioni logiche (SE annidati, PIÙ.SE)
- Gestire soglie e avvisi automatici
- Creare sistemi di alert intelligenti

---

## Scenario

Gestisci un magazzino di ferramenta e devi creare un sistema che monitori automaticamente la giacenza, segnali quando è necessario riordinare prodotti e stabilisca le priorità di riordino.

---

## Dati di Partenza

```
A          B          C          D              E
Prodotto   Giacenza   Minimo     Stato         Azione
Viti       150        100
Bulloni    45         50
Rondelle   200        80
Dadi       30         40
Chiodi     500        200
```

---

## Compiti da Svolgere

### 1. Colonna D - Stato Giacenza

Mostra "OK" se la giacenza >= minimo, "BASSO" altrimenti.

**Formula in D2:**
```
=SE(B2>=C2;"OK";"BASSO")
```

Copia la formula da D2 a D6.

### 2. Colonna E - Azione Richiesta

Mostra "RIORDINA" se lo stato è "BASSO", altrimenti lascia vuoto ("").

**Formula in E2:**
```
=SE(D2="BASSO";"RIORDINA";"")
```

Copia la formula da E2 a E6.

### 3. Colonna F - Priorità Riordino

Logica più complessa con SE annidati:

**Criteri:**
- "URGENTE": se giacenza < 50% del minimo
- "NORMALE": se giacenza < minimo ma >= 50% del minimo
- "OK": altrimenti

**Formula in F2:**
```
=SE(B2<C2*0,5;"URGENTE";SE(B2<C2;"NORMALE";"OK"))
```

**Spiegazione passo-passo:**
1. Prima verifica: `B2<C2*0,5` → Giacenza sotto il 50% del minimo? → URGENTE
2. Se no, seconda verifica: `B2<C2` → Giacenza sotto il minimo? → NORMALE
3. Se no → OK

Copia la formula da F2 a F6.

### 4. Conta Prodotti in Stato "BASSO"

In una cella separata (es. H2):
```
=CONTA.SE(D2:D6;"BASSO")
```

### 5. Percentuale Prodotti con Giacenza Sufficiente

In una cella separata (es. H3):
```
=CONTA.SE(D2:D6;"OK")/CONTA.VALORI(D2:D6)*100
```

---

## Risultati Attesi

| Prodotto | Giacenza | Minimo | Stato | Azione | Priorità |
|----------|----------|--------|-------|--------|----------|
| Viti | 150 | 100 | OK | | OK |
| Bulloni | 45 | 50 | BASSO | RIORDINA | NORMALE |
| Rondelle | 200 | 80 | OK | | OK |
| Dadi | 30 | 40 | BASSO | RIORDINA | NORMALE |
| Chiodi | 500 | 200 | OK | | OK |

**Statistiche:**
- Prodotti in stato "BASSO": **2** (Bulloni, Dadi)
- % Giacenza sufficiente: **60%** (3 OK su 5 totali)

---

## Sfide Avanzate

### Challenge 1: Quantità da Ordinare

Aggiungi colonna G "Quantità Ordine":
- Se priorità "URGENTE": ordina 2 × minimo
- Se priorità "NORMALE": ordina 1 × minimo
- Se priorità "OK": 0

**Formula:**
```
=SE(F2="URGENTE";C2*2;SE(F2="NORMALE";C2;0))
```

### Challenge 2: Costo Totale Riordino

Aggiungi colonna H "Costo Unitario" con prezzi per ogni prodotto, poi:
- Colonna I "Costo Totale": `=G2*H2`
- Somma totale: `=SOMMA(I2:I6)`

### Challenge 3: Alerta Multipli

Aggiungi colonna J "Avviso Speciale":
- "⚠️ CRITICO" se giacenza = 0
- "❌ ESAURITO" se giacenza < 10 unità
- "🟡 ATTENZIONE" se giacenza < 30% minimo
- Altrimenti vuoto

**Formula (complessa):**
```
=SE(B2=0;"⚠️ CRITICO";SE(B2<10;"❌ ESAURITO";SE(B2<C2*0,3;"🟡 ATTENZIONE";"")))
```

### Challenge 4: Formattazione Condizionale

Applica colori automatici:
- Rosso: Stato "BASSO"
- Verde: Stato "OK"
- Giallo: Priorità "NORMALE"
- Rosso scuro: Priorità "URGENTE"

---

## Funzioni Utilizzate

| Funzione | Scopo | Esempio |
|----------|-------|---------|
| `SE()` | Decisione if-then-else | `=SE(B2<C2;"BASSO";"OK")` |
| `SE annidati` | Decisioni multiple | `=SE(X;"A";SE(Y;"B";"C"))` |
| `CONTA.SE()` | Conta celle con criterio | `=CONTA.SE(D:D;"BASSO")` |
| `CONTA.VALORI()` | Conta celle non vuote | `=CONTA.VALORI(A:A)` |

---

## Alternativa Moderna: PIÙ.SE

Invece di SE annidati, puoi usare PIÙ.SE (Google Sheets) o IFS (Excel 2019+):

```
=PIÙ.SE(
  B2<C2*0,5;"URGENTE";
  B2<C2;"NORMALE";
  VERO;"OK"
)
```

**Vantaggi:**
- Più leggibile
- Meno parentesi
- Più facile da modificare

---

## Approfondimento Teorico: Logica Booleana

### Operatori di Confronto

| Operatore | Significato | Esempio | Risultato |
|-----------|-------------|---------|-----------|
| `=` | Uguale | `5=5` | VERO |
| `<>` | Diverso | `5<>3` | VERO |
| `>` | Maggiore | `5>3` | VERO |
| `<` | Minore | `5<3` | FALSO |
| `>=` | Maggiore o uguale | `5>=5` | VERO |
| `<=` | Minore o uguale | `5<=3` | FALSO |

### Operatori Logici

**E() - AND:**
Tutte le condizioni devono essere vere:
```
=SE(E(B2<50; C2="Urgente"); "ALERT"; "OK")
```

**O() - OR:**
Almeno una condizione deve essere vera:
```
=SE(O(B2=0; B2<10); "RIORDINA"; "OK")
```

**NON() - NOT:**
Inverte il risultato:
```
=SE(NON(B2>=C2); "BASSO"; "OK")
```

---

## Casi d'Uso Reali

Questo tipo di logica si usa per:

- 📦 **Gestione inventario** (come questa esercitazione)
- 💰 **Controllo budget** (alert se spese > budget)
- 📊 **Valutazione performance** (classificazione voti)
- ⚠️ **Sistemi di allarme** (monitoraggio temperatura, pressione, ecc.)
- 📈 **Analisi vendite** (obiettivi raggiunti/mancati)
- 🎯 **Gestione progetti** (task in ritardo, milestone)

---

## Errori Comuni da Evitare

❌ **Errore 1: Parentesi sbilanciate**
```
=SE(B2<C2;"BASSO";"OK"  ❌ Manca )
```

❌ **Errore 2: Troppi SE annidati (>7)**
```
=SE(...SE(...SE(...  ❌ Difficile da leggere
```
✅ Usa PIÙ.SE o tabelle di lookup

❌ **Errore 3: Confondere virgola e punto e virgola**
```
=SE(B2<C2,"BASSO","OK")  ❌ In alcune versioni
```
✅ Verifica la sintassi della tua versione

---

## Prossimi Passi

- ✅ Esercitazione 6: Calcolo Fabbisogno Calorico
- 📚 Approfondisci: Funzioni logiche avanzate (SOMMA.SE, MEDIA.SE)
- 💡 Esplora: Formattazione condizionale con formule

---

*Tempo medio di completamento: 40-50 minuti*  
*Difficoltà: ⭐⭐⭐ (3/5)*  
*Concetto chiave: Logica condizionale e automazione decisioni*
