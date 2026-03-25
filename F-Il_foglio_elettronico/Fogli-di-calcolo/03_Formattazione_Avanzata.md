# Modulo 3: Formattazione Avanzata

## 3.1 Formattazione Numeri e Valute

### Introduzione
La formattazione corretta dei numeri migliora la leggibilità e la comprensione dei dati. Google Fogli offre molte opzioni per visualizzare i numeri in formati diversi.

### Accesso alla formattazione
**Metodi**:
1. Menu: **Formato → Numero**
2. Barra strumenti: Icone di formattazione rapida
3. Tasto destro → **Formato numeri**
4. Scorciatoia: **Ctrl + Shift + 1-7** per formati comuni

### Formati numerici disponibili

#### Numero standard
- **Percorso**: Formato → Numero → Numero
- **Uso**: Numeri generici
- **Opzioni**: Decimali, separatore migliaia

**Esempi**:
```
Input: 1234.567
Standard: 1234.567
Con separatore migliaia: 1.234,567
2 decimali: 1.234,57
```

#### Valuta
- **Percorso**: Formato → Numero → Valuta
- **Scorciatoia**: **Ctrl + Shift + 4**
- **Uso**: Importi monetari

**Formati disponibili**:
```
€1.234,56        → Euro (Italia)
$1,234.56        → Dollaro USA
£1,234.56        → Sterlina britannica
¥1,234           → Yen giapponese
```

**Personalizzazione**:
1. Seleziona celle
2. Formato → Numero → Altre valute
3. Scegli simbolo e formato

**Valuta personalizzata**:
- Formato → Numero → Formato numero personalizzato
- Inserisci: `#.##0,00 €` o `"€" #.##0,00`

#### Percentuale
- **Percorso**: Formato → Numero → Percentuale
- **Scorciatoia**: **Ctrl + Shift + 5**

**Comportamento**:
```
Input: 0,25    → Visualizzato come: 25%
Input: 1       → Visualizzato come: 100%
Input: 0,5678  → Visualizzato come: 56,78%
```

**Nota importante**: Se inserisci 25 e applichi formato percentuale, diventa 2500%!

**Soluzione corretta**:
1. Inserisci il valore come decimale (0,25)
2. Oppure inserisci 25% direttamente

#### Notazione scientifica
- **Uso**: Numeri molto grandi o molto piccoli
- **Formato**: 1,23E+05 (significa 123.000)

**Esempi**:
```
123000000      → 1,23E+08
0,00000123     → 1,23E-06
```

#### Numeri contabili
- **Uso**: Report finanziari
- **Caratteristiche**:
  - Allinea simboli valuta
  - Mostra valori negativi tra parentesi
  - Zero visualizzato come trattino (-)

**Esempio**:
```
Standard           Contabile
€ 1.234,56        €    1.234,56
€ -567,89         €     (567,89)
€ 0,00            €           -
```

### Formattazione personalizzata numeri

#### Sintassi base
`[POSITIVO];[NEGATIVO];[ZERO];[TESTO]`

**Esempi pratici**:
```
#.##0,00                     → 1.234,56
#.##0,00 €                   → 1.234,56 €
#.##0,00;[Rosso]-#.##0,00    → Negativi in rosso con segno meno
#.##0;(#.##0);"-"            → Zero come trattino, negativi tra parentesi
```

#### Codici formato
- `#` - Cifra opzionale (nasconde zero non significativi)
- `0` - Cifra obbligatoria (mostra zero)
- `,` - Separatore migliaia
- `.` - Separatore decimali
- `€` o `$` - Simboli valuta

**Esempi avanzati**:
```
#.##0                → 1.234 (nessun decimale)
0,00                 → 1,23 (sempre 2 decimali)
#.##0,00;-#.##0,00   → -1.234,56 (negativi con segno meno)
[Rosso]#.##0,##      → Numeri in rosso
```

---

## 3.2 Formattazione Date e Ore

### Formati data

#### Formati predefiniti
**Accesso**: Formato → Numero → Data

**Formati disponibili**:
```
24/03/2026           → Giorno/Mese/Anno (breve)
24 marzo 2026        → Giorno Mese Anno (esteso)
24/03/26             → Giorno/Mese/Anno (2 cifre)
2026-03-24           → Anno-Mese-Giorno (ISO)
mar 24, 2026         → Mese gg, Anno (USA)
lunedì 24 marzo      → Giorno settimana e data
```

