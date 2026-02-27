# Esercitazione 16: 10 esercizi di Chimica con i Fogli di Calcolo

**Livello:** 📚 Intermedio  
**Tempo stimato:** 120–180 minuti  
**Strumento:** Google Sheets o Microsoft Excel

---

## Obiettivi didattici

- Applicare formule e leggi chimiche in contesti numerici reali
- Organizzare dati sperimentali in tabelle
- Usare formule (`SE`, `SOMMA`, `MEDIA`, `MIN`, `MAX`, `ARROTONDA`, `CERCA.VERT`/`CERCA.X`)
- Rappresentare dati con grafici (linea e dispersione)
- Interpretare i risultati con unità corrette

---

## Struttura consigliata del file

Per ogni esercizio usa 3 aree:

1. **Input** (dati iniziali)  
2. **Calcoli** (formule chimiche)  
3. **Risultati** (valori finali + commento)

Aggiungi sempre colonna **Unità** e una cella **Controllo** con verifica (es. `SE(errore<0,01;"OK";"RICONTROLLA")`).

---

## Esercizio 1 — Massa molare e quantità di sostanza

### Scenario
Calcolo delle moli di diverse sostanze a partire dalla massa.

### Dati
- Sostanze: H₂O, NaCl, CO₂, NH₃
- Massa campione (g): 36, 58,5, 44, 17
- Masse molari (g/mol): 18, 58,5, 44, 17

### Richieste
- Calcolare le moli di ciascun campione
- Verificare quale campione contiene più particelle

### Formula
- $n = m / M$

### Formula foglio
- `=B2/C2`

---

## Esercizio 2 — Numero di particelle (costante di Avogadro)

### Scenario
Determinare quante molecole/atomi sono presenti in un campione.

### Dati
- Moli calcolate dall'esercizio 1
- $N_A = 6,022\times10^{23}$ particelle/mol

### Richieste
- Calcolare numero di particelle per ogni sostanza

### Formula
- $N = n\cdot N_A$

### Formula foglio
- `=B2*$B$1`

---

## Esercizio 3 — Concentrazione molare (molarità)

### Scenario
Preparazione di soluzioni in laboratorio.

### Dati
- Moli soluto: 0,10 ; 0,25 ; 0,50
- Volumi soluzione (L): 0,50 ; 1,00 ; 2,00

### Richieste
- Calcolare la molarità per ogni soluzione
- Identificare la soluzione più concentrata

### Formula
- $M = n / V$

### Formula foglio
- `=A2/B2`
- Soluzione più concentrata: `=MAX(C2:C10)`

---

## Esercizio 4 — Diluzioni

### Scenario
Partendo da una soluzione concentrata, preparare soluzioni più diluite.

### Dati
- Soluzione madre: $C_1 = 2,0$ M
- Volumi finali: 100, 250, 500 mL
- Concentrazioni target: 0,5 M, 0,2 M, 0,1 M

### Richieste
- Calcolare il volume da prelevare dalla soluzione madre

### Formula
- $C_1V_1 = C_2V_2$
- $V_1 = (C_2V_2)/C_1$

### Formula foglio
- `=(B2*C2)/$B$1`

---

## Esercizio 5 — pH di acidi e basi forti

### Scenario
Calcolo del pH di soluzioni acquose.

### Dati
- [H⁺] (M): 1E-1, 1E-2, 1E-3, 1E-4
- [OH⁻] (M): 1E-1, 1E-2, 1E-3, 1E-4

### Richieste
- Calcolare pH da [H⁺]
- Calcolare pOH da [OH⁻]
- Trovare pH da pOH

### Formule
- $pH = -\log_{10}[H^+]$
- $pOH = -\log_{10}[OH^-]$
- $pH + pOH = 14$

### Formule foglio
- pH: `=-LOG10(A2)`
- pOH: `=-LOG10(B2)`
- pH da pOH: `=14-C2`

---

## Esercizio 6 — Stechiometria di reazione

