# Esempio 4: Dashboard con Sparkline

**Livello**: 🟡 Intermedio  
**Tipo grafico**: Sparkline (mini-grafici in-cell)  
**Obiettivo**: Creare dashboard compatta con trend visivi

---

## Dati da Inserire

### Performance Venditori 2026

```
Venditore	Gen	Feb	Mar	Apr	Mag	Giu	Lug	Ago	Set	Ott	Nov	Dic
Mario Rossi	12000	13500	14200	15800	16500	17200	16800	15900	18500	19200	20100	21500
Laura Bianchi	15000	15800	16200	16500	17000	17800	18200	17500	19200	20000	21500	22800
Giovanni Verdi	10500	11200	10800	12000	13500	14200	14800	13900	15500	16800	17200	18500
Anna Neri	13500	14000	14800	15200	15800	16500	17200	16800	18000	19500	20500	21200
Paolo Gialli	11000	12500	11800	13200	14000	14800	15200	14500	16000	17500	18200	19500
```

---

## Parte A: Tabella con Sparkline Trend

### Setup Colonne Aggiuntive

Dopo la colonna M (Dic), aggiungi:
- Colonna N: **Totale**
- Colonna O: **Media**
- Colonna P: **Trend**
- Colonna Q: **Performance**

### Formule

#### Colonna N - Totale (cella N2)
```
=SOMMA(B2:M2)
```

#### Colonna O - Media (cella O2)
```
=MEDIA(B2:M2)
```

#### Colonna P - Trend Linea (cella P2)
```
=SPARKLINE(B2:M2; {"linewidth", 2; "color", "blue"})
```

#### Colonna Q - Performance Colonne (cella Q2)
```
=SPARKLINE(B2:M2; {
  "charttype", "column";
  "color", "green";
  "highcolor", "darkgreen";
  "lowcolor", "orange"
})
```

### Copia Formule
Seleziona N2:Q2 e trascina verso il basso fino a Q6.

---

## Parte B: Sparkline Avanzati

### Sparkline con Media di Riferimento

Aggiungi colonna R: **Trend vs Media**

Formula (cella R2):
```
=SPARKLINE(B2:M2; {
  "charttype", "column";
  "color", IF(B2:M2>$O2, "green", "red")
})
```

**Effetto**: Colonne verdi per mesi sopra media, rosse sotto media.

**⚠️ Nota**: Questo richiede logica per ogni singola cella. Versione semplificata:

```
=SPARKLINE(B2:M2; {
  "charttype", "column";
  "color", "blue";
  "axis", TRUE;
  "axiscolor", "gray"
})
```

### Sparkline Win/Loss

Aggiungi colonna S: **Obiettivo Raggiunto**

Prima, crea colonna helper T (nascosta) con:
```
=IF(B2>=15000, 1, -1)
```
Per ogni mese (B2, C2, ..., M2).

Poi in colonna S:
```
=SPARKLINE(T2:AE2; {"charttype", "winloss"})
```

**Effetto**: Barra su (verde) per mesi che raggiungono obiettivo 15k, barra giù (rosso) per mesi sotto.

---

## Parte C: Formattazione Dashboard

### Intestazione Tabella

