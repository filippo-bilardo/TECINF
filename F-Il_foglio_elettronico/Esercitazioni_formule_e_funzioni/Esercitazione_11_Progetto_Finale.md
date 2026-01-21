# Esercitazione 11: Progetto Finale - Sistema Gestionale E-commerce

**Livello:** 🏆 PROGETTO FINALE  
**Tempo stimato:** 4-6 ore (multi-sessione)

---

## Obiettivi

- Integrare tutte le competenze acquisite
- Creare un sistema multi-foglio complesso
- Automatizzare processi aziendali completi
- Dimostrare padronanza completa dei fogli di calcolo

---

## Struttura del Progetto - 5 Fogli Obbligatori

### FOGLIO 1: Prodotti (Catalogo)

```
Codice  Nome          Categoria    Prezzo  Giacenza  Minimo  Fornitore
P001    Laptop        Elettronica  800     15        5       TechSupply
P002    Mouse         Periferiche  25      50        20      OfficeKit
P003    Tastiera      Periferiche  45      30        10      OfficeKit
P004    Monitor       Elettronica  350     8         5       TechSupply
P005    Webcam        Periferiche  80      12        8       TechSupply
```

**Funzionalità richieste:**
- Alert giacenza bassa (< minimo)
- Valore totale magazzino
- Prodotti più/meno venduti

---

### FOGLIO 2: Ordini Clienti

```
ID   Data      Cliente  Cod.Prod  Quantità  Stato          Spedizione
1    02/01/26  C001     P001      1         Spedito        03/01/26
2    03/01/26  C002     P002      5         In Lavoraz.    -
3    04/01/26  C001     P003      2         Spedito        05/01/26
```

**Funzionalità richieste:**
- Ricerca automatica prezzo prodotto (CERCA.VERT)
- Calcolo totale ordine
- Applicazione sconto cliente
- Verifica disponibilità giacenza
- Alert ordini in ritardo (>3 giorni)

**Colonne calcolate da aggiungere:**
- Prezzo Unitario (da catalogo)
- Sconto % (da anagrafica clienti)
- Totale (Quantità × Prezzo × (1-Sconto))

---

### FOGLIO 3: Clienti (Anagrafica)

```
ID    Nome           Cognome   Email                Città    Sconto%  Tot.Acquisti
C001  Mario          Rossi     m.rossi@email.it     Milano   5%       [calc]
C002  Anna           Verdi     a.verdi@email.it     Roma     0%       [calc]
C003  Luca           Bianchi   l.bianchi@email.it   Torino   10%      [calc]
```

**Funzionalità richieste:**
- Calcolo totale storico acquisti
- Categoria cliente:
  - Bronzo: < 500€ (sconto 0%)
  - Argento: 500-1000€ (sconto 5%)
  - Oro: > 1000€ (sconto 10%)
- Numero ordini effettuati
- Data ultimo acquisto

---

### FOGLIO 4: Dashboard

```
=== KPI GENERALI ===

Vendite Oggi                [formula]
Vendite Mese Corrente       [formula]
Numero Ordini Attivi        [formula]
Valore Medio Ordine         [formula]

=== MAGAZZINO ===

Prodotti Sotto Scorta       [formula]
Valore Magazzino Totale     [formula]
Prodotti da Riordinare      [lista]

=== TOP 5 ===

Prodotti Più Venduti        [grafico]
Clienti Top Acquisti        [grafico]
Categorie Più Redditizie    [grafico]

=== ANALISI ===

Crescita Vendite vs Mese Scorso    [%]
Tasso Conversione Ordini           [%]
Prodotti Critici (giacenza<2)      [alert]
```

---

### FOGLIO 5: Ordini Fornitore

Genera automaticamente ordini ai fornitori per prodotti sotto scorta:

```
Data       Fornitore   Prodotto  Quantità  Prezzo  Totale
[auto]     TechSupply  Laptop    10        700     7000
[auto]     OfficeKit   Mouse     40        18      720
```

**Logica:**
- Se giacenza < minimo → genera ordine
- Quantità ordine = (minimo × 2) - giacenza
- Raggruppa per fornitore

---

## Requisiti Tecnici Obbligatori

### Formule da Utilizzare

**Base:**
- ✅ SOMMA, MEDIA, MAX, MIN
- ✅ CONTA.SE, CONTA.VALORI
- ✅ SE, SE annidati o PIÙ.SE
- ✅ E, O, NON

**Intermedio:**
- ✅ SOMMA.SE, SOMMA.PIÙ.SE
- ✅ MEDIA.SE, CONTA.PIÙ.SE
- ✅ MAIUSC, MINUSC, MAIUSC.INIZ
- ✅ CONCATENA o &

