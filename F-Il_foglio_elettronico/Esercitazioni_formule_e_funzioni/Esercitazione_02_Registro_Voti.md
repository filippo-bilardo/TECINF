# Esercitazione 2: Gestione Registro Voti

**Livello:** 📚 BASE  
**Tempo stimato:** 40 minuti

---

## Obiettivi

- Calcolare medie per righe e colonne
- Utilizzare funzioni statistiche avanzate
- Applicare formule a più studenti contemporaneamente
- Analizzare performance di una classe

---

## Dati di Partenza

Crea una tabella con studenti e voti:

```
   A          B       C       D       E
1  Studente   Voto1   Voto2   Voto3   Media
2  Marco      7       8       7
3  Anna       9       8       9
4  Luca       6       7       6
5  Giulia     8       9       8
6  Paolo      5       6       5
```

---

## Compiti da Svolgere

### 1. Media per Ogni Studente

Nella colonna E, calcola la media dei tre voti per ogni studente.

**Formula in E2:**
```
=MEDIA(B2:D2)
```

Copia la formula da E2 a E6.

### 2. Statistiche di Classe

Aggiungi una riga finale (riga 7) con etichetta "MEDIA CLASSE" in A7, poi:

**Media della classe per ogni verifica:**
- In B7: `=MEDIA(B2:B6)` (media Voto1)
- In C7: `=MEDIA(C2:C6)` (media Voto2)
- In D7: `=MEDIA(D2:D6)` (media Voto3)

**Media generale della classe:**
- In E7: `=MEDIA(E2:E6)` o `=MEDIA(B2:D6)`

### 3. Voti Massimi e Minimi

Aggiungi due righe:
- Riga 8 con etichetta "VOTO MAX" in A8
- Riga 9 con etichetta "VOTO MIN" in A9

**Voto massimo per ogni verifica:**
- In B8: `=MAX(B2:B6)`
- In C8: `=MAX(C2:C6)`
- In D8: `=MAX(D2:D6)`
- In E8: `=MAX(E2:E6)`

**Voto minimo per ogni verifica:**
- In B9: `=MIN(B2:B6)`
- In C9: `=MIN(C2:C6)`
- In D9: `=MIN(D2:D6)`
- In E9: `=MIN(E2:E6)`

### 4. Studenti con Media >= 7

In una cella separata (es. G2):
```
=CONTA.SE(E2:E6;">=7")
```

### 5. Studenti con Media < 6

In una cella separata (es. G3):
```
=CONTA.SE(E2:E6;"<6")
```

---

## Formule da Utilizzare

| Funzione | Scopo | Esempio |
|----------|-------|---------|  
| `MEDIA()` | Calcola media aritmetica | `=MEDIA(B2:D2)` |
| `MAX()` | Trova valore massimo | `=MAX(B2:B6)` |
| `MIN()` | Trova valore minimo | `=MIN(B2:B6)` |
| `CONTA.SE()` | Conta celle con criterio | `=CONTA.SE(E2:E6;">=7")` |

---

## Risultati Attesi

| Studente | Voto1 | Voto2 | Voto3 | Media |
|----------|-------|-------|-------|-------|
| Marco | 7 | 8 | 7 | 7,33 |
| Anna | 9 | 8 | 9 | 8,67 |
| Luca | 6 | 7 | 6 | 6,33 |
| Giulia | 8 | 9 | 8 | 8,33 |
| Paolo | 5 | 6 | 5 | 5,33 |
| **MEDIA CLASSE** | **7** | **7,6** | **7** | **7,20** |
| **VOTO MAX** | **9** | **9** | **9** | **8,67** |
| **VOTO MIN** | **5** | **6** | **5** | **5,33** |

**Conteggi:**
- Studenti con media >= 7: **3** (Marco, Anna, Giulia)
- Studenti con media < 6: **1** (Paolo)

---

## Prossimi Passi

- ✅ Esercitazione 3: Riferimenti Assoluti e Relativi
- 📚 Approfondisci le funzioni condizionali (SE)
- 💡 Esplora altre funzioni statistiche (MEDIANA, PERCENTILE, QUARTILE)

---

*Tempo medio di completamento: 30-40 minuti*  
*Difficoltà: ⭐⭐ (2/5)*
