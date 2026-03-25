# Esempio 7: Dashboard KPI con Indicatori

**Livello**: 🔴 Avanzato  
**Tipo grafico**: Gauge, KPI Cards, Sparkline combinati  
**Obiettivo**: Creare dashboard esecutiva compatta e visuale

---

## Scenario

Dashboard direzionale con KPI principali:
- Performance vendite
- Qualità servizio
- Efficienza operativa
- Soddisfazione cliente

---

## Dati da Inserire

### Foglio "Dati_KPI"

```
Metrica	Valore_Attuale	Obiettivo	Minimo	Massimo	Trend_12M
Vendite (€k)	875	1000	0	1200	780,795,810,825,840,855,870,885,900,890,875,890
Margine %	24,5	25,0	0	100	22,22.5,23,23.5,24,24.2,24.5,24.8,25,24.8,24.5,24.6
NPS (1-100)	72	75	0	100	68,69,70,71,72,73,74,72,71,72,72,73
Uptime %	99,2	99,5	0	100	98.5,99,99.2,99.5,99.8,99.9,99.5,99.2,98.8,99,99.2,99.4
Lead Time (gg)	3,2	2,5	0	10	4.5,4.2,4,3.8,3.6,3.5,3.4,3.3,3.2,3.1,3.2,3.1
Conversione %	4,8	5,0	0	100	3.8,4,4.2,4.3,4.5,4.6,4.7,4.8,4.9,4.8,4.8,4.9
```

---

## Parte A: KPI Cards Base

### Layout Dashboard

```
┌─────────────────────────────────────────────────────┐
│  🎯 DASHBOARD KPI - MARZO 2026                      │
├──────────────┬──────────────┬──────────────┬────────┤
│  📊 VENDITE  │  💰 MARGINE  │  😊 NPS      │ ⚙️ OPS │
│              │              │              │        │
│  €875k/1000k │  24.5%/25%   │  72/75       │ 99.2% │
│  ████████░░  │  ███████████░│  ██████████░ │ █████░│
│  88%         │  98%         │  96%         │ 99.7% │
│  ───────╱    │  ────────    │  ─╱──        │ ──╲   │
└──────────────┴──────────────┴──────────────┴────────┘
```

### Setup Foglio "Dashboard"

