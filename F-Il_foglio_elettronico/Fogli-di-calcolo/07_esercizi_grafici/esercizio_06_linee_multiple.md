# Esercizio 6: Performance Venditori nel Tempo

**Livello**: 🟡 Intermedio  
**Tipo grafico**: Linee multiple  
**Tempo stimato**: 25 minuti  
**Competenze**: Grafici multi-linea, confronti performance, trend temporali, marcatori

---

## 🎯 Obiettivo

Creare un grafico a linee multiple per confrontare le performance mensili di 4 venditori e identificare il top performer e i trend individuali.

## 📖 Scenario

Sei il Sales Manager di un'azienda B2B. Vuoi monitorare le performance mensili del tuo team di 4 venditori (Mario, Laura, Gianni, Sara) nell'ultimo anno per decidere chi merita il bonus annuale e chi necessita di coaching.

## 📊 Dati Forniti

Copia questa tabella nel tuo Google Foglio (celle A1:E13):

```
Mese	Mario	Laura	Gianni	Sara
Gen	45000	52000	38000	48000
Feb	47000	54000	39000	51000
Mar	46000	58000	41000	49000
Apr	48000	61000	40000	53000
Mag	51000	63000	42000	56000
Giu	49000	59000	43000	54000
Lug	50000	62000	41000	52000
Ago	48000	55000	38000	49000
Set	52000	64000	44000	57000
Ott	54000	67000	46000	59000
Nov	56000	70000	45000	61000
Dic	59000	72000	47000	65000
```

**Nota**: Usa Tab per separare le colonne quando copi.

---

## ✅ Requisiti

Crea un grafico a linee multiple che rispetti questi criteri:

1. **Tipo**: Grafico a linee (non area, non colonne)
2. **Dati**: Tutte e 4 le serie (venditori) per 12 mesi
3. **Titolo**: "Performance Vendite Annuali per Venditore"
4. **Sottotitolo**: "Gennaio - Dicembre 2026" (opzionale)
5. **Asse X**: 
   - Etichetta "Mese"
   - Tutti i 12 mesi visibili
6. **Asse Y**: 
   - Etichetta "Vendite Mensili (€)"
   - Formato: Numero con separatore migliaia
   - Range: 35.000 - 75.000
7. **Linee**: 
   - Spessore: 2-3px
   - Stile: Continuo (solido)
