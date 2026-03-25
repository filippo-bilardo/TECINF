# Esempio 2: Confronto Vendite Multi-Anno

**Livello**: 🟢 Base  
**Tipo grafico**: Colonne raggruppate  
**Obiettivo**: Confrontare performance anno su anno

---

## Dati da Inserire

```
Trimestre	2024	2025	2026
Q1	142000	158000	178000
Q2	156000	168000	189000
Q3	148000	162000	175000
Q4	178000	195000	218000
```

---

## Creazione Grafico a Colonne Raggruppate

### Passi Base

1. **Seleziona**: A1:D5
2. **Inserisci → Grafico**
3. **Tipo**: Colonne (raggruppate è il default)

### Personalizzazione

#### Titolo
- Testo: `Analisi Vendite Trimestrali 2024-2026`
- Sottotitolo: `Confronto anno su anno`

#### Colori Serie
- **2024**: Azzurro chiaro (#A4C2F4)
- **2025**: Blu medio (#6D9EEB)
- **2026**: Blu scuro (#1155CC)

**Suggerimento**: Gradazioni dello stesso colore facilitano il confronto temporale.

#### Assi
- **X**: Etichetta "Trimestre", Font 12pt
- **Y**: Etichetta "Vendite (€)", Formato: Valuta breve (es. 150k)

#### Legenda
- Posizione: In alto a destra
- Ordine: Inverti (2026, 2025, 2024) per enfatizzare l'anno corrente

---

## Variante: Colonne In Pila

### Quando Usarla
Per mostrare il totale trimestrale oltre al dettaglio per anno.

### Cambia Tipo
1. Editor grafico → Configurazione
2. Tipo grafico: **Istogramma a colonne in pila**

### Risultato
Colonne uniche per trimestre con segmenti colorati per ogni anno.

---

## Variante: Colonne In Pila 100%

### Quando Usarla
Per mostrare la proporzione di contributo di ogni anno.

**Nota**: In questo caso specifico non ha molto senso (anni diversi), ma utile per categorie che contribuiscono a un totale.

---

## Analisi dei Dati

### Calcoli Aggiuntivi

#### Crescita Anno su Anno
Aggiungi colonna E "Crescita 2025-2026":
```
=((D2-C2)/C2)*100
```

#### Media Trimestrale
Aggiungi riga 6:
```
=MEDIA(B2:B5)
```

#### Migliore Trimestre
```
=MAX(D2:D5)
```

### Grafico Crescita
Crea un secondo grafico a linee con solo la colonna Crescita% per visualizzare il trend di miglioramento.

---

## Esercizio Guidato

### Passo 1: Aggiungi Dati Mensili
Espandi la tabella con dati mensili invece che trimestrali.

### Passo 2: Grafico Linee Multi-Anno
Crea grafico a linee con i 12 mesi per ogni anno (3 linee).

### Passo 3: Evidenzia il Miglior Anno
Rendi la linea 2026 più spessa (4px) e con marcatori più grandi.

---

## Domande di Analisi

1. Quale trimestre mostra la crescita più consistente?
2. Q3 è sempre il trimestre più debole: perché?
3. Come interpreti l'accelerazione in Q4 2026?
4. Qual è il tasso di crescita medio annuale?

---

## Formattazione Professionale

### Tabella Dati
- Intestazioni: Grassetto, sfondo blu, testo bianco
- Righe alternate: Grigio chiaro (#F3F3F3)
- Bordi: Sottili grigi
- Totali: Bordo doppio superiore

### Layout Foglio
```
┌─────────────────────────────┐
│  Tabella Dati (A1:D5)       │
├─────────────────────────────┤
│  Grafico Colonne (A7:H22)   │
├─────────────────────────────┤
│  Statistiche Riepilogo      │
│  - Crescita media           │
│  - Miglior trimestre        │
│  - Totale anno              │
└─────────────────────────────┘
```

---

## Best Practice Confronto Temporale

✓ Usa gradazioni dello stesso colore per timeline  
✓ Ordina le serie cronologicamente  
✓ Evidenzia l'anno più recente  
✓ Mantieni scala Y coerente per confronto equo  
✗ Evita troppi anni (max 3-4)  
✗ Non usare colori casuali
