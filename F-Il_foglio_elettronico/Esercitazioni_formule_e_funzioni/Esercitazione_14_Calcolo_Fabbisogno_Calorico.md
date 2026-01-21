# Esercitazione - Calcolo Fabbisogno Calorico e Analisi Menu

**Obiettivi:**
- Calcolare il fabbisogno calorico giornaliero in base a parametri personali
- Analizzare le calorie di un menu giornaliero
- Confrontare fabbisogno e consumo calorico
- Utilizzare formule condizionali per valutazioni nutrizionali

**Scenario:**
Creare un sistema per calcolare il fabbisogno calorico personale e confrontarlo con l'apporto calorico di un menu giornaliero, fornendo feedback nutrizionali.

---

### 📖 TEORIA: Concetti Nutrizionali e Metabolici

Prima di iniziare con i calcoli, è fondamentale comprendere i concetti scientifici alla base di questa esercitazione.

#### 1. Che cos'è una Caloria?

Una **caloria** (cal) è l'unità di misura dell'energia. In nutrizione si usa la **kilocaloria** (kcal), equivalente a 1000 calorie. Quando parliamo di "calorie" nel cibo, intendiamo sempre kilocalorie.

**Definizione tecnica:** Una kilocaloria è l'energia necessaria per aumentare di 1°C la temperatura di 1 kg di acqua da 14,5°C a 15,5°C a pressione atmosferica standard (1 atm).

**Sistema Internazionale:**
Nel Sistema Internazionale (SI), l'energia si misura in **Joule** (J):
- 1 kcal = 4,184 kJ (kilojoule)
- 1 kJ = 0,239 kcal

Sulle etichette europee spesso trovate entrambi: "350 kcal / 1465 kJ"

**Come vengono misurate le calorie negli alimenti?**

Storicamente si usava la **bomba calorimetrica** (calorimetro):
1. L'alimento viene bruciato completamente in una camera sigillata
2. Il calore prodotto riscalda l'acqua circostante
3. L'aumento di temperatura indica le calorie contenute

Oggi si usano anche calcoli basati sulla composizione:
- Carboidrati: 4 kcal/g
- Proteine: 4 kcal/g
- Grassi: 9 kcal/g
- Alcol: 7 kcal/g
- Fibre: 2 kcal/g (parzialmente digerite)

**Esempi pratici di dispendio energetico:**

**Attività quotidiane:**
- Dormire: 60-70 kcal/ora
- Stare seduti: 80-100 kcal/ora
- Stare in piedi: 100-120 kcal/ora
- Camminare lento (3 km/h): 150-200 kcal/ora
- Camminare veloce (5 km/h): 250-300 kcal/ora
- Salire scale: 400-500 kcal/ora

**Attività domestiche:**
- Pulire casa: 150-200 kcal/ora
- Cucinare: 100-150 kcal/ora
- Giardinaggio: 200-300 kcal/ora
- Lavare l'auto: 150-200 kcal/ora

**Sport e esercizio:**
- Jogging (8 km/h): 400-500 kcal/ora
- Ciclismo moderato: 300-400 kcal/ora
- Nuoto: 400-600 kcal/ora
- Calcio: 450-600 kcal/ora
- Palestra (pesi): 200-300 kcal/ora

**Digestione (Termogenesi indotta dalla dieta - TID):**
Anche digerire costa energia!
- Proteine: 20-30% delle calorie vengono usate per digerirle
- Carboidrati: 5-10%
- Grassi: 0-3%

Questo è il motivo per cui le proteine sono considerate "termogeniche" e aiutano nel dimagrimento.

#### 2. BMI - Indice di Massa Corporea

Il **BMI (Body Mass Index)** o **IMC (Indice di Massa Corporea)** è un indicatore del rapporto tra peso e altezza di una persona.

**Formula:**
```
BMI = Peso (kg) / [Altezza (m)]²
```

**Esempio:**
Una persona di 75 kg alta 1,75 m ha:
```
BMI = 75 / (1,75)² = 75 / 3,06 = 24,5
```

**Classificazione WHO (Organizzazione Mondiale della Sanità):**

| BMI | Categoria | Rischi per la salute |
|-----|-----------|---------------------|
| < 16 | Grave magrezza | Molto alti (malnutrizione) |
| 16 - 18,5 | Sottopeso | Moderati |
| 18,5 - 25 | Normopeso | Minimi |
| 25 - 30 | Sovrappeso | Moderati |
| 30 - 35 | Obesità I grado | Elevati |
| 35 - 40 | Obesità II grado | Molto elevati |
| > 40 | Obesità III grado | Estremamente elevati |