#### Riga 1: Titolo
Unisci celle A1:H1:
- Testo: `🎯 DASHBOARD KPI - MARZO 2026`
- Font: 18pt, Grassetto
- Allineamento: Centro
- Sfondo: Blu scuro (#1155CC)
- Testo: Bianco
- Altezza: 50px

#### Righe 3-10: Cards KPI

**Card 1: Vendite (Colonne A-B)**

Cella A3:
```
📊 VENDITE
```
Grassetto, 14pt

Cella A4:
```
€875k / €1000k
```
12pt

Cella A5 (Progress Bar con Sparkline):
```
=SPARKLINE(875/1000; {
  "charttype", "bar";
  "max", 1;
  "color1", IF(875>=1000, "green", IF(875>=800, "orange", "red"))
})
```

Cella A6 (Percentuale):
```
=B2/C2
```
Formatta come %: `88%`
Formattazione condizionale:
- Verde se ≥100%
- Arancione se 80-99%
- Rosso se <80%

Cella A7 (Trend Sparkline):
```
=SPARKLINE(SPLIT(F2; ","); {"linewidth", 2; "color", "blue"})
```

**Nota**: Colonna F contiene trend separato da virgole, va splittato.

### Automatizzare con SPLIT

**Metodo migliore**: Crea colonne helper (nascoste) con valori mensili separati.

**Foglio "Dati_Trend"** (nascosto):
```
	A	B	C	D	E	F	...	M
2	780	795	810	825	840	855	...	890  (Vendite)
3	22	22.5	23	23.5	24	24.2	...	24.6 (Margine)
```

**Sparkline in Dashboard**:
```
=SPARKLINE(Dati_Trend!A2:L2; {"linewidth", 2; "color", "blue"})
```

---

## Parte B: Gauge Simulato con Ciambella

### Gauge per Vendite

**Foglio Helper "Gauge_Vendite"**:
```
	A	B
1	Stato	Valore
2	Raggiunto	875
3	Rimanente	125
```

Formula B3: `=MAX(0; Dati_KPI!C2 - Dati_KPI!B2)`

### Grafico Ciambella

1. Seleziona A1:B3
2. Inserisci → Grafico → Ciambella
3. Editor → Personalizza:
   - Foro: 60%
   - Angolo iniziale: 270° (inizia dal basso)
   - Raggiunto: Verde (#34A853)
   - Rimanente: Grigio chiaro (#E0E0E0)
4. Nascondi legenda
5. Dimensione: 150x150px

### Etichetta Centrale

**Metodo 1: Casella di Testo Sovrapposta**
1. Inserisci → Disegno → Casella testo
2. Testo:
   ```
   875k
   88%
   ```
3. Centra sopra il grafico
4. Sfondo trasparente

**Metodo 2: Cell con Valore**
Posiziona cella con formula sopra il grafico (oggetto flottante trasparente).

---

## Parte C: Gauge con Zona Colorata (Semaforizzazione)

### Gauge NPS (Net Promoter Score)

**Logica zone**:
- 0-50: Rosso (Critico)
- 51-70: Giallo (Da migliorare)
- 71-85: Verde (Buono)
- 86-100: Verde scuro (Eccellente)

### Setup Dati

**Foglio "Gauge_NPS"**:
```
	A	B
1	Zona	Valore
2	Critico	50
3	Migliorare	20
4	Buono	15
5	Eccellente	15
6	Attuale	72
```

**Nota**: Righe 2-5 sommano a 100 (zone cumulative)

### Grafico Ciambella Multi-Zona

1. Seleziona A1:B5 (solo zone)
2. Ciambella con colori:
   - Rosso (#EA4335)
   - Giallo (#FBBC04)
   - Verde (#34A853)
   - Verde scuro (#0F9D58)
3. Foro: 70%

### Indicatore Valore Attuale

**Metodo avanzato**: Sovrapponi un marker

**Calcolo angolo**:
```
Valore: 72
Posizione angolare: (72/100) * 360° = 259,2°
```

**Soluzione semplice**: Casella testo con freccia:
```
→ 72
```
Posizionata alla giusta angolazione (manuale).

**Soluzione Google Apps Script**: Grafico gauge nativo (vedi Esempio 7 - Modulo 7.6).

---

## Parte D: KPI Card Completa Templata

### Template Riutilizzabile

**Struttura Cella** (esempio A3:B10):

```
┌─────────────────────┐
│ A3  📊 VENDITE      │  ← Titolo
├─────────────────────┤
│ A4  Valore / Target │  ← Valori
├─────────────────────┤
│ A5  ███████████░░░  │  ← Progress bar (Sparkline)
├─────────────────────┤
│ A6  88%             │  ← Percentuale (colorato)
├─────────────────────┤
│ A7  vs Mese Prec.   │  ← Confronto
│     +5.2% ▲         │  ← Delta con freccia
├─────────────────────┤
│ A8  ───────╱────    │  ← Trend 12M (Sparkline)
├─────────────────────┤
│ A9  Ultimo agg:     │  ← Timestamp
│     24/03 15:30     │
└─────────────────────┘
```

### Formule Template

**A3** (Titolo): Testo statico

**A4** (Valore/Target):
```
=TESTO(Dati_KPI!B2; "€#.##0k") & " / " & TESTO(Dati_KPI!C2; "€#.##0k")
```

**A5** (Progress bar):
```
=SPARKLINE(Dati_KPI!B2/Dati_KPI!C2; {
  "charttype", "bar"; 
  "max", 1; 
  "color1", IF(B2>=C2, "#34A853", IF(B2>=C2*0.8, "#FBBC04", "#EA4335"))
})
```

**A6** (Percentuale):
```
=Dati_KPI!B2/Dati_KPI!C2
```
Formattazione condizionale (vedi sopra)

**A7** (Delta vs precedente):
```
=((B2-B_prec)/B_prec)
```
Con formattazione:
```
=TESTO(A7; "+0.0%;-0.0%") & " " & SE(A7>0; "▲"; SE(A7<0; "▼"; "─"))
```

**A8** (Trend):
```
=SPARKLINE(Dati_Trend!A2:L2; {
  "charttype", "line";
  "linewidth", 2;
  "color", "blue"
})
```

**A9** (Timestamp):
```
="Agg: " & TESTO(ADESSO(); "DD/MM HH:MM")
```

---

## Parte E: Dashboard Completa con Layout

### Grid Layout (Vista Completa)

```
Row 1: [Titolo Dashboard - Unito A1:H1]

Row 3-10:  KPI Cards
┌─────────┬─────────┬─────────┬─────────┐
│ Vendite │ Margine │   NPS   │  Uptime │
│  Card   │  Card   │  Card   │  Card   │
└─────────┴─────────┴─────────┴─────────┘
  A-B       C-D       E-F       G-H

Row 12-20: Grafici Dettaglio
┌──────────────────┬──────────────────┐
│  Trend Vendite   │  Composizione    │
│  (Linee)         │  Margine (Torta) │
└──────────────────┴──────────────────┘
  A-D                E-H

Row 22-30:
┌──────────────────┬──────────────────┐
│  Performance     │  Alert Summary   │
│  Team (Colonne)  │  (Tabella)       │
└──────────────────┴──────────────────┘
```

### Formattazione Globale

**Colori tema**:
- Primario: Blu (#1155CC)
- Successo: Verde (#34A853)
- Warning: Arancione (#FBBC04)
- Errore: Rosso (#EA4335)
- Neutro: Grigio (#9E9E9E)

**Bordi KPI Cards**:
- Bordo esterno: Spesso grigio
- Ombra: Effetto 3D con celle grigie offset

**Icone**:
- Emoji Unicode (📊 💰 😊 ⚙️ 🎯 📈 📉 ✅ ⚠️)
- Oppure: Google Material Icons (tramite Apps Script)

---

## Parte F: Alert e Notifiche Visive

### Sistema Alerts

**Foglio "Alerts"**:
```
Metrica	Status	Messaggio
Vendite	⚠️	Sotto obiettivo 12% - Azione richiesta
Margine	✅	In linea con target
NPS	⚠️	Calo rispetto a mese precedente
Uptime	✅	Performance eccellente
```

**Formula Status**:
```
=SE(B2/C2<0.8; "🔴 Critico"; SE(B2/C2<0.95; "⚠️ Attenzione"; "✅ OK"))
```

### Tabella Alert in Dashboard

Inserisci tabella formattata nella sezione bassa:

**Formattazione condizionale**:
- Riga con 🔴: Sfondo rosso chiaro
- Riga con ⚠️: Sfondo giallo chiaro
- Riga con ✅: Sfondo verde chiaro (o nascosta)

---

## Esercizi Pratici

### Esercizio 1: Dashboard Personalizzabile

Aggiungi dropdown per selezionare periodo:
- Ultimo mese
- Ultimo trimestre
- Anno corrente
- Custom

Usa QUERY o FILTER per aggiornare dati dinamicamente.

### Esercizio 2: Drill-Down Interattivo

Rendi le KPI cards cliccabili (link a fogli dettaglio):
- Click "Vendite" → Foglio analisi vendite dettagliata
- Click "NPS" → Foglio feedback clienti

**Metodo**: Inserisci → Link nelle celle

### Esercizio 3: Real-Time Dashboard

Connetti a Google Forms per input dati real-time:
- Form per inserimento vendite giornaliere
- Dashboard si aggiorna automaticamente

---

## Best Practice Dashboard KPI

✓ **Visual Hierarchy**: KPI più importanti in alto/sinistra  
✓ **Colori semantici**: Verde=buono, Rosso=critico  
✓ **Comparazione sempre**: Valore + Target + % completamento  
✓ **Trend visibili**: Sparkline per contesto storico  
✓ **Aggiornamento chiaro**: Timestamp ultimo refresh  
✓ **Alerts visivi**: Evidenzia solo eccezioni  
✗ **Evita overload**: Max 8-10 KPI principali  
✗ **No falsa precisione**: Arrotonda a 1-2 decimali  
✗ **Non nascondere problemi**: Rendi le criticità evidenti  

---

## Automazione con Google Apps Script (Bonus)

### Auto-Refresh Dashboard

```javascript
function refreshDashboard() {
  var ss = SpreadsheetApp.getActiveSpreadsheet();
  var dashSheet = ss.getSheetByName("Dashboard");
  
  // Aggiorna timestamp
  dashSheet.getRange("H1").setValue("Agg: " + new Date());
  
  // Ricalcola metriche
  ss.getSheetByName("Dati_KPI").getDataRange().getValues();
  
  // Log
  Logger.log("Dashboard aggiornata: " + new Date());
}

// Trigger automatico ogni 1 ora
function createTrigger() {
  ScriptApp.newTrigger("refreshDashboard")
    .timeBased()
    .everyHours(1)
    .create();
}
```

---

## Checklist Dashboard Professionale

- [ ] KPI chiari e misurabili
- [ ] Valori confrontati con target/benchmark
- [ ] Visualizzazione immediata (verde/rosso)
- [ ] Trend storico visibile (sparkline)
- [ ] Layout pulito e organizzato
- [ ] Colori consistenti e significativi
- [ ] Timestamp ultimo aggiornamento
- [ ] Alert per eccezioni evidenziati
- [ ] Dimensioni ottimizzate per schermo
- [ ] Test su diversi dispositivi (mobile-friendly)

---

## Risorse Aggiuntive

**Template Google Fogli**:
- Cerca "KPI Dashboard Template" in Google Templates
- CloneUna copia e personalizza

**Add-on Utili**:
- **Awesome Table**: Dashboard interattive
- **Supermetrics**: Connessione a fonti dati esterne
- **Data Studio**: Per dashboard più avanzate (ora Looker Studio)

**Livello successivo**: Google Data Studio / Looker Studio per dashboard pubbliche e interattive avanzate.