### Scenario
Reazione: $2H_2 + O_2 \rightarrow 2H_2O$

### Dati
- Massa H₂: 4 g
- Massa O₂: 32 g
- Masse molari: H₂ = 2 g/mol, O₂ = 32 g/mol, H₂O = 18 g/mol

### Richieste
- Calcolare moli iniziali dei reagenti
- Individuare reagente limitante
- Calcolare massa teorica di H₂O prodotta

### Formule
- $n = m/M$
- Reagente limitante tramite confronto $n/coefficienti$

### Formule foglio
- Moli H₂: `=B1/B2`
- Moli O₂: `=C1/C2`
- Limite: `=MIN(D1/2;E1/1)`
- Moli H₂O: `=2*F1`
- Massa H₂O: `=G1*18`

---

## Esercizio 7 — Resa percentuale

### Scenario
Confronto tra resa teorica e resa reale in una sintesi.

### Dati
- Massa teorica prodotto (g): 12,5 ; 18,0 ; 25,0
- Massa reale ottenuta (g): 10,8 ; 15,3 ; 20,5

### Richieste
- Calcolare resa percentuale
- Evidenziare esperimenti con resa < 80%

### Formula
- $\%\,resa = (m_{reale}/m_{teorica})\cdot 100$

### Formule foglio
- `=(B2/A2)*100`
- Valutazione: `=SE(C2<80;"Bassa";"Accettabile")`

---

## Esercizio 8 — Legge dei gas ideali

### Scenario
Studio di campioni gassosi in diverse condizioni.

### Dati
- $n$ (mol): 0,5 ; 1,0 ; 1,5
- $T$ (K): 273 ; 298 ; 350
- $V$ (L): 5 ; 10 ; 15
- Costante $R = 0,0821$ L·atm/(mol·K)

### Richieste
- Calcolare la pressione $P$ per ogni caso

### Formula
- $PV = nRT \Rightarrow P = nRT/V$

### Formula foglio
- `=(A2*$B$1*B2)/C2`

---

## Esercizio 9 — Termochimica (calore scambiato)

### Scenario
Riscaldamento/raffreddamento di campioni.

### Dati
- Massa (g): 100, 250, 500
- Calore specifico acqua: 4,18 J/(g·°C)
- Variazione temperatura ΔT (°C): 5, 10, 20

### Richieste
- Calcolare il calore scambiato $Q$
- Convertire i risultati in kJ

### Formula
- $Q = mc\Delta T$

### Formule foglio
- Q in J: `=A2*$B$1*C2`
- Q in kJ: `=D2/1000`

---

## Esercizio 10 — Cinetica chimica (velocità media)

### Scenario
Monitoraggio concentrazione di un reagente nel tempo.

### Dati
- Tempo (s): 0, 20, 40, 60, 80
- [A] (mol/L): 0,100 ; 0,082 ; 0,067 ; 0,055 ; 0,045

### Richieste
- Calcolare velocità media di consumo in ogni intervallo
- Creare grafico [A] vs tempo

### Formula
- $v_{media} = -\Delta[A]/\Delta t$

### Formula foglio
- `=-(B3-B2)/(A3-A2)`

---

## Estensione (facoltativa)

Per 2 esercizi a scelta:

- Aggiungi **validazione dati** sugli input
- Inserisci **formattazione condizionale** per evidenziare risultati anomali
- Costruisci una **tabella pivot** riassuntiva
- Crea una mini **dashboard** con 2 grafici e 3 KPI

---

## Criteri di valutazione (rubrica)

- Correttezza formule chimiche: **40%**
- Correttezza formule foglio: **25%**
- Organizzazione e leggibilità: **15%**
- Grafici e interpretazione risultati: **20%**

---

## Consegna

- Nome file consigliato: `Esercitazione_16_Chimica_FoglioElettronico_CognomeNome.xlsx` o `.gsheet`
- Includere almeno 1 commento finale per ogni esercizio: "Cosa ho imparato"
