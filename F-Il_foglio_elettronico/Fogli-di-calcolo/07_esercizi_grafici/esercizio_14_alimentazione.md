# Esercizio 14: Alimentazione e Nutrizione Consapevole

**Livello**: 🟡 Intermedio  
**Tipo grafico**: Multiplo (Colonne in pila + Torta + Linee temporali)  
**Tempo stimato**: 40 minuti  
**Tema**: Educazione alimentare, sprechi, obesità  
**Competenze**: Composizione dati, trend temporali, sensibilizzazione sociale

---

## 🎯 Obiettivo

Analizzare i pattern alimentari italiani, gli sprechi e l'emergenza obesità attraverso visualizzazioni che stimolino riflessioni su scelte individuali e collettive.

## 📖 Scenario

Sei un nutrizionista che prepara materiali educativi per scuole e famiglie. Vuoi mostrare con dati concreti come mangiamo, quanto sprechiamo e le conseguenze sulla salute, per promuovere comportamenti più consapevoli e sostenibili.

## 📊 Dati Forniti

### Dataset 1: Consumo Calorico Giornaliero

Copia in celle A1:F6:

```
Fascia_Età	Colazione	Pranzo	Cena	Snack	Totale
6-10 anni	320	650	580	250	1800
11-14 anni	380	750	680	350	2160
15-18 anni	420	850	780	450	2500
19-30 anni	350	720	680	380	2130
31-50 anni	300	650	620	320	1890
```

### Dataset 2: Spreco Alimentare Annuale (Famiglia Media)

Copia in celle H1:K8:

```
Categoria	Kg_Anno	Valore_Euro	Percentuale
Frutta_Verdura	68	280	28
Pane_Pasta	42	105	17
Latticini	35	158	14
Carne_Pesce	28	245	11
Dolci	32	128	13
Bevande	18	52	7
Altro	25	50	10
```

**Totale spreco**: 248 kg, €968/anno per famiglia

### Dataset 3: Tasso Obesità per Età (Trend 2010-2026)

Copia in celle M1:Q6:

```
Anno	6-10_anni	11-14_anni	15-18_anni	Adulti
2010	18,5	15,2	12,8	32,5
2014	20,1	17,5	14,2	34,8
2018	22,8	19,8	16,5	36,2
2022	24,5	21,5	18,1	37,5
2026	25,2	22,8	19,2	38,1
```

---

## ✅ Requisiti

### Grafico 1: Distribuzione Calorie per Pasto

