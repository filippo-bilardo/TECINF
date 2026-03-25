# Esercizio 3: Budget Familiare

**Livello**: 🟢 Base  
**Tipo grafico**: Torta (Pie Chart)  
**Tempo stimato**: 15 minuti  
**Competenze**: Proporzioni, percentuali, grafico a torta, formattazione

---

## 🎯 Obiettivo

Creare un grafico a torta per visualizzare la distribuzione del budget familiare mensile tra diverse categorie di spesa.

## 📖 Scenario

Stai pianificando il budget familiare e vuoi visualizzare come si distribuisce la spesa mensile totale di €3.200. Questo ti aiuterà a identificare le voci più importanti e possibili aree di ottimizzazione.

## 📊 Dati Forniti

Copia questa tabella nel tuo Google Foglio (celle A1:B8):

```
Categoria	Importo
Affitto	950
Alimentari	520
Trasporti	280
Utenze	180
Svago	350
Salute	220
Risparmio	450
Varie	250
```

**Verifica**: La somma dovrebbe essere €3.200

---

## ✅ Requisiti

Crea un grafico a torta che rispetti questi criteri:

1. **Tipo**: Grafico a torta
2. **Dati**: Tutte le 7 categorie + Varie
3. **Titolo**: "Budget Familiare Mensile - €3.200"
4. **Fette**: Ordinate dalla più grande alla più piccola
5. **Etichette**: 
   - Mostra nome categoria + percentuale
   - Posizione: Esterna con linee di collegamento
6. **Fetta principale** (Affitto): "Esplodi" leggermente (distaccata)
7. **Colori**: Palette coordinata e professionale
8. **Legenda**: Visibile a destra o in basso

---

## 🤔 Domande di Analisi

Dopo aver creato il grafico, rispondi:

1. Quale categoria occupa la maggior parte del budget? Che percentuale rappresenta?
2. Le tre categorie principali insieme che % del budget totale rappresentano?
3. C'è equilibrio nella distribuzione o alcune voci dominano?
4. Quanto budget rimane per risparmio e svago combinati?
5. Se dovessi ridurre il budget del 10%, quali categorie considereresti?

---

## 💡 Suggerimenti

- Il grafico a torta è ideale per mostrare proporzioni di un totale
- Max 6-8 categorie per leggibilità (oltre → raggruppa in "Altro")
- Ordina sempre le fette per dimensione (senso orario da ore 12)
- Usa "Esplodi fetta" con moderazione (solo la più importante)
- Percentuali sono essenziali: sempre visibili!

---

<details>
<summary><strong>📝 Soluzione - Clicca per Espandere</strong></summary>

## Passi Dettagliati

### 1. Preparazione Dati
- Copia dati in A1:B8
- Verifica somma: =SOMMA(B2:B8) → dovrebbe essere 3200

**Formula percentuali** (opzionale, colonna C):
```
C2: =B2/SOMMA($B$2:$B$8)
```
Formatta come percentuale.

### 2. Creazione Grafico
1. Seleziona **solo A1:B8** (non serve colonna %)
2. **Inserisci → Grafico**
3. Tipo: **Torta** (dovrebbe essere automatico)
4. Se no: Editor → Configurazione → Tipo → Grafico a torta

### 3. Ordinamento Fette

**Editor → Configurazione**:
1. Scorri fino a "Ordina per"
2. Seleziona: **Importo**
3. Direzione: **Decrescente**

**Risultato**: Affitto (più grande) inizia da ore 12, senso orario decrescente.

### 4. Personalizzazione Titolo

**Editor → Personalizza → Titolo grafico**:
- Testo: `Budget Familiare Mensile - €3.200`
- Font: 14pt, grassetto
- Posizione: Centro (sopra il grafico)

### 5. Personalizzazione Etichette

**Sezione "Etichette fetta"**:
1. **Mostra**: Categoria + Percentuale
   - Formato etichetta: `%l: %p` oppure seleziona preset
2. **Posizione**: Esterna (fuori dal cerchio)
3. **Linee di collegamento**: Sì
4. **Font**: 10pt, nero
5. **Formato percentuale**: 1 decimale (es: 29,7%)

**Esempio etichetta**: `Affitto: 29,7%`

### 6. "Esplodi" Fetta Principale

1. **Clicca sulla fetta "Affitto"** nel grafico
2. Oppure: Editor → Personalizza → Fetta
3. Seleziona: **Affitto**
4. **Distanza dal centro**: 0,1-0,15 (10-15%)

**Effetto**: La fetta Affitto si stacca leggermente, attirando attenzione.

### 7. Personalizzazione Colori

**Opzione A - Colori Automatici**:
Lascia i colori di default di Google (già coordinati).