8. **Marcatori**: Punti visibili su ogni data point
9. **Colori distintivi**:
   - Mario: Blu (#4285F4)
   - Laura: Verde (#34A853)
   - Gianni: Arancione (#FBBC04)
   - Sara: Rosso (#EA4335)
10. **Legenda**: Posizione in basso, orizzontale
11. **Griglia**: Linee orizzontali e verticali principali

---

## 🤔 Domande di Analisi

Dopo aver creato il grafico, rispondi:

1. Chi è il top performer dell'anno (vendite totali più alte)?
2. Chi ha il trend di crescita più costante?
3. C'è un mese in cui tutti i venditori hanno avuto un calo? Quale?
4. Qual è il gap (differenza) tra il miglior e peggior venditore a Dicembre?
5. Chi ha avuto la crescita percentuale più alta da Gennaio a Dicembre?
6. Quale venditore è più "stabile" (minor variabilità)?

---

## 💡 Suggerimenti

- Seleziona tutto l'intervallo A1:E13 con gli header
- Per cambiare colore: Personalizza → Serie → Seleziona nome venditore
- Attiva marcatori: Serie → Tipo punto → Cerchio (o altro)
- Se le linee si sovrappongono, aumenta spessore o dimensione marcatori
- Usa colori Google standard per massima leggibilità
- Verifica che tutti i 12 mesi siano visibili sull'asse X

---

<details>
<summary><strong>📝 Soluzione - Clicca per Espandere</strong></summary>

## Passi Dettagliati

### 1. Preparazione Dati
- Copia i dati nelle celle A1:E13
- Verifica allineamento: testo a sinistra (mesi), numeri a destra (vendite)
- Formatta intestazioni (riga 1) in grassetto

### 2. Creazione Grafico
1. Seleziona **A1:E13** (tutto, inclusi header)
2. Menu: **Inserisci → Grafico**
3. Tipo suggerito: dovrebbe essere "Grafico a linee"
4. Se no: Editor → Configurazione → Tipo → **Grafico a linee**
5. Verifica che ci siano 4 linee (una per venditore)

### 3. Personalizzazione Titolo
1. Editor grafico → Tab **Personalizza**
2. Sezione **Titolo grafico**
3. Testo: `Performance Vendite Annuali per Venditore`
4. Font: Arial, 16pt, Grassetto
5. (Opzionale) Sottotitolo: `Gennaio - Dicembre 2026`, 12pt

### 4. Personalizzazione Assi

**Asse Orizzontale (X)**:
1. Sezione **Asse orizzontale**
2. Titolo: `Mese`
3. Inclina testo etichette: 45° (se i nomi si sovrappongono)
4. Mostra tutte le etichette: ✓

**Asse Verticale (Y)**:
1. Sezione **Asse verticale**
2. Titolo: `Vendite Mensili (€)`
3. Formato: Numero con separatore migliaia
4. Min: `35000`
5. Max: `75000`
6. Intervalli principali: 5000 (opzionale)

### 5. Personalizzazione Serie

Ripeti per ogni venditore:

**Serie "Mario"**:
1. Sezione **Serie** → Dropdown: "Mario"
2. Colore linea: Blu `#4285F4`
3. Spessore linea: 3px
4. Tipo punto: **Cerchio** (●)
5. Dimensione punto: 5-6
6. Opacità linea: 100%

**Serie "Laura"**:
1. Sezione **Serie** → Dropdown: "Laura"
2. Colore: Verde `#34A853`
3. Spessore: 3px
4. Tipo punto: **Cerchio** (●)
5. Dimensione punto: 5-6

**Serie "Gianni"**:
1. Sezione **Serie** → Dropdown: "Gianni"
2. Colore: Arancione `#FBBC04`
3. Spessore: 3px
4. Tipo punto: **Cerchio** (●)
5. Dimensione punto: 5-6

**Serie "Sara"**:
1. Sezione **Serie** → Dropdown: "Sara"
2. Colore: Rosso `#EA4335`
3. Spessore: 3px
4. Tipo punto: **Cerchio** (●)
5. Dimensione punto: 5-6

### 6. Legenda e Griglia

**Legenda**:
1. Sezione **Legenda**
2. Posizione: **In basso** (orizzontale)
3. Font: 10pt
4. Formato: Mario | Laura | Gianni | Sara

**Griglia**:
1. Sezione **Stile grafico**
2. Griglia orizzontale: ✓ (principale)
3. Griglia verticale: ✓ (leggera, opzionale)
4. Colore griglia: Grigio chiaro (#E8E8E8)

### 7. Stile Generale
1. Sfondo: Bianco
2. Bordo grafico: Nessuno o grigio sottile
3. Altezza grafico: 400-500px (per vedere bene i dettagli)

### Risultato Atteso

```
    Performance Vendite Annuali per Venditore
          Gennaio - Dicembre 2026

€  ▲
75k│                              ●────● Laura
   │                          ●──╱
   │                      ●──╱  ●────● Sara
70k│                  ●──╱    ╱
   │              ●──╱      ╱
65k│          ●──╱        ●────● Mario
   │      ●──╱          ╱
60k│  ●──╱            ●
   │ ╱              ╱
55k│             ●──────● Gianni
   │         ●──╱
50k│     ●──╱
   │ ●──╱
45k│●
   │
40k└───┬───┬───┬───┬───┬───┬───┬───┬───┬───┬───┬──→
      Gen Feb Mar Apr Mag Giu Lug Ago Set Ott Nov Dic

    ─●─ Mario  ─●─ Laura  ─●─ Gianni  ─●─ Sara
```

Il grafico mostra chiaramente:
- **Laura** costantemente sopra tutti (linea verde più alta)
- **Gianni** costantemente il più basso (linea arancione)
- **Agosto** è un mese debole per tutti (piccolo calo)
- Trend generale di crescita per tutti

## Risposte Domande di Analisi

1. **Top performer (totale annuo)**:
   - Mario: €605.000
   - **Laura: €737.000** ⭐ (vincitore)
   - Gianni: €504.000
   - Sara: €654.000
   
   **Laura** è la top performer con €737k

2. **Trend di crescita più costante**:
   - **Laura**: crescita quasi monotona, solo 2 cali leggeri
   - Mario: 3 cali (Mar, Giu, Ago)
   - Sara: 2 cali (Mar, Ago)
   - Gianni: volatilità maggiore
   
   **Laura** ha il trend più costante

3. **Mese con calo generale**:
   - **Agosto** mostra calo per tutti:
     - Mario: -2.000 vs Lug
     - Laura: -7.000 vs Lug
     - Gianni: -3.000 vs Lug
     - Sara: -3.000 vs Lug
   
   Tipico calo estivo (vacanze)

4. **Gap Dicembre (migliore vs peggiore)**:
   - Migliore: Laura €72.000
   - Peggiore: Gianni €47.000
   - **Differenza: €25.000** (53% in più)

5. **Maggior crescita % Gen→Dic**:
   - Mario: da €45k a €59k = **+31,1%** ⭐
   - Laura: da €52k a €72k = +38,5%** ⭐⭐ (vincitore!)
   - Gianni: da €38k a €47k = +23,7%
   - Sara: da €48k a €65k = +35,4%
   
   **Laura** anche qui: +38,5% (€20k in valore assoluto)

6. **Venditore più stabile (minor variabilità)**:
   
   Calcolo deviazione standard (approssimativa):
   - Mario: ~€3.500-4.000
   - Laura: ~€5.500-6.000
   - **Gianni: ~€2.500-3.000** ⭐ (più stabile)
   - Sara: ~€4.500-5.000
   
   **Gianni** è il più stabile (purtroppo anche il più basso)
   Laura ha più variabilità ma sempre alta

## Insight Manageriali

**Decisioni da prendere**:

1. **Bonus annuale**: 
   - **Laura** merita il bonus principale
   - Sara seconda scelta (buone performance costanti)

2. **Coaching necessario**:
   - **Gianni** necessita supporto (sempre sotto 50k)
   - Analizzare perché performance così inferiori

3. **Best practices**:
   - Intervistare Laura: qual è il suo metodo?
   - Condividere tecniche vincenti con il team

4. **Agosto planning**:
   - Pianificare meglio periodo estivo
   - Tutti calano → opportunità miglioramento

5. **Potenziale**:
   - Mario e Sara in crescita costante → incoraggiare
   - Gianni stabile ma basso → serve cambio strategia

## Formule Utili (Bonus)

**Colonna F - Totale Annuo** (in F1):
```
=SOMMA(B2:B13)
```

**Colonna G - Media Mensile**:
```
=MEDIA(B2:B13)
```

**Colonna H - Deviazione Standard** (volatilità):
```
=DEV.ST(B2:B13)
```

**Cella F14 - Crescita % Gen→Dic**:
```
=((B13-B2)/B2)*100
```

</details>

---

## 🚀 Varianti (Bonus)

Prova queste estensioni:

### Variante A: Aggiungi Media Mobile
- Crea colonna "Laura Media Mobile 3 mesi"
- Formula: `=MEDIA(B2:B4)` trascinata
- Aggiungi al grafico come quinta linea tratteggiata
- Smoothing per identificare trend meglio

### Variante B: Focus Top 2
- Crea grafico separato: solo Laura e Sara
- Aggiungi etichette dati su ogni punto
- Calcola gap mensile Laura-Sara
- Quando Sara è stata più vicina?

### Variante C: Ranking Mensile
- Crea tabella con ranking (1-4) per ogni mese
- Conta quante volte ogni venditore è stato 1°, 2°, 3°, 4°
- Grafico a colonne impilate: distribuzione posizioni

### Variante D: Target vs Actual
- Aggiungi riga "Target" = 55.000 per tutti
- Linea tratteggiata grigia per target
- Evidenzia chi supera/non raggiunge target
- Calcola % raggiungimento target per venditore

### Variante E: Grafico Area Impilata
- Converti grafico in "Area impilata"
- Mostra contributo di ogni venditore al totale team
- Calcola vendite totali team per mese
- Analizza evoluzione composizione team

---

## 📚 Concetti Chiave Appresi

✅ Grafici a linee multiple per confronti  
✅ Scelta palette colori distinguibili  
✅ Uso di marcatori per data point  
✅ Analisi trend temporali individuali  
✅ Identificazione pattern stagionali  
✅ Valutazione performance comparative  
✅ Calcolo metriche di volatilità  

---

**Esercizio Precedente**: [Esercizio 5 - Colonne Raggruppate](esercizio_05_colonne_raggruppate.md)  
**Prossimo Esercizio**: [Esercizio 7 - Grafico Combinato](esercizio_07_combinato_doppio.md)