**Riga 1**:
- Grassetto
- Sfondo: Blu scuro (#1155CC)
- Testo: Bianco
- Allineamento: Centro
- Bordo: Sotto doppio

### Celle Sparkline

**Dimensioni**:
- Altezza riga: 35-40px
- Larghezza colonna P, Q: 120px

### Formattazione Condizionale

#### Su Colonna N (Totale)
Scala 3 colori:
- Minimo: Rosso chiaro
- Medio (50%): Giallo
- Massimo: Verde chiaro

#### Su Colonna O (Media)
Regola: Se sopra 16000, grassetto verde

---

## Parte D: Statistiche Riepilogo

Sotto la tabella (riga 9), aggiungi sezione riepilogo:

### Layout

```
	A	B	C	D
9	📊 STATISTICHE RIEPILOGO
10	Top Performer:	=INDICE(A2:A6; CONFRONTA(MAX(N2:N6); N2:N6; 0))	Totale:	=MAX(N2:N6)
11	Miglior Mese:	=INDICE(B1:M1; CONFRONTA(MAX(B7:M7); B7:M7; 0))	Valore:	=MAX(B7:M7)
12	Crescita Media:	=((MEDIA(M2:M6)-MEDIA(B2:B6))/MEDIA(B2:B6))	Format:	+45%
```

**Nota**: Riga 7 contiene SOMMA di ogni colonna mese.

### Sparkline Riepilogo

Aggiungi sparkline per totale mensile team (riga 7):

```
=SPARKLINE(B7:M7; {
  "charttype", "line";
  "linewidth", 3;
  "color", "darkblue"
})
```

---

## Parte E: Mini Gauge con Sparkline

### Percentuale Obiettivo

Obiettivo annuale team: 1.000.000€  
Totale raggiunto: =SOMMA(N2:N6)

Calcola percentuale:
```
=SOMMA(N2:N6)/1000000
```

### Sparkline Bar come Gauge

```
=SPARKLINE(SOMMA(N2:N6)/1000000; {
  "charttype", "bar";
  "max", 1;
  "color1", IF(SOMMA(N2:N6)>=1000000, "green", "orange")
})
```

**Visualizzazione**:
```
Obiettivo Annuale Team:
████████████████░░░░  92%
```

---

## Layout Completo Dashboard

```
┌─────────────────────────────────────────────────────────────┐
│ DASHBOARD PERFORMANCE VENDITORI 2026                         │
├─────────────────────────────────────────────────────────────┤
│ Venditore │ Gen │...│ Dic │ Tot │ Media│ Trend │Performance │
│ Mario R.  │12000│...│21500│ XXX │ XXXX │ ───╱ │ ▂▃▄▅▅     │
│ Laura B.  │15000│...│22800│ XXX │ XXXX │ ──── │ ▃▄▅▅▆     │
│ ...       │     │   │     │     │      │      │            │
├─────────────────────────────────────────────────────────────┤
│ 📊 STATISTICHE RIEPILOGO                                    │
│ • Top Performer: Laura Bianchi (€XXX)                       │
│ • Crescita Media: +45%                                       │
│ • Obiettivo Team: ████████████░░ 92%                        │
└─────────────────────────────────────────────────────────────┘
```

---

## Esercizi di Approfondimento

### Esercizio 1: Confronto Anno Precedente
Aggiungi dati 2025 e crea sparkline che confronta 2025 vs 2026 per ogni venditore.

### Esercizio 2: Trend Settimanale
Espandi a dati settimanali (52 settimane) con sparkline più dettagliati.

### Esercizio 3: Alert Automatico
Usa formattazione condizionale con icone:
- 🟢 Se trend positivo (ultimo mese > media)
- 🟡 Se stabile
- 🔴 Se trend negativo

---

## Best Practice Sparkline

✓ **Dimensione cella adeguata**: Min 100px larghezza, 30px altezza  
✓ **Colori semplici**: Max 2-3 colori  
✓ **Contestualizza**: Sparkline da soli dicono poco, servono valori numerici affianco  
✓ **Scala coerente**: Stessa min/max per sparkline comparabili  
✓ **Tipo appropriato**: Linea per trend, colonne per confronti  
✗ **Evita in celle troppo piccole**: Illeggibile  
✗ **Non usare per dati complessi**: Preferisci grafico normale  
✗ **Non mischiare troppi tipi**: Massimo 2 stili sparkline per dashboard  

---

## Domande di Analisi

1. Chi è il venditore più costante? (guarda sparkline)
2. Quale mese è stato il migliore per il team?
3. C'è stagionalità evidente? (cali ad agosto?)
4. Chi ha il trend di crescita più forte?

---

## Download Esempio

Questa dashboard è perfetta per:
- Report mensili vendite
- Performance tracker team
- KPI monitoring compatto
- Dashboard esecutive

**Pro-tip**: Combina con formattazione condizionale per massimo impatto visivo!