1. **Tipo**: Colonne in pila
2. **Titolo**: "Distribuzione Calorica Giornaliera per Fascia d'Età"
3. **Colonne**: 5 segmenti colorati (1 per pasto)
4. **Colori**:
   - Colazione: Giallo (#FBBC04)
   - Pranzo: Verde (#34A853)
   - Cena: Arancione (#FF6D01)
   - Snack: Rosso (#EA4335)
   - Totale visibile sommando
5. **Asse Y**: "Calorie (kcal)"
6. **Etichette**: Totale sopra ogni colonna
7. **Annotazione**: Linea fabbisogno raccomandato (2000 kcal)

### Grafico 2: Spreco Alimentare

1. **Tipo**: Grafico a torta
2. **Titolo**: "Spreco Alimentare Annuale - €968 per Famiglia"
3. **Sottotitolo**: "248 kg di cibo buttato"
4. **Fette**: Ordinate decrescente
5. **Etichette**: Categoria + Percentuale + Valore €
6. **Evidenzia**: Fetta "Frutta/Verdura" (esplodi 10%)
7. **Colori**: Palette naturale (verdi, marroni)

### Grafico 3: Trend Obesità

1. **Tipo**: Grafico a linee multiple
2. **Titolo**: "Emergenza Obesità - Trend 2010-2026"
3. **Sottotitolo**: "Crescita allarmante in tutte le fasce d'età"
4. **Serie**: 4 linee (bambini, pre-adolescenti, adolescenti, adulti)
5. **Colori gradiente**: Dal chiaro (bambini) allo scuro (adulti)
6. **Marcatori**: Cerchi grandi
7. **Linee**: Spessore 3px
8. **Annotazione**: Obiettivo OMS 2030 (riduzione 10%)

---

## 🤔 Domande di Analisi Critica

### Grafico 1 - Calorie:
1. Quale fascia d'età consuma più calorie? Perché?
2. Gli snack rappresentano che % delle calorie totali per adolescenti?
3. Il consumo reale è bilanciato rispetto al fabbisogno (2000 kcal)?
4. Cosa noti sulla distribuzione: colazione leggera è un problema?

### Grafico 2 - Sprechi:
1. Frutta/verdura sono lo spreco maggiore: perché?
2. €968/anno per famiglia = quanto per l'Italia (15M famiglie)?
3. Quali categorie potrebbero essere ridotte facilmente?
4. Impatto ambientale di 248 kg cibo sprecato?

### Grafico 3 - Obesità:
1. Quale fascia ha crescita più rapida?
2. Trend è lineare o accelera?
3. Se continua, quale sarà il tasso nel 2030?
4. Quali sono cause e conseguenze socio-sanitarie?

---

## 💡 Riflessioni Educative

- **Consapevolezza porzioni**: Mangiamo più del necessario?
- **Cultura spreco**: Pianificazione spesa salva soldi e ambiente
- **Obesità infantile**: Responsabilità genitori, scuola, pubblicità
- **Prevenzione**: Educazione alimentare fin da piccoli
- **Sostenibilità**: Cibo sprecato = risorse sprecate (acqua, energia)

---

<details>
<summary><strong>📝 Soluzione Completa</strong></summary>

## Grafico 1: Distribuzione Calorie

### Preparazione
Verifica che Totale sia calcolato:
```
F2: =SOMMA(B2:E2)
```
Copia giù fino a F6.

### Creazione

1. Seleziona A1:E6 (senza colonna Totale)
2. Inserisci → Grafico → Istogramma a colonne in pila
3. **Personalizza colori**:

**Segmenti**:
- Colazione: #FBBC04 (giallo)
- Pranzo: #34A853 (verde)
- Cena: #FF6D01 (arancione)
- Snack: #EA4335 (rosso)

**Etichette**:
- Mostra totale sopra colonna: 
  - Aggiungi serie "Totale" invisibile
  - Attiva etichette solo su questa

**Linea fabbisogno**:
Crea serie helper colonna G con 2000 per ogni riga.
Aggiungi come serie linea, colore grigio tratteggiato.

### Risultato Atteso

```
kcal
2500│       ┌───┐
    │       │Snk│        Fabbisogno
2000│ ─ ─ ─│─ ─│─ ─ ─ ─ (2000 kcal)
    │ ┌───┐│Cen│┌───┐
1500││Snk ││na ││   │
    ││┌──┐││   ││┌──┐│
1000│││Ce│││Prn│││Ce││
    │││na│││zo │││na││
 500││└──┘││   ││└──┘│
    ││Col││   ││Col │
    │└───┘└───┘└────┘
    └─────────────────→
     6-10  15-18  31-50
```

**Insight**:
- 15-18 anni: 2500 kcal (+25% su fabbisogno)
- Snack adolescenti: 450 kcal = 18% totale!
- Colazione sempre sottodimensionata

## Grafico 2: Spreco Alimentare

### Preparazione

**Ordina** per Kg_Anno decrescente prima di creare grafico:
1. Seleziona H1:K8
2. Dati → Ordina intervallo
3. Ordina per: Kg_Anno, Decrescente

### Creazione

1. Seleziona H1:H8 e J1:J8 (Categoria + Percentuale)
2. Inserisci → Grafico → Torta
3. **Titolo**: `Spreco Alimentare Annuale - €968 per Famiglia`
4. **Sottotitolo**: `248 kg/anno di cibo buttato`

**Etichette**:
- Formato: `Categoria: % (€valore)`
- Esempio: `Frutta/Verdura: 28% (€280)`
- Posizione: Esterna con linee

**Esplodi fetta principale**:
- Frutta/Verdura: Distanza 0,12

**Colori palette naturale**:
- Frutta/Verdura: Verde (#34A853)
- Pane/Pasta: Marrone chiaro (#F4B400)
- Latticini: Bianco sporco (#F8F9FA)
- Carne/Pesce: Rosso (#EA4335)
- Dolci: Rosa (#F48FB1)
- Bevande: Azzurro (#81D4FA)
- Altro: Grigio (#9E9E9E)

### Analisi Visiva

```
        Altro 10%
    Bevande 7%
  Dolci 13%      ╱─────╲
              ╱  Frutta  ╲ ← Esplosa
            │   Verdura   │
            │    28%      │
            │   (€280)    │
             ╲───────────╱
  Carne 11%    ╲       ╱  Latticini 14%
                ╲─────╱
            Pane/Pasta 17%
```

**Calcolo impatto nazionale**:
15 milioni famiglie × €968 = **€14,5 miliardi/anno**!

## Grafico 3: Trend Obesità

### Creazione

1. Seleziona M1:Q6
2. Inserisci → Grafico → Linee
3. **4 serie** (una per fascia d'età)

**Personalizzazione serie**:

**6-10 anni**:
- Colore: Azzurro chiaro (#81D4FA)
- Spessore: 3px
- Marcatori: Cerchi 8px

**11-14 anni**:
- Colore: Blu medio (#4285F4)
- Spessore: 3px
- Marcatori: Cerchi 8px

**15-18 anni**:
- Colore: Blu scuro (#1976D2)
- Spessore: 3px
- Marcatori: Cerchi 8px

**Adulti**:
- Colore: Blu molto scuro (#0D47A1)
- Spessore: 4px (enfatizza)
- Marcatori: Cerchi 10px

**Titolo**: `Emergenza Obesità - Trend 2010-2026`
**Sottotitolo**: `Crescita allarmante in tutte le fasce d'età`

**Asse Y**: "Tasso Obesità (%)", 10-40%

**Legenda**: Destra, ordine età crescente

### Risultato Atteso

```
%
40│                        ─────○ Adulti
  │                  ─────○
35│            ─────○
  │      ─────○
30│─────○
  │
25│                  ─────○ 6-10 anni
  │            ─────○
20│      ─────○
  │─────○
15│○
  │
10└─────────────────────────────→
   2010 2014 2018 2022 2026
```

**Trend allarmante**:
- Tutte le linee in crescita costante
- Bambini 6-10: da 18,5% a 25,2% (+36%!)
- Adulti: da 32,5% a 38,1% (+17%)
- **Peggio**: Più giovani, più rapida crescita

## Risposte Domande di Analisi

### Grafico 1 - Calorie

1. **Maggior consumo?**
   - 15-18 anni: 2.500 kcal
   - **Perché**: Crescita rapida, metabolismo alto, attività sportiva
   - Ma: Spesso eccesso rispetto a spesa energetica reale
   - Rischio: Se sedentari, 500 kcal extra/giorno = +15 kg/anno!

2. **Snack adolescenti?**
   - 450 kcal su 2.500 totali = **18%**
   - Quasi 1/5 delle calorie da fuoripasto
   - Spesso: merendine, bibite zuccherate, fast food
   - **Problema**: Calorie vuote (pochi nutrienti, molto zucchero/grassi)

3. **Bilanciamento?**
   - Solo fascia 31-50 anni vicina a 2000 kcal
   - Adolescenti: eccesso +25%
   - **Ma**: Conta anche qualità, non solo quantità
   - Fabbisogno varia: sesso, altezza, attività fisica

4. **Colazione leggera?**
   - **Sì, problema**: 300-420 kcal = 15-17% totale
   - Raccomandato: 20-25% (400-500 kcal)
   - Conseguenze:
     - Fame a metà mattina → snack poco salutari
     - Metabolismo rallentato
     - Concentrazione ridotta (scuola/lavoro)
   - **Detto**: "Colazione da re, pranzo da principe, cena da povero"

### Grafico 2 - Sprechi

1. **Frutta/verdura spreco maggiore?**
   - 68 kg (28%) perché:
     - Deperibilità rapida (3-7 giorni)
     - Acquisti impulsivi ("mangerò sano")
     - Porzioni troppo grandi
     - Aspetto estetico (buttate se ammaccate)
     - Stagionalità ignorata (costano ma rovinano)

2. **Impatto nazionale?**
   - €968 × 15 milioni famiglie = **€14,5 miliardi/anno**
   - 248 kg × 15M = **3,72 milioni tonnellate cibo**
   - Equivalente: Sfamare 10 milioni persone per 1 anno
   - CO2 sprecata: ~13 milioni tonnellate

3. **Categorie riducibili?**
   - **Frutta/verdura**: Comprare piccole quantità, più spesso
   - **Pane/pasta**: Congelare pane, usare avanzi (panzanella, frittate)
   - **Dolci**: Non acquistare se non richiesti
   - **Risparmio facile**: -30% spreco = €290/anno recuperati

4. **Impatto ambientale 248 kg?**
   - **Acqua**: ~50.000 litri sprecati (per produrre il cibo)
   - **Terra**: ~500 m² occupati inutilmente
   - **CO2**: ~900 kg emessi per nulla
   - **Biodiversità**: Risorse sottratte agli ecosistemi
   - **Discarica**: Spreco produce metano (gas serra)

### Grafico 3 - Obesità

1. **Crescita più rapida?**
   - **6-10 anni**: +6,7 punti percentuali (18,5% → 25,2%)
   - Crescita: +36% in 16 anni
   - **Allarme**: Bambini obesi → Adulti obesi (80% probabilità)
   - Cause: Stili vita sedentari, junk food, schermi

2. **Trend lineare o accelera?**
   - Quasi **lineare** (crescita costante)
   - Leggera accelerazione 2018-2022 (lockdown COVID?)
   - **Non rallenta**: Nessun intervento efficace finora
   - Preoccupante: Nessuna inversione tendenza

3. **Proiezione 2030?**
   - Se trend continua lineare:
   - 6-10 anni: ~27% (+1,7 punti)
   - Adulti: ~40% (+1,9 punti)
   - **Scenario**: 2 adulti su 5 obesi
   - OMS target: -10% entro 2030 (sembra irraggiungibile)

4. **Cause e conseguenze?**

   **Cause**:
   - Alimentazione: Cibi ultra-processati, zuccheri, porzioni XXL
   - Sedentarietà: Auto, ascensori, divano, schermi
   - Urbanism: Poche aree verdi, insicurezza stradale (no bici)
   - Marketing: Pubblicità junk food vs frutta/verdura
   - Socioeconomiche: Cibo sano costa di più

   **Conseguenze sanitarie**:
   - Diabete tipo 2 (anche in bambini!)
   - Malattie cardiovascolari
   - Problemi articolari
   - Disturbi psicologici (bullismo, bassa autostima)
   - Aspettativa vita ridotta -5/10 anni

   **Conseguenze sociali**:
   - Costi SSN: €9 miliardi/anno obesità-correlata
   - Assenteismo lavoro/scuola
   - Ridotta produttività
   - Disuguaglianze (fasci deboli più colpite)

## Riflessioni Finali

**Messaggi chiave**:
1. 🍎 **Educare fin da piccoli**: Scuola ruolo fondamentale
2. 🗑️ **Sprecare meno = risparmiare + ambiente**: Pianificare spesa
3. 🏃 **Movimento è vita**: Ridurre sedentarietà
4. 📊 **Dati allarmano**: Serve intervento politiche pubbliche
5. 🥗 **Dieta mediterranea**: Patrimonio da riscoprire

**Azioni concrete**:
- Lista spesa pianificata (evita impulsi)
- Porzioni giuste (usa piatti piccoli)
- 5 porzioni frutta/verdura al giorno
- Colazione nutriente
- Attività fisica 30 min/giorno
- Meno schermi, più movimento
- Cucinare insieme (educazione familiare)

</details>

---

## 🚀 Varianti Bonus

### Variante A: Piramide Alimentare
Crea grafico a piramide con frequenza consumi:
```
Livello	Alimento	Freq_Giornaliera
1	Acqua	2000ml
2	Frutta/Verdura	5 porzioni
3	Cereali	3 porzioni
4	Proteine	2 porzioni
5	Dolci	Occasionale
```

### Variante B: Confronto Internazionale Obesità
```
Paese	Obesità_Infantile	Obesità_Adulti
Italia	25,2	38,1
USA	36,5	42,8
Giappone	8,2	4,3
Francia	18,5	28,5
```
Grafico a barre: Stili vita e cultura fanno differenza!

### Variante C: Costo Dieta Sana vs Junk
```
Tipologia	Costo_Kcal	Qualità_Nutrienti
Frutta/Verdura	€0,15/kcal	Alta
Cereali Integrali	€0,08/kcal	Alta
Fast Food	€0,05/kcal	Bassa
Snack Industriali	€0,06/kcal	Bassa
```
Scatter plot: Cibo sano costa più ma nutre meglio.

---

## 📚 Risorse

- **Ministero Salute**: www.salute.gov.it
- **CREA Alimenti e Nutrizione**: www.crea.gov.it
- **Too Good To Go** (anti-spreco): www.toogoodtogo.it
- **OMS Obesità**: www.who.int/obesity

---

**Esercizio Precedente**: [Esercizio 13 - Salute Pubblica](esercizio_13_salute_pubblica.md)  
**Prossimo Esercizio**: [Esercizio 15 - Ambiente e Sostenibilità](esercizio_15_ambiente.md)
