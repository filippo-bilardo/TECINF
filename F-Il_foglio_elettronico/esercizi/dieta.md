## **Esercizio: Gestione della Dieta e Calcolo del Fabbisogno Calorico Giornaliero**

### **Obiettivi**
1. **Calcolare il fabbisogno calorico giornaliero** di una persona in base a età, peso, altezza e livello di attività.
2. **Monitorare le calorie assunte** attraverso i pasti giornalieri.
3. **Analizzare la differenza** tra calorie assunte e fabbisogno, per valutare l’equilibrio della dieta.
4. **Creare un report settimanale** per monitorare l’andamento nel tempo.

---

## **Struttura del Foglio di Calcolo**

### **1. Foglio “Tabella Ingredienti”**
**Scopo:** Elenco generale degli ingredienti con le calorie per 100g.
**Colonne:**
- **Ingrediente** (nome)
- **Calorie per 100g**
- **Macronutrienti** (opzionale: grammi di carboidrati, proteine, grassi per 100g)


Esempio Tabella Ingredienti


| Ingrediente   | Calorie per 100g | Carboidrati (g) | Proteine (g) | Grassi (g) |
|---------------|------------------|-----------------|--------------|------------|
| Farina 00     | 333              | 72              | 10           | 1          |
| Zucchero      | 387              | 97              | 0            | 0          |
| Uova          | 143              | 1               | 13           | 9          |
| ...           | ...              | ...             | ...          | ...        |

---

### **2. Foglio “Ricetta” (uno per ogni ricetta/pasto)**
**Scopo:** Calcolare le calorie totali e per porzione di ogni pasto.
**Colonne:**
- **Ingrediente** (nome)
- **Quantità (g)**
- **Calorie per 100g** (da “Tabella Ingredienti”)
- **Calorie totali ingrediente** (formula: `(Quantità/100)*Calorie per 100g`)
- **Numero porzioni**
- **Calorie totali ricetta** (somma delle calorie totali di tutti gli ingredienti)
- **Calorie per porzione** (formula: `Calorie totali ricetta / Numero porzioni`)


Esempio Foglio Ricetta


| Ingrediente | Quantità (g) | Calorie per 100g | Calorie totali ingrediente | Numero porzioni | Calorie totali ricetta | Calorie per porzione |
|-------------|--------------|------------------|----------------------------|-----------------|------------------------|-----------------------|
| Pasta       | 100          | 350              | 350                        | 2               | 700                    | 350                   |
| Pomodoro    | 150          | 18               | 27                         | 2               |                        |                       |
| Olio        | 10           | 900              | 90                         | 2               |                        |                       |
| ...         | ...          | ...              | ...                        | ...             |                        |                       |

---

### **3. Foglio “Dieta Giornaliera”**
**Scopo:** Monitorare i pasti consumati in una giornata e calcolare il totale calorico.
**Colonne:**
- **Data**
- **Pasto** (colazione, pranzo, cena, spuntino)
- **Nome ricetta/pasto**
- **Calorie per porzione** (da foglio “Ricetta”)
- **Porzioni consumate**
- **Calorie totali pasto** (formula: `Calorie per porzione * Porzioni consumate`)
- **Totale calorie giornaliere** (somma delle calorie di tutti i pasti)


Esempio Foglio Dieta Giornaliera


| Data       | Pasto    | Nome ricetta/pasto | Calorie per porzione | Porzioni consumate | Calorie totali pasto | Totale calorie giornaliere |
|------------|----------|--------------------|----------------------|--------------------|----------------------|----------------------------|
| 05/02/2026 | Colazione| Yogurt e muesli    | 250                  | 1                  | 250                  | 2000                       |
| 05/02/2026 | Pranzo   | Pasta al pomodoro  | 350                  | 2                  | 700                  |                            |
| ...        | ...      | ...                | ...                  | ...                | ...                  |                            |

---

### **4. Foglio “Fabbisogno e Bilancio”**
**Scopo:** Calcolare il fabbisogno calorico e confrontarlo con le calorie assunte.
**Colonne:**
- **Nome persona**
- **Età**
- **Peso (kg)**
- **Altezza (cm)**
- **Livello attività** (sedentario, moderato, attivo)
- **Fabbisogno calorico giornaliero** (formula: Harris-Benedict o Mifflin-St Jeor)
- **Calorie assunte giornaliere** (da foglio “Dieta Giornaliera”)
- **Differenza** (formula: `Calorie assunte - Fabbisogno calorico`)
- **Obiettivo** (mantenimento, dimagrimento, aumento peso)


Esempio Foglio Fabbisogno e Bilancio


| Nome       | Età | Peso (kg) | Altezza (cm) | Livello attività | Fabbisogno calorico | Calorie assunte | Differenza | Obiettivo      |
|------------|-----|-----------|--------------|------------------|---------------------|------------------|------------|----------------|
| Mario Rossi| 30  | 70        | 175          | Moderato         | 2500 kcal          | 2300 kcal        | -200 kcal  | Mantenimento   |
| ...        | ... | ...       | ...          | ...              | ...                 | ...              | ...        | ...            |

---

### **5. Foglio “Report Settimanale”**
**Scopo:** Monitorare l’andamento settimanale delle calorie assunte vs fabbisogno.
**Colonne:**
- **Giorno della settimana**
- **Totale calorie giornaliere** (da foglio “Dieta Giornaliera”)
- **Fabbisogno calorico**
- **Differenza**
- **Media settimanale calorie assunte**
- **Media settimanale differenza**


Esempio Foglio Report Settimanale


| Giorno         | Totale calorie giornaliere | Fabbisogno calorico | Differenza | Media settimanale calorie assunte | Media settimanale differenza |
|----------------|----------------------------|---------------------|------------|------------------------------------|-------------------------------|
| Lunedì         | 2000                       | 2500                | -500       | 2200                               | -300                          |
| Martedì        | 2300                       | 2500                | -200       |                                    |                               |
| ...            | ...                        | ...                 | ...        |                                    |                               |

---

## **Istruzioni per gli Studenti**
1. **Popolare la “Tabella Ingredienti”** con almeno 20 ingredienti comuni.
2. **Creare almeno 5 ricette/pasti** (es. colazione, pranzo, cena, spuntini) nel foglio “Ricetta”.
3. **Compilare il foglio “Dieta Giornaliera”** per 3 giorni diversi, inserendo i pasti consumati.
4. **Calcolare il fabbisogno calorico** per 2 persone diverse nel foglio “Fabbisogno e Bilancio”.
5. **Generare un “Report Settimanale”** per una persona, analizzando l’andamento delle calorie assunte.
6. **Usare grafici** per visualizzare:
   - Calorie assunte vs fabbisogno (a barre o a linea).
   - Andamento settimanale della differenza calorica.

---

## **Domande per la Riflessione**
- Quali sono i pasti che contribuiscono maggiormente al totale calorico giornaliero?
- Come potresti modificare la dieta per raggiungere un obiettivo di dimagrimento o aumento peso?
- Quali sono i limiti di questo metodo di monitoraggio?

---
**Suggerimento:** Usare la formattazione condizionale per evidenziare in rosso i giorni in cui le calorie assunte superano il fabbisogno e in verde quando sono inferiori.