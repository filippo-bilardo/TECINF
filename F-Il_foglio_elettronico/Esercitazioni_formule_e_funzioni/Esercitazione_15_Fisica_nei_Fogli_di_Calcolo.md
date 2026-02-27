# Esercitazione 15: 10 esercizi di Fisica con i Fogli di Calcolo

**Livello:** 📚 Intermedio  
**Tempo stimato:** 120–180 minuti  
**Strumento:** Google Sheets o Microsoft Excel

---

## Obiettivi didattici

- Applicare formule di fisica in contesti numerici reali
- Costruire tabelle con input, calcoli e output
- Usare formule (`SE`, `SOMMA`, `MEDIA`, `MIN`, `MAX`, `CERCA.VERT`/`CERCA.X`)
- Creare grafici scientifici (linea e dispersione)
- Interpretare i risultati con unità di misura corrette

---

## Struttura consigliata del file

Per ogni esercizio usa 3 aree:

1. **Input** (dati iniziali)  
2. **Calcoli** (formule fisiche)  
3. **Risultati** (valori finali + commento)

Aggiungi sempre colonna **Unità** e una cella **Controllo** con verifica (es. `SE(errore<0,01;"OK";"RICONTROLLA")`).

---

## Esercizio 1 — Moto rettilineo uniforme (MRU)

### Scenario
Un ciclista percorre una strada a velocità costante.

### Dati
- Distanza (m): 250, 500, 750, 1000
- Velocità costante: 5 m/s

### Richieste
- Calcolare il tempo per ogni distanza
- Creare grafico **spazio-tempo**

### Formula
- $t = s / v$

### Formula foglio
- In colonna Tempo: `=A2/$B$1`

---

## Esercizio 2 — Moto uniformemente accelerato (MUA)

### Scenario
Un'auto parte da ferma e accelera in modo costante.

### Dati
- Accelerazione: 2,4 m/s²
- Tempo: da 0 a 10 s

### Richieste
- Calcolare velocità nel tempo
- Calcolare spazio percorso
- Grafico **v-t** e **s-t**

### Formule
- $v = v_0 + at$ con $v_0 = 0$
- $s = v_0t + \frac{1}{2}at^2$

### Formule foglio
- Velocità: `=$B$1*A2`
- Spazio: `=0,5*$B$1*A2^2`

---

## Esercizio 3 — Caduta libera

### Scenario
Un oggetto viene lasciato cadere da un balcone.

### Dati
- Altezza iniziale: 45 m
- $g = 9,81$ m/s²

### Richieste
- Calcolare tempo di caduta
- Calcolare velocità all'impatto

### Formule
- $t = \sqrt{2h/g}$
- $v = gt$

### Formule foglio
- Tempo: `=RADQ((2*B1)/B2)`
- Velocità: `=B2*B3`

---

## Esercizio 4 — Forza, massa, accelerazione (2ª legge di Newton)

### Scenario
Un carrello viene spinto con forze diverse.

### Dati
- Massa fissa: 12 kg
- Forze applicate: 10, 20, 35, 50 N

### Richieste
- Calcolare accelerazione per ogni forza
- Individuare forza minima per superare 3 m/s²

### Formula
- $a = F/m$

### Formula foglio
- Accelerazione: `=A2/$B$1`
- Verifica soglia: `=SE(C2>=3;"SI";"NO")`

---

## Esercizio 5 — Lavoro ed energia

### Scenario
Una cassa viene trascinata su una superficie.

### Dati
- Forza: 120 N
- Spostamento: 18 m
- Angolo tra forza e spostamento: 0°

### Richieste
- Calcolare il lavoro meccanico
- Confrontare con energia cinetica finale di una massa da 15 kg

### Formule
- $L = F\cdot s\cdot \cos(\theta)$
- $E_c = \frac{1}{2}mv^2$

### Formula foglio
- Lavoro: `=B1*B2*COS(RADIANTI(B3))`

