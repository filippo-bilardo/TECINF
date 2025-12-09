# Guida alle Codifiche dei Caratteri

## Indice
- [Introduzione](#introduzione)
- [ASCII](#ascii)
- [Extended ASCII](#extended-ascii)
- [Unicode](#unicode)
- [UTF-8](#utf-8)
- [UTF-16](#utf-16)
- [UTF-32](#utf-32)
- [Confronto tra le codifiche](#confronto-tra-le-codifiche)
- [Esempi pratici](#esempi-pratici)
- [Digitare caratteri speciali da tastiera](#digitare-caratteri-speciali-da-tastiera)

---

## Introduzione

La **codifica dei caratteri** è il processo di assegnazione di un numero univoco (chiamato *code point*) a ogni carattere, simbolo o segno utilizzato nella comunicazione scritta. Questo permette ai computer di rappresentare, memorizzare e trasmettere testo in formato digitale.

### Perché servono le codifiche?

I computer lavorano solo con numeri binari (0 e 1). Per rappresentare lettere, numeri, simboli e caratteri speciali, è necessario un sistema che associ ogni carattere a un codice numerico specifico.

---

## ASCII

### Cos'è ASCII?

**ASCII** (*American Standard Code for Information Interchange*) è stato uno dei primi standard di codifica dei caratteri, sviluppato negli anni '60.

### Caratteristiche principali

- **Dimensione**: 7 bit (può rappresentare 128 caratteri, da 0 a 127)
- **Caratteri supportati**:
  - Lettere maiuscole e minuscole (A-Z, a-z)
  - Cifre numeriche (0-9)
  - Segni di punteggiatura
  - Caratteri di controllo (come newline, tab, ecc.)

### Struttura della tabella ASCII

| Intervallo | Tipo di caratteri |
|------------|-------------------|
| 0-31       | Caratteri di controllo (non stampabili) |
| 32-47      | Simboli e spazi |
| 48-57      | Cifre numeriche (0-9) |
| 58-64      | Simboli di punteggiatura |
| 65-90      | Lettere maiuscole (A-Z) |
| 91-96      | Simboli |
| 97-122     | Lettere minuscole (a-z) |
| 123-127    | Simboli |

### Esempi di codici ASCII

```
Carattere  Decimale  Binario     Esadecimale
    A         65      0100 0001      41
    B         66      0100 0010      42
    a         97      0110 0001      61
    0         48      0011 0000      30
    !         33      0010 0001      21
  spazio      32      0010 0000      20
```

### Limitazioni di ASCII

- Non supporta caratteri accentati (à, è, ì, ò, ù)
- Non include simboli di altre lingue (ñ, ç, ß)
- Inadeguato per lingue non latine (cinese, arabo, cirillico)

---

## Extended ASCII

### Cos'è Extended ASCII?

Per superare le limitazioni di ASCII, sono state create diverse estensioni che utilizzano 8 bit invece di 7.

### Caratteristiche

- **Dimensione**: 8 bit (256 caratteri, da 0 a 255)
- **Caratteri aggiuntivi**: I caratteri 128-255 includono:
  - Lettere accentate
  - Simboli monetari (£, ¥, €)
  - Caratteri grafici per tabelle
  - Simboli matematici

### Varianti principali

- **ISO-8859-1 (Latin-1)**: Per lingue dell'Europa occidentale
- **ISO-8859-2 (Latin-2)**: Per lingue dell'Europa centrale
- **ISO-8859-5**: Per cirillico
- **Windows-1252**: Variante Microsoft di Latin-1

### Problema di Extended ASCII

Le diverse versioni non sono compatibili tra loro. Lo stesso codice può rappresentare caratteri diversi in codepage diverse, causando problemi di visualizzazione.

---

## Unicode

### Cos'è Unicode?

**Unicode** è uno standard universale che mira a rappresentare tutti i caratteri di tutte le lingue del mondo, più simboli, emoji e caratteri storici.

### Caratteristiche principali

- **Code space**: Può rappresentare oltre 1 milione di caratteri (da U+0000 a U+10FFFF)
- **Versione attuale**: Unicode 15.1 (settembre 2023) con oltre 149.000 caratteri
- **Obiettivo**: Un unico standard universale per tutte le lingue

### Organizzazione di Unicode

Unicode è organizzato in **piani** (planes):

1. **Piano 0 (BMP - Basic Multilingual Plane)**: U+0000 a U+FFFF
   - Contiene i caratteri più comuni di tutte le lingue moderne
   - Include alfabeto latino, greco, cirillico, arabo, cinese, giapponese, ecc.

2. **Piano 1 (SMP - Supplementary Multilingual Plane)**: U+10000 a U+1FFFF
   - Caratteri storici, emoji, simboli musicali

3. **Piani 2-16**: Altri caratteri speciali e riservati

### Esempi di code points Unicode

```
Carattere  Code Point  Descrizione
    A        U+0041    Lettera latina maiuscola A
    à        U+00E0    Lettera latina minuscola a con accento grave
    €        U+20AC    Simbolo dell'euro
    中        U+4E2D    Carattere cinese (zhōng)
    😀       U+1F600   Emoji faccina sorridente
    𝕏        U+1D54F   Lettera matematica grassetto X
```

### Unicode non è una codifica

**Importante**: Unicode è uno *standard di caratteri* (character set), non una *codifica*. Specifica quali caratteri esistono e i loro code points, ma non come rappresentarli in memoria. Per questo esistono le codifiche UTF.

---

## UTF-8

### Cos'è UTF-8?

**UTF-8** (*8-bit Unicode Transformation Format*) è la codifica Unicode più diffusa sul web e nei sistemi operativi moderni.

### Caratteristiche principali

- **Lunghezza variabile**: Usa da 1 a 4 byte per carattere
- **Compatibilità ASCII**: I primi 128 caratteri sono identici ad ASCII
- **Efficienza**: Ottimizza lo spazio per testi in lingue occidentali

### Come funziona UTF-8

UTF-8 usa un numero variabile di byte in base al carattere:

| Intervallo Unicode | Byte usati | Schema dei bit |
|-------------------|------------|----------------|
| U+0000 - U+007F   | 1 byte     | 0xxxxxxx |
| U+0080 - U+07FF   | 2 byte     | 110xxxxx 10xxxxxx |
| U+0800 - U+FFFF   | 3 byte     | 1110xxxx 10xxxxxx 10xxxxxx |
| U+10000 - U+10FFFF| 4 byte     | 11110xxx 10xxxxxx 10xxxxxx 10xxxxxx |

### Esempi di codifica UTF-8

```
Carattere  Unicode   UTF-8 (hex)        UTF-8 (binario)
    A      U+0041    41                 01000001
    è      U+00E8    C3 A8              11000011 10101000
    €      U+20AC    E2 82 AC           11100010 10000010 10101100
    😀     U+1F600   F0 9F 98 80        11110000 10011111 10011000 10000000
```

### Vantaggi di UTF-8

✅ **Compatibile con ASCII**: File ASCII sono validi UTF-8
✅ **Efficiente per testi occidentali**: 1 byte per caratteri comuni
✅ **Self-synchronizing**: Facile trovare l'inizio di un carattere
✅ **Nessun problema di byte order**: Non servono BOM (Byte Order Mark)
✅ **Standard de facto**: Usato da oltre 98% dei siti web

### Svantaggi di UTF-8

❌ **Lunghezza variabile**: Accesso diretto a un carattere specifico richiede scansione
❌ **Inefficiente per lingue asiatiche**: 3-4 byte per caratteri cinesi/giapponesi

---

## UTF-16

### Cos'è UTF-16?

**UTF-16** codifica i caratteri Unicode usando 2 o 4 byte.

### Caratteristiche principali

- **Lunghezza variabile**: 2 o 4 byte per carattere
- **BMP in 2 byte**: Caratteri del piano base (U+0000 a U+FFFF) usano 2 byte
- **Surrogate pairs**: Caratteri oltre U+FFFF usano 4 byte (coppia di surrogati)

### Come funziona UTF-16

- **Caratteri BMP** (U+0000 - U+FFFF): Codificati direttamente in 2 byte
- **Caratteri supplementari** (U+10000 - U+10FFFF): Usano una coppia di surrogati:
  - High surrogate: D800-DBFF
  - Low surrogate: DC00-DFFF

### Esempi di codifica UTF-16

```
Carattere  Unicode   UTF-16 (hex)
    A      U+0041    0041
    è      U+00E8    00E8
    €      U+20AC    20AC
    😀     U+1F600   D83D DE00 (coppia di surrogati)
```

### Byte Order e BOM

UTF-16 può essere:
- **UTF-16LE** (Little-Endian): Byte meno significativo prima
- **UTF-16BE** (Big-Endian): Byte più significativo prima

**BOM** (*Byte Order Mark*): U+FEFF all'inizio del file indica l'ordine dei byte:
- `FF FE` → Little-Endian
- `FE FF` → Big-Endian

### Vantaggi di UTF-16

✅ **Efficiente per BMP**: 2 byte fissi per i caratteri più comuni
✅ **Bilanciato**: Buon compromesso tra spazio e complessità

### Svantaggi di UTF-16

❌ **Non compatibile con ASCII**: Byte nulli causano problemi in alcuni sistemi
❌ **Ancora variabile**: Complessità delle coppie di surrogati
❌ **Problema di byte order**: Necessita BOM o specifica esplicita

### Dove si usa UTF-16

- **Windows**: API interne di Windows
- **Java**: Tipo `String` interno
- **JavaScript**: Rappresentazione interna delle stringhe
- **.NET**: Tipo `String` in C#

---

## UTF-32

### Cos'è UTF-32?

**UTF-32** codifica ogni carattere Unicode usando esattamente 4 byte (32 bit).

### Caratteristiche principali

- **Lunghezza fissa**: Sempre 4 byte per carattere
- **Semplicità**: Codifica diretta del code point Unicode
- **Nessuna trasformazione**: Il valore è direttamente il code point

### Esempi di codifica UTF-32

```
Carattere  Unicode   UTF-32 (hex)
    A      U+0041    00 00 00 41
    è      U+00E8    00 00 00 E8
    €      U+20AC    00 00 20 AC
    😀     U+1F600   00 01 F6 00
```

### Byte Order

Come UTF-16, esiste in due varianti:
- **UTF-32LE** (Little-Endian)
- **UTF-32BE** (Big-Endian)

### Vantaggi di UTF-32

✅ **Lunghezza fissa**: Accesso diretto a qualsiasi carattere O(1)
✅ **Semplicità**: Nessuna trasformazione, code point diretto
✅ **Nessuna ambiguità**: Ogni sequenza di 4 byte è un carattere

### Svantaggi di UTF-32

❌ **Sprecone**: 4 byte per ogni carattere, anche per ASCII
❌ **4x spazio di ASCII**: Inefficiente per testi occidentali
❌ **Poco usato**: Quasi mai usato per storage o trasmissione

### Dove si usa UTF-32

- **Elaborazione interna**: In alcuni parser e analizzatori di testo
- **Ricerca accademica**: Per semplicità in algoritmi di ricerca
- **Casi rari**: Quando l'accesso random è critico

---

## Confronto tra le codifiche

### Tabella comparativa

| Caratteristica | ASCII | Extended ASCII | UTF-8 | UTF-16 | UTF-32 |
|---------------|-------|----------------|-------|--------|--------|
| **Dimensione** | 7 bit | 8 bit | 1-4 byte | 2-4 byte | 4 byte |
| **Caratteri max** | 128 | 256 | 1,112,064 | 1,112,064 | 1,112,064 |
| **Compatibilità ASCII** | ✅ | ✅ | ✅ | ❌ | ❌ |
| **Lunghezza fissa** | ✅ | ✅ | ❌ | ❌ | ✅ |
| **Byte per 'A'** | 1 | 1 | 1 | 2 | 4 |
| **Byte per 'è'** | ❌ | 1 | 2 | 2 | 4 |
| **Byte per '中'** | ❌ | ❌ | 3 | 2 | 4 |
| **Byte per '😀'** | ❌ | ❌ | 4 | 4 | 4 |
| **Uso principale** | Legacy | Legacy | Web, Unix | Windows, Java | Raro |

### Spazio occupato - Esempio pratico

Confrontiamo lo spazio per la stringa "Hello 世界!" (Hello World in inglese e cinese):

| Codifica | Byte totali | Dettaglio |
|----------|-------------|-----------|
| ASCII    | ❌ Non può rappresentare 世界 | - |
| UTF-8    | 13 byte     | Hello (5) + spazio (1) + 世(3) + 界(3) + ! (1) |
| UTF-16   | 18 byte     | 9 caratteri × 2 byte |
| UTF-32   | 36 byte     | 9 caratteri × 4 byte |

### Quale scegliere?

**UTF-8** è la scelta migliore per:
- ✅ File di testo, documenti
- ✅ Pagine web, HTML, XML, JSON
- ✅ Codice sorgente
- ✅ Email e messaggi
- ✅ Database (MySQL, PostgreSQL raccomandano UTF-8)

**UTF-16** si usa per:
- 📱 API Windows
- ☕ Stringhe interne Java/JavaScript
- 🔷 .NET Framework

**UTF-32** si usa raramente:
- 🔬 Ricerca e algoritmi specifici
- 🎯 Quando serve accesso diretto ai caratteri

---

## Esempi pratici

### Esempio 1: Visualizzare i byte di una stringa

#### Python
```python
# UTF-8
testo = "Ciao!"
print(testo.encode('utf-8'))  # b'Ciao!'
print(list(testo.encode('utf-8')))  # [67, 105, 97, 111, 33]

# UTF-16
print(testo.encode('utf-16'))  # b'\xff\xfeC\x00i\x00a\x00o\x00!\x00'

# UTF-32
print(testo.encode('utf-32'))  # b'\xff\xfe\x00\x00C\x00\x00\x00i\x00\x00\x00...'
```

#### JavaScript
```javascript
// UTF-16 (interno)
const testo = "Ciao!";
for (let i = 0; i < testo.length; i++) {
    console.log(testo.charCodeAt(i).toString(16)); // Esadecimale
}
// Output: 43, 69, 61, 6f, 21

// UTF-8 (Node.js)
const buffer = Buffer.from(testo, 'utf8');
console.log(buffer); // <Buffer 43 69 61 6f 21>
```

#### Java
```java
String testo = "Ciao!";

// UTF-8
byte[] utf8 = testo.getBytes(StandardCharsets.UTF_8);
System.out.println(Arrays.toString(utf8));
// [67, 105, 97, 111, 33]

// UTF-16
byte[] utf16 = testo.getBytes(StandardCharsets.UTF_16);
System.out.println(Arrays.toString(utf16));
```

### Esempio 2: Conversione tra codifiche

#### Python
```python
# Leggere file con codifica specifica
with open('file.txt', 'r', encoding='utf-8') as f:
    contenuto = f.read()

# Convertire da una codifica all'altra
testo_utf8 = b'\xc3\xa8'  # 'è' in UTF-8
testo_unicode = testo_utf8.decode('utf-8')  # Decodifica
testo_latin1 = testo_unicode.encode('latin-1')  # Ricodifica
print(testo_latin1)  # b'\xe8'
```

### Esempio 3: Problemi comuni e soluzioni

#### Problema: "Mojibake" (caratteri illeggibili)

```
Testo originale: "Caffè"
Scritto come: UTF-8
Letto come: Latin-1
Risultato: "CaffÃ¨"  ← Mojibake!
```

**Soluzione**: Specificare sempre la codifica corretta:
```python
# ❌ Sbagliato
with open('file.txt', 'r') as f:  # Usa codifica di default del sistema
    contenuto = f.read()

# ✅ Corretto
with open('file.txt', 'r', encoding='utf-8') as f:
    contenuto = f.read()
```

#### Problema: BOM (Byte Order Mark) indesiderato

Il BOM (U+FEFF) all'inizio di un file UTF-8 può causare problemi:

```python
# Rimuovere BOM da file UTF-8
with open('file.txt', 'r', encoding='utf-8-sig') as f:  # -sig rimuove BOM
    contenuto = f.read()
```

### Esempio 4: Contare i caratteri correttamente

```python
testo = "Hello 世界! 😀"

# Byte
print(len(testo.encode('utf-8')))  # 17 byte in UTF-8

# Caratteri (code points)
print(len(testo))  # 11 caratteri

# Caratteri visibili (grapheme clusters)
import unicodedata
print(len([c for c in testo if not unicodedata.combining(c)]))  # 11
```

### Esempio 5: Validare UTF-8

```python
def is_valid_utf8(data):
    try:
        data.decode('utf-8')
        return True
    except UnicodeDecodeError:
        return False

# Test
valid = b'Ciao'
invalid = b'\xff\xfe'  # Non valido UTF-8

print(is_valid_utf8(valid))    # True
print(is_valid_utf8(invalid))  # False
```

### Esempio 6: Caratteri emoji e surrogate pairs

```javascript
// JavaScript usa UTF-16 internamente
const emoji = "😀";

// Lunghezza in code units UTF-16
console.log(emoji.length);  // 2 (è una coppia di surrogati!)

// Code points reali
console.log([...emoji].length);  // 1

// Ottenere i code points
console.log(emoji.codePointAt(0).toString(16));  // 1f600
```

---

## Best Practices

### Raccomandazioni generali

1. **Usa sempre UTF-8** per file di testo, a meno che non ci siano motivi specifici
2. **Specifica sempre la codifica** esplicitamente nel codice
3. **Attenzione al BOM** in UTF-8 (generalmente non necessario)
4. **Validazione**: Controlla che i dati siano nella codifica attesa
5. **Database**: Configura il charset a UTF-8 (MySQL: utf8mb4, PostgreSQL: UTF8)

### In HTML
```html
<!-- Specifica sempre il charset -->
<meta charset="UTF-8">
```

### In HTTP Headers
```
Content-Type: text/html; charset=UTF-8
```

### In file sorgente
```python
# -*- coding: utf-8 -*-  (Python 2, non più necessario in Python 3)
```

```java
// Specificare in compilazione: javac -encoding UTF-8 File.java
```

### In SQL
```sql
-- MySQL
CREATE DATABASE mydb CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

-- PostgreSQL
CREATE DATABASE mydb ENCODING 'UTF8';
```

---

## Digitare caratteri speciali da tastiera

### Metodo ALT + Codice (Windows)

Su **Windows**, è possibile digitare caratteri speciali usando il tasto **ALT** e un codice numerico sul tastierino numerico.

#### Come funziona

1. Assicurati che il **Num Lock** sia attivo
2. Tieni premuto il tasto **ALT**
3. Digita il codice numerico sul **tastierino numerico** (non i numeri sopra le lettere)
4. Rilascia il tasto **ALT**

#### Codici ASCII comuni (0-255)

##### Lettere accentate maiuscole
```
ALT + 0192 = À
ALT + 0200 = È
ALT + 0201 = É
ALT + 0204 = Ì
ALT + 0210 = Ò
ALT + 0211 = Ó
ALT + 0217 = Ù
ALT + 0218 = Ú
```

##### Lettere accentate minuscole
```
ALT + 133 = à    oppure    ALT + 0224 = à
ALT + 138 = è    oppure    ALT + 0232 = è
ALT + 130 = é    oppure    ALT + 0233 = é
ALT + 141 = ì    oppure    ALT + 0236 = ì
ALT + 149 = ò    oppure    ALT + 0242 = ò
ALT + 162 = ó    oppure    ALT + 0243 = ó
ALT + 151 = ù    oppure    ALT + 0249 = ù
ALT + 163 = ú    oppure    ALT + 0250 = ú
```

##### Simboli comuni
```
ALT + 0128 = €  (Euro)
ALT + 156  = £  (Sterlina)
ALT + 157  = ¥  (Yen)
ALT + 0169 = ©  (Copyright)
ALT + 0174 = ®  (Registered)
ALT + 0153 = ™  (Trademark)
ALT + 0176 = °  (Grado)
ALT + 0177 = ±  (Più o meno)
ALT + 0215 = ×  (Per/Moltiplicazione)
ALT + 0247 = ÷  (Diviso)
```

##### Frazioni e matematica
```
ALT + 171 = ½  (Un mezzo)
ALT + 172 = ¼  (Un quarto)
ALT + 0188 = ¼
ALT + 0189 = ½
ALT + 0190 = ¾
ALT + 251 = √  (Radice quadrata)
ALT + 252 = ⁿ  (Elevato a n)
ALT + 0178 = ²  (Quadrato)
ALT + 0179 = ³  (Cubo)
```

##### Caratteri grafici
```
ALT + 1   = ☺  (Faccina)
ALT + 2   = ☻  (Faccina piena)
ALT + 3   = ♥  (Cuore)
ALT + 4   = ♦  (Quadri)
ALT + 5   = ♣  (Fiori)
ALT + 6   = ♠  (Picche)
ALT + 11  = ♂  (Maschio)
ALT + 12  = ♀  (Femmina)
ALT + 13  = ♪  (Nota musicale)
ALT + 14  = ♫  (Note musicali)
```

##### Frecce
```
ALT + 16  = ►  (Freccia destra piena)
ALT + 17  = ◄  (Freccia sinistra piena)
ALT + 18  = ↕  (Freccia su-giù)
ALT + 23  = ↨  (Freccia su-giù con base)
ALT + 24  = ↑  (Freccia su)
ALT + 25  = ↓  (Freccia giù)
ALT + 26  = →  (Freccia destra)
ALT + 27  = ←  (Freccia sinistra)
```

##### Caratteri speciali per tabelle/box
```
ALT + 179 = │  (Linea verticale)
ALT + 196 = ─  (Linea orizzontale)
ALT + 218 = ┌  (Angolo alto-sinistra)
ALT + 191 = ┐  (Angolo alto-destra)
ALT + 192 = └  (Angolo basso-sinistra)
ALT + 217 = ┘  (Angolo basso-destra)
ALT + 197 = ┼  (Croce)
```

#### Nota sui codici ALT

Esistono due set di codici:
- **Codici 0-127**: Standard ASCII
- **Codici 128-255**: Extended ASCII (dipendono dalla code page, solitamente Windows-1252)
- **Codici con 0 davanti (es. 0233)**: Usano la code page Windows ANSI corrente

### Metodo Unicode (Windows 10/11)

Per caratteri Unicode più avanzati:

1. Digita il code point Unicode in esadecimale
2. Premi **ALT + X**

Esempio:
```
2764 + ALT + X = ❤ (cuore rosso)
1F600 + ALT + X = 😀 (emoji sorridente)
03B1 + ALT + X = α (alfa greco)
```

### Scorciatoie da tastiera su Windows

#### Combinazioni con ALT Gr (tasto a destra della barra spaziatrice)

```
ALT Gr + E = €  (Euro - su tastiere italiane)
ALT Gr + Shift + 2 = ≈  (Circa uguale)
```

### Metodo su macOS

Su **Mac**, i caratteri speciali si digitano con **Option** (⌥):

#### Caratteri accentati
```
Option + ` poi a = à
Option + e poi a = á
Option + i poi a = â
Option + u poi a = ä
Option + n poi a = ã
```

#### Simboli comuni
```
Option + 2 = €  (Euro)
Option + 3 = £  (Sterlina)
Option + Y = ¥  (Yen)
Option + G = ©  (Copyright)
Option + R = ®  (Registered)
Option + 0 = °  (Grado)
Option + Shift + 8 = •  (Punto elenco)
Option + - = –  (Trattino medio)
Option + Shift + - = —  (Trattino lungo)
```

#### Visualizzatore caratteri Mac
Premi **Control + Command + Spazio** per aprire il pannello emoji e simboli.

### Metodo su Linux

Su **Linux**, usa la combinazione **Ctrl + Shift + U** seguita dal code point Unicode:

```
Ctrl + Shift + U, poi 00E8, poi Invio = è
Ctrl + Shift + U, poi 20AC, poi Invio = €
Ctrl + Shift + U, poi 1F600, poi Invio = 😀
```

Oppure usa il **Compose key** (se configurato):

```
Compose + a + ` = à
Compose + e + ' = é
Compose + c + , = ç
Compose + o + o = °
Compose + = + e = €
```

### Mappa caratteri di Windows

Windows include un'utilità per trovare e copiare caratteri speciali:

1. Apri **Mappa caratteri**: Cerca "charmap" nel menu Start
2. Seleziona il carattere desiderato
3. Clicca su "Seleziona" e poi "Copia"
4. Incolla dove serve (Ctrl + V)

### Emoji su Windows 10/11

Premi **Windows + .** (punto) oppure **Windows + ;** (punto e virgola) per aprire il pannello emoji.

### Tabella riassuntiva per piattaforma

| Sistema | Metodo principale | Esempio |
|---------|------------------|---------|
| Windows | ALT + codice numerico | ALT + 0233 = é |
| Windows | Code point + ALT + X | 20AC + ALT + X = € |
| Windows | Win + . | Pannello emoji |
| macOS | Option + combinazioni | Option + e poi e = é |
| macOS | Ctrl + Cmd + Spazio | Pannello emoji |
| Linux | Ctrl + Shift + U + code point | Ctrl + Shift + U, E8 = è |
| Linux | Compose key | Compose + e + ' = é |

### Consigli pratici

1. **Memorizza i più comuni**: à (ALT+133), è (ALT+138), é (ALT+130), € (ALT+0128)
2. **Stampa una guida**: Tieni una lista dei codici più usati vicino al computer
3. **Usa AutoCorrect**: Programmi come Word sostituiscono automaticamente (c) con ©
4. **Configura scorciatoie**: Molti programmi permettono di creare scorciatoie personalizzate
5. **Pannelli caratteri speciali**: Usa gli strumenti grafici quando disponibili

---

## Risorse aggiuntive

- [Unicode.org](https://unicode.org/) - Sito ufficiale dello standard Unicode
- [UTF-8 Everywhere](https://utf8everywhere.org/) - Manifesto per l'uso di UTF-8
- [Joel on Software - The Absolute Minimum Every Software Developer Absolutely, Positively Must Know About Unicode and Character Sets](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)

---

[TORNA ALL'INDICE](<README.md>)
