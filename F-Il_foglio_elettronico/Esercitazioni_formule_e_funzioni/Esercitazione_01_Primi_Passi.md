# Esercitazione 1: Primi Passi con le Formule

**Livello:** 📚 BASE  
**Tempo stimato:** 30 minuti

---

## Obiettivi

- Scrivere formule semplici con operatori aritmetici
- Utilizzare riferimenti di cella
- Creare somme e medie
- Familiarizzare con le funzioni base

---

## Dati di Partenza

Crea un foglio con questi dati nella colonna A (Prodotto), B (Quantità), C (Prezzo Unitario):

```
   A              B          C
1  Prodotto       Quantità   Prezzo Unitario
2  Mele           50         1,50
3  Banane         30         2,00
4  Arance         40         1,80
5  Pere           25         2,50
6  Kiwi           35         3,00
```

---

## Compiti da Svolgere

### 1. Calcolo Totale per Prodotto
Nella colonna D (Totale), calcola il totale per ogni prodotto (Quantità × Prezzo)

**Formula in D2:**
```
=B2*C2
```

Copia la formula verso il basso fino a D6.

### 2. Quantità Totale
Alla fine della colonna B (cella B7), calcola la quantità totale di tutti i prodotti.

**Formula in B7:**
```
=SOMMA(B2:B6)
```

### 3. Valore Totale Merce
Alla fine della colonna D (cella D7), calcola il valore totale di tutta la merce.

**Formula in D7:**
```
=SOMMA(D2:D6)
```

**Alternativa:**
```
=SOMMA.PIÙ(B2:B6;C2:C6)
```

### 4. Prezzo Medio
Calcola il prezzo medio dei prodotti (ad esempio in cella C8).

**Formula in C8:**
```
=MEDIA(C2:C6)
```

### 5. Prezzo Massimo e Minimo
Trova il prezzo più alto e quello più basso.

**Prezzo massimo (C9):**
```
=MAX(C2:C6)
```

**Prezzo minimo (C10):**
```
=MIN(C2:C6)
```

---

## Formule da Utilizzare

| Funzione | Scopo | Esempio |
|----------|-------|---------|
| `=A1*B1` | Moltiplicazione | `=B2*C2` |
| `SOMMA()` | Somma intervallo | `=SOMMA(B2:B6)` |
| `MEDIA()` | Media aritmetica | `=MEDIA(C2:C6)` |
| `MAX()` | Valore massimo | `=MAX(C2:C6)` |
| `MIN()` | Valore minimo | `=MIN(C2:C6)` |

---

## Risultati Attesi

Dopo aver completato l'esercitazione, il tuo foglio dovrebbe mostrare:

- **Totali per prodotto:** Mele = 75,00€, Banane = 60,00€, ecc.
- **Quantità totale:** 180 unità
- **Valore totale:** 327,50€
- **Prezzo medio:** 2,16€
- **Prezzo massimo:** 3,00€
- **Prezzo minimo:** 1,50€

---

## Sfide Aggiuntive (Opzionali)

1. **Percentuale sul totale:**  
   Calcola quale % del valore totale rappresenta ogni prodotto.
   ```
   =D2/$D$7
   ```
   Nota: usa il riferimento assoluto `$D$7` per bloccare la cella totale.

2. **Prodotto più venduto:**  
   Trova il nome del prodotto con la quantità maggiore usando CERCA.VERT o INDICE+CONFRONTA.

3. **Formattazione:**
   - Applica formato valuta alle colonne C e D
   - Usa il formato percentuale per le percentuali
   - Aggiungi bordi e colori per migliorare la leggibilità

4. **Grafico:**
   Crea un grafico a barre che mostri il valore totale per ciascun prodotto.

---

## Note Didattiche

### Concetti Chiave

**Riferimenti di cella:**
- `B2` è un riferimento relativo (cambia copiando la formula)
- `$B$2` è un riferimento assoluto (rimane fisso)
- `$B2` o `B$2` sono riferimenti misti

**Intervalli:**
- `B2:B6` indica "da B2 a B6"
- Includono tutte le celle tra l'inizio e la fine

**Operatori:**
- `+` Addizione
- `-` Sottrazione
- `*` Moltiplicazione
- `/` Divisione
- `^` Elevamento a potenza

---

## Errori Comuni da Evitare

❌ **Dimenticare il simbolo =**
- Tutte le formule devono iniziare con `=`

❌ **Usare la virgola invece del punto e virgola**
- In italiano si usa `;` per separare gli argomenti
- Esempio corretto: `=SOMMA(A1;A2;A3)`

❌ **Non usare i due punti per gli intervalli**
- Usare `=SOMMA(B2:B6)` non `=SOMMA(B2;B3;B4;B5;B6)`

❌ **Riferimenti circolari**
- Non inserire in D2 la formula `=SOMMA(D2:D6)` (include se stessa!)

---

## Valutazione

| Criterio | Punti |
|----------|-------|
| Formule corrette (1-5) | 50% |
| Risultati esatti | 30% |
| Formattazione | 10% |
| Sfide opzionali | 10% |

**Totale:** 100 punti

---

## Prossimi Passi

Dopo aver completato questa esercitazione:
- ✅ Passa all'Esercitazione 2: Gestione Registro Voti
- 📚 Studia i riferimenti assoluti e relativi
- 💡 Sperimenta con altre funzioni statistiche (MEDIANA, MODA)

---

*Tempo medio di completamento: 20-30 minuti*  
*Difficoltà: ⭐ (1/5)*
