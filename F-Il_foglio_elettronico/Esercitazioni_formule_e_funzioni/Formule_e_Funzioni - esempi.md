# Guida alle Formule e Funzioni nei Fogli di Calcolo

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