**Limiti del BMI:**
- Non distingue tra massa grassa e massa muscolare
- Non considera la distribuzione del grasso corporeo
- Può non essere accurato per atleti, anziani, bambini
- È solo un indicatore generale, non diagnostico

#### 3. Metabolismo Basale (MB)

Il **Metabolismo Basale** o **BMR (Basal Metabolic Rate)** è la quantità minima di energia (calorie) che il corpo consuma a riposo per mantenere le funzioni vitali.

**Funzioni coperte dal MB:**
- Respirazione
- Circolazione sanguigna
- Regolazione temperatura corporea
- Funzioni cerebrali
- Sintesi proteica
- Funzioni cellulari

**Fattori che influenzano il MB (approfondimento):**

1. **Sesso:**
   - Uomini: MB mediamente 5-10% più alto
   - Motivo: maggiore massa muscolare, maggior livello di testosterone
   - Le donne hanno più grasso essenziale (riserve per gravidanza/allattamento)
   - Durante il ciclo mestruale il MB può variare del 5-10%

2. **Età:**
   - MB diminuisce del 2-3% ogni 10 anni dopo i 20-25 anni
   - Motivo principale: perdita di massa muscolare (sarcopenia)
   - A 50 anni: MB circa 10-15% inferiore rispetto ai 20 anni
   - Mantenere massa muscolare con allenamento può rallentare questo declino

3. **Peso corporeo:**
   - Più massa corporea = più cellule = più energia
   - 1 kg di muscolo brucia circa 13 kcal/giorno a riposo
   - 1 kg di grasso brucia circa 4,5 kcal/giorno a riposo
   - Perdere peso riduce il MB (il corpo si adatta)

4. **Altezza e superficie corporea:**
   - Persone alte hanno più superficie = più dispersione termica
   - Formula di Du Bois: Superficie (m²) = 0,007184 × Peso^0,425 × Altezza^0,725
   - Maggior superficie = maggior MB per termoregolazione

5. **Composizione corporea:**
   - Massa muscolare è metabolicamente attiva (13 kcal/kg/giorno)
   - Grasso è meno attivo (4,5 kcal/kg/giorno)
   - Differenza tra due persone stesso peso può essere 200-300 kcal/giorno
   - Allenamento con pesi aumenta MB nel lungo periodo

6. **Genetica:**
   - Variabilità individuale fino al 20-30%
   - "Metabolismo veloce" vs "metabolismo lento" ha base genetica
   - Polimorfismi genetici influenzano efficienza energetica
   - Storia evolutiva e adattamenti popolazioni

7. **Temperatura ambientale:**
   - Temperature fredde: aumento MB per termogenesi (fino a 10-15%)
   - Temperature molto calde: lieve aumento per raffreddamento
   - Temperatura comfort (20-25°C): MB minimo
   - Esposizione regolare al freddo può attivare "grasso bruno" termogenico

8. **Fattori ormonali (dettaglio):**
   
   **Tiroide (ormoni T3 e T4):**
   - Regolatori principali del metabolismo
   - Ipertiroidismo: MB aumentato fino al 50-100%
   - Ipotiroidismo: MB ridotto del 20-40%
   - Sintomi ipotiroidismo: affaticamento, aumento peso, freddo
   
   **Cortisolo (stress):**
   - Stress cronico eleva cortisolo
   - Favorisce accumulo grasso addominale
   - Può influenzare appetito e metabolismo
   
   **Testosterone:**
   - Promuove massa muscolare → aumenta MB
   - Declino con età riduce MB
   - Differenza principale uomo/donna
   
   **Estrogeni:**
   - Menopausa: calo estrogeni → riduzione MB (2-5%)
   - Influenzano distribuzione grasso corporeo
   
   **Insulina:**
   - Resistenza insulinica altera metabolismo
   - Collegata a obesità e sindrome metabolica
   
   **Leptina e grelina:**
   - Leptina: ormone sazietà
   - Grelina: ormone fame
   - Diete drastiche alterano questi equilibri

9. **Altri fattori:**
   - **Gravidanza**: MB aumenta del 15-20%
   - **Allattamento**: richiede 300-500 kcal/giorno extra
   - **Malattie**: febbre aumenta MB del 13% per ogni grado oltre 37°C
   - **Farmaci**: alcuni aumentano/riducono MB
   - **Caffeina**: aumento temporaneo MB del 3-11%
   - **Sonno**: poco sonno può ridurre MB del 5-20%
   - **Diete yo-yo**: riducono MB nel tempo

**Percentuale del fabbisogno totale (TDEE breakdown):**

Il dispendio energetico totale giornaliero (TDEE) si divide in:

