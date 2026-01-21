# Guida alle Formule e Funzioni nei Fogli di Calcolo

## Indice
1. [Introduzione](#introduzione)
2. [Nozioni di Base](#nozioni-di-base)
3. [Operatori Matematici](#operatori-matematici)
4. [Riferimenti di Cella](#riferimenti-di-cella)
5. [Funzioni Matematiche](#funzioni-matematiche)
6. [Funzioni Statistiche](#funzioni-statistiche)
7. [Funzioni Logiche](#funzioni-logiche)
8. [Funzioni di Testo](#funzioni-di-testo)
9. [Funzioni di Data e Ora](#funzioni-di-data-e-ora)
10. [Funzioni di Ricerca](#funzioni-di-ricerca)
11. [Funzioni Specifiche di Google Fogli](#funzioni-specifiche-google-fogli)
12. [Esempi Pratici](#esempi-pratici)
13. [Esercitazioni per Studenti](#esercitazioni-per-studenti)

---

## Introduzione

### Cosa sono i Fogli di Calcolo

I **fogli di calcolo elettronici** (spreadsheet) sono applicazioni software progettate per organizzare, analizzare e memorizzare dati in formato tabellare. Nati negli anni '70, hanno rivoluzionato il modo in cui aziende, professionisti e studenti gestiscono informazioni numeriche e testuali.

#### Storia e Evoluzione

- **1979**: VisiCalc, il primo foglio elettronico per computer personali
- **1983**: Lotus 1-2-3, che dominò gli anni '80
- **1985**: Excel di Microsoft, che divenne lo standard industriale
- **2006**: Google Fogli (Google Sheets), portando il cloud computing ai fogli di calcolo

#### Caratteristiche Fondamentali

Un foglio di calcolo si compone di:

1. **Celle**: l'unità base dove si inseriscono dati
2. **Righe**: identificate da numeri (1, 2, 3...)
3. **Colonne**: identificate da lettere (A, B, C...)
4. **Fogli**: un documento può contenere più fogli (tab)
5. **Cartella di lavoro**: il file completo contenente tutti i fogli

### Il Potere delle Formule e delle Funzioni

Le **formule** e le **funzioni** rappresentano il vero potere dei fogli di calcolo, trasformandoli da semplici tabelle in potenti strumenti di analisi e automazione. Senza formule, un foglio di calcolo sarebbe solo una griglia per inserire dati manualmente; con le formule, diventa uno strumento dinamico e intelligente.

#### Vantaggi dell'Uso di Formule

1. **Automazione**: Calcoli complessi eseguiti automaticamente
2. **Precisione**: Eliminazione degli errori di calcolo manuale
3. **Aggiornamento dinamico**: I risultati si aggiornano automaticamente quando cambiano i dati
4. **Scalabilità**: Una formula può essere applicata a migliaia di celle
5. **Riproducibilità**: Le stesse formule possono essere riutilizzate in contesti diversi
6. **Trasparenza**: La logica di calcolo è visibile e verificabile

### Differenza tra Formula e Funzione

#### Formula
Una **formula** è un'espressione matematica personalizzata che inizia con il simbolo `=` e può contenere:
- Valori numerici diretti (es. `5`, `3.14`)
- Riferimenti di cella (es. `A1`, `B2`)
- Operatori matematici (es. `+`, `-`, `*`, `/`)
- Funzioni predefinite

**Esempio di formula semplice:**
```
=A1*B1+C1
```
Questa formula moltiplica il valore di A1 per B1 e aggiunge il valore di C1.

#### Funzione
Una **funzione** è un comando predefinito che esegue calcoli specifici o operazioni sui dati. Le funzioni:
- Hanno un nome specifico (es. SOMMA, MEDIA, SE)
- Accettano argomenti (input) tra parentesi
- Restituiscono un risultato
- Sono ottimizzate per operazioni comuni

**Esempio di funzione:**
```
=SOMMA(A1:A10)
```
Questa funzione somma tutti i valori dall'intervallo A1 a A10.

#### Formula con Funzioni
Spesso, le formule più potenti combinano funzioni multiple:
```
=SE(MEDIA(A1:A10)>50;"Superato";"Non superato")
```

### Tipi di Dati nei Fogli di Calcolo

Prima di lavorare con formule, è essenziale comprendere i tipi di dati:

#### 1. Numeri
- **Interi**: 1, 42, -5
- **Decimali**: 3.14, -2.5 (nota: in Italia si usa la virgola, ma nelle formule si usa il punto)
- **Percentuali**: 50% (memorizzato come 0.5)
- **Valuta**: €10,00
- **Notazione scientifica**: 1.5E+10 (15.000.000.000)

#### 2. Testo (Stringhe)
- Qualsiasi sequenza di caratteri
- Deve essere racchiuso tra virgolette nelle formule: `"Ciao"`
- Può contenere numeri che non devono essere calcolati (es. codici postali)

#### 3. Date e Ore
- Le date sono memorizzate come numeri (giorni dal 30/12/1899)
- Le ore sono frazioni di giorno
- Formato visualizzato: 21/01/2026 oppure 14:30:00

#### 4. Booleani
- VERO o FALSO
- Utilizzati nelle funzioni logiche
- VERO = 1, FALSO = 0 nei calcoli

#### 5. Errori
- `#DIV/0!`: divisione per zero
- `#N/D`: valore non disponibile
- `#NOME?`: nome funzione non riconosciuto
- Altri errori che vedremo in dettaglio

### Ordine delle Operazioni (Precedenza)

Quando si scrivono formule complesse, è fondamentale conoscere l'ordine in cui le operazioni vengono eseguite:

1. **Parentesi** `()`
2. **Elevamento a potenza** `^`
3. **Moltiplicazione e Divisione** `*` `/` (da sinistra a destra)
4. **Addizione e Sottrazione** `+` `-` (da sinistra a destra)
5. **Operatori di confronto** `=`, `>`, `<`, ecc.
6. **Concatenazione** `&`

**Esempio:**
```
=2+3*4        // Risultato: 14 (prima 3*4=12, poi 2+12=14)
=(2+3)*4      // Risultato: 20 (prima 2+3=5, poi 5*4=20)
=10/2*5       // Risultato: 25 (da sinistra: 10/2=5, poi 5*5=25)
```

### Perché Imparare le Formule è Importante

#### Nel Mondo del Lavoro
- **Finanza**: Analisi di bilanci, previsioni, calcoli di interessi
- **Marketing**: Analisi ROI, statistiche campagne, segmentazione clienti
- **Risorse Umane**: Calcolo stipendi, analisi presenze, valutazione performance
- **Vendite**: Report vendite, analisi trend, gestione inventario
- **Ricerca**: Elaborazione dati statistici, analisi risultati

#### Competenze Trasversali
Padroneggiare i fogli di calcolo sviluppa:
- **Pensiero logico**: Scomposizione problemi complessi
- **Attenzione ai dettagli**: Precisione nei riferimenti
- **Problem solving**: Trovare soluzioni creative
- **Efficienza**: Automatizzare compiti ripetitivi

### Approccio Didattico di questa Guida

Questa guida segue un percorso progressivo:

1. **Fondamenti**: Concetti base e sintassi
2. **Funzioni Base**: Operazioni matematiche e statistiche semplici
3. **Funzioni Intermedie**: Logica condizionale e manipolazione testo
4. **Funzioni Avanzate**: Ricerca dati e analisi complesse
5. **Applicazioni Pratiche**: Esempi reali e casi d'uso
6. **Esercitazioni**: Pratica guidata per consolidare le competenze

### Convenzioni Utilizzate

In questa guida:
- Le **formule** sono scritte in formato codice: `=SOMMA(A1:A10)`
- Gli **intervalli** usano i due punti: `A1:A10`
- Il **separatore di argomenti** in Italia è il punto e virgola `;` (in inglese è la virgola `,`)
- I **decimali** nelle formule usano la virgola: `3,14`
- Il **testo** è sempre tra virgolette: `"Esempio"`

---

## Nozioni di Base

### Sintassi di una Formula
Tutte le formule in Google Fogli iniziano con il simbolo `=`:

```
=A1+B1
=SOMMA(A1:A10)
=SE(B2>100;"Alto";"Basso")
```

### Componenti di una Formula
- **Operatori**: +, -, *, /, ^
- **Riferimenti di cella**: A1, B2, C3
- **Costanti**: numeri o testo fissi
- **Funzioni**: comandi predefiniti

---

## Operatori Matematici

### Operatori Aritmetici

| Operatore | Operazione | Esempio | Risultato |
|-----------|------------|---------|-----------|
| `+` | Addizione | `=5+3` | 8 |
| `-` | Sottrazione | `=10-4` | 6 |
| `*` | Moltiplicazione | `=4*3` | 12 |
| `/` | Divisione | `=15/3` | 5 |
| `^` | Elevamento a potenza | `=2^3` | 8 |
| `%` | Percentuale | `=50%` | 0,5 |

### Operatori di Confronto

| Operatore | Significato | Esempio | Risultato |
|-----------|-------------|---------|-----------|
| `=` | Uguale a | `=A1=B1` | VERO/FALSO |
| `>` | Maggiore di | `=A1>B1` | VERO/FALSO |
| `<` | Minore di | `=A1<B1` | VERO/FALSO |
| `>=` | Maggiore o uguale | `=A1>=B1` | VERO/FALSO |
| `<=` | Minore o uguale | `=A1<=B1` | VERO/FALSO |
| `<>` | Diverso da | `=A1<>B1` | VERO/FALSO |

### Operatori di Concatenazione

| Operatore | Operazione | Esempio | Risultato |
|-----------|------------|---------|-----------|
| `&` | Concatenazione testo | `="Ciao "&"Mondo"` | Ciao Mondo |

---

## Riferimenti di Cella

### Riferimento Relativo
Si adatta automaticamente quando la formula viene copiata:
```
=A1+B1
```
Se copiata in basso, diventa `=A2+B2`, `=A3+B3`, ecc.

### Riferimento Assoluto
Rimane fisso usando il simbolo `$`:
```
=$A$1+B1
```
La cella A1 rimane sempre la stessa, B1 cambia.

### Riferimento Misto
Una combinazione dei due:
```
=$A1+B$1
```
- `$A1`: la colonna A è fissa, la riga cambia
- `B$1`: la colonna B cambia, la riga 1 è fissa

### Intervalli di Celle
```
A1:A10    (da A1 a A10, verticale)
A1:E1     (da A1 a E1, orizzontale)
A1:E10    (rettangolo da A1 a E10)
A:A       (intera colonna A)
1:1       (intera riga 1)
```

---

## Funzioni Matematiche

### SOMMA
Somma tutti i numeri in un intervallo:
```
=SOMMA(A1:A10)
=SOMMA(A1;B1;C1)
=SOMMA(A1:A10;B1:B10)
```

**Esempio pratico:**
```
   A         B
1  100       =SOMMA(A1;A2;A3)
2  200       Risultato: 600
3  300
```

### PRODOTTO
Moltiplica tutti i numeri:
```
=PRODOTTO(A1:A5)
```

### POTENZA
Eleva un numero a potenza:
```
=POTENZA(2;3)    // 2^3 = 8
=POTENZA(A1;2)   // A1 al quadrato
```

### RADQ
Calcola la radice quadrata:
```
=RADQ(16)    // Risultato: 4
=RADQ(A1)
```

### ARROTONDA
Arrotonda un numero a un numero specifico di decimali:
```
=ARROTONDA(3.14159;2)      // Risultato: 3.14
=ARROTONDA.PER.ECC(3.4)    // Arrotonda per eccesso: 4
=ARROTONDA.PER.DIF(3.8)    // Arrotonda per difetto: 3
```

### ASS
Restituisce il valore assoluto:
```
=ASS(-5)    // Risultato: 5
```

---

## Funzioni Statistiche

### MEDIA
Calcola la media aritmetica:
```
=MEDIA(A1:A10)
=MEDIA(A1;B1;C1)
```

### MEDIANA
Restituisce il valore mediano:
```
=MEDIANA(A1:A10)
```

### MODA
Restituisce il valore più frequente:
```
=MODA(A1:A10)
```

### MAX e MIN
Trovano il valore massimo o minimo:
```
=MAX(A1:A10)
=MIN(A1:A10)
```

### CONTA.NUMERI
Conta le celle che contengono numeri:
```
=CONTA.NUMERI(A1:A10)
```

### CONTA.VALORI
Conta le celle non vuote:
```
=CONTA.VALORI(A1:A10)
```

### CONTA.VUOTE
Conta le celle vuote:
```
=CONTA.VUOTE(A1:A10)
```

### CONTA.SE
Conta le celle che soddisfano un criterio:
```
=CONTA.SE(A1:A10;">50")
=CONTA.SE(A1:A10;"Rosso")
=CONTA.SE(A1:A10;"<>"&"")    // Conta celle non vuote
```

### SOMMA.SE
Somma le celle che soddisfano un criterio:
```
=SOMMA.SE(A1:A10;">100")
=SOMMA.SE(B1:B10;"Venduto";C1:C10)
```

### MEDIA.SE
Media delle celle che soddisfano un criterio:
```
=MEDIA.SE(A1:A10;">50")
```

---

## Funzioni Logiche

### SE
Esegue un test logico e restituisce un valore se VERO, un altro se FALSO:
```
=SE(A1>100;"Alto";"Basso")
=SE(A1>=18;"Maggiorenne";"Minorenne")
```

**Esempio con riferimenti:**
```
   A          B
1  85         =SE(A1>=60;"Promosso";"Bocciato")
```

### SE.ERRORE
Gestisce gli errori nelle formule:
```
=SE.ERRORE(A1/B1;"Errore di divisione")
=SE.ERRORE(CERCA.VERT(A1;B:C;2;FALSO);"Non trovato")
```

### E
Restituisce VERO se tutti gli argomenti sono VERI:
```
=E(A1>10;A1<100)
=E(A1="Attivo";B1>0)
```

### O
Restituisce VERO se almeno un argomento è VERO:
```
=O(A1="Rosso";A1="Verde";A1="Blu")
```

### NON
Inverte il valore logico:
```
=NON(A1>100)
```

### SE annidati
È possibile annidare più funzioni SE:
```
=SE(A1>=90;"Eccellente";SE(A1>=70;"Buono";SE(A1>=60;"Sufficiente";"Insufficiente")))
```

### PIÙ.SE (Google Fogli)
Alternativa più leggibile ai SE annidati:
```
=PIÙ.SE(A1>=90;"Eccellente";A1>=70;"Buono";A1>=60;"Sufficiente";VERO;"Insufficiente")
```

---

## Funzioni di Testo

### CONCATENA / CONCAT
Unisce più stringhe di testo:
```
=CONCATENA("Buongiorno ";A1)
=CONCAT(A1;" ";B1)
```

In Google Fogli è preferibile usare `&`:
```
=A1&" "&B1
```

### SINISTRA, DESTRA, STRINGA.ESTRAI
Estraggono parti di una stringa:
```
=SINISTRA("Google Fogli";6)         // Risultato: "Google"
=DESTRA("Google Fogli";5)           // Risultato: "Fogli"
=STRINGA.ESTRAI("Google Fogli";8;5) // Risultato: "Fogli"
```

### LUNGHEZZA
Restituisce il numero di caratteri:
```
=LUNGHEZZA("Ciao")    // Risultato: 4
```

### MAIUSC, MINUSC, MAIUSC.INIZ
Cambiano il formato del testo:
```
=MAIUSC("ciao")          // Risultato: "CIAO"
=MINUSC("CIAO")          // Risultato: "ciao"
=MAIUSC.INIZ("ciao mondo") // Risultato: "Ciao Mondo"
```

### SOSTITUISCI
Sostituisce un testo con un altro:
```
=SOSTITUISCI("Google Sheets";"Sheets";"Fogli")
```

### SPAZI
Rimuove spazi extra:
```
=SPAZI("  Troppi   spazi  ")    // Risultato: "Troppi spazi"
```

### TESTO
Formatta un numero come testo:
```
=TESTO(1234,56;"#.##0,00 €")    // Risultato: "1.234,56 €"
=TESTO(OGGI();"GG/MM/AAAA")     // Risultato: "21/01/2026"
```

### VALORE
Converte testo in numero:
```
=VALORE("123")    // Risultato: 123
```

---

## Funzioni di Data e Ora

### OGGI
Restituisce la data corrente:
```
=OGGI()
```

### ADESSO
Restituisce data e ora correnti:
```
=ADESSO()
```

### ANNO, MESE, GIORNO
Estraggono componenti da una data:
```
=ANNO(A1)     // Estrae l'anno
=MESE(A1)     // Estrae il mese (1-12)
=GIORNO(A1)   // Estrae il giorno (1-31)
```

### GIORNO.SETTIMANA
Restituisce il giorno della settimana:
```
=GIORNO.SETTIMANA(A1)    // 1=Domenica, 7=Sabato
```

### DATA
Crea una data da anno, mese, giorno:
```
=DATA(2026;1;21)
```

### DATA.DIFF (Google Fogli)
Calcola la differenza tra due date:
```
=DATA.DIFF(A1;B1;"D")    // Differenza in giorni
=DATA.DIFF(A1;B1;"M")    // Differenza in mesi
=DATA.DIFF(A1;B1;"Y")    // Differenza in anni
```

### ORA, MINUTO, SECONDO
Estraggono componenti da un orario:
```
=ORA(A1)
=MINUTO(A1)
=SECONDO(A1)
```

---

## Funzioni di Ricerca

### CERCA.VERT
Cerca un valore nella prima colonna di una tabella e restituisce un valore nella stessa riga:
```
=CERCA.VERT(valore_cercato;intervallo_tabella;numero_colonna;[intervallo_ricerca])
```

**Esempio:**
```
   A           B         C
1  Codice      Prodotto  Prezzo
2  A001        Mela      1,50
3  A002        Banana    2,00
4  A003        Arancia   1,80

=CERCA.VERT("A002";A1:C4;2;FALSO)    // Risultato: "Banana"
=CERCA.VERT("A002";A1:C4;3;FALSO)    // Risultato: 2,00
```

**Parametri:**
- `FALSO`: corrispondenza esatta
- `VERO`: corrispondenza approssimativa (la prima colonna deve essere ordinata)

### CERCA.ORIZZ
Simile a CERCA.VERT ma cerca orizzontalmente:
```
=CERCA.ORIZZ(valore_cercato;intervallo_tabella;numero_riga;[intervallo_ricerca])
```

### INDICE
Restituisce il valore di una cella in base a riga e colonna:
```
=INDICE(A1:C10;5;2)    // Valore nella 5ª riga, 2ª colonna
```

### CONFRONTA
Trova la posizione di un valore in un intervallo:
```
=CONFRONTA("Mela";A1:A10;0)    // Restituisce la posizione
```

### INDICE + CONFRONTA
Combinazione potente per ricerche flessibili:
```
=INDICE(C:C;CONFRONTA("Mela";A:A;0))
```

Questa formula cerca "Mela" nella colonna A e restituisce il valore corrispondente nella colonna C.

### FILTER (Google Fogli)
Filtra un intervallo in base a condizioni:
```
=FILTER(A1:C10;B1:B10>100)
=FILTER(A1:C10;B1:B10>100;C1:C10="Attivo")
```

---

## Funzioni Specifiche di Google Fogli

### IMPORTRANGE
Importa dati da un altro foglio di calcolo:
```
=IMPORTRANGE("URL_foglio";"Nome_foglio!A1:D10")
```

### QUERY
Esegue query SQL-like sui dati:
```
=QUERY(A1:D10;"SELECT A, B WHERE C > 100 ORDER BY D DESC")
```

**Esempi:**
```
// Seleziona colonne specifiche
=QUERY(A1:E10;"SELECT A, C, E")

// Filtra con WHERE
=QUERY(A1:E10;"SELECT * WHERE B > 100")

// Ordina con ORDER BY
=QUERY(A1:E10;"SELECT * ORDER BY C DESC")

// Raggruppa con GROUP BY
=QUERY(A1:E10;"SELECT A, SUM(C) GROUP BY A")
```

### ARRAYFORMULA
Applica una formula a un intero intervallo:
```
=ARRAYFORMULA(A1:A10*2)
=ARRAYFORMULA(SE(A1:A10>100;"Alto";"Basso"))
```

### UNIQUE
Restituisce valori univoci da un intervallo:
```
=UNIQUE(A1:A100)
```

### SORT
Ordina un intervallo:
```
=SORT(A1:C10;2;VERO)    // Ordina per 2ª colonna, crescente
=SORT(A1:C10;2;FALSO)   // Ordina per 2ª colonna, decrescente
```

### IMPORTHTML
Importa dati da una tabella HTML:
```
=IMPORTHTML("URL";"table";1)    // Importa la prima tabella
```

### IMPORTXML
Importa dati usando XPath:
```
=IMPORTXML("URL";"//h1")
```

### SPARKLINE
Crea grafici in una cella:
```
=SPARKLINE(A1:A10)
=SPARKLINE(A1:A10;{"charttype"\"bar"})
```

### GOOGLETRANSLATE
Traduce testo:
```
=GOOGLETRANSLATE("Hello";"en";"it")    // Risultato: "Ciao"
```

---

## Esempi Pratici

### Esempio 1: Calcolo Stipendio con Bonus

```
   A           B          C                D
1  Dipendente  Stipendio  Vendite         Bonus
2  Mario       2000       150000          =SE(C2>100000;B2*0.1;0)
3  Luigi       2500       80000           =SE(C3>100000;B3*0.1;0)
4  Anna        2200       120000          =SE(C4>100000;B4*0.1;0)

// Stipendio Totale
5  TOTALE                                 =SOMMA(B2:B4)+SOMMA(D2:D4)
```

### Esempio 2: Analisi Vendite

```
   A           B          C               D
1  Prodotto    Q.tà       Prezzo         Totale
2  Mele        10         1,50           =B2*C2
3  Banane      15         2,00           =B3*C3
4  Arance      8          1,80           =B4*C4
5
6  TOTALE                                =SOMMA(D2:D4)
7  MEDIA VENDITA                         =MEDIA(D2:D4)
8  MAX VENDITA                           =MAX(D2:D4)
9  MIN VENDITA                           =MIN(D2:D4)
```

### Esempio 3: Valutazione Studenti

```
   A           B          C          D          E
1  Studente    Voto1      Voto2      Media      Risultato
2  Marco       75         82         =MEDIA(B2:C2)  =SE(D2>=60;"PROMOSSO";"BOCCIATO")
3  Sara        58         63         =MEDIA(B3:C3)  =SE(D3>=60;"PROMOSSO";"BOCCIATO")
4  Luca        90         88         =MEDIA(B4:C4)  =SE(D4>=60;"PROMOSSO";"BOCCIATO")
```

### Esempio 4: Gestione Inventario

```
   A           B          C          D              E
1  Prodotto    Stock      Minimo     Stato         Azione
2  Item A      50         20         =SE(B2<C2;"BASSO";"OK")  =SE(D2="BASSO";"RIORDINA";"")
3  Item B      15         20         =SE(B3<C3;"BASSO";"OK")  =SE(D3="BASSO";"RIORDINA";"")
4  Item C      100        50         =SE(B4<C4;"BASSO";"OK")  =SE(D4="BASSO";"RIORDINA";"")
```

### Esempio 5: Calcolo IVA e Totali

```
   A           B          C              D
1  Descrizione Imponibile IVA (22%)      Totale
2  Servizio 1  1000       =B2*0.22       =B2+C2
3  Servizio 2  1500       =B3*0.22       =B3+C3
4  Servizio 3  2000       =B4*0.22       =B4+C4
5
6  SUBTOTALE   =SOMMA(B2:B4)  =SOMMA(C2:C4)  =SOMMA(D2:D4)
```

### Esempio 6: Ricerca con CERCA.VERT

**Tabella Prezzi (A:B):**
```
   A           B
1  Codice      Prezzo
2  P001        15,00
3  P002        22,50
4  P003        18,00
```

**Fattura (D:F):**
```
   D           E                              F
1  Codice      Quantità                       Totale
2  P002        3                              =CERCA.VERT(D2;$A$2:$B$4;2;FALSO)*E2
3  P001        5                              =CERCA.VERT(D3;$A$2:$B$4;2;FALSO)*E3
```

### Esempio 7: Analisi Date

```
   A               B                      C
1  Data Ordine     Giorni Trascorsi      Stato
2  15/01/2026      =OGGI()-A2            =SE(B2>7;"RITARDO";"OK")
3  10/01/2026      =OGGI()-A3            =SE(B3>7;"RITARDO";"OK")
4  20/01/2026      =OGGI()-A4            =SE(B4>7;"RITARDO";"OK")
```

### Esempio 8: Formattazione Condizionale con Formule

**Formula per evidenziare valori sopra la media:**
```
=A1>MEDIA($A$1:$A$10)
```

**Formula per evidenziare duplicati:**
```
=CONTA.SE($A$1:$A$10;A1)>1
```

### Esempio 9: QUERY Avanzata

```
=QUERY(A1:D100;"SELECT A, SUM(C), AVG(D) WHERE B = 'Venduto' GROUP BY A ORDER BY SUM(C) DESC")
```
Questa query:
- Seleziona la colonna A
- Calcola la somma della colonna C
- Calcola la media della colonna D
- Filtra dove colonna B = "Venduto"
- Raggruppa per colonna A
- Ordina per somma decrescente

### Esempio 10: Dashboard Dinamica

```
// Contatori
=CONTA.SE(Stato;"Completato")
=CONTA.SE(Stato;"In Corso")
=CONTA.SE(Stato;"Da Fare")

// Percentuali
=CONTA.SE(Stato;"Completato")/CONTA.VALORI(Stato)

// Grafici SPARKLINE
=SPARKLINE(B2:B10;{"charttype"\"column";"color1"\"green"})
```

---

## Consigli e Best Practices

### 1. Usa Nomi Intervallo
Invece di `=SOMMA(A1:A10)`, definisci un nome "Vendite" e usa:
```
=SOMMA(Vendite)
```

### 2. Evita Riferimenti Circolari
Non fare riferimento alla cella in cui si trova la formula stessa.

### 3. Usa SE.ERRORE per Gestire Errori
```
=SE.ERRORE(A1/B1;0)
```

### 4. Commenta Formule Complesse
In una cella adiacente, spiega cosa fa la formula.

### 5. Utilizza la Convalida dei Dati
Per limitare gli input e ridurre errori nelle formule.

### 6. Formattazione Condizionale
Usa formule personalizzate per evidenziare automaticamente dati importanti.

### 7. Tasti Rapidi Utili in Google Fogli
- `Ctrl + ~`: Mostra/nascondi formule
- `F4`: Cambia tipo di riferimento (relativo/assoluto)
- `Ctrl + D`: Riempi in basso
- `Ctrl + R`: Riempi a destra
- `Ctrl + ;`: Inserisci data corrente
- `Ctrl + Shift + ;`: Inserisci ora corrente

### 8. Debugging delle Formule
- Usa `Strumenti > Editor di script` per funzioni personalizzate
- Controlla la precedenza degli operatori
- Verifica i tipi di dati (testo vs numero)

---

## Errori Comuni e Soluzioni

| Errore | Significato | Soluzione |
|--------|-------------|-----------|
| `#DIV/0!` | Divisione per zero | Verifica il divisore o usa `SE.ERRORE` |
| `#N/D` | Valore non disponibile | Controlla i riferimenti in CERCA.VERT |
| `#NOME?` | Nome funzione non riconosciuto | Verifica l'ortografia della funzione |
| `#RIF!` | Riferimento non valido | La cella a cui si fa riferimento è stata eliminata |
| `#VALORE!` | Tipo di argomento sbagliato | Verifica i tipi di dati utilizzati |
| `#NUM!` | Problema con un numero | Numero troppo grande o argomento non valido |
| `#ERRORE!` | Errore generico | Controlla la sintassi della formula |

---

## Esercitazioni per Studenti

Questa sezione contiene esercitazioni pratiche organizzate per livello di difficoltà. Ogni esercitazione include obiettivi, dati da utilizzare e compiti da svolgere.

---

### 📚 LIVELLO BASE

#### Esercitazione 1: Primi Passi con le Formule

**Obiettivi:**
- Scrivere formule semplici con operatori aritmetici
- Utilizzare riferimenti di cella
- Creare somme e medie

**Dati di partenza:**
Crea un foglio con questi dati nella colonna A (Prodotto), B (Quantità), C (Prezzo Unitario):

```
A              B          C
Mele           50         1,50
Banane         30         2,00
Arance         40         1,80
Pere           25         2,50
Kiwi           35         3,00
```

**Compiti:**
1. Nella colonna D (Totale), calcola il totale per ogni prodotto (Quantità × Prezzo)
2. Alla fine della colonna B, calcola la quantità totale di tutti i prodotti
3. Alla fine della colonna D, calcola il valore totale di tutta la merce
4. Calcola il prezzo medio dei prodotti
5. Trova il prezzo più alto e quello più basso

**Formule da utilizzare:** Operatori base, SOMMA, MEDIA, MAX, MIN

---

#### Esercitazione 2: Gestione Registro Voti

**Obiettivi:**
- Calcolare medie
- Utilizzare funzioni statistiche
- Applicare formule a più studenti

**Dati di partenza:**
Crea una tabella con studenti e voti:

```
A          B       C       D       E
Studente   Voto1   Voto2   Voto3   Media
Marco      7       8       7
Anna       9       8       9
Luca       6       7       6
Giulia     8       9       8
Paolo      5       6       5
```

**Compiti:**
1. Calcola la media per ogni studente nella colonna E
2. Aggiungi una riga finale con:
   - Media della classe per ogni verifica
   - Media generale della classe
3. Trova il voto massimo e minimo per ogni verifica
4. Conta quanti studenti hanno media >= 7
5. Conta quanti studenti hanno media < 6

**Formule da utilizzare:** MEDIA, MAX, MIN, CONTA.SE

---

#### Esercitazione 3: Riferimenti Assoluti e Relativi

**Obiettivi:**
- Comprendere la differenza tra riferimenti relativi e assoluti
- Applicare il cambio valuta
- Usare riferimenti misti

**Dati di partenza:**
```
A              B          C (Tasso cambio: 1,10)
Prodotto       Euro       Dollari
Laptop         800
Mouse          25
Tastiera       45
Monitor        350
Webcam         80
```

**Compiti:**
1. Inserisci il tasso di cambio Euro/Dollaro in una cella (es. D1 = 1,10)
2. Nella colonna C, calcola il prezzo in dollari usando un riferimento assoluto al tasso
3. Copia la formula verso il basso per tutti i prodotti
4. Prova a cambiare il tasso di cambio e verifica che tutti i prezzi si aggiornino
5. Aggiungi una colonna D per convertire da Dollari a Sterline (tasso 0,85)

**Formule da utilizzare:** Riferimenti assoluti ($), moltiplicazione

---

### 📊 LIVELLO INTERMEDIO

#### Esercitazione 4: Gestione Magazzino con Logica

**Obiettivi:**
- Utilizzare la funzione SE
- Combinare funzioni logiche
- Gestire soglie e avvisi

**Dati di partenza:**
```
A          B          C          D              E
Prodotto   Giacenza   Minimo     Stato         Azione
Viti       150        100
Bulloni    45         50
Rondelle   200        80
Dadi       30         40
Chiodi     500        200
```

**Compiti:**
1. Nella colonna D, mostra "OK" se la giacenza >= minimo, "BASSO" altrimenti
2. Nella colonna E, mostra "RIORDINA" se lo stato è "BASSO", altrimenti lascia vuoto
3. Aggiungi una colonna F "Priorità" con:
   - "URGENTE" se giacenza < 50% del minimo
   - "NORMALE" se giacenza < minimo ma >= 50% del minimo
   - "OK" altrimenti
4. Conta quanti prodotti sono in stato "BASSO"
5. Calcola la percentuale di prodotti con giacenza sufficiente

**Formule da utilizzare:** SE, SE annidati o PIÙ.SE, CONTA.SE, CONTA.VALORI

---

#### Esercitazione 5: Analisi Vendite Mensili

**Obiettivi:**
- Utilizzare SOMMA.SE e MEDIA.SE
- Analizzare dati per categoria
- Creare report riassuntivi

**Dati di partenza:**
```
A          B          C          D
Data       Categoria  Prodotto   Importo
05/01      Elettr.    TV         450
08/01      Casa       Divano     800
12/01      Elettr.    Radio      80
15/01      Sport      Bici       350
18/01      Casa       Tavolo     250
22/01      Sport      Palla      25
25/01      Elettr.    PC         900
28/01      Casa       Lampada    45
```

**Compiti:**
1. Crea una tabella riassuntiva con:
   - Totale vendite per categoria (Elettronica, Casa, Sport)
   - Numero di vendite per categoria
   - Importo medio per categoria
2. Calcola il totale generale delle vendite
3. Trova la vendita di importo massimo
4. Conta quante vendite superano i 200€
5. Calcola la percentuale di vendite per ogni categoria sul totale

**Formule da utilizzare:** SOMMA.SE, CONTA.SE, MEDIA.SE, SOMMA, MAX

---

#### Esercitazione 6: Elaborazione Testi e Date

**Obiettivi:**
- Manipolare stringhe di testo
- Lavorare con funzioni di data
- Estrarre informazioni da codici

**Dati di partenza:**
```
A                      B              C
Codice Completo        Data Ordine    Cliente
PRD-2026-001-ROSSI     15/01/2026     Mario Rossi
PRD-2026-002-BIANCHI   18/01/2026     anna bianchi
PRD-2026-003-VERDI     20/01/2026     LUCA VERDI
PRD-2026-004-NERI      21/01/2026     giulia neri
```

**Compiti:**
1. Estrai il numero d'ordine (001, 002, ecc.) dal codice nella colonna D
2. Estrai il cognome dal codice nella colonna E
3. Nella colonna F, formatta il nome cliente con iniziali maiuscole (Mario Rossi)
4. Nella colonna G, calcola i giorni trascorsi dall'ordine
5. Nella colonna H, mostra "SOLLECITO" se sono passati più di 5 giorni
6. Crea un codice di spedizione concatenando: "SPED-" + numero ordine + "-" + prime 3 lettere cognome

**Formule da utilizzare:** STRINGA.ESTRAI, MAIUSC.INIZ, OGGI, CONCATENA o &, SE

---

### 🎯 LIVELLO AVANZATO

#### Esercitazione 7: Database Dipendenti con CERCA.VERT

**Obiettivi:**
- Utilizzare CERCA.VERT per cercare informazioni
- Creare un sistema di lookup tra tabelle
- Gestire errori con SE.ERRORE

**Dati di partenza:**

**Tabella 1 - Anagrafica Dipendenti (A:D):**
```
Codice  Nome           Reparto    Livello
D001    Marco Rossi    Vendite    3
D002    Anna Verdi     IT         4
D003    Luca Bianchi   Vendite    2
D004    Sara Neri      HR         3
D005    Paolo Gialli   IT         5
```

**Tabella 2 - Livelli Retributivi (F:G):**
```
Livello  Stipendio Base
1        1200
2        1500
3        1800
4        2200
5        2800
```

**Compiti:**
1. Crea una sezione "Calcolo Stipendi" con:
   - Colonna con codice dipendente
   - Cerca automaticamente nome, reparto e livello
   - Cerca lo stipendio base corrispondente al livello
2. Aggiungi una colonna "Bonus" che calcola:
   - 15% per reparto Vendite
   - 10% per reparto IT
   - 5% per altri reparti
3. Calcola lo stipendio totale (base + bonus)
4. Gestisci eventuali codici dipendente non trovati con SE.ERRORE
5. Calcola il costo totale del personale per reparto

**Formule da utilizzare:** CERCA.VERT, SE, SE.ERRORE, SOMMA.SE

---

#### Esercitazione 8: Dashboard Vendite Interattiva

**Obiettivi:**
- Creare un dashboard di riepilogo
- Utilizzare formule complesse combinate
- Implementare KPI (Key Performance Indicators)

**Dati di partenza:**
```
Data        Venditore  Regione  Prodotto    Quantità  Prezzo  
02/01/2026  Mario      Nord     Laptop      2         800
03/01/2026  Anna       Sud      Mouse       10        25
04/01/2026  Luca       Centro   Tastiera    5         45
05/01/2026  Mario      Nord     Monitor     3         350
06/01/2026  Sara       Sud      Laptop      1         800
...(continua con almeno 20 righe)
```

**Compiti:**
1. Crea una sezione "KPI GENERALI":
   - Totale vendite (importo)
   - Numero totale ordini
   - Valore medio ordine
   - Prodotto più venduto
   - Regione con più vendite
2. Crea una tabella "Performance Venditori":
   - Elenco venditori unici
   - Totale vendite per venditore
   - Numero ordini per venditore
   - Media per ordine
   - Ranking (1° migliore venditore, ecc.)
3. Crea una tabella "Analisi per Regione":
   - Totale vendite per regione
   - Percentuale sul totale
   - Numero ordini per regione
4. Aggiungi calcoli temporali:
   - Vendite settimanali
   - Crescita rispetto alla settimana precedente
5. Implementa un sistema di "Target":
   - Target mensile: 50.000€
   - Percentuale raggiungimento
   - Proiezione fine mese

**Formule da utilizzare:** SOMMA.SE, CONTA.SE, MEDIA.SE, MAX, CERCA.VERT, UNIQUE (Google Fogli), PERCENTUALE

---

#### Esercitazione 9: Sistema di Prenotazioni

**Obiettivi:**
- Gestire disponibilità e prenotazioni
- Utilizzare logica complessa con SE annidati
- Validazione automatica dei dati

**Dati di partenza:**

**Tabella Camere:**
```
Camera  Tipo      Posti  Prezzo/Notte
101     Singola   1      80
102     Doppia    2      120
103     Doppia    2      120
104     Suite     4      200
105     Singola   1      80
```

**Tabella Prenotazioni:**
```
ID   Camera  Check-in    Check-out   Ospiti  Nome Cliente
1    102     20/01/2026  23/01/2026  2       Mario Rossi
2    104     21/01/2026  25/01/2026  4       Anna Verdi
```

**Compiti:**
1. Nella tabella prenotazioni, aggiungi colonne:
   - Notti (calcola la differenza tra check-out e check-in)
   - Prezzo/Notte (cerca dalla tabella camere)
   - Totale prenotazione
2. Aggiungi una colonna "Validazione":
   - "OK" se numero ospiti <= posti camera
   - "ERRORE: Troppi ospiti" altrimenti
3. Crea una sezione "Disponibilità" che per ogni camera mostri:
   - Se è occupata oggi
   - Data fine occupazione
   - Stato: "Libera" o "Occupata"
4. Calcola statistiche:
   - Tasso di occupazione (% camere occupate)
   - Ricavo totale prenotazioni
   - Ricavo medio per camera
   - Camera più redditizia
5. Crea un calendario settimanale che mostri la disponibilità giornaliera

**Formule da utilizzare:** DATA.DIFF, CERCA.VERT, SE, E, O, CONTA.SE, SOMMA.SE

---

#### Esercitazione 10: Analisi Finanziaria Aziendale

**Obiettivi:**
- Creare bilancio aziendale
- Calcolare margini e KPI finanziari
- Analisi del punto di pareggio (break-even)

**Dati di partenza:**

**Costi Fissi Mensili:**
```
Voce           Importo
Affitto        2000
Stipendi       8000
Utenze         500
Assicurazioni  300
Altro          200
```

**Vendite Prodotti:**
```
Prodotto     Prezzo Vendita  Costo Unitario  Q.tà Venduta
Prodotto A   50              30              150
Prodotto B   80              45              100
Prodotto C   120             70              80
Prodotto D   35              20              200
```

**Compiti:**
1. Calcola per ogni prodotto:
   - Ricavo totale
   - Costo variabile totale
   - Margine di contribuzione unitario
   - Margine di contribuzione totale
   - Margine % sul prezzo
2. Calcola il totale:
   - Ricavi totali
   - Costi variabili totali
   - Costi fissi totali
   - Costi totali
   - Utile/Perdita
3. Calcola KPI:
   - Margine di contribuzione %
   - ROI (Return on Investment)
   - Break-even point in unità
   - Break-even point in valore
4. Crea scenari "What-if":
   - Cosa succede aumentando i prezzi del 10%?
   - Cosa succede riducendo i costi fissi del 15%?
   - Quante unità servono per raggiungere 5000€ di utile?
5. Analisi prodotti:
   - Quale prodotto è più redditizio?
   - Quale contribuisce maggiormente all'utile?
   - Quale ha il margine % migliore?

**Formule da utilizzare:** SOMMA, operatori matematici, SE, CERCA.VERT, percentuali, formule finanziarie

---

### 🏆 PROGETTO FINALE COMPLETO

#### Esercitazione 11: Sistema Gestionale E-commerce

**Obiettivi:**
- Integrare tutte le competenze acquisite
- Creare un sistema multi-foglio complesso
- Automatizzare processi aziendali

**Struttura del progetto:**

Il progetto deve includere minimo 5 fogli interconnessi:

**FOGLIO 1 - Prodotti (Catalogo):**
```
Codice  Nome           Categoria  Prezzo  Giacenza  Minimo  Fornitore
```

**FOGLIO 2 - Ordini Clienti:**
```
ID  Data  Cliente  Codice Prod  Quantità  Stato  Spedizione
```

**FOGLIO 3 - Clienti (Anagrafica):**
```
ID  Nome  Cognome  Email  Città  Sconto%  Totale Acquisti
```

**FOGLIO 4 - Dashboard:**
Riepilogo con KPI e grafici

**FOGLIO 5 - Ordini Fornitore:**
Ordini automatici da generare per prodotti sotto scorta

**Requisiti funzionali:**

1. **Gestione Ordini:**
   - Ricerca automatica prezzo prodotto
   - Calcolo totale ordine
   - Applicazione sconto cliente
   - Verifica disponibilità giacenza
   - Aggiornamento automatico giacenze
   - Stato ordine (In lavorazione, Spedito, Consegnato)

2. **Gestione Clienti:**
   - Calcolo totale storico acquisti
   - Categoria cliente (Bronzo <500€, Argento 500-1000€, Oro >1000€)
   - Sconto automatico in base alla categoria
   - Numero ordini effettuati

3. **Gestione Magazzino:**
   - Segnalazione prodotti sotto scorta minima
   - Generazione automatica ordini a fornitori
   - Valore magazzino totale
   - Rotazione prodotti (velocità vendita)

4. **Dashboard e Analisi:**
   - Totale vendite giornaliere/settimanali/mensili
   - Numero ordini per stato
   - Prodotti più venduti (Top 5)
   - Categorie più redditizie
   - Trend vendite (crescita %)
   - Clienti più importanti (Top 5 per acquisti)
   - Tasso di riordino (% prodotti sotto minimo)
   - Valore medio ordine
   - Previsione vendite prossimo mese

5. **Funzionalità Avanzate:**
   - Sistema di ricerca prodotti
   - Calcolo commissioni venditori (3% su ordini)
   - Gestione resi (stato "Reso")
   - Report spedizioni per corriere
   - Alert automatici (email da inviare)

**Formule richieste:**
- CERCA.VERT per lookup tra fogli
- SOMMA.SE e SOMMA.PIÙ.SE per aggregazioni
- SE annidati o PIÙ.SE per logica complessa
- CONTA.SE per conteggi condizionali
- Funzioni di testo per formattazione
- Funzioni di data per analisi temporali
- FILTER e QUERY (Google Fogli) per estrarre dati
- ARRAYFORMULA per applicare formule a intervalli

**Criteri di valutazione:**
1. Completezza (tutti i fogli implementati): 30%
2. Correttezza formule: 30%
3. Automazione e interconnessione fogli: 20%
4. Usabilità e presentazione: 10%
5. Funzionalità extra e creatività: 10%

**Bonus opzionali:**
- Formattazione condizionale per evidenziare dati
- Grafici interattivi nella dashboard
- Funzioni personalizzate (Google Apps Script)
- Pulsanti per azioni automatiche
- Sistema di login e permessi (simulato)

---

### 📝 Modalità di Svolgimento

#### Per gli Studenti

1. **Organizzazione:**
   - Crea un nuovo Google Foglio per ogni esercitazione
   - Rinomina il file con: "Esercitazione_X_NomeCognome"
   - Aggiungi un foglio "Note" per documentare difficoltà o domande

2. **Svolgimento:**
   - Leggi attentamente i requisiti
   - Inserisci i dati di partenza
   - Risolvi un compito alla volta
   - Testa ogni formula prima di procedere
   - Verifica i risultati per coerenza

3. **Consegna:**
   - Condividi il foglio con l'insegnante
   - Assicurati che le formule siano visibili (non solo i valori)
   - Aggiungi commenti nelle celle complesse

#### Per gli Insegnanti

1. **Assegnazione:**
   - Livello Base: settimane 1-2
   - Livello Intermedio: settimane 3-4
   - Livello Avanzato: settimane 5-7
   - Progetto Finale: settimane 8-10

2. **Supporto:**
   - Sessioni di tutoring per dubbi
   - Forum classe per domande comuni
   - Video tutorial per concetti complessi

3. **Valutazione:**
   - Esercizi base: 1 punto ciascuno
   - Esercizi intermedi: 2 punti ciascuno
   - Esercizi avanzati: 3 punti ciascuno
   - Progetto finale: 10 punti

4. **Feedback:**
   - Commenti diretti nel foglio Google
   - Evidenziare errori comuni
   - Suggerire ottimizzazioni

---

### 💡 Suggerimenti per il Successo

1. **Non aver paura di sperimentare**: Prova diverse formule, il foglio di calcolo non si rompe!

2. **Usa i riferimenti assoluti quando necessario**: Il simbolo $ è tuo amico.

3. **Testa con dati semplici**: Prima di applicare formule complesse, verifica con numeri semplici.

4. **Documenta il tuo lavoro**: Aggiungi note e commenti per ricordare la logica.

5. **Cerca aiuto**: Usa la documentazione di Google Fogli, forum e video tutorial.

6. **Pratica regolarmente**: 30 minuti al giorno sono meglio di 3 ore una volta a settimana.

7. **Impara dagli errori**: Ogni errore è un'opportunità per capire meglio.

8. **Condividi con i compagni**: Lavora in gruppo per discutere approcci diversi.

9. **Pensa prima di scrivere**: Pianifica la formula su carta prima di digitarla.

10. **Verifica sempre i risultati**: I numeri hanno senso logico?

---

## Risorse Aggiuntive

### Documentazione Ufficiale
- [Guida Google Fogli](https://support.google.com/docs/topic/9054603)
- [Elenco Funzioni Google Fogli](https://support.google.com/docs/table/25273)

### Formazione
- Google Workspace Learning Center
- YouTube: Tutorial Google Fogli
- Corsi online (Coursera, Udemy)

### Comunità
- Forum di Google Fogli
- Stack Overflow
- Reddit: r/googlesheets

---

## Conclusione

Le formule e le funzioni sono strumenti potenti che trasformano un semplice foglio di calcolo in uno strumento di analisi dati professionale. Con la pratica costante e l'esplorazione di funzioni sempre più avanzate, è possibile automatizzare compiti complessi e prendere decisioni basate su dati accurati.

**Ricorda:** La chiave per padroneggiare i fogli di calcolo è la pratica continua e la sperimentazione con diverse funzioni e combinazioni!

---

*Questa guida è stata creata per aiutare studenti e professionisti a sfruttare al meglio le potenzialità di Google Fogli e dei fogli di calcolo in generale.*
