# Esercitazione 9: Dashboard Vendite Interattiva

**Livello:** 🎯 AVANZATO  
**Tempo stimato:** 90 minuti

---

## Obiettivi

- Creare dashboard di riepilogo con KPI
- Utilizzare formule complesse combinate
- Implementare analisi statistiche avanzate
- Creare report automatici

---

## Dati di Partenza

Crea tabella vendite (almeno 20 righe):

```
A          B           C        D          E          F
Data       Venditore   Regione  Prodotto   Quantità   Prezzo
02/01/26   Mario       Nord     Laptop     2          800
03/01/26   Anna        Sud      Mouse      10         25
04/01/26   Luca        Centro   Tastiera   5          45
05/01/26   Mario       Nord     Monitor    3          350
06/01/26   Sara        Sud      Laptop     1          800
07/01/26   Anna        Sud      Tastiera   8          45
08/01/26   Luca        Centro   Mouse      15         25
09/01/26   Mario       Nord     Monitor    2          350
10/01/26   Sara        Sud      Laptop     3          800
...
```

---

## SEZIONE 1: KPI GENERALI

Crea dashboard in area separata (es. colonne H-J):

```
=== KPI GENERALI ===

Totale Vendite (€)           [formula]
Numero Ordini               [formula]
Valore Medio Ordine         [formula]
Prodotto Più Venduto        [formula]
Regione con Più Vendite     [formula]
```

### Formule

**1. Totale Vendite (€):**
```
=SOMMA(E2:E21*F2:F21)
```
o meglio con colonna G "Importo" = E×F, poi `=SOMMA(G2:G21)`

**2. Numero Ordini:**
```
=CONTA.VALORI(A2:A21)
```

**3. Valore Medio Ordine:**
```
=TotaleVendite/NumeroOrdini
```

**4. Prodotto Più Venduto:**
```
=INDICE(D2:D21;CONFRONTA(MAX(E2:E21);E2:E21;0))
```

**5. Regione con Più Vendite:**
Prima calcola vendite per regione, poi trova max.

---

## SEZIONE 2: Performance Venditori

```
Venditore    Tot Vendite    N° Ordini    Media Ordine    Ranking
Mario        [formula]      [formula]    [formula]       [formula]
Anna         [formula]      [formula]    [formula]       [formula]
Luca         [formula]      [formula]    [formula]       [formula]
Sara         [formula]      [formula]    [formula]       [formula]
```

### Formule

**Tot Vendite per Mario:**
```
=SOMMA.SE(B:B;"Mario";G:G)
```
(assumendo colonna G = Importo)

**N° Ordini:**
```
=CONTA.SE(B:B;"Mario")
```

**Media Ordine:**
```
=TotVendite/NumOrdini
```

**Ranking:**
```
=RANGO(TotVendite;$IntervalloTotVendite;0)
```

---

## SEZIONE 3: Analisi per Regione

```
Regione    Tot Vendite    % su Totale    N° Ordini
Nord       [formula]      [formula]      [formula]
Centro     [formula]      [formula]      [formula]
Sud        [formula]      [formula]      [formula]
```

### Formule

**Tot Vendite Nord:**
```
=SOMMA.SE(C:C;"Nord";G:G)
```

**% su Totale:**
```
=(TotVenditeNord/TotaleGenerale)*100
```

---

## SEZIONE 4: Analisi Temporale

```
=== ANALISI SETTIMANALE ===

Settimana 1 (2-8 Gen)        [formula]
Settimana 2 (9-15 Gen)       [formula]
Crescita % (W2 vs W1)        [formula]
```

### Formule

**Vendite Settimana 1:**
```
=SOMMA.PIÙ.SE(G:G; A:A;">=2/1/2026"; A:A;"<=8/1/2026")
```

**Crescita %:**
```
=((Sett2-Sett1)/Sett1)*100
```

---

## SEZIONE 5: Sistema Target

```
=== OBIETTIVI MENSILI ===

Target Mensile                50.000 €
Vendite Attuali              [formula]
% Raggiungimento             [formula]
Mancano                      [formula]
Giorni Rimanenti            [formula]
Media Giornaliera Necessaria [formula]
Proiezione Fine Mese        [formula]
```

### Formule

**% Raggiungimento:**
```
=(VenditeAttuali/Target)*100
```

**Giorni Rimanenti:**
```
=GIORNO(FINE.MESE(OGGI();0))-GIORNO(OGGI())
```

**Media Giornaliera Necessaria:**
```
=(Target-VenditeAttuali)/GiorniRimanenti
```

**Proiezione Fine Mese:**
```
=VenditeAttuali+(MediaGiornalieraAttuale*GiorniRimanenti)
```

---

## FUNZIONALITÀ AVANZATE

### 1. Grafico a Torta - Vendite per Regione

Seleziona dati regioni → Inserisci → Grafico → Torta

### 2. Grafico a Barre - Top Venditori

Seleziona venditori e totali → Grafico a barre orizzontali

### 3. Grafico a Linee - Trend Vendite Giornaliere

X: Date, Y: Vendite giornaliere

### 4. Formattazione Condizionale

**Target Raggiungimento:**
- Verde: >= 100%
- Giallo: 75-99%
- Rosso: < 75%

**Ranking Venditori:**
- Oro: 1° posto
- Argento: 2° posto
- Bronzo: 3° posto

---

## Criteri di Valutazione

| Criterio | Peso |
|----------|------|
| KPI Generali | 20% |
| Performance Venditori | 20% |
| Analisi Regioni | 20% |
| Analisi Temporale | 15% |
| Target e Proiezioni | 15% |
| Grafici e Presentazione | 10% |

---

*Tempo medio: 80-90 minuti*  
*Difficoltà: ⭐⭐⭐⭐⭐ (5/5)*  
*Utilità: Business Intelligence reale*