#### Scorciatoie
- **Ctrl + ;** - Inserisce data odierna (statica)
- **Ctrl + Shift + ;** - Inserisce ora corrente (statica)
- **Ctrl + Alt + Shift + ;** - Inserisce data e ora (statiche)

#### Funzioni data
```
=OGGI()              → Data odierna (dinamica)
=ADESSO()            → Data e ora correnti (dinamiche)
=DATA(2026;3;24)     → Crea una data specifica
```

### Formati ora

#### Formati predefiniti
**Accesso**: Formato → Numero → Ora

**Formati disponibili**:
```
14:30:00             → Formato 24 ore (completo)
14:30                → Formato 24 ore (senza secondi)
2:30:00 PM           → Formato 12 ore con AM/PM
2:30 PM              → Formato 12 ore breve
```

### Formato data e ora combinato
```
24/03/2026 14:30              → Data e ora standard
lunedì 24 marzo 2026 14:30    → Data e ora esteso
24/03/26 2:30 PM              → Data breve e ora 12h
```

### Formattazione personalizzata date

#### Codici formato data
```
g      → Giorno (1-31)
gg     → Giorno con zero (01-31)
ggg    → Giorno settimana abbreviato (lun, mar)
gggg   → Giorno settimana completo (lunedì, martedì)
m      → Mese (1-12)
mm     → Mese con zero (01-12)
mmm    → Mese abbreviato (gen, feb)
mmmm   → Mese completo (gennaio, febbraio)
aa     → Anno 2 cifre (26)
aaaa   → Anno 4 cifre (2026)
```

**Esempi personalizzati**:
```
gg/mm/aaaa           → 24/03/2026
gggg, gg mmmm aaaa   → lunedì, 24 marzo 2026
gg-mmm-aa            → 24-mar-26
mmmm aaaa            → marzo 2026
"Giorno" gg          → Giorno 24
```

#### Codici formato ora
```
h      → Ora formato 12h (1-12)
hh     → Ora formato 12h con zero (01-12)
H      → Ora formato 24h (0-23)
HH     → Ora formato 24h con zero (00-23)
m      → Minuti (0-59)
mm     → Minuti con zero (00-59)
s      → Secondi (0-59)
ss     → Secondi con zero (00-59)
AM/PM  → Indicatore ante/post meridiano
```

**Esempi personalizzati**:
```
HH:mm                → 14:30
hh:mm AM/PM          → 02:30 PM
HH:mm:ss             → 14:30:45
"Ore" HH "e" mm "min" → Ore 14 e 30 min
```

### Calcoli con date

**Differenza tra date**:
```
=B1-A1               → Numero di giorni tra due date
```

**Aggiungere giorni**:
```
=A1+7                → Aggiunge 7 giorni alla data in A1
=OGGI()+30           → Data tra 30 giorni
```

**Estrarre componenti**:
```
=ANNO(A1)            → Estrae l'anno
=MESE(A1)            → Estrae il mese (1-12)
=GIORNO(A1)          → Estrae il giorno (1-31)
=GIORNO.SETTIMANA(A1) → Restituisce numero giorno (1=domenica)
```

**Casi d'uso**:
- Calcolare scadenze: `=DataInizio+30`
- Calcolare età: `=(OGGI()-DataNascita)/365,25`
- Giorni rimanenti: `=DataScadenza-OGGI()`

---

## 3.3 Formattazione Condizionale

### Introduzione
La formattazione condizionale applica stili automaticamente in base ai valori delle celle, evidenziando pattern e anomalie.

**Accesso**: Formato → Formattazione condizionale

### Regole base

#### 1. Maggiore di / Minore di
**Uso**: Evidenziare valori sopra o sotto una soglia

**Esempio**: Evidenziare vendite superiori a 1000€
1. Seleziona intervallo (es. B2:B50)
2. Formato → Formattazione condizionale
3. Scegli "Maggiore di"
4. Inserisci: 1000
5. Scegli stile (es. sfondo verde)

**Applicazioni**:
- Vendite sopra obiettivo
- Temperature anomale
- Punteggi insufficienti

#### 2. Tra
**Uso**: Evidenziare valori in un intervallo specifico