1. **Metabolismo Basale (BMR)**: 60-75%
2. **Termogenesi indotta dalla dieta (TID)**: 10-15%
3. **Attività fisica programmata (EAT)**: 5-15%
4. **Termogenesi non da esercizio (NEAT)**: 10-20%

**NEAT (Non-Exercise Activity Thermogenesis):**
Calorie bruciate con attività quotidiane non sportive:
- Fidgeting (muoversi sulla sedia)
- Camminare al lavoro
- Fare le scale
- Lavori domestici
- Stare in piedi vs seduti

Può variare da 200 a 800 kcal/giorno tra individui sedentari e attivi!

#### 4. Formula di Harris-Benedict

La **formula di Harris-Benedict** è una delle più utilizzate per calcolare il metabolismo basale. Pubblicata nel 1918 e rivista nel 1984, tiene conto di sesso, peso, altezza ed età.

**Formula originale rivista (1984):**

**Per UOMINI:**
```
MB = 88,362 + (13,397 × Peso in kg) + (4,799 × Altezza in cm) - (5,677 × Età in anni)
```

**Per DONNE:**
```
MB = 447,593 + (9,247 × Peso in kg) + (3,098 × Altezza in cm) - (4,330 × Età in anni)
```

**Esempio pratico - Uomo:**
- Età: 35 anni
- Peso: 75 kg
- Altezza: 175 cm

```
MB = 88,362 + (13,397 × 75) + (4,799 × 175) - (5,677 × 35)
MB = 88,362 + 1.004,775 + 839,825 - 198,695
MB = 1.734,27 kcal/giorno
```

**Altre formule disponibili:**
- **Mifflin-St Jeor** (più recente, 1990): considerata più accurata
- **Katch-McArdle**: basata sulla massa magra
- **Cunningham**: specifica per atleti

#### 5. Fattori di Attività Fisica (PAL)

Il **PAL (Physical Activity Level)** è un moltiplicatore che considera l'attività fisica quotidiana oltre al metabolismo basale.

**Livelli dettagliati:**

| Livello | Fattore | Descrizione | Esempi |
|---------|---------|-------------|--------|
| **Sedentario** | 1,2 | Nessuna o poca attività | Lavoro d'ufficio, nessun esercizio |
| **Leggermente attivo** | 1,375 | Leggera attività | Camminata leggera, esercizio 1-3 giorni/settimana |
| **Moderatamente attivo** | 1,55 | Moderata attività | Esercizio 3-5 giorni/settimana, lavoro in piedi |
| **Molto attivo** | 1,725 | Intensa attività | Esercizio intenso 6-7 giorni/settimana, sport |
| **Estremamente attivo** | 1,9 | Attività estrema | Atleti, lavoro fisico pesante quotidiano |

**Calcolo Fabbisogno Totale:**
```
Fabbisogno Calorico Totale = MB × PAL
```

**Esempio:**
Se il MB è 1.734 kcal e l'attività è moderata (PAL = 1,55):
```
Fabbisogno = 1.734 × 1,55 = 2.688 kcal/giorno
```

#### 6. Distribuzione dei Macronutrienti

I **macronutrienti** sono i nutrienti che forniscono energia (calorie):

**1. Carboidrati (Glucidi):**
- **Energia**: 4 kcal per grammo
- **Funzione**: Fonte primaria di energia rapida
- **% raccomandata**: 45-60% delle calorie totali
- **Fonti**: Pasta, pane, riso, patate, frutta, verdura

**2. Proteine:**
- **Energia**: 4 kcal per grammo
- **Funzione**: Costruzione e riparazione tessuti, enzimi, ormoni
- **% raccomandata**: 10-35% delle calorie totali (circa 0,8-1,2 g/kg peso)
- **Fonti**: Carne, pesce, uova, legumi, latticini

**3. Grassi (Lipidi):**
- **Energia**: 9 kcal per grammo (più del doppio di carbo e proteine!)
- **Funzione**: Energia di riserva, membrane cellulari, ormoni, vitamine liposolubili
- **% raccomandata**: 20-35% delle calorie totali
- **Fonti**: Olio, burro, frutta secca, pesce grasso, avocado

**Distribuzione ideale (linee guida):**
- Carboidrati: 50%
- Grassi: 30%
- Proteine: 20%

**Esempio su 2000 kcal/giorno:**
- Carboidrati: 1000 kcal = 250 g (1000÷4)
- Grassi: 600 kcal = 67 g (600÷9)
- Proteine: 400 kcal = 100 g (400÷4)

#### 7. Micronutrienti: Vitamine e Minerali

Oltre ai macronutrienti (che forniscono energia), sono essenziali i **micronutrienti**: sostanze necessarie in piccole quantità ma vitali per la salute.

