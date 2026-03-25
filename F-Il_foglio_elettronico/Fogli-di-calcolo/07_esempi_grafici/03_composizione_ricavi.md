# Esempio 3: Composizione Ricavi per Categoria

**Livello**: 🟢 Base  
**Tipo grafico**: Torta e Ciambella  
**Obiettivo**: Visualizzare proporzioni e composizione

---

## Dati da Inserire

```
Categoria	Ricavi	Percentuale
Elettronica	285000	35%
Abbigliamento	195000	24%
Casa e Giardino	162000	20%
Sport	114000	14%
Libri	57000	7%
```

**Nota**: La colonna Percentuale è calcolata automaticamente, ma puoi inserirla per verifica.

Formula per colonna C:
```
=B2/SOMMA($B$2:$B$6)
```

---

## Parte A: Grafico a Torta

### Creazione Base

1. **Seleziona**: A1:B6 (Categoria e Ricavi)
2. **Inserisci → Grafico**
3. **Tipo**: Torta

### Personalizzazione

#### Titolo
- Testo: `Distribuzione Ricavi per Categoria 2026`
- Font: 14pt, Grassetto

#### Fette
- **Ordina**: Da più grande a più piccola (senso orario da ore 12)
  - Editor → Configurazione → Ordina: Decrescente per valore
  
#### Colori Personalizzati
- Elettronica: Blu (#4285F4)
- Abbigliamento: Verde (#34A853)
- Casa e Giardino: Giallo (#FBBC04)
- Sport: Arancione (#FF6D01)
- Libri: Rosso (#EA4335)

#### Etichette
- Mostra: Categoria + Percentuale
- Posizione: Esterna con linee di collegamento
- Font: 11pt

#### Evidenzia Categoria Principale
1. Clicca sulla fetta "Elettronica"
2. Editor → Personalizza → Fetta
3. Distanza dal centro: 0,1 (effetto "esploso")

### Risultato Atteso
Torta colorata con Elettronica (35%) leggermente staccata, evidenziando che rappresenta oltre un terzo dei ricavi.

---

## Parte B: Grafico a Ciambella

### Creazione

1. **Copia il grafico a torta** oppure ricrea da zero
2. **Editor → Configurazione**
3. **Tipo grafico**: Ciambella

### Personalizzazione Ciambella

#### Dimensione Foro
- Foro: 50% (default)
- Prova: 40% (ciambella più spessa) o 60% (più sottile)

#### Testo Centrale
**Trucco**: Aggiungi casella di testo sopra il grafico

1. Inserisci → Disegno
2. Casella di testo con:
   ```
   Totale Ricavi
   €813.000
   ```
3. Centra il testo: Grassetto, 16pt/12pt
4. Sfondo trasparente
5. Posiziona al centro della ciambella

#### Rotazione
- Ruota: -90° (inizia dall'alto)
- Effetto: Prima categoria parte dalle ore 12

---

## Parte C: Grafico a Torta 3D (Sconsigliato)

**⚠️ Attenzione**: I grafici 3D distorcono la percezione delle proporzioni.

**Perché evitarlo**:
- Fette in prospettiva sembrano più grandi/piccole
- Difficile confrontare fette simili
- Appare meno professionale

**Se proprio necessario**: Menu → Editor → Personalizza → 3D: Attivo

---

## Analisi dei Dati

### Insight da Evidenziare

1. **Categoria dominante**: Elettronica (35%) - oltre 1/3 dei ricavi
2. **Top 2 categorie**: Elettronica + Abbigliamento = 59% (quasi 2/3)
3. **Categoria più piccola**: Libri (7%) - possibile area di crescita
4. **Distribuzione**: Relativamente equilibrata, nessuna categoria sopra 40%

### Calcoli Aggiuntivi

#### Ricavi Cumulativi
Aggiungi colonna D:
```
=SOMMA($B$2:B2)
```

#### Analisi Pareto (80/20)
Quali categorie rappresentano l'80% dei ricavi?
```
Elettronica + Abbigliamento + Casa = 79%
→ 3 categorie su 5 generano quasi l'80%
```

---

## Varianti da Provare

### Variante 1: Grafico a Ciambella Multipla

**Confronto Anno su Anno**

Dati:
```
Categoria	2025	2026
Elettronica	260000	285000
Abbigliamento	185000	195000
Casa e Giardino	155000	162000
Sport	105000	114000
Libri	52000	57000
```

**Risultato**: Due ciambelle concentriche (interna=2025, esterna=2026)

**Come fare in Google Fogli**:
- Crea due grafici a ciambella separati
- Sovrapponi manualmente (regola trasparenza)

### Variante 2: Barre Orizzontali (Alternativa)

Per molte categorie (>6), le barre sono più leggibili delle torte.

1. Seleziona A1:B6
2. Grafico a barre orizzontali
3. Ordina per valore decrescente
4. Aggiungi etichette dati con %

---

## Esercizi Pratici

### Esercizio 1: Soglia 5%
Raggruppa categorie sotto 5% in "Altro":
```
Categoria	Ricavi
Elettronica	285000
Abbigliamento	195000
Casa e Giardino	162000
Sport	114000
Altro	57000
```

### Esercizio 2: Subcategorie
Espandi "Elettronica" in sotto-categorie:
- Smartphone: 125000
- Computer: 95000
- Accessori: 65000

Crea grafico a torta annidato (drill-down).

### Esercizio 3: Trend Mensile
Traccia l'evoluzione % di ogni categoria nei 12 mesi con grafico ad area in pila 100%.

---

## Best Practice Grafici a Torta

✓ **Max 6-7 categorie** (oltre → usa barre)  
✓ **Ordina per dimensione** (più grande a ore 12, senso orario)  
✓ **Mostra percentuali** sempre  
✓ **Esplodi la fetta principale** per enfasi  
✓ **Colori distinti** facilmente distinguibili  
✗ **Evita torte 3D** (distorcono)  
✗ **Non usare per trend temporali** (usa linee/area)  
✗ **Non confrontare più torte** (difficile comparazione)  

---

## Domande di Riflessione

1. Quando una torta è preferibile a barre orizzontali?
2. Come comunicare che Elettronica è strategica?
3. Libri al 7%: è un problema o un'opportunità?
4. Quale layout è più efficace: torta o ciambella?

---

## Checklist Grafico Torta Professionale

- [ ] Max 6 categorie (altro raggruppato in "Altro")
- [ ] Ordinato per dimensione
- [ ] Percentuali visibili e leggibili
- [ ] Colori accessibili e distinti
- [ ] Categoria principale evidenziata (esplosa)
- [ ] Titolo descrittivo
- [ ] Legenda chiara (o etichette dirette)
- [ ] Nessun effetto 3D
- [ ] Dimensione adeguata (min 300x300px)