**Esempio**: Evidenziare temperature tra 18-22°
1. Condizione: "È compreso tra"
2. Valore minimo: 18
3. Valore massimo: 22
4. Formattazione: sfondo azzurro

#### 3. È uguale a / Contiene
**Uso**: Evidenziare valori specifici o testo

**Esempi**:
```
È uguale a "Completato"     → Evidenzia status completati
Contiene "Urgente"          → Evidenzia celle con parola "Urgente"
Il testo inizia con "VIP"   → Evidenzia clienti VIP
```

#### 4. La cella è vuota / non è vuota
**Uso**: Evidenziare dati mancanti

**Esempio**: Evidenziare in rosso le celle vuote obbligatorie
1. Condizione: "La cella è vuota"
2. Formattazione: sfondo rosso chiaro

### Scale di colori

**Accesso**: Formattazione condizionale → Scale di colori

**Tipi disponibili**:
- **2 colori**: Minimo e massimo (es. rosso → verde)
- **3 colori**: Minimo, medio, massimo (es. rosso → giallo → verde)

**Configurazione**:
- Punto minimo: Valore minimo, percentuale, numero
- Punto medio: 50%, percentuale, numero
- Punto massimo: Valore massimo, percentuale, numero

**Uso tipico**:
- Visualizzare performance su mappa di calore
- Dashboard vendite
- Analisi tendenze

**Esempio**: Dashboard vendite mensili
```
Scala: Rosso (min) → Giallo (50%) → Verde (max)
Intervallo: B2:M50
Effetto: Mesi con vendite basse in rosso, alte in verde
```

### Barre dati

**Cosa sono**: Barre colorate dentro le celle proporzionali al valore

**Configurazione**:
1. Formattazione condizionale → Barre dati
2. Scegli colore
3. Opzioni:
   - Mostra/nascondi numero
   - Solo barra o barra + numero
   - Direzione (sinistra a destra o destra a sinistra)

**Uso tipico**:
- Grafici in linea in tabelle
- Percentuali di completamento
- Confronti rapidi

**Esempio**: Percentuali di completamento progetto
```
Colonna: % Completamento
Formato: Barra verde
Risultato: Barra più lunga = più completo
```

### Formula personalizzata

**Potenza**: Puoi creare regole complesse usando formule

**Sintassi**: La formula deve restituire VERO o FALSO

#### Esempio 1: Evidenziare righe in base a una colonna
**Obiettivo**: Evidenziare intera riga se status = "Scaduto"

**Passi**:
1. Seleziona intervallo: A2:E50
2. Formattazione condizionale → Formula personalizzata
3. Formula: `=$D2="Scaduto"` (nota il $ prima della colonna)
4. Formato: sfondo rosso

**Spiegazione**: `$D2` blocca la colonna D ma la riga cambia (2, 3, 4...)

#### Esempio 2: Evidenziare valori sopra la media
**Formula**: `=B2>MEDIA($B$2:$B$50)`

**Effetto**: Celle con valore sopra la media in grassetto verde

#### Esempio 3: Evidenziare duplicati
**Formula**: `=CONTA.SE($A$2:$A$50; A2)>1`

**Effetto**: Evidenzia valori che compaiono più di una volta

#### Esempio 4: Evidenziare weekend
**Formula**: `=O(GIORNO.SETTIMANA(A2)=1; GIORNO.SETTIMANA(A2)=7)`

**Effetto**: Evidenzia sabato e domenica in grigio

#### Esempio 5: Righe alternate (zebra striping)
**Formula**: `=RESTO(RIF.RIGA(); 2)=0`

**Effetto**: Colora righe pari con sfondo grigio chiaro

### Gestione regole multiple

**Ordine di precedenza**:
- Le regole sono applicate dall'alto verso il basso
- Prima regola ha priorità
- Puoi riordinare trascinando

**Best practices**:
1. Regole più specifiche in alto
2. Regole generali in basso
3. Usa "Interrompi se vero" per evitare sovrapposizioni

**Esempio ordinamento regole**:
```
1. =$D2="Urgente"          → Rosso (priorità massima)
2. =$D2="Importante"       → Arancione
3. =B2>1000               → Verde
4. Scala colori           → Sfondo graduato (base)
```

### Copia formato condizionale