**Caratteristiche:**
- Non forniscono calorie
- Necessari in mg o μg (microgrammi)
- Coinvolti in migliaia di processi metabolici
- Carenze causano problemi di salute specifici

**VITAMINE (13 essenziali):**

**Liposolubili (accumulate nei grassi):**

*Vitamina A (retinolo):*
- Funzioni: vista, sistema immunitario, pelle
- Fonti: fegato, carote, zucca, uova
- RDA: 900 μg (uomini), 700 μg (donne)

*Vitamina D (colecalciferolo):*
- Funzioni: assorbimento calcio, ossa, immunità
- Fonti: sole (sintesi cutanea), pesce grasso, uova
- RDA: 15 μg (600 UI)
- Carenza molto comune (specie inverno)

*Vitamina E (tocoferolo):*
- Funzioni: antiossidante, protegge membrane cellulari
- Fonti: frutta secca, oli vegetali, semi
- RDA: 15 mg

*Vitamina K:*
- Funzioni: coagulazione sangue, metabolismo osseo
- Fonti: verdure a foglia verde, broccoli
- RDA: 120 μg (uomini), 90 μg (donne)

**Idrosolubili (non accumulate, serve apporto quotidiano):**

*Vitamina C (acido ascorbico):*
- Funzioni: antiossidante, collagene, sistema immunitario
- Fonti: agrumi, kiwi, peperoni, fragole
- RDA: 90 mg (uomini), 75 mg (donne)
- Fumatori: +35 mg/giorno

*Vitamine del gruppo B (8 vitamine):*

- **B1 (tiamina)**: metabolismo carboidrati, sistema nervoso
  * RDA: 1,2 mg
  * Fonti: cereali integrali, legumi, carne

- **B2 (riboflavina)**: produzione energia, pelle
  * RDA: 1,3 mg
  * Fonti: latticini, uova, verdure verdi

- **B3 (niacina)**: metabolismo energetico, DNA
  * RDA: 16 mg
  * Fonti: carne, pesce, cereali

- **B5 (acido pantotenico)**: sintesi ormoni, metabolismo
  * RDA: 5 mg
  * Fonti: diffusa in molti alimenti

- **B6 (piridossina)**: metabolismo proteine, neurotrasmettitori
  * RDA: 1,3-1,7 mg
  * Fonti: pollame, pesce, patate, banane

- **B7 (biotina)**: metabolismo grassi, capelli/unghie
  * RDA: 30 μg
  * Fonti: uova, frutta secca, legumi

- **B9 (folato/acido folico)**: DNA, gravidanza (previene difetti tubo neurale)
  * RDA: 400 μg (600 μg in gravidanza)
  * Fonti: verdure a foglia, legumi, agrumi

- **B12 (cobalamina)**: globuli rossi, DNA, sistema nervoso
  * RDA: 2,4 μg
  * Fonti: solo animali! (carne, pesce, uova, latticini)
  * Vegani: supplementazione obbligatoria

**MINERALI (maggiori e traccia):**

**Minerali maggiori (> 100 mg/giorno):**

*Calcio:*
- Funzioni: ossa, denti, contrazione muscolare, coagulazione
- RDA: 1000-1200 mg
- Fonti: latticini, verdure verdi, sardine con lische

*Fosforo:*
- Funzioni: ossa, DNA, ATP (energia cellulare)
- RDA: 700 mg
- Fonti: carne, pesce, latticini, cereali

*Magnesio:*
- Funzioni: 300+ reazioni enzimatiche, muscoli, nervi
- RDA: 400 mg (uomini), 310 mg (donne)
- Fonti: frutta secca, legumi, cereali integrali, verdure verdi
- Carenza comune: crampi, stanchezza

*Sodio:*
- Funzioni: equilibrio idrico, trasmissione nervosa
- Limite: < 2.300 mg/giorno (< 1 cucchiaino sale)
- Eccesso: ipertensione, ritenzione idrica

*Potassio:*
- Funzioni: contrasta sodio, pressione sanguigna, muscoli
- RDA: 3.400 mg (uomini), 2.600 mg (donne)
- Fonti: banane, patate, spinaci, pomodori, legumi
- Rapporto K/Na dovrebbe essere 2:1

**Minerali traccia (< 100 mg/giorno):**

*Ferro:*
- Funzioni: trasporto ossigeno (emoglobina)
- RDA: 8 mg (uomini), 18 mg (donne in età fertile)
- Forme: eme (animali, meglio assorbito), non-eme (vegetali)
- Fonti: carne rossa, fegato, legumi, spinaci
- Vitamina C aumenta assorbimento ferro vegetale
- Carenza: anemia (stanchezza, pallore)

