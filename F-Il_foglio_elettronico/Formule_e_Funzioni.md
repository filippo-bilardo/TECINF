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

---

## Introduzione

Le **formule** e le **funzioni** sono strumenti fondamentali nei fogli di calcolo che permettono di automatizzare calcoli, analizzare dati e prendere decisioni basate su informazioni.

### Differenza tra Formula e Funzione
- **Formula**: un'espressione matematica che inizia con il simbolo `=` e può contenere valori, riferimenti di cella e operatori.
- **Funzione**: un comando predefinito che esegue calcoli specifici (es. SOMMA, MEDIA).

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
