# Esercizio 16: Educazione Civica e Partecipazione Democratica

**Livello**: 🟡 Intermedio  
**Tipo grafico**: Multiplo (Colonne raggruppate + Bolle + Linee multiple)  
**Tempo stimato**: 40 minuti  
**Tema**: Democrazia, partecipazione, volontariato, solidarietà  
**Competenze**: Analisi sociologica, correlazioni, riflessione civica

---

## 🎯 Obiettivo

Analizzare lo stato della partecipazione democratica in Italia attraverso tre dimensioni: affluenza elettorale per età e tipo di elezione, distribuzione del volontariato, e trend delle donazioni di sangue e organi, per riflettere sui valori di cittadinanza attiva.

## 📖 Scenario

Lavori per un'associazione che promuove l'educazione civica nelle scuole. Devi preparare materiali che mostrino ai giovani l'importanza della partecipazione democratica e della solidarietà, usando dati concreti per stimolare riflessioni sui comportamenti civici.

## 📊 Dati Forniti

### Dataset 1: Affluenza Elettorale per Fascia d'Età

Copia in celle A1:F7:

```
Fascia_Età	Politiche%	Europee%	Regionali%	Comunali%
18-25 anni	52,3	38,5	45,2	41,8
26-35 anni	68,5	52,7	61,3	58,2
36-50 anni	78,2	65,8	72,5	69,8
51-65 anni	85,6	74,3	81,2	78,5
66+ anni	88,9	78,5	84,7	82,3
Media	74,7	61,9	69,0	66,1
```

**Media storica**: Anni '80 affluenza >90%  
**Trend**: Calo costante, soprattutto giovani

### Dataset 2: Volontariato per Settore

Copia in celle H1:L8:

```
Settore	Volontari_N	Ore_Anno_Medie	Valore_Euro_Mln	Beneficiari_K
Sociale	1250000	180	3375	4200
Sanitario	850000	120	1530	2800
Culturale	620000	95	884,5	1500
Ambientale	480000	110	792	980
Protezione_Civile	420000	85	535,5	1200
Sport	380000	75	427,5	850
Altro	200000	60	180	450
```

**Totale**: 4,2 milioni volontari (7% popolazione)  
**Valore economico totale**: €7,72 miliardi/anno  
**Nota**: Valore calcolato su €15/ora media

### Dataset 3: Donazioni Sangue e Organi - Trend 2018-2026

Copia in celle N1:Q10:

```
Anno	Donatori_Sangue_K	Sacche_Raccolte_K	Iscritti_Registro_Organi_K
2018	1680	2856	3250
2019	1715	2915	3420
2020	1580	2688	3580
2021	1635	2780	3850
2022	1698	2885	4120
2023	1745	2967	4485
2024	1790	3043	4920
2025	1828	3108	5380
2026	1865	3170	5850
```

**Note importanti**:
- 2020: Calo per lockdown COVID-19
- Iscrizioni organi: Boom dopo campagne sensibilizzazione
- 1 donatore sangue = media 1,7 sacche/anno

---

## ✅ Requisiti

### Grafico 1: Affluenza Elettorale per Età