*Zinco:*
- Funzioni: sistema immunitario, guarigione ferite, DNA
- RDA: 11 mg (uomini), 8 mg (donne)
- Fonti: carne, frutti di mare (ostriche!), legumi, semi

*Iodio:*
- Funzioni: ormoni tiroidei (T3, T4)
- RDA: 150 μg
- Fonti: sale iodato, pesce, alghe
- Carenza: gozzo, ipotiroidismo

*Selenio:*
- Funzioni: antiossidante, tiroide
- RDA: 55 μg
- Fonti: noci del Brasile (1-2 bastano!), pesce, cereali

*Altri:* rame, manganese, fluoro, cromo, molibdeno

**Integrazione: quando serve?**

✅ **Utile/necessaria:**
- Vitamina D (latitudini alte, poca esposizione sole)
- B12 (vegani, anziani)
- Ferro (donne con mestruazioni abbondanti, anemia)
- Acido folico (gravidanza)
- Calcio (intolleranti lattosio, vegani)
- Omega-3 (chi non mangia pesce)

❌ **Spesso inutile:**
- Multivitaminici generici (se dieta varia)
- Megadosi vitamine (eccessi possono essere dannosi)
- "Detox" e "cleanse" (fegato e reni fanno già questo)

**Dieta varia = micronutrienti coperti:**
- Frutta e verdura di tutti i colori
- Cereali integrali
- Proteine varie (animali e vegetali)
- Frutta secca e semi
- Latticini o alternative fortificate

#### 8. Idratazione: L'Acqua nel Bilancio Energetico

**L'acqua è il nutriente più importante!**
- Corpo adulto: 55-60% acqua
- Cervello: 75% acqua
- Sangue: 90% acqua
- Muscoli: 75% acqua
- Ossa: 25% acqua

**Acqua NON ha calorie ma è essenziale per:**
- Tutte le reazioni metaboliche
- Trasporto nutrienti
- Eliminazione scorie
- Termoregolazione (sudore)
- Lubrificazione articolazioni
- Digestione

**Fabbisogno idrico:**

*Formula generale:*
- 30-35 ml per kg di peso corporeo
- Esempio: 75 kg × 30 ml = 2.250 ml (2,25 litri)

*Raccomandazioni:*
- Uomini: 3,7 litri/giorno totali (3 litri da bevande)
- Donne: 2,7 litri/giorno totali (2,2 litri da bevande)
- 20-30% viene da cibi (frutta, verdura, zuppe)

*Aumentare con:*
- Esercizio fisico (+400-800 ml/ora)
- Clima caldo
- Febbre, vomito, diarrea
- Altitudine
- Gravidanza/allattamento (+300-700 ml)
- Diete iperproteiche

**Disidratazione:**

- **1-2% peso corporeo:** sete, ridotta performance
- **3-4%:** mal di testa, irritabilità, stanchezza
- **5-6%:** vertigini, nausea
- **>7%:** rischio per la salute

**Indicatori idratazione:**
✅ Urine chiare/giallo pallido = ben idratato
❌ Urine giallo scuro = disidratato

**Acqua e metabolismo:**
- Bere acqua fredda: lieve aumento metabolismo (corpo scalda acqua)
- Circa 8 kcal per bicchiere
- Bere prima dei pasti: aumenta sazietà

**Bevande e calorie nascoste:**
- Acqua: 0 kcal ✅
- Tè/caffè senza zucchero: 0-5 kcal ✅
- Succhi frutta: 40-60 kcal/100ml ⚠️
- Bibite: 40-50 kcal/100ml ❌
- Alcol: 7 kcal/g (quasi come grassi!) ❌

**Alcol e metabolismo:**
- Non è un nutriente ma ha 7 kcal/g
- Priorità metabolica (il corpo lo elimina prima)
- Blocca temporaneamente metabolismo grassi
- Disidrata (effetto diuretico)
- Interferisce con sonno e recupero
- Limite: 1 drink/giorno (donne), 2 drinks/giorno (uomini)

#### 9. Distribuzione dei Pasti nella Giornata

La distribuzione delle calorie durante la giornata è importante per ottimizzare il metabolismo e l'energia.

**Distribuzione ideale:**

| Pasto | % Calorie | Motivazione |
|-------|-----------|-------------|
| **Colazione** | 20-25% | Dopo il digiuno notturno, serve energia per iniziare |
| **Spuntino mattina** | 5-10% | Mantiene stabile la glicemia |
| **Pranzo** | 35-40% | Pasto principale, energia per pomeriggio |
| **Spuntino pomeriggio** | 5-10% | Evita cali energetici, controlla appetito sera |
| **Cena** | 25-30% | Pasto importante ma non eccessivo (sonno) |

