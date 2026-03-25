# Esempio 1: Vendite Mensili - Grafico a Colonne e Linee

**Livello**: 🟢 Base  
**Tipo grafico**: Colonne e Linee  
**Obiettivo**: Visualizzare l'andamento delle vendite mensili e identificare trend

---

## Dati da Inserire

Copia questa tabella nel tuo Google Foglio (a partire dalla cella A1):

```
Mese	Vendite	Obiettivo
Gennaio	48500	45000
Febbraio	52300	45000
Marzo	51800	45000
Aprile	55200	50000
Maggio	58900	50000
Giugno	62100	50000
Luglio	59800	55000
Agosto	54300	55000
Settembre	63400	55000
Ottobre	67200	60000
Novembre	71500	60000
Dicembre	75800	60000
```

**Nota**: Usa il tabulatore (Tab) per separare le colonne quando copi.

---

## Parte A: Grafico a Colonne

### Passi per la Creazione

1. **Seleziona i dati**: A1:B13 (Mese e Vendite)
2. **Inserisci grafico**: Menu → Inserisci → Grafico
3. **Verifica tipo**: Dovrebbe essere automaticamente "Grafico a colonne"

### Personalizzazione

**Editor Grafico → Tab Personalizza**:

#### Titolo Grafico
- Testo: `Vendite Mensili 2026`
- Font: Arial, 16pt, Grassetto
- Allineamento: Centro

#### Asse Orizzontale (X)
- Titolo: `Mese`
- Formato etichette: Ruota 45° (se troppo lunghe)

#### Asse Verticale (Y)
- Titolo: `Vendite (€)`
- Formato numeri: Valuta arrotondata
- Min: 0 (automatico)
- Max: 80000

#### Serie "Vendite"
- Colore: Blu (#1155CC)
- Etichette dati: Nessuna (opzionale)

#### Stile
- Sfondo: Bianco
- Bordo: Grigio chiaro
- Linee griglia: Orizzontali (principali)

### Risultato Atteso

Un grafico a colonne blu che mostra chiaramente la crescita delle vendite da gennaio a dicembre, con un'accelerazione nel secondo semestre.

---

## Parte B: Grafico a Linee con Obiettivo

### Passi per la Creazione

1. **Seleziona dati**: A1:C13 (Mese, Vendite, Obiettivo)
2. **Inserisci grafico**: Menu → Inserisci → Grafico
3. **Cambia tipo**: Editor → Configurazione → Tipo di grafico → Linee

### Personalizzazione

#### Titolo
- Testo: `Vendite vs Obiettivo 2026`

#### Serie "Vendite"
- Colore: Blu scuro (#1155CC)
- Spessore linea: 3px
- Marcatori: Cerchi, dimensione 6
- Etichette: Nessuna

#### Serie "Obiettivo"
- Colore: Rosso (#CC0000)
- Spessore linea: 2px
- Tipo linea: Tratteggiata
- Marcatori: Nessuno
- Etichette: Nessuna

#### Linea di Tendenza (solo su Vendite)
1. Clicca serie "Vendite"
2. Aggiungi linea di tendenza
3. Tipo: Lineare
4. Colore: Blu chiaro, tratteggiata
5. Mostra equazione: No
6. Mostra R²: Opzionale

#### Legenda
- Posizione: In basso
- Font: 11pt

### Risultato Atteso

Due linee che mostrano come le vendite effettive (blu continua) superano costantemente l'obiettivo (rosso tratteggiata), con un gap che aumenta nel tempo.

---

## Parte C: Grafico Combinato (Avanzato)

### Passi per la Creazione

1. **Seleziona dati**: A1:C13
2. **Inserisci grafico**: Menu → Inserisci → Grafico
3. **Tipo**: Editor → Configurazione → Grafico combinato

### Configurazione Serie

#### Serie "Vendite"
- Tipo: Colonne
- Colore: Verde (#34A853)
- Asse: Sinistro

#### Serie "Obiettivo"
- Tipo: Linea
- Colore: Arancione (#FBBC04)
- Spessore: 3px
- Marcatori: Rombi, dimensione 8
- Asse: Sinistro (stessa scala)

### Personalizzazione Avanzata

#### Formattazione Condizionale (opzionale)
Evidenzia le colonne:
- Verde scuro: Mesi sopra obiettivo
- Arancione chiaro: Mesi sotto obiettivo

**Formula**: `=B2>C2` (applica a colonna Vendite)

### Risultato Atteso

Colonne verdi per le vendite con linea arancione dell'obiettivo sovrapposta, permettendo confronto immediato visivo.

---

## Esercizi di Approfondimento

### Esercizio 1: Variazione Percentuale
Aggiungi colonna D con formula:
```
=((B2-B1)/B1)*100
```
Crea grafico a linee per mostrare % crescita mensile.

### Esercizio 2: Analisi Trimestrale
Raggruppa dati per trimestre:
- Q1: Gen-Mar
- Q2: Apr-Giu
- Q3: Lug-Set
- Q4: Ott-Dic

Crea grafico a colonne per confronto trimestrale.

### Esercizio 3: Cumulative
Aggiungi colonna "Vendite Cumulate":
```
=SOMMA($B$2:B2)
```
Crea grafico ad area che mostra accumulo nel tempo.

---

## Domande di Riflessione

1. Quale tipo di grafico comunica meglio il superamento dell'obiettivo?
2. Quando è meglio usare colonne vs linee?
3. Come evidenzieresti il mese con le migliori performance?
4. Cosa suggerisce la linea di tendenza per il futuro?

---

## Varianti da Provare

### Variante 1: Colori Condizionali
Colora le colonne in base alla performance:
- Verde: >110% obiettivo
- Giallo: 100-110% obiettivo
- Rosso: <100% obiettivo

### Variante 2: Annotazioni
Aggiungi caselle di testo sul grafico per evidenziare:
- Mese migliore (Dicembre: +26% vs obiettivo)
- Mese più basso (Gennaio)
- Eventi speciali (campagne marketing)

### Variante 3: Previsione
Estendi la linea di tendenza per 3 mesi futuri.

---

## File da Scaricare

Vuoi il file già pronto? Crea un nuovo Google Foglio e salva come "Vendite_Mensili_2026".

**Link modello**: (Crea il tuo seguendo queste istruzioni!)