**Metodo 1**: Copia incolla formato
1. Seleziona cella con formato condizionale
2. **Ctrl + C**
3. Seleziona destinazione
4. Tasto destro → Incolla speciale → Incolla solo formato

**Metodo 2**: Strumento Copia formato
1. Seleziona cella sorgente
2. Clicca icona rullo di vernice
3. Seleziona destinazione

---

## 3.4 Stili e Temi

### Temi documento

**Accesso**: Formato → Tema

**Cosa include un tema**:
- Combinazioni colori coordinate
- Font titoli e testo
- Stili grafici

**Temi disponibili**:
- Standard (blu/grigio)
- Marina (blu scuro)
- Corallo (rosso/arancione)
- Terra (marroni/verdi)
- Personalizzato

**Personalizzazione tema**:
1. Formato → Tema
2. Clicca "Personalizza"
3. Modifica:
   - Colore primario
   - Colore accento
   - Font titolo
   - Font testo
4. Salva come tema personalizzato

### Stili di testo rapidi

#### Grassetto, Corsivo, Sottolineato
- **Grassetto**: Ctrl + B
- *Corsivo*: Ctrl + I
- <u>Sottolineato</u>: Ctrl + U
- ~~Barrato~~: Alt + Shift + 5

#### Font e dimensioni
**Accesso rapido**: Barra strumenti

**Font consigliati**:
- **Arial**: Standard, leggibile
- **Roboto**: Moderno, pulito
- **Georgia**: Elegante, formale
- **Courier**: Monospace, per codice

**Dimensioni comuni**:
- 8-9 pt: Note piccole
- 10-11 pt: Testo standard
- 12-14 pt: Intestazioni secondarie
- 16-20 pt: Titoli principali

#### Colore testo e sfondo
- **Icona A**: Colore testo
- **Icona barattolo**: Colore sfondo

**Consigli**:
- Alto contrasto testo/sfondo
- Evitare troppi colori
- Usare palette coordinata

### Stili predefiniti

Google Fogli non ha "stili predefiniti" come Word, ma puoi creare template riutilizzabili:

**Creazione template intestazione**:
1. Formatta cella (es. grassetto, 14pt, sfondo blu, testo bianco)
2. Copia cella
3. Usa per tutte le intestazioni

**Esempio tabella formattata**:
```
Riga 1 (Intestazione):
- Grassetto
- Sfondo blu scuro (#1155CC)
- Testo bianco
- Bordo inferiore spesso

Righe dati:
- Testo nero
- Righe alternate grigio chiaro (#F0F0F0)
- Bordi sottili
```

---

## 3.5 Bordi e Colori

### Bordi

**Accesso**: 
- Icona bordi nella barra strumenti
- Menu: Formato → Bordi

**Opzioni bordi**:
- Tutti i bordi
- Bordi esterni
- Bordi interni (orizzontali/verticali)
- Bordi singoli (sopra/sotto/sinistra/destra)
- Nessun bordo

**Stile bordo**:
- Sottile (default)
- Medio
- Spesso
- Doppio
- Tratteggiato
- Punteggiato

**Colore bordo**:
- Nero (default)
- Grigio
- Colori personalizzati

**Scorciatoie bordi**:
- **Alt + Shift + 7**: Bordo esterno
- **Alt + Shift + 6**: Bordo superiore
- **Alt + Shift + 4**: Bordo destro
- **Alt + Shift + 3**: Bordo inferiore
- **Alt + Shift + 2**: Bordo sinistro

**Best practices**:
- Usa bordi spessi per intestazioni
- Bordi sottili per dati
- Bordo doppio per totali
- Non esagerare: troppi bordi confondono

**Esempio tabella professionale**:
```
Intestazione: Bordo inferiore doppio spesso
Dati: Bordi sottili grigi
Totale: Bordo superiore doppio + sfondo grigio chiaro
```

### Colori sfondo

**Accesso**: Icona barattolo vernice

**Palette predefinita**:
- Colori tema (coordinati)
- Colori standard
- Colori personalizzati

**Uso strategico colori**:

#### Codifica per categorie
```
🟢 Verde:   Positivo, completato, sopra target
🟡 Giallo:  Attenzione, in corso, medio
🔴 Rosso:   Negativo, scaduto, sotto target
🔵 Blu:     Informativo, intestazioni
🟣 Viola:   Priorità alta, VIP
⚪ Grigio:  Neutro, disabilitato, note
```