**Errori comuni:**
- ❌ Saltare la colazione
- ❌ Pasti troppo abbondanti la sera
- ❌ Troppe ore tra i pasti
- ❌ Spuntini eccessivi

**Timing ottimale:**
- Colazione: entro 1 ora dal risveglio
- Spuntino: 2-3 ore dopo colazione
- Pranzo: 4-5 ore dopo colazione
- Spuntino: 3-4 ore dopo pranzo
- Cena: almeno 2-3 ore prima di dormire

#### 8. Bilancio Energetico

Il **bilancio energetico** determina se il peso corporeo aumenta, diminuisce o rimane stabile.

**Formula:**
```
Bilancio = Energia IN (cibo) - Energia OUT (consumo)
```

**Tre scenari:**

**1. Bilancio Positivo (Surplus calorico):**
```
IN > OUT  →  Aumento di peso
```
Se consumi 2.500 kcal ma ne spendi solo 2.000: +500 kcal/giorno
- 7.700 kcal = 1 kg di grasso corporeo
- In 15 giorni: 7.500 kcal accumulate ≈ +1 kg

**2. Bilancio Negativo (Deficit calorico):**
```
IN < OUT  →  Perdita di peso
```
Se consumi 1.800 kcal ma ne spendi 2.200: -400 kcal/giorno
- In 19 giorni: 7.600 kcal bruciate ≈ -1 kg

**3. Bilancio Neutro (Mantenimento):**
```
IN = OUT  →  Peso stabile
```
Consumi esattamente quello che spendi

**Regola pratica per dimagrimento sano:**
- Deficit di 500 kcal/giorno = -0,5 kg/settimana
- Deficit di 1000 kcal/giorno = -1 kg/settimana (massimo consigliato)

**Attenzione:**
- Non scendere sotto 1.200 kcal/giorno (donne) o 1.500 kcal/giorno (uomini)
- Deficit troppo elevati rallentano il metabolismo
- La perdita rapida è spesso massa muscolare e acqua, non grasso

#### 9. Valori Nutrizionali degli Alimenti

I valori nutrizionali sono espressi per **100 grammi di prodotto**.

**Come leggere le etichette:**

Esempio - Pasta:
```
Valori per 100g:
Energia: 350 kcal
Carboidrati: 70 g
  di cui zuccheri: 3 g
Proteine: 12 g
Grassi: 1,5 g
  di cui saturi: 0,3 g
Fibre: 3 g
Sale: 0,01 g
```

**Calcolo per porzione reale:**
Se mangi 80g di pasta:
```
Calorie = (350 × 80) / 100 = 280 kcal
Carboidrati = (70 × 80) / 100 = 56 g
Proteine = (12 × 80) / 100 = 9,6 g
```

**Densità calorica:**
Alimenti con alta densità calorica (molte calorie per peso):
- Olio: 884 kcal/100g
- Frutta secca: 600-700 kcal/100g
- Cioccolato: 550 kcal/100g

Alimenti con bassa densità calorica:
- Verdure: 15-50 kcal/100g
- Frutta: 30-80 kcal/100g
- Brodi: 10-30 kcal/100g

#### 10. Applicazione Pratica nel Foglio di Calcolo

**Perché usare i fogli di calcolo per la nutrizione?**

1. **Automazione**: Calcoli complessi eseguiti istantaneamente
2. **Precisione**: Riduzione errori di calcolo manuale
3. **Personalizzazione**: Adattabile a ogni persona
4. **Monitoraggio**: Tracciamento nel tempo
5. **Analisi**: Confronti e trend facilmente visibili
6. **Educazione**: Comprensione pratica dei concetti nutrizionali

**Competenze sviluppate:**
- Uso di formule matematiche complesse
- Logica condizionale per valutazioni
- Collegamenti tra diverse tabelle (fogli)
- Analisi dati e interpretazione risultati
- Presentazione informazioni in modo chiaro

---

**PARTE 1 - DATI PERSONALI E CALCOLO FABBISOGNO**

Crea un foglio "Profilo" con questi dati:

```
A                          B
--- DATI PERSONALI ---
Nome                       Mario Rossi
Sesso                      M
Età (anni)                 35
Peso (kg)                  75
Altezza (cm)               175
Livello Attività           Moderata

--- CALCOLI ---
BMI (Indice Massa Corporea)
Categoria BMI
Metabolismo Basale (MB)
Fabbisogno Calorico Totale
```