**Opzione B - Personalizzati**:
Clicca su ogni fetta e assegna colori tematici:
- Affitto: Blu scuro (#1155CC) - casa
- Alimentari: Verde (#34A853) - cibo
- Trasporti: Giallo (#FBBC04) - movimento
- Utenze: Azzurro (#4285F4) - servizi
- Svago: Viola (#9C27B0) - divertimento
- Salute: Rosso (#EA4335) - salute
- Risparmio: Verde scuro (#0F9D58) - soldi
- Varie: Grigio (#9E9E9E) - neutro

**Opzione C - Gradazioni**:
Usa gradazioni dello stesso colore (es: blu chiaro → blu scuro).

### 8. Legenda

**Sezione "Legenda"**:
- Posizione: **Destra** (default) o **Basso**
- Font: 10pt
- Mostra: Tutte le categorie

**Nota**: Con etichette esterne, la legenda è meno critica ma utile per riferimento.

### 9. Stile Finale

- Sfondo: Bianco
- Bordo: Nessuno
- Dimensione: Adegua perché tutte le etichette siano leggibili

### Risultato Atteso

```
Budget Familiare Mensile - €3.200

         Risparmio
          14,1%
                    ╱────╲
     Svago         │      │
     10,9%        │  29,7% │ ← Affitto (esplosa)
              ╱──│  Affitto│──╮
   Varie    ╱    │        │   │
   7,8%    │     ╲────────╱   │ Alimentari
          │                   │ 16,3%
          │                   │
  Salute  │                  ╱  Trasporti
   6,9%   │                 │    8,8%
          │                 │
          ╰────────╯────────╯
                │
            Utenze
            5,6%
```

**Ordine fette (senso orario da ore 12)**:
1. Affitto: 29,7% (€950) - distaccata
2. Alimentari: 16,3% (€520)
3. Risparmio: 14,1% (€450)
4. Svago: 10,9% (€350)
5. Trasporti: 8,8% (€280)
6. Varie: 7,8% (€250)
7. Salute: 6,9% (€220)
8. Utenze: 5,6% (€180)

## Risposte Domande di Analisi

1. **Categoria principale**:
   - **Affitto**: €950 (29,7% del budget)
   - Quasi 1/3 del budget totale
   - Tipico per famiglie in affitto

2. **Top 3 categorie**:
   - Affitto (29,7%) + Alimentari (16,3%) + Risparmio (14,1%) = **60,1%**
   - Oltre metà budget concentrato su 3 voci
   - Indica che sono le priorità familiari

3. **Equilibrio distribuzione**:
   - **Sbilanciato**: Affitto domina (30%)
   - **Medio**: Alimentari, Risparmio, Svago (10-17%)
   - **Piccolo**: Trasporti, Salute, Utenze, Varie (<10%)
   - Pattern comune: housing è la spesa maggiore

4. **Risparmio + Svago**:
   - Risparmio: €450 (14,1%)
   - Svago: €350 (10,9%)
   - **Totale: €800 (25%)**
   - Buon equilibrio tra godersi la vita e pianificare il futuro

5. **Riduzione 10% (€320)**:
   **Opzioni**:
   - **Svago**: -€100 (da 350 a 250, ancora accettabile)
   - **Alimentari**: -€100 (da 520 a 420, più attenzione agli acquisti)
   - **Varie**: -€100 (da 250 a 150, tagliare spese non essenziali)
   - **Restanti**: -€20 distribuiti

   **Da evitare**:
   - ❌ Affitto (fisso, non negoziabile facilmente)
   - ❌ Utenze (fisso, bisogno essenziale)
   - ❌ Salute (priorità)
   - ⚠️ Risparmio (meglio preservarlo)

**Insight**: Il budget è ben strutturato con priorità chiare. C'è spazio per ottimizzare Svago e Alimentari senza compromettere qualità vita. Il 14% destinato a risparmio è sano.

</details>

---

## 🚀 Varianti (Bonus)

### Variante A: Grafico a Ciambella
Cambia tipo da Torta a **Ciambella**:
- Lascia spazio centrale per totale €3.200
- Aggiungi casella testo centrata con totale

### Variante B: Raggruppa Voci Piccole
Categorie <5% raggruppa in "Altro":
- Utenze (5,6%) → Altro
- Varie già piccole

Risultato: 7 fette invece di 8, più leggibile.

### Variante C: Confronto Obiettivo
Aggiungi colonna "Budget_Ideale":
```
Affitto	950	900	(-50)
Alimentari	520	450	(-70)
...
Risparmio	450	600	(+150)
```
Crea due grafici a torta affiancati (Reale vs Ideale).

### Variante D: Sparkline Bar
Invece della torta, usa Sparkline bar per ogni categoria:
```
Affitto    ██████████████░░ 29,7%
Alimentari ████████░░░░░░░░ 16,3%
...
```

---

## 📚 Concetti Chiave Appresi

✅ Grafici a torta per proporzioni  
✅ Ordinamento fette per dimensione  
✅ Uso strategico di "Esplodi fetta"  
✅ Etichette con percentuali  
✅ Interpretazione budget e priorità  
✅ Analisi composizione totale  

---

**Esercizio Precedente**: [Esercizio 2 - Trend Temperature](esercizio_02_linee_trend.md)  
**Prossimo Esercizio**: [Esercizio 4 - Top Prodotti](esercizio_04_barre_ranking.md)
