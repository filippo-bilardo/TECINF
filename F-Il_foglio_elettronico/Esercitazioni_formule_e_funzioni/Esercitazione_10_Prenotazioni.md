# Esercitazione 10: Sistema di Prenotazioni

**Livello:** 🎯 AVANZATO  
**Tempo stimato:** 80 minuti

---

## Obiettivi

- Gestire disponibilità e prenotazioni
- Utilizzare logica complessa con date
- Validazione automatica dei dati
- Calcoli temporali avanzati

---

## Dati di Partenza

### Tabella Camere (A1:D6)

```
Camera  Tipo      Posti  Prezzo/Notte
101     Singola   1      80
102     Doppia    2      120
103     Doppia    2      120
104     Suite     4      200
105     Singola   1      80
```

### Tabella Prenotazioni (F1:K3)

```
ID  Camera  Check-in    Check-out   Ospiti  Nome
1   102     20/01/26    23/01/26    2       Mario Rossi
2   104     21/01/26    25/01/26    4       Anna Verdi
```

---

## Compiti da Svolgere

### 1. Colonna L - Notti

Calcola numero notti:
```
=J2-I2
```

### 2. Colonna M - Prezzo/Notte

Cerca prezzo dalla tabella camere:
```
=CERCA.VERT(G2;$A$2:$D$6;4;FALSO)
```

### 3. Colonna N - Totale Prenotazione

```
=L2*M2
```

### 4. Colonna O - Validazione

Verifica che numero ospiti non superi posti camera:
```
=SE(K2<=CERCA.VERT(G2;$A$2:$D$6;3;FALSO);"OK";"ERRORE: Troppi ospiti")
```

### 5. Disponibilità Oggi

Per ogni camera, verifica se è occupata oggi:
```
=SE(E(OGGI()>=I2;OGGI()<=J2);"Occupata";"Libera")
```

---

## SEZIONE STATISTICHE

```
=== STATISTICHE HOTEL ===

Camere Totali              5
Camere Occupate Oggi       [formula]
Tasso Occupazione         [formula]
Ricavo Totale Prenotaz.   [formula]
Ricavo Medio per Camera   [formula]
Camera Più Redditizia     [formula]
```

### Formule

**Camere Occupate:**
```
=CONTA.SE(ColonnaStato;"Occupata")
```

**Tasso Occupazione:**
```
=(CamereOccupate/CamereTotali)*100
```

**Ricavo Totale:**
```
=SOMMA(N:N)
```

---

## SEZIONE CALENDARIO SETTIMANALE

Crea una tabella che mostra per ogni camera lo stato per i prossimi 7 giorni:

```
Camera  Lun  Mar  Mer  Gio  Ven  Sab  Dom
101     L    L    L    O    O    L    L
102     O    O    O    L    L    L    L
...
```

L = Libera, O = Occupata

**Formula (esempio per Lunedì, camera 101):**
```
=SE(CONTA.PIÙ.SE(PrenotazioniCamere;101;CheckIn;"<="&DataLun;CheckOut;">="&DataLun)>0;"O";"L")
```

---

## Sfide Avanzate

### Challenge 1: Preventivo Automatico

Input utente:
- Tipo camera desiderata
- Numero notti
- Numero ospiti

Output:
- Camere disponibili di quel tipo
- Prezzo totale
- Validazione numero ospiti

### Challenge 2: Gestione Pulizie

Aggiungi stato pulizie:
- "Pulizia necessaria" se check-out = oggi
- "Pronta" altrimenti

### Challenge 3: Upgrade Automatico

Se camera richiesta non disponibile, suggerire camera superiore disponibile.

---

*Tempo medio: 70-80 minuti*  
*Difficoltà: ⭐⭐⭐⭐⭐ (5/5)*  
*Applicazione: Hospitality management*