**Livelli di Attività:**
- Sedentario (fattore 1,2): poco o nessun esercizio
- Leggero (fattore 1,375): esercizio leggero 1-3 giorni/settimana
- Moderato (fattore 1,55): esercizio moderato 3-5 giorni/settimana
- Intenso (fattore 1,725): esercizio intenso 6-7 giorni/settimana
- Molto Intenso (fattore 1,9): esercizio molto intenso, lavoro fisico

---

**PARTE 2 - MENU GIORNALIERO**

Crea un foglio "Menu Giornaliero" con questa struttura:

```
A          B              C          D         E         F          G
Pasto      Alimento       Quantità   Unità     Cal/100g  Calorie   Proteine(g)
COLAZIONE  Latte          200        ml        64        128       6,4
COLAZIONE  Fette bisc.    40         g         410       164       10,8
COLAZIONE  Marmellata     20         g         250       50        0,2
COLAZIONE  Caffè          1          tazza     2         2         0,1

SPUNTINO   Mela           150        g         52        78        0,4
SPUNTINO   Noci           30         g         654       196       15,2

PRANZO     Pasta          80         g         350       280       10,4
PRANZO     Sugo pomod.    100        g         24        24        1,2
PRANZO     Parmigiano     10         g         431       43        3,6
PRANZO     Insalata       100        g         15        15        1,2
PRANZO     Olio oliva     10         ml        884       88        0
PRANZO     Pane           50         g         265       133       8,5

SPUNTINO   Yogurt         125        g         61        76        5,1

CENA       Petto pollo    150        g         110       165       23,1
CENA       Patate         200        g         77        154       2,0
CENA       Zucchine       150        g         17        26        1,2
CENA       Olio oliva     10         ml        884       88        0
CENA       Pane           30         g         265       80        5,1
```

---

**COMPITI DA SVOLGERE:**

**1. Calcoli nel Foglio "Profilo":**

a) **BMI (Indice Massa Corporea):**
   - Formula: BMI = Peso / (Altezza/100)²
   - Inserisci la formula per calcolare automaticamente

b) **Categoria BMI:**
   - Sottopeso: BMI < 18,5
   - Normopeso: 18,5 ≤ BMI < 25
   - Sovrappeso: 25 ≤ BMI < 30
   - Obesità: BMI ≥ 30
   - Usa funzione SE (o PIÙ.SE) per determinare la categoria

c) **Metabolismo Basale (MB):**
   - Formula Harris-Benedict per UOMINI: MB = 88,362 + (13,397 × peso) + (4,799 × altezza) - (5,677 × età)
   - Formula Harris-Benedict per DONNE: MB = 447,593 + (9,247 × peso) + (3,098 × altezza) - (4,330 × età)
   - Usa SE per scegliere la formula in base al sesso

d) **Fabbisogno Calorico Totale:**
   - Moltiplica il MB per il fattore di attività
   - Crea una tabella di lookup per i fattori:
     ```
     Sedentario        1,2
     Leggero          1,375
     Moderato         1,55
     Intenso          1,725
     Molto Intenso    1,9
     ```
   - Usa CERCA.VERT per trovare il fattore corretto

**2. Calcoli nel Foglio "Menu Giornaliero":**

a) **Colonna F - Calorie:**
   - Calcola le calorie effettive in base alla quantità consumata
   - Formula: (Cal/100g × Quantità) / 100 per grammi
   - Per ml, considera che 100ml ≈ 100g

b) **Totali per Pasto:**
   - Aggiungi righe di totale dopo ogni pasto
   - Calcola calorie totali per COLAZIONE, SPUNTINO mattina, PRANZO, SPUNTINO pomeriggio, CENA

c) **Totale Giornaliero:**
   - Alla fine del menu, calcola:
     - Totale calorie giornaliere
     - Totale proteine giornaliere

**3. Foglio "Analisi e Confronto":**

Crea un nuovo foglio con questa struttura:

```
A                                  B
--- RIEPILOGO GIORNALIERO ---
Fabbisogno Calorico               [da Profilo]
Calorie Consumate                 [da Menu]
Differenza (consumo - fabbisogno)
Differenza %

--- VALUTAZIONE ---
Stato                             
Consiglio                         

--- DISTRIBUZIONE PASTI ---
Calorie Colazione
% su totale giornaliero
Calorie Pranzo
% su totale giornaliero
Calorie Cena
% su totale giornaliero

--- DISTRIBUZIONE IDEALE ---
Colazione dovrebbe essere         20-25%
Pranzo dovrebbe essere            35-40%
Cena dovrebbe essere              25-30%
Spuntini dovrebbero essere        10-15%
```

**Formule da implementare:**

