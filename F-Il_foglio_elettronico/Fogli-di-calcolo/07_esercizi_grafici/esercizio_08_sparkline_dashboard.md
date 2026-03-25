# Esercizio 8: Dashboard Vendite con Sparkline

**Livello**: 🟡 Intermedio  
**Tipo grafico**: Sparkline (micro-grafici in cella) + Formattazione condizionale  
**Tempo stimato**: 35 minuti  
**Competenze**: Funzione SPARKLINE, dashboard compatte, formattazione condizionale, metriche aggregate

---

## 🎯 Obiettivo

Creare una dashboard compatta con dati di 5 venditori usando la funzione SPARKLINE per visualizzare trend e performance mensili direttamente nelle celle, insieme a metriche aggregate e formattazione condizionale.

## 📖 Scenario

Sei il Sales Director di un'azienda con 5 venditori. Devi creare un report esecutivo "one-page" che mostri rapidamente le performance mensili, totali, medie e trend di ogni venditore senza dover aprire grafici separati. Il CEO vuole vedere tutto in un colpo d'occhio.

## 📊 Dati Forniti

### Tabella Dati Mensili

Copia questa tabella nel tuo Google Foglio (celle A1:M6):

```
Venditore	Gen	Feb	Mar	Apr	Mag	Giu	Lug	Ago	Set	Ott	Nov	Dic
Anna	12000	13500	14200	15000	16500	15800	14900	13200	16800	18000	19200	20000
Bruno	15000	15200	14800	16000	17000	16500	15500	14000	17500	18500	19000	19500
Clara	10000	10500	11000	11800	12500	13000	12200	11000	13500	14500	15000	15800
Diego	13000	13800	14500	15500	16000	15200	14500	13500	16500	17500	18000	18500
Elena	11000	11500	12000	13000	14000	14500	13800	12500	15000	16000	17000	18000
```

**Nota**: Usa Tab per separare le colonne quando copi.

---

## ✅ Requisiti

Crea una dashboard con le seguenti colonne (aggiungi a destra dei dati mensili):

### Colonne Dashboard (N, O, P, Q)

1. **Colonna N - Totale Annuo**:
   - Formula: `=SOMMA(B2:M2)`
   - Formattazione: Numero con separatore migliaia + simbolo €

2. **Colonna O - Media Mensile**:
   - Formula: `=MEDIA(B2:M2)` oppure `=N2/12`
   - Formattazione: Numero arrotondato + simbolo €
   - Formattazione condizionale:
     - Verde scuro se ≥ 15.000
     - Verde chiaro se ≥ 13.000
     - Giallo se ≥ 11.000
     - Rosso se < 11.000

3. **Colonna P - Trend (Sparkline Linea)**:
   - Formula: `=SPARKLINE(B2:M2)`
   - Tipo: Linea
   - Opzioni: Colore blu, mostra min/max, asse X visibile

4. **Colonna Q - Performance (Sparkline Colonne)**:
   - Formula: `=SPARKLINE(B2:M2;{"charttype";"column"})`
   - Tipo: Colonne verticali
   - Opzioni: Colore verde per valori positivi

### Formattazione Aggiuntiva