1. **Tipo**: Grafico a colonne raggruppate
2. **Titolo**: "Affluenza Elettorale per Fascia d'Età e Tipo Elezione"
3. **Sottotitolo**: "La disaffezione colpisce soprattutto i giovani"
4. **Colonne**: 4 gruppi (una per tipo elezione)
5. **Colori**:
   - Politiche: Blu scuro (#1976D2) - più importante
   - Europee: Azzurro (#4285F4)
   - Regionali: Verde (#34A853)
   - Comunali: Arancione (#FBBC04)
6. **Etichette**: Percentuale sulle colonne
7. **Asse Y**: "Affluenza (%)", 0-100%
8. **Annotazione**: Linea orizzontale al 90% (affluenza anni '80)
9. **Legenda**: Visibile

### Grafico 2: Volontariato - Analisi Multidimensionale

1. **Tipo**: Grafico a bolle
2. **Titolo**: "Volontariato Italiano - Persone, Tempo, Impatto"
3. **Asse X**: Numero volontari (migliaia)
4. **Asse Y**: Ore medie anno per volontario
5. **Dimensione bolla**: Valore economico (milioni €)
6. **Colore bolla**: Beneficiari (scala colori caldo/freddo)
7. **Etichette**: Nome settore dentro/vicino bolla
8. **Legenda**: Dimensione e colore
9. **Sfondo**: Griglia leggera

### Grafico 3: Trend Donazioni - Solidarietà nel Tempo

1. **Tipo**: Grafico a linee multiple con annotazioni
2. **Titolo**: "Donazioni Sangue e Adesioni Registro Organi 2018-2026"
3. **Sottotitolo**: "Crescita solidarietà nonostante COVID"
4. **Serie**:
   - Donatori sangue: Rosso (#EA4335), spessore 3px
   - Sacche raccolte: Rosso chiaro (#F48FB1), spessore 2px, tratteggiato
   - Iscritti organi: Verde (#34A853), spessore 3px
5. **Marcatori**: Cerchi visibili
6. **Asse Y sinistro**: Sangue (K), 1.500-3.500
7. **Asse Y destro**: Organi (K), 3.000-6.000
8. **Annotazione**: Freccia + testo "Lockdown COVID" su 2020
9. **Legenda**: Destra

---

## 🤔 Domande di Analisi Critica

### Grafico 1 - Affluenza:
1. Quale fascia d'età ha l'affluenza più bassa? Cosa significa per la democrazia?
2. Perché le elezioni Europee hanno affluenza così bassa?
3. Calcola il gap giovani (18-25) vs anziani (66+) nelle Politiche
4. Cosa provoca la disaffezione giovanile? Come invertire il trend?

### Grafico 2 - Volontariato:
1. Quale settore ha più volontari? E quale impatto economico maggiore?
2. C'è correlazione tra ore/anno e numero volontari?
3. Il volontariato vale €7,72 mld: cosa significa per la società?
4. Perché il settore Sociale ha così tanti volontari e beneficiari?

### Grafico 3 - Donazioni:
1. I donatori sangue crescono costantemente o ci sono anomalie?
2. Quanto ha impattato il COVID nel 2020? Come si è recuperato?
3. Gli iscritti registro organi triplicano quasi: cosa ha funzionato?
4. 1,86 milioni donatori su 60 milioni abitanti: è abbastanza?

---

## 💡 Riflessioni Educative

Questo esercizio ci porta a riflettere su:

- **Democrazia è partecipazione**: Non votare significa delegare scelte ad altri
- **Rappresentanza giovani**: Se non votano, chi li rappresenta?
- **Volontariato come pilastro**: 7% popolazione regge servizi essenziali
- **Solidarietà salva vite**: Donare sangue/organi è gesto concreto di cittadinanza
- **Valore tempo**: 4,2 milioni persone donano il proprio tempo per il bene comune
- **Cittadinanza attiva**: Non solo diritti, anche doveri e responsabilità

---

<details>
<summary><strong>📝 Soluzione Completa</strong></summary>

## Grafico 1: Affluenza Elettorale

### Preparazione Dati

Dati già pronti in A1:F7. Verifica che riga "Media" sia esclusa dal grafico (seleziona solo A1:F6).

### Creazione Grafico

1. Seleziona A1:F6 (no riga Media)
2. Inserisci → Grafico → Istogramma a colonne raggruppate
3. **Configurazione base**:
   - Asse X: Fascia_Età
   - Serie: 4 colonne per riga (Politiche, Europee, Regionali, Comunali)

**Personalizza colori**:
- Politiche: Blu scuro #1976D2
- Europee: Azzurro #4285F4
- Regionali: Verde #34A853
- Comunali: Arancione #FBBC04

**Etichette dati**:
- Mostra percentuale su ogni colonna
- Font piccolo (8pt) per leggibilità

**Linea affluenza storica**:
Crea serie helper con valore 90 per ogni fascia.
Aggiungi come linea:
- Colore: Grigio #9E9E9E
- Stile: Tratteggiata
- Etichetta: "Anni '80: >90%"

**Titolo**: `Affluenza Elettorale per Fascia d'Età e Tipo Elezione`
**Sottotitolo**: `La disaffezione colpisce soprattutto i giovani`

**Assi**:
- X: Fasce d'età
- Y: "Affluenza (%)", 0-100%

### Risultato Atteso

```
%
100│                           ─ ─ ─ ─ ─ ─ Anni '80 (90%)
   │
 90│                           ┌┐┌┐┌┐┌┐
   │                       ┌┐┌┐│││││││││
 80│                   ┌┐┌┐│││││││││││││
   │               ┌┐┌┐│││││││││││││││││
 70│           ┌┐┌┐│││││││││││││││││││││
   │       ┌┐┌┐│││││││││││││││││││││││││
 60│       │││││││││││││││││││││││││││││
   │   ┌┐┌┐│││││││││││││││││││││││││││││
 50│   │││││││││││││││││││││││││││││││││
   │┌┐┌┐│││││││││││││││││││││││││││││││││
 40││││││││││││││││││││││││││││││││││││││
   │└┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┴┘
   └────────────────────────────────────→
    18-25  26-35  36-50  51-65  66+

    █ Politiche  █ Europee  █ Regionali  █ Comunali
```

**Insight visivi**:
- Pattern a scalino: Più vecchi = più partecipazione
- 18-25 anni: Solo 52,3% Politiche, 38,5% Europee!
- Tutte le elezioni sotto il 90% storico
- Gap generazionale enorme (36,6 punti!)

## Grafico 2: Volontariato a Bolle

### Preparazione Dati

Dati in H1:L8 già pronti. Per grafico bolle servono:
- **X**: Volontari_N (colonna I)
- **Y**: Ore_Anno_Medie (colonna J)
- **Dimensione**: Valore_Euro_Mln (colonna K)
- **Colore**: Beneficiari_K (colonna L)

### Creazione Grafico

1. Seleziona H1:L8
2. Inserisci → Grafico → Dispersione → Bolle
3. **Configurazione**:
   - Asse X: Volontari_N
   - Asse Y: Ore_Anno_Medie
   - Dimensione: Valore_Euro_Mln
   - Serie: Settore

**Personalizza bolle**:
- Dimensione: Scala lineare, max 50px
- Trasparenza: 60% (vedere sovrapposizioni)
- Bordo: 2px, colore più scuro

**Colori per settore**:
- Sociale: Rosso #EA4335 (più impatto)
- Sanitario: Verde #34A853
- Culturale: Blu #4285F4
- Ambientale: Verde chiaro #7CB342
- Protezione Civile: Arancione #FF6D01
- Sport: Giallo #FBBC04
- Altro: Grigio #9E9E9E

**Etichette**:
- Nome settore dentro bolla (se spazio) o vicino
- Font: Bold per leggibilità

**Titolo**: `Volontariato Italiano - Persone, Tempo, Impatto`
**Sottotitolo**: `Dimensione bolla = valore economico (€)`

**Assi**:
- X: "Numero Volontari (migliaia)", 0-1.400
- Y: "Ore Medie per Volontario (anno)", 0-200

**Griglia**: Leggera, grigio chiaro

### Risultato Atteso

```
Ore/anno
200│
   │
180│        ⬤ Sociale
   │      (3.375M€)
160│
   │
140│
   │
120│                   ⬤ Sanitario
   │                 (1.530M€)
110│             ⬤ Ambientale
   │            (792M€)
100│
   │
 95│  ⬤ Culturale
   │ (884M€)
 85│              ⬤ Prot.Civile
   │             (535M€)
 75│               ⬤ Sport (427M€)
   │
 60│ ⬤ Altro
   └──────────────────────────────→ Volontari (K)
    200  400  600  800 1000 1200
```

**Insight visivi**:
- **Sociale**: Bolla gigante (più persone, più impatto)
- **Sanitario**: Impegno medio-alto (120h/anno)
- Settori culturali: Meno ore ma prezioso
- Totale: €7,72 miliardi valore economico!

## Grafico 3: Trend Donazioni

### Creazione Grafico

1. Seleziona N1:Q10
2. Inserisci → Grafico → Linee multiple
3. **3 serie**

**Personalizza serie**:

**Donatori Sangue**:
- Colore: Rosso #EA4335
- Spessore: 3px
- Marcatori: Cerchi pieni 8px
- Asse: Sinistro

**Sacche Raccolte**:
- Colore: Rosso chiaro #F48FB1
- Spessore: 2px
- Stile: Tratteggiato
- Marcatori: Quadrati 6px
- Asse: Sinistro

**Iscritti Registro Organi**:
- Colore: Verde #34A853
- Spessore: 3px
- Marcatori: Cerchi pieni 8px
- Asse: Destro

**Titolo**: `Donazioni Sangue e Adesioni Registro Organi 2018-2026`
**Sottotitolo**: `Crescita solidarietà nonostante impatto COVID`

**Assi**:
- X: Anno
- Y sinistro: "Sangue (migliaia)", 1.500-3.500
- Y destro: "Registro Organi (migliaia)", 3.000-6.000

**Annotazione COVID**:
- Freccia verticale su anno 2020
- Testo: "Lockdown COVID-19"
- Colore: Rosso
- Posizione: Sopra grafico

**Legenda**: Destra, titoli chiari

### Risultato Atteso

```
Sangue (K)      Anno          Organi (K)
3500│                               │6000
    │                      ○────○   │
3000│    ─○──○──○──○──○───○        │5000
    │   ╱         ╲                 │
    │  ○           ○        ▼       │4000
2500│              COVID            │
    │  ○ ╱╱○╱╱○╱╱○╱╱○╱╱○╱╱○╱╱○╱╱○  │3000
    │                               │
2000│                               │2000
    └───────────────────────────────┘
     2018 2019 2020 2021 2022 2023 2024 2025 2026

     ──○── Donatori    ╱╱○╱╱ Sacche    ──○── Organi
```

**Insight visivi**:
- **2020**: Calo brusco donatori (-7,9%) causa lockdown
- **2021-2026**: Recupero e crescita costante
- **Organi**: Boom incredibile (+80% in 8 anni!)
- Sacche/donatore stabile ~1,7 (coerenza)

## Risposte Domande di Analisi

### Grafico 1 - Affluenza

1. **Fascia affluenza più bassa e significato?**
   - **18-25 anni**: 52,3% Politiche, 38,5% Europee
   - **Significato**:
     - Solo 1 giovane su 2 vota (1 su 3 in Europee!)
     - Classe politica non rappresenta giovani
     - Decisioni prese da generazioni più anziane
     - Rischio: Politiche ignorate esigenze giovani (lavoro, clima, futuro)
   - **Conseguenza**: Auto-esclusione dal processo democratico

2. **Perché Europee così basse?**
   - Media 61,9% (vs 74,7% Politiche)
   - **Cause**:
     - Percepite come "lontane" (Bruxelles vs Roma)
     - Meno copertura mediatica
     - Temi complessi (es: regolamenti UE)
     - Elettori non capiscono poteri Parlamento Europeo
     - Mancano leader carismatici europei
   - **Paradosso**: UE decide il 60% leggi nazionali!

3. **Gap giovani-anziani Politiche?**
   - 18-25 anni: 52,3%
   - 66+ anni: 88,9%
   - **Gap: 36,6 punti percentuali**
   - Quasi **doppia affluenza** anziani!
   - Calcolo voti:
     - 5M giovani 18-25 → 2,6M votano
     - 14M anziani 66+ → 12,4M votano
   - **Peso politico**: Anziani contano 5 volte!

4. **Cause disaffezione e soluzioni?**
   
   **Cause disaffezione giovani**:
   - Sfiducia partiti ("promesse non mantenute")
   - Linguaggio politico incomprensibile
   - Temi elettorali non rilevanti (pensioni vs lavoro)
   - Social: Semplificazione, polarizzazione, fake news
   - Educazione civica scarsa (non sanno come votare)
   - Precariato: "Tanto non cambia nulla"

   **Soluzioni**:
   - **Scuola**: Educazione civica obbligatoria e pratica
   - **Abbassare età voto**: 16 anni per Comunali (coinvolgimento precoce)
   - **Voto online**: Sperimentare per facilitare accesso
   - **Candidati giovani**: Liste con quote generazionali
   - **Temi giovani**: Lavoro, clima, casa in agenda
   - **Trasparenza**: Parlamento aperto, decisioni chiare

### Grafico 2 - Volontariato

1. **Più volontari e impatto economico?**
   - **Più volontari**: Sociale (1,25M = 30% totale)
     - Settore eterogeneo: Povertà, disabili, anziani, immigrati
     - Bisogni crescenti (disuguaglianze, invecchiamento)
     - Barriera ingresso bassa (tutti possono aiutare)
   - **Maggior impatto economico**: Anche Sociale (€3,37 mld)
     - Più persone × più ore (180/anno) = massimo valore
     - Se retribuito: Costo welfare raddoppierebbe!

2. **Correlazione ore/anno e numero volontari?**
   - **Correlazione inversa debole**:
     - Sociale: Molti volontari, ore medio-alte (180)
     - Ambientale: Pochi volontari, ore alte (110)
     - Sport: Pochi volontari, ore basse (75)
   - **Perché?**
     - Settori "pesanti" (sociale, sanitario) richiedono impegno costante
     - Sport: Più occasionale (weekend, stagionale)
   - **Insegnamento**: Conta sia quantità che qualità (ore)

3. **€7,72 mld significato?**
   - Equivalente a:
     - 514.667 persone retribuite full-time a €15/h
     - 1,2% PIL italiano
     - Budget di una regione media
   - **Significato**:
     - Sistema welfare **dipende** da volontari
     - Senza: Molti servizi collasserebbero (es: mense poveri)
     - **Ma**: Non può sostituire Stato (diritti = dovere pubblico)
   - **Valore sociale**: Coesione, comunità, solidarietà (inestimabile)

4. **Sociale: perché tanti volontari e beneficiari?**
   - **Volontari**: 1,25M
   - **Beneficiari**: 4,2M (più di 3x volontari!)
   - **Perché?**
     - Disuguaglianze crescenti (povertà al 11,1%)
     - Anziani soli (invecchiamento popolazione)
     - Immigrazione (integrazione, lingua)
     - Disabilità (assistenza, inclusione)
   - **Modello**: 1 volontario aiuta 3-4 persone
   - **Riflessione**: Segnale bisogno ma anche umanità

### Grafico 3 - Donazioni

1. **Donatori sangue trend?**
   - **Quasi costante** con fluttuazione COVID:
     - 2018: 1.680K
     - 2020: 1.580K (-6,0%, lockdown)
     - 2026: 1.865K (+11% vs 2018)
   - **Crescita lenta**: +2,3K/anno media
   - **Problema**: Popolazione invecchia, serve più giovani donatori

2. **Impatto COVID e recupero?**
   - **2019 → 2020**: -135K donatori (-7,9%)
     - Lockdown: Paura contagio, ospedali chiusi
     - Interventi chirurgici rimandati → Meno fabbisogno
   - **Sacche**: -227K (-7,8%)
   - **Recupero**:
     - 2021: +55K (+3,5%)
     - 2022-2026: Crescita costante
     - 2026: Supera 2019 del +8,7%
   - **Resilienza**: Sistema donatori ha retto shock

3. **Organi: cosa ha funzionato?**
   - **2018**: 3,25M iscritti
   - **2026**: 5,85M (+80%!)
   - **Strategie vincenti**:
     - **Campagne TV/social** (testimonial, storie vere)
     - **Semplificazione iscrizione** (online, app IO, carta identità)
     - **Sensibilizzazione scuole** (giovani target)
     - **Trasparenza liste attesa** (19.000 persone, dati pubblici)
     - **Opt-out silenzio-assenso** (discusso ma efficace)
   - **Risultato**: 1 italiano su 10 iscritto!

4. **1,86M donatori su 60M: abbastanza?**
   - **Percentuale**: 3,1% popolazione
   - **Chi può donare**: 18-65 anni, sani = ~35M persone
   - **Percentuale eleggibili**: 5,3%
   - **Target OMS**: 3-5% popolazione dona regolarmente
   - **Valutazione**: ✅ **Siamo nella media**, ma:
     - Donatori anziani in aumento (età media 45 anni)
     - Servono giovani per ricambio generazionale
     - Alcune regioni sotto media (Sud)
   - **Obiettivo**: 2,5M donatori entro 2030 (+35%)

## Riflessioni Finali

**Messaggi chiave**:
1. 🗳️ **Voto è potere**: Non votare = consegnare decisioni ad altri
2. 👴👦 **Gap generazionale**: Giovani si auto-escludono, anziani decidono
3. 🤝 **Volontariato pilastro**: 4,2M persone reggono welfare (€7,7 mld)
4. 🩸 **Donare salva vite**: 1,86M donatori, ma servono più giovani
5. 💚 **Solidarietà cresce**: +80% iscritti organi, speranza nel futuro
6. 🎓 **Educazione civica chiave**: Serve formazione pratica, non teorica

**Azioni concrete per giovani**:
- 🗳️ **Vota sempre**: Anche "meno peggio" > astensione
- 📚 **Informati**: Leggi programmi, fact-check notizie
- 🤝 **Volontariato**: Anche 2h/settimana fanno differenza
- 🩸 **Dona sangue**: 450ml ogni 3 mesi = 6 vite salvate/anno
- 💚 **Registro organi**: 5 min online, potenziali 8 vite salvate
- 🗣️ **Parla politica**: Con amici, famiglia (senza odio)
- 📱 **Social responsabile**: Verifica fonti, no disinformazione

**Domande per riflettere**:
- Se non voti, chi decide per te?
- Quale mondo vuoi tra 20 anni?
- Hai mai considerato volontariato?
- Sei iscritto registro organi?
- Cosa significa per te "cittadinanza attiva"?

</details>

---

## 🚀 Varianti e Approfondimenti

### Variante A: Affluenza Internazionale
Confronta Italia con altri Paesi (dati 2024):
```
Paese	Affluenza%	Voto_Obbligatorio
Belgio	89,5	Sì
Australia	91,2	Sì (multa)
Italia	63,8	No
USA	62,8	No
Svizzera	48,5	No
```
Grafico a barre: Obbligo voto aumenta partecipazione?

### Variante B: Motivazioni Non-Voto Giovani
Survey 18-25 anni (risposte multiple):
```
Motivazione	Percentuale
"Non mi fido partiti"	58%
"Il mio voto non conta"	42%
"Troppo complicato"	28%
"Non so abbastanza"	35%
"Candidati tutti uguali"	51%
```
Grafico a barre orizzontali: Identifica ostacoli da rimuovere.

### Variante C: Impatto Volontariato su Benessere
Correlazione volontariato-felicità:
```
Frequenza	Wellbeing_Score_/10	Stress_Basso%
Mai	6,2	45
Occasionale	7,1	58
Mensile	7,8	68
Settimanale	8,3	76
```
Scatter plot: Donare tempo fa bene a chi dona!

### Variante D: Donazioni per Età
```
Fascia_Età	Donatori_Sangue%	Iscritti_Organi%
18-25	2,1	12,5
26-40	4,8	18,2
41-65	3,9	8,7
66+	0,5	2,3
```
Colonne raggruppate: Giovani donano meno sangue ma si iscrivono più per organi.

---

## 🔗 Risorse Approfondimento

### Democrazia e Partecipazione:
- **Ministero Interno** (dati affluenza): www.interno.gov.it/elezioni
- **Parlamento Europeo**: www.europarl.europa.eu
- **Openpolis** (dati aperti politica): www.openpolis.it

### Volontariato:
- **CSV** (Centri Servizio Volontariato): www.csvnet.it
- **Portale Volontariato**: www.volontariato.org
- **Forum Terzo Settore**: www.forumterzosettore.it

### Donazioni:
- **AVIS** (sangue): www.avis.it
- **AIDO** (organi): www.aido.it
- **Centro Nazionale Trapianti**: www.trapianti.salute.gov.it
- **Iscrizione registro organi**: www.donailtuosì.it

### Educazione Civica:
- **Cittadinanza e Costituzione**: www.cittadinanzaecostituzione.it
- **Educazione Digitale**: www.educazionedigitale.it/civica

---

**Esercizio Precedente**: [Esercizio 15 - Ambiente](esercizio_15_ambiente.md)  
**Prossimo Esercizio**: [Esercizio 17 - Stili di Vita](esercizio_17_stili_vita.md)