---

## Esercizio 6 — Potenza media

### Scenario
Un ascensore solleva un carico.

### Dati
- Massa: 400 kg
- Altezza: 12 m
- Tempo: 18 s
- $g = 9,81$ m/s²

### Richieste
- Calcolare lavoro contro la gravità
- Calcolare potenza media in W e kW

### Formule
- $L = mgh$
- $P = L/t$

### Formule foglio
- Lavoro: `=B1*B2*B4`
- Potenza W: `=B5/B3`
- Potenza kW: `=B6/1000`

---

## Esercizio 7 — Legge di Ohm (circuiti elettrici)

### Scenario
Analisi di un circuito con più resistenze.

### Dati
- Tensione: 12 V
- Resistenze: 4 Ω, 6 Ω, 8 Ω, 12 Ω

### Richieste
- Calcolare corrente per ogni resistenza
- Calcolare potenza dissipata
- Trovare il caso con massima potenza

### Formule
- $I = V/R$
- $P = VI = V^2/R$

### Formule foglio
- Corrente: `=$B$1/A2`
- Potenza: `=$B$1^2/A2`
- Max potenza: `=MAX(C2:C5)`

---

## Esercizio 8 — Densità e galleggiamento

### Scenario
Si confrontano materiali diversi immersi in acqua.

### Dati
- Massa (kg) e volume (m³) di 6 oggetti
- Densità acqua: 1000 kg/m³

### Richieste
- Calcolare densità di ogni oggetto
- Stabilire se galleggia o affonda

### Formule
- $\rho = m/V$
- Galleggia se $\rho_{oggetto} < \rho_{acqua}$

### Formule foglio
- Densità: `=A2/B2`
- Esito: `=SE(C2<$B$1;"Galleggia";"Affonda")`

---

## Esercizio 9 — Pressione idrostatica

### Scenario
Calcolo pressione a varie profondità.

### Dati
- Profondità: 0, 2, 5, 10, 20, 30 m
- $\rho$ acqua = 1000 kg/m³
- $g = 9,81$ m/s²
- $P_0 = 101325$ Pa

### Richieste
- Calcolare pressione assoluta
- Convertire in bar
- Grafico pressione-profondità

### Formula
- $P = P_0 + \rho gh$

### Formule foglio
- Pressione Pa: `=$B$4+($B$1*$B$2*A2)`
- Pressione bar: `=B2/100000`

---

## Esercizio 10 — Calorimetria (scambio termico)

### Scenario
Miscelazione di acqua calda e fredda.

### Dati
- Massa acqua calda: 0,30 kg a 70°C
- Massa acqua fredda: 0,20 kg a 20°C
- Calore specifico acqua: 4186 J/(kg·°C)

### Richieste
- Calcolare temperatura finale di equilibrio (senza dispersioni)
- Verificare energia ceduta = energia assorbita

### Formule
- $Q = mc\Delta T$
- Equilibrio:  
  $m_1c(T_1-T_f)=m_2c(T_f-T_2)$

### Formula foglio (Tf)
- `=(B1*B2 + B3*B4)/(B1+B3)`

---

## Estensione (facoltativa)

Per 2 esercizi a scelta:

- Aggiungi **validazione dati** sugli input
- Inserisci **formattazione condizionale** sugli output non fisici
- Costruisci una **tabella pivot** riassuntiva dei risultati
- Crea una mini **dashboard** con 2 grafici e 3 KPI

---

## Criteri di valutazione (rubrica)

- Correttezza formule fisiche: **40%**
- Correttezza formule foglio: **25%**
- Organizzazione e leggibilità: **15%**
- Grafici e interpretazione risultati: **20%**

---

## Consegna

- Nome file consigliato: `Esercitazione_15_Fisica_FoglioElettronico_CognomeNome.xlsx` o `.gsheet`
- Includere almeno 1 commento finale per ogni esercizio: "Cosa ho imparato"