5. **Intestazioni**: 
   - Riga 1: Grassetto, sfondo blu (#4285F4), testo bianco
   - Allineamento: Centrato

6. **Riga Totale (riga 7)**:
   - Etichetta "TOTALE TEAM" in A7
   - Somma di ogni mese (B7:M7)
   - Totale generale, media generale
   - Grassetto, sfondo grigio chiaro

7. **Bordi**: 
   - Tabella completa con bordi sottili
   - Bordo spesso sotto intestazione

---

## 🤔 Domande di Analisi

Dopo aver creato la dashboard, rispondi:

1. Chi ha il totale annuo più alto? E la media mensile migliore?
2. Osservando le sparkline linea, chi ha il trend di crescita più costante?
3. Chi ha la maggior variabilità mensile (picchi e valli nelle sparkline)?
4. In quale mese il team ha venduto complessivamente di più?
5. Quale venditore ha superato €20.000 in un mese?
6. Se l'obiettivo medio mensile è €14.000, quanti venditori lo raggiungono?

---

## 💡 Suggerimenti

- La funzione SPARKLINE crea mini-grafici direttamente in una cella
- Sintassi base: `=SPARKLINE(dati; opzioni)`
- Opzioni come dizionario: `{"chiave";"valore"}`
- Per formattazione condizionale: Formato → Formattazione condizionale
- Allarga colonne P e Q per vedere bene le sparkline
- Usa CTRL+D per copiare formula in basso nelle colonne N-Q

---

<details>
<summary><strong>📝 Soluzione - Clicca per Espandere</strong></summary>

## Passi Dettagliati

### 1. Preparazione Dati
1. Copia dati in A1:M6
2. Verifica numeri allineati a destra
3. Formatta A1:M1 (intestazione):
   - Grassetto
   - Sfondo blu (#4285F4)
   - Testo bianco
   - Allineamento centrato

### 2. Colonna N - Totale Annuo

**In N1** (intestazione):
```
Totale Annuo
```

**In N2** (prima formula):
```
=SOMMA(B2:M2)
```

**Formattazione N2**:
1. Seleziona N2
2. Formato → Numero → Personalizzato
3. Formato: `#.##0 €` o `#,##0 "€"`

**Copia in basso**:
1. Seleziona N2
2. CTRL+C (copia)
3. Seleziona N3:N6
4. CTRL+V (incolla)

### 3. Colonna O - Media Mensile

**In O1**:
```
Media Mensile
```

**In O2**:
```
=MEDIA(B2:M2)
```
Oppure:
```
=ARROTONDA(N2/12;0)
```

**Formattazione O2**: 
- Formato: `#.##0 €`

**Formattazione Condizionale**:
1. Seleziona **O2:O6**
2. Menu: **Formato → Formattazione condizionale**
3. Regola 1:
   - Condizione: **Maggiore o uguale a** `15000`
   - Colore sfondo: Verde scuro (#00FF00 o #34A853)
   - Colore testo: Bianco (opzionale)
4. **Aggiungi nuova regola** (stesso intervallo):
   - Condizione: **Maggiore o uguale a** `13000`
   - Colore: Verde chiaro (#B7E1CD)
5. **Aggiungi nuova regola**:
   - Condizione: **Maggiore o uguale a** `11000`
   - Colore: Giallo (#FFF2CC)
6. **Aggiungi nuova regola**:
   - Condizione: **Minore di** `11000`
   - Colore: Rosso chiaro (#F4CCCC)

**Nota**: L'ordine delle regole conta! Metti le più restrittive prima.

### 4. Colonna P - Sparkline Trend (Linea)

**In P1**:
```
Trend
```

**In P2** (sparkline linea base):
```
=SPARKLINE(B2:M2)
```

**Versione avanzata con opzioni**:
```
=SPARKLINE(B2:M2;{"charttype"\"linewidth";"color";"rtl"; "line"\2;"blue";FALSE})
```

**Versione con evidenziazione min/max**:
```
=SPARKLINE(B2:M2;{
  "charttype","line";
  "linewidth",2;
  "color","#4285F4";
  "min",10000;
  "max",20000
})
```

**Nota**: In Google Fogli italiano usa `;` invece di `,` nei dizionari.

**Sintassi corretta per italiano**:
```
=SPARKLINE(B2:M2;{"charttype";"line";"linewidth";2;"color";"#4285F4"})
```

**Formattazione cella P2**:
- Larghezza colonna: 150-200px
- Altezza riga: 40-50px (per vedere bene il grafico)

**Copia in P3:P6**

### 5. Colonna Q - Sparkline Performance (Colonne)

**In Q1**:
```
Performance
```

**In Q2** (sparkline colonne):
```
=SPARKLINE(B2:M2;{"charttype";"column"})
```

**Versione con colori personalizzati**:
```
=SPARKLINE(B2:M2;{
  "charttype","column";
  "color","#34A853";
  "max",20000
})
```

**Versione con evidenziazione massimo**:
```
=SPARKLINE(B2:M2;{
  "charttype","column";
  "color","#4285F4";
  "highcolor","#34A853";
  "max",20000
})
```

**Per italiano**:
```
=SPARKLINE(B2:M2;{"charttype";"column";"color";"#34A853"})
```

**Formattazione Q2**:
- Larghezza: 150-200px
- Altezza: 40-50px

**Copia in Q3:Q6**

### 6. Riga Totale Team (riga 7)

**In A7**:
```
TOTALE TEAM
```

**In B7** (totale Gennaio):
```
=SOMMA(B2:B6)
```

**Copia B7 in C7:M7** (trascina orizzontalmente)

**In N7** (totale generale):
```
=SOMMA(N2:N6)
```

**In O7** (media generale):
```
=MEDIA(O2:O6)
```

**Formattazione riga 7**:
- Grassetto
- Sfondo grigio chiaro (#F3F3F3)
- Bordo superiore spesso

### 7. Formattazione Finale

**Bordi**:
1. Seleziona A1:Q7
2. Bordi → Tutti i bordi (sottili)
3. Seleziona A1:Q1
4. Bordo inferiore → Spesso

**Allineamenti**:
- A2:A7: Sinistra
- B2:O7: Destra
- P2:Q7: Centrato (per sparkline)

**Intestazioni dashboard** (N1:Q1):
- Grassetto
- Centrato
- Sfondo blu (come A1:M1)
- Testo bianco

### Risultato Atteso

```
┌──────────┬─────┬─────┬─────┬─────┬──────┬─────┬──────┬──────┬──────┬──────┬──────┬──────┬──────────┬──────────┬────────────┬────────────┐
│Venditore │ Gen │ Feb │ Mar │ Apr │ Mag  │ Giu │ Lug  │ Ago  │ Set  │ Ott  │ Nov  │ Dic  │Totale    │Media     │Trend       │Performance │
│          │     │     │     │     │      │     │      │      │      │      │      │      │Annuo     │Mensile   │            │            │
├──────────┼─────┼─────┼─────┼─────┼──────┼─────┼──────┼──────┼──────┼──────┼──────┼──────┼──────────┼──────────┼────────────┼────────────┤
│Anna      │12000│13500│14200│15000│16500 │15800│14900 │13200 │16800 │18000 │19200 │20000 │189.100 € │15.758 €  │  ╱╲╱╲╱──   │ ▂▃▄▅▆▅▅▃▆▇▇█│
│          │     │     │     │     │      │     │      │      │      │      │      │      │          │  VERDE   │            │            │
│Bruno     │15000│15200│14800│16000│17000 │16500│15500 │14000 │17500 │18500 │19000 │19500 │199.000 € │16.583 €  │ ──╱╲╱╲──   │ ▅▅▅▆▇▆▅▄▇▇▇█│
│          │     │     │     │     │      │     │      │      │      │      │      │      │          │  VERDE   │            │            │
│Clara     │10000│10500│11000│11800│12500 │13000│12200 │11000 │13500 │14500 │15000 │15800 │151.300 € │12.608 €  │   ╱──╲╱──  │ ▃▃▄▄▅▅▄▃▅▆▆█│
│          │     │     │     │     │      │     │      │      │      │      │      │      │          │  GIALLO  │            │            │
│Diego     │13000│13800│14500│15500│16000 │15200│14500 │13500 │16500 │17500 │18000 │18500 │186.500 € │15.542 €  │  ╱╲╲╲╱──   │ ▄▄▅▆▆▆▅▄▆▇▇█│
│          │     │     │     │     │      │     │      │      │      │      │      │      │          │  VERDE   │            │            │
│Elena     │11000│11500│12000│13000│14000 │14500│13800 │12500 │15000 │16000 │17000 │18000 │158.300 € │13.192 €  │   ╱──╲╱──  │ ▃▃▄▅▅▅▅▄▆▆▇█│
│          │     │     │     │     │      │     │      │      │      │      │      │      │          │VERDE CH. │            │            │
├──────────┼─────┼─────┼─────┼─────┼──────┼─────┼──────┼──────┼──────┼──────┼──────┼──────┼──────────┼──────────┼────────────┼────────────┤
│TOTALE    │61000│64500│66500│71300│76000 │75000│70900 │64200 │79300 │84500 │88200 │91800 │884.200 € │14.737 €  │            │            │
│TEAM      │     │     │     │     │      │     │      │      │      │      │      │      │          │          │            │            │
└──────────┴─────┴─────┴─────┴─────┴──────┴─────┴──────┴──────┴──────┴──────┴──────┴──────┴──────────┴──────────┴────────────┴────────────┘
```

## Risposte Domande di Analisi

1. **Totale e media migliori**:
   - **Totale più alto**: Bruno con €199.000
   - **Media migliore**: Bruno con €16.583/mese
   - Anna seconda (€15.758)
   
   Bruno è il top performer assoluto

2. **Trend di crescita più costante**:
   
   Osservando le sparkline:
   - **Anna**: Crescita forte Gen-Mag, calo Giu-Ago, forte ripresa Set-Dic
   - **Bruno**: Molto costante, oscillazioni minime, crescita graduale
   - Clara: Crescita graduale, abbastanza lineare
   - Diego: Simile ad Anna, buona crescita
   - Elena: Crescita graduale costante
   
   **Bruno ed Elena** hanno trend più costanti (meno zigzag)

3. **Maggior variabilità**:
   
   - **Anna**: Picchi evidenti (Dic €20k, Ago €13.2k = €6.8k differenza)
   - Bruno: Variabilità minore
   - Clara: Variabilità media
   - Diego: Variabilità media-alta
   - Elena: Variabilità media
   
   **Anna** ha la maggior variabilità (colonne sparkline più disomogenee)

4. **Mese con vendite team più alte**:
   
   Osserva riga 7 (TOTALE TEAM):
   - Dic: €91.800 ⭐ (massimo)
   - Nov: €88.200
   - Ott: €84.500
   - Ago: €64.200 (minimo)
   
   **Dicembre** è il mese migliore per il team

5. **Chi ha superato €20.000**:
   
   Scorrendo i dati mensili:
   - **Anna**: Dicembre €20.000 (unica!)
   - Nessun altro ha superato €20k
   
   Anna ha il record mensile assoluto

6. **Obiettivo €14.000 di media**:
   
   Verifica colonna O (Media Mensile):
   - Anna: €15.758 ✓ (sopra)
   - Bruno: €16.583 ✓ (sopra)
   - Clara: €12.608 ✗ (sotto)
   - Diego: €15.542 ✓ (sopra)
   - Elena: €13.192 ✗ (sotto)
   
   **3 venditori su 5** raggiungono l'obiettivo (60%)
   
   Clara ed Elena necessitano coaching

## Opzioni Avanzate SPARKLINE

### Sparkline Linea con tutti i parametri

```
=SPARKLINE(B2:M2;{
  "charttype","line";
  "linewidth",2;
  "color","blue";
  "xmin",1;
  "xmax",12;
  "ymin",10000;
  "ymax",20000;
  "rtl",FALSE;
  "nan","ignore"
})
```

### Sparkline Colonne con Win/Loss

Per mostrare crescita (verde) vs decrescita (rosso) mese su mese:

```
=SPARKLINE(B2:M2-OFFSET(B2:M2;0;-1;1;12);{
  "charttype","column";
  "color","green";
  "negcolor","red"
})
```

### Sparkline Bar (barre orizzontali)

```
=SPARKLINE(B2:M2;{
  "charttype","bar";
  "max",20000;
  "color1","lightblue";
  "color2","darkblue"
})
```

## Analisi Aggiuntiva

### Ranking Venditori

Aggiungi colonna R "Ranking":

**In R2**:
```
=RANGO(N2;$N$2:$N$6;0)
```
Dove 0 = ordine decrescente (1 = più alto)

### Percentuale su Totale Team

Aggiungi colonna S "% Team":

**In S2**:
```
=N2/$N$7
```
Formato: Percentuale con 1 decimale

Risultati:
- Bruno: 22,5% del team
- Anna: 21,4%
- Diego: 21,1%
- Elena: 17,9%
- Clara: 17,1%

### Crescita Gen→Dic

Aggiungi colonna T "Crescita %":

**In T2**:
```
=((M2-B2)/B2)*100
```

Risultati:
- Anna: +66,7% ⭐
- Bruno: +30,0%
- Clara: +58,0%
- Diego: +42,3%
- Elena: +63,6%

**Anna ha la crescita più alta!**

</details>

---

## 🚀 Varianti (Bonus)

Prova queste estensioni:

### Variante A: Aggiungi Crescita Mensile
- Colonna R: Crescita % Gen→Dic = `(Dic-Gen)/Gen`
- Sparkline "win/loss": celle verdi per crescita, rosse per calo
- Formula: `=SPARKLINE(C2:M2-B2:L2)`

### Variante B: Target vs Actual
- Aggiungi colonna "Obiettivo" = 14.000 per tutti
- Colonna "Gap": Differenza vs obiettivo
- Sparkline che evidenzia mesi sotto target in rosso

### Variante C: Dashboard Trimestrale
- Crea seconda tabella: Q1, Q2, Q3, Q4 per ogni venditore
- Sparkline colonne per confronto trimestrale
- Identifica trimestre più forte di ogni venditore

### Variante D: Mini Classifica
- In area separata crea tabella:
  - Top 3 venditori (nomi + totale)
  - Usare GRANDE() e CONFRONTA() per automatizzare
- Sparkline dei soli top performer

### Variante E: Heatmap Mensile
- Formattazione condizionale su B2:M6
- Scala colori: rosso (basso) → giallo → verde (alto)
- Visualizzazione immediata mesi forti/deboli
- Combina con sparkline per doppia vista

### Variante F: Sparkline con Threshold
- Linea orizzontale a €15.000 (obiettivo)
- Sparkline evidenzia punti sopra/sotto soglia
- Formula avanzata con `highpoints` e `lowpoints`

---

## 📚 Concetti Chiave Appresi

✅ Funzione SPARKLINE (linee, colonne, bar)  
✅ Dashboard compatte e informative  
✅ Formattazione condizionale con scale di colori  
✅ Metriche aggregate (SOMMA, MEDIA)  
✅ Visualizzazioni in-cell (senza grafici esterni)  
✅ Sintassi dizionari per opzioni avanzate  
✅ Design report esecutivi "one-page"  

---

## 🎓 Nota sulla Funzione SPARKLINE

La funzione `SPARKLINE()` è potentissima per dashboard:

**Vantaggi**:
- ✅ Visualizzazione immediata dentro la cella
- ✅ Aggiorna automaticamente con i dati
- ✅ Non occupa spazio extra (no grafici separati)
- ✅ Ideale per report stampati/PDF
- ✅ Confronti rapidi tra righe

**Limitazioni**:
- ❌ Meno personalizzabile dei grafici standard
- ❌ No etichette dati dettagliate
- ❌ Dimensione limitata alla cella

**Quando usare**:
- Dashboard esecutive
- Tabelle con trend incluso
- Report one-page
- Confronti multipli rapidi

**Quando NON usare**:
- Analisi dettagliata di singolo dataset
- Presentazioni con grafici grandi
- Necessità di etichette/annotazioni

---

**Esercizio Precedente**: [Esercizio 7 - Grafico Combinato](esercizio_07_combinato_doppio.md)  
**Corso Completo**: [Torna all'Indice](../INDICE_CORSO.md)
