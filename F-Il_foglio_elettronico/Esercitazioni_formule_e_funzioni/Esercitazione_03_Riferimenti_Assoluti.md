# Esercitazione 3: Riferimenti Assoluti e Relativi

**Livello:** 📚 BASE  
**Tempo stimato:** 45 minuti

---

## Obiettivi

- Comprendere la differenza tra riferimenti relativi e assoluti
- Applicare il cambio valuta con riferimenti fissi
- Usare riferimenti misti ($A1, A$1)
- Copiare formule mantenendo riferimenti corretti

---

## Concetto Teorico: Riferimenti nelle Formule

### Riferimenti Relativi (A1)
Cambiano quando copi la formula:
- `=A1+B1` copiata una riga sotto diventa `=A2+B2`
- Utili quando vuoi applicare la stessa operazione a righe/colonne diverse

### Riferimenti Assoluti ($A$1)
Rimangono fissi quando copi la formula:
- `=$A$1*B1` copiata mantiene sempre il riferimento ad A1
- Utili per valori costanti (tassi, aliquote, fattori di conversione)

### Riferimenti Misti
- `$A1` - Colonna fissa, riga relativa
- `A$1` - Colonna relativa, riga fissa

**Scorciatoia:** Premi `F4` mentre modifichi un riferimento per ciclare tra i tipi!

---

## Dati di Partenza

Crea una tabella prezzi in Euro con tasso di cambio:

```
   A          B          C
1              Euro       Dollari
2  Laptop      800
3  Mouse       25
4  Tastiera    45
5  Monitor     350
6  Webcam      80

8  Tasso €/$   1,10
```

---

## Compiti da Svolgere

### 1. Conversione Euro → Dollari

**Formula in C2:**
```
=B2*$B$8
```

**Spiegazione:**
- `B2` è relativo: cambierà in B3, B4, ecc. quando copi la formula
- `$B$8` è assoluto: rimarrà sempre B8 (il tasso di cambio)

**Copia la formula da C2 a C6.**

### 2. Verifica del Funzionamento

1. Controlla che tutti i prezzi in dollari siano corretti
2. Prova a cambiare il tasso in B8 (es. 1,15)
3. Verifica che TUTTI i prezzi in dollari si aggiornino automaticamente

**Questo è il potere dei riferimenti assoluti!**

### 3. Aggiungi Colonna Sterline

Aggiungi in D1 l'intestazione "Sterline" e in B9 il tasso "Tasso $|£: 0,85"

**Formula in D2:**
```
=C2*$B$9
```

Copia la formula da D2 a D6.

---

## Risultati Attesi

Con tassi € → $ = 1,10 e $ → £ = 0,85:

| Prodotto | Euro | Dollari | Sterline |
|----------|------|---------|----------|
| Laptop | 800 | 880,00 | 748,00 |
| Mouse | 25 | 27,50 | 23,38 |
| Tastiera | 45 | 49,50 | 42,08 |
| Monitor | 350 | 385,00 | 327,25 |
| Webcam | 80 | 88,00 | 74,80 |

---

## Sfide Avanzate

### Challenge 1: Tripla Conversione
Aggiungi una colonna E per Yen giapponesi (tasso $ → ¥ = 150)

### Challenge 2: Conversione Inversa
Aggiungi una colonna F che converte da Dollari a Euro (usa 1/tasso)

### Challenge 3: Riferimenti Misti
Crea una tabella di moltiplicazione 10x10 usando riferimenti misti:
```
=$A2*B$1
```

---

## Formule Utilizzate

| Tipo | Sintassi | Comportamento |
|------|----------|---------------|
| Relativo | `B2` | Cambia copiando |
| Assoluto | `$B$8` | Rimane fisso |
| Misto (colonna fissa) | `$B2` | Solo colonna fissa |
| Misto (riga fissa) | `B$2` | Solo riga fissa |

---

## Errori Comuni da Evitare

❌ **Errore 1:** Non usare $ per il tasso
```
=B2*B8  ❌ Copiando diventa =B3*B9, =B4*B10...
```

✅ **Corretto:**
```
=B2*$B$8  ✅ Il tasso rimane sempre in B8
```

❌ **Errore 2:** Usare $ dove non serve
```
=$B$2*$B$8  ❌ Anche il prezzo è fisso!
```

---

## Prossimi Passi

- ✅ Esercitazione 4: Sistema di Produttività Personale
- 📚 Approfondisci: Riferimenti tra fogli diversi (`Foglio1!A1`)
- 💡 Esplora: Riferimenti a intervalli dinamici

---

*Tempo medio di completamento: 35-45 minuti*  
*Difficoltà: ⭐⭐ (2/5)*  
*Concetto chiave: Controllo del comportamento delle formule*