#### Intensità colore
- **Pastello chiaro**: Dati normali
- **Colori medi**: Evidenziazioni
- **Colori scuri**: Intestazioni (con testo bianco)

**Codici colore consigliati**:
```
Intestazione blu:    #1155CC (scuro) + testo bianco
Evidenzia verde:     #D9EAD3 (chiaro)
Attenzione giallo:   #FFF2CC (chiaro)
Allarme rosso:       #F4CCCC (chiaro)
Grigio alternato:    #F3F3F3 (molto chiaro)
```

### Allineamento

**Tipi allineamento orizzontale**:
- Sinistra (default per testo)
- Centro
- Destra (default per numeri)
- Giustificato

**Tipi allineamento verticale**:
- Alto
- Centro
- Basso

**Scorciatoie allineamento**:
- **Ctrl + Shift + L**: Allinea sinistra
- **Ctrl + Shift + E**: Allinea centro
- **Ctrl + Shift + R**: Allinea destra

**Best practices**:
- Testo: allineato a sinistra
- Numeri: allineati a destra
- Intestazioni: centrate
- Date: allineate a destra o centro

### Ritorno a capo

**Opzioni**:
1. **Ritorno a capo automatico**: Il testo va a capo automaticamente
   - Icona: Ritorno a capo
   - Altezza riga si adatta

2. **Overflow**: Il testo esce dalla cella
   - Default
   - Va sopra le celle adiacenti vuote

3. **Tronca**: Il testo viene tagliato
   - Testo non visibile oltre la cella

**Scorciatoia**: **Alt + Invio** per forzare ritorno a capo dentro la cella

**Uso consigliato**:
- Intestazioni: Ritorno a capo
- Dati brevi: Overflow/Tronca
- Note/descrizioni: Ritorno a capo

---

## 3.6 Unione Celle e Allineamento

### Unione celle

**Accesso**: 
- Icona "Unisci celle" nella barra strumenti
- Formato → Unisci celle

**Opzioni unione**:
1. **Unisci tutto**: Unisce tutte le celle selezionate in una
2. **Unisci orizzontalmente**: Unisce celle per riga
3. **Unisci verticalmente**: Unisce celle per colonna
4. **Separa**: Annulla unione

**⚠️ Attenzione**: L'unione conserva solo il valore della cella in alto a sinistra!

**Quando usare**:
- Titoli centrati su più colonne
- Intestazioni di sezione
- Layout report

**Esempio titolo centrato**:
```
Unisci A1:E1 → Inserisci "Report Vendite 2026" → Centra
```

**Quando NON usare**:
- Dati che devono essere ordinati
- Tabelle per calcoli
- Intervalli per grafici

### Rientro testo

**Uso**: Creare gerarchie visive

**Accesso**: Formato → Allineamento → Aumenta/Riduci rientro

**Esempio gerarchico**:
```
Ricavi Totali
  Ricavi Italia
    Ricavi Nord
    Ricavi Sud
  Ricavi Estero
```