a) **Collegamento tra Fogli:**
   - Usa riferimenti tra fogli: `=Profilo!B12` per il fabbisogno
   - Usa SOMMA per calorie consumate dal menu

b) **Differenza e Percentuale:**
   - Differenza = Consumate - Fabbisogno
   - Differenza % = (Differenza / Fabbisogno) × 100

c) **Valutazione Stato:**
   - Usa SE con condizioni multiple:
     - "ECCESSO" se differenza > 10%
     - "ADEGUATO" se differenza tra -10% e +10%
     - "DEFICIT" se differenza < -10%

d) **Consiglio Personalizzato:**
   - Usa SE per dare consigli:
     - ECCESSO: "Ridurre l'apporto calorico o aumentare l'attività fisica"
     - ADEGUATO: "Alimentazione bilanciata, continua così!"
     - DEFICIT: "Aumentare l'apporto calorico per evitare carenze"

e) **Percentuali Pasti:**
   - Calcola la % di ogni pasto sul totale giornaliero
   - Confronta con i valori ideali

**4. Funzionalità Avanzate (Bonus):**

a) **Grafico a Torta:**
   - Crea un grafico che mostri la distribuzione calorica tra i pasti

b) **Semaforo Nutrizionale:**
   - Usa formattazione condizionale per colorare:
     - Verde: alimentazione adeguata
     - Giallo: leggero eccesso/deficit
     - Rosso: eccesso/deficit significativo

c) **Tabella Macronutrienti:**
   - Aggiungi colonne per carboidrati e grassi
   - Calcola la distribuzione % dei macronutrienti
   - Confronta con i valori ideali (50% carbo, 30% grassi, 20% proteine)

d) **Tracker Settimanale:**
   - Crea un foglio per tracciare 7 giorni
   - Calcola media settimanale
   - Mostra trend con grafici

e) **Database Alimenti:**
   - Crea un foglio separato con tabella alimenti completa
   - Usa CERCA.VERT per cercare automaticamente le calorie inserendo solo il nome

**5. Validazione Dati:**

a) Aggiungi controlli:
   - Peso deve essere tra 30 e 200 kg
   - Altezza tra 100 e 250 cm
   - Età tra 10 e 100 anni

b) Usa SE.ERRORE per gestire errori nei calcoli

c) Aggiungi messaggi di avviso per valori anomali

---

**SOLUZIONE GUIDATA:**

**Formula BMI:**
```
=B5/(B6/100)^2
```

**Formula Categoria BMI:**
```
=SE(B10<18,5;"Sottopeso";SE(B10<25;"Normopeso";SE(B10<30;"Sovrappeso";"Obesità")))
```

**Formula Metabolismo Basale (assumendo sesso in B3):**
```
=SE(B3="M";88,362+(13,397*B5)+(4,799*B6)-(5,677*B4);447,593+(9,247*B5)+(3,098*B6)-(4,330*B4))
```

**Formula Fabbisogno Totale (con tabella fattori in H1:I5):**
```
=B11*CERCA.VERT(B7;H1:I5;2;FALSO)
```

**Formula Calorie nel Menu (riga singola):**
```
=SE(D2="g";(E2*C2)/100;SE(D2="ml";(E2*C2)/100;E2))
```

**Formula Valutazione:**
```
=SE(B4>B3*1,1;"ECCESSO";SE(B4<B3*0,9;"DEFICIT";"ADEGUATO"))
```

---

**CRITERI DI VALUTAZIONE:**

1. Correttezza formule calcolo fabbisogno: 25%
2. Correttezza calcoli menu: 20%
3. Analisi e confronto: 20%
4. Collegamenti tra fogli: 15%
5. Presentazione e usabilità: 10%
6. Funzionalità bonus: 10%

---

**ESTENSIONI POSSIBILI:**

1. **Piano Settimanale:** Creare menu per 7 giorni con analisi completa
2. **Obiettivi:** Aggiungere obiettivi (dimagrimento, mantenimento, aumento massa)
3. **Acqua:** Tracciare anche l'assunzione di acqua (30ml × peso corporeo)
4. **Sport:** Calcolare calorie bruciate con diverse attività
5. **Storia:** Tracciare peso nel tempo e calcolare progressi

---

**DATI AGGIUNTIVI PER TESTARE:**

Prova il foglio con questi profili:

**Profilo 2 - Donna Attiva:**
- Sesso: F
- Età: 28 anni
- Peso: 58 kg
- Altezza: 165 cm
- Attività: Intenso

**Profilo 3 - Uomo Sedentario:**
- Sesso: M
- Età: 45 anni
- Peso: 92 kg
- Altezza: 178 cm
- Attività: Sedentario

---