**Avanzato:**
- ✅ CERCA.VERT (almeno 3 lookup diversi)
- ✅ SE.ERRORE
- ✅ INDICE + CONFRONTA (almeno 1)
- ✅ OGGI, DATA, DATA.DIFF
- ✅ UNICI o UNIQUE (per elenchi)

### Collegamenti tra Fogli

**Obbligatori:**
- Dashboard legge da tutti gli altri fogli
- Ordini cerca dati da Prodotti e Clienti
- Clienti calcola totali da Ordini
- Ordini Fornitore legge da Prodotti

---

## Funzionalità Extra (Bonus)

### +10 punti ciascuna:

1. **Sistema Alert Email**
   - Genera testo email automatico per:
     - Conferma ordine cliente
     - Alert giacenza a fornitore
     - Sollecito pagamento

2. **Grafici Interattivi**
   - Minimo 3 grafici:
     - Vendite per categoria (torta)
     - Trend vendite mensili (linee)
     - Top 5 prodotti (barre)

3. **Formattazione Condizionale**
   - Giacenze basse (rosso)
   - Ordini in ritardo (giallo)
   - Clienti top (verde)
   - Stati ordini (colori diversi)

4. **Sistema Commissioni**
   - Calcola commissioni venditori
   - 3% su ogni ordine completato
   - Report commissioni mensili

5. **Gestione Resi**
   - Stato ordine "Reso"
   - Riaccredito giacenza prodotto
   - Calcolo impatto su statistiche

---

## Criteri di Valutazione (100 punti)

| Criterio | Punti | Descrizione |
|----------|-------|-------------|
| **Completezza** | 30 | Tutti i 5 fogli implementati con tutte le sezioni |
| **Formule Corrette** | 30 | Formule funzionanti e appropriate |
| **Collegamenti** | 20 | Collegamenti corretti tra fogli |
| **Usabilità** | 10 | Facile da usare, ben organizzato |
| **Bonus** | 10 | Funzionalità extra e creatività |

**Votazione:**
- 90-100: Eccellente (10)
- 75-89: Ottimo (9)
- 60-74: Buono (8)
- 50-59: Sufficiente (7)
- 40-49: Quasi sufficiente (6)
- <40: Insufficiente (<6)

---

## Dati di Test Completi

### 10 Prodotti, 20 Ordini, 5 Clienti

Forniti separatamente per testare il sistema in modo completo.

---

## Modalità di Consegna

1. **File Google Fogli**
   - Nome: "Progetto_E-commerce_NomeCognome"
   - Condiviso con permessi di visualizzazione

2. **Documentazione**
   - Foglio "Istruzioni" con:
     - Descrizione funzionalità
     - Formule complesse spiegate
     - Eventuali limitazioni

3. **Presentazione** (opzionale per +5 punti)
   - Video 5 minuti che mostra:
     - Navigazione sistema
     - Funzionalità principali
     - Casi d'uso esempio

---

## Tempistica Consigliata

**Settimana 1-2:**
- Fogli 1-3 (Prodotti, Ordini, Clienti)

**Settimana 3:**
- Foglio 4 (Dashboard)
- Collegamenti tra fogli

**Settimana 4:**
- Foglio 5 (Ordini Fornitore)
- Funzionalità bonus
- Test completo
- Documentazione

---

## Suggerimenti per il Successo

1. ✅ Inizia dai fogli semplici (Prodotti, Clienti)
2. ✅ Testa ogni formula prima di procedere
3. ✅ Usa nomi intervallo per formule più leggibili
4. ✅ Documenta formule complesse con note
5. ✅ Crea dati di test realistici
6. ✅ Verifica collegamenti tra fogli
7. ✅ Fai backup regolari
8. ✅ Chiedi aiuto quando bloccato
9. ✅ Dedica tempo alla presentazione
10. ✅ Testa scenari estremi (giacenza 0, sconti 100%, ecc.)

---

## Risorse di Supporto

- Tutte le esercitazioni precedenti (1-10)
- Documentazione Google Fogli
- Forum classe
- Sessioni di tutoring
- Video tutorial disponibili

---

**Questo progetto è la sintesi di tutto il corso. Rappresenta competenze spendibili nel mondo del lavoro reale. Buon lavoro! 🚀**

---

*Tempo totale: 20-24 ore distribuite su 4 settimane*  
*Difficoltà: ⭐⭐⭐⭐⭐ (5/5)*  
*Valore: Certificazione competenze avanzate*