**Scorciatoie**:
- **Ctrl + ]**: Aumenta rientro
- **Ctrl + [**: Riduci rientro

### Rotazione testo

**Accesso**: Formato → Rotazione testo

**Opzioni**:
- 0° (standard)
- 45° (inclinato su)
- 90° (verticale su)
- -90° (verticale giù)
- Angolo personalizzato

**Uso tipico**:
- Intestazioni colonne strette
- Etichette compatte
- Layout creativi

**Esempio intestazioni verticali**:
```
   G   M   A   M
   e   a   p   a
   n   r   r   g
```
Risparmia spazio in larghezza!

### Dimensioni righe e colonne

#### Ridimensionamento manuale
- Trascina bordo tra intestazioni righe/colonne
- Doppio clic: Adatta automaticamente al contenuto

#### Ridimensionamento preciso
1. Tasto destro su intestazione
2. "Ridimensiona riga/colonna"
3. Inserisci dimensione in pixel

**Dimensioni consigliate**:
- Riga standard: 21 px
- Riga intestazione: 30-40 px
- Colonna testo breve: 80-120 px
- Colonna numeri: 100-150 px
- Colonna descrizione: 200-300 px

#### Nascondi/Mostra
**Nascondi**:
- Tasto destro su intestazione → "Nascondi"
- Utile per dati intermedi/calcoli

**Mostra**:
- Clicca sulle frecce tra le intestazioni

#### Blocca righe/colonne

**Accesso**: Visualizza → Blocca

**Opzioni**:
- Blocca 1 riga (intestazioni)
- Blocca 2+ righe
- Blocca 1 colonna
- Blocca 2+ colonne
- Blocca riga E colonna (intestazioni tabella)

**Uso**: Mantenere visibili intestazioni durante lo scorrimento

**Esempio**:
```
Blocca: 1 riga + 1 colonna
Risultato: A1 sempre visibile durante lo scorrimento
```

---

## Esercizi Pratici Modulo 3

### Esercizio 1: Formattazione Tabella Vendite
**Obiettivo**: Creare tabella vendite mensili formattata professionalmente

**Dati**:
```
      A          B       C       D
1   Mese     Vendite  Obiettivo  Scarto
2   Gennaio   12500    10000    
3   Febbraio  9800     10000
4   Marzo     15200    10000
```

**Compiti**:
1. Formatta B2:B4 come valuta €
2. Calcola Scarto (D = B - C)
3. Formattazione condizionale:
   - Verde se Vendite > Obiettivo
   - Rosso se Vendite < Obiettivo
4. Intestazione: grassetto, sfondo blu, testo bianco
5. Aggiungi bordo doppio sotto l'intestazione
6. Totale in B5 con bordo superiore doppio

### Esercizio 2: Dashboard con Scale di Colori
**Obiettivo**: Visualizzare performance team con mappa calore

**Dati**: Punteggi team (0-100)

**Compiti**:
1. Applica scala 3 colori (Rosso-Giallo-Verde)
2. Aggiungi barre dati per visualizzazione rapida
3. Evidenzia il valore MAX in grassetto
4. Formatta intestazioni con rotazione 45°

### Esercizio 3: Calendario con Formattazione Condizionale
**Obiettivo**: Evidenziare automaticamente weekend e festività

**Compiti**:
1. Crea colonna date (01/03/2026 - 31/03/2026)
2. Formula personalizzata per weekend (sabato/domenica) → grigio
3. Formula personalizzata per date specifiche (festività) → rosso chiaro
4. Formatta date come "gggg gg mmmm"

### Esercizio 4: Report Formattato
**Obiettivo**: Creare report professionale con tutti gli elementi

**Compiti**:
1. Titolo unito e centrato (A1:E1)
2. Sottotitolo con data (usa OGGI())
3. Tabella dati con:
   - Intestazioni formattate
   - Righe alternate grigio chiaro
   - Bordi appropriati
4. Sezione totali con sfondo diverso
5. Applica tema colori coordinato

---

## Riepilogo Modulo 3

### Concetti chiave appresi
✓ Formattazione numeri, valute e percentuali  
✓ Gestione date e ore con formati personalizzati  
✓ Formattazione condizionale (regole, scale, barre)  
✓ Formula personalizzate per formattazione avanzata  
✓ Stili, temi e palette colori  
✓ Bordi, allineamento e unione celle  

### Best Practices Formattazione
1. **Coerenza**: Usa gli stessi formati in tutto il foglio
2. **Semplicità**: Non esagerare con colori e formattazione
3. **Contrasto**: Assicura leggibilità (testo scuro su sfondo chiaro)
4. **Gerarchia**: Usa dimensioni e stili per indicare importanza
5. **Accessibilità**: Evita solo colore per trasmettere informazioni
6. **Performance**: Troppa formattazione condizionale rallenta il foglio

### Checklist Foglio Professionale
- [ ] Intestazioni chiare e formattate
- [ ] Valute con simbolo € e 2 decimali
- [ ] Date in formato leggibile
- [ ] Formattazione condizionale per evidenziare pattern
- [ ] Bordi per separare sezioni
- [ ] Allineamento coerente (testo sx, numeri dx)
- [ ] Colori coordinati (max 3-4 colori)
- [ ] Righe/colonne bloccate per intestazioni
- [ ] Totali evidenziati con bordi/sfondo

### Prossimi passi
Nel Modulo 4 esploreremo la gestione e l'analisi dei dati con ordinamento, filtri e convalida.
