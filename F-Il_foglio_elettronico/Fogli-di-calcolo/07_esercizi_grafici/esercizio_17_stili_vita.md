# Esercizio 17: Stili di Vita Salutari

**Livello**: 🟡 Intermedio  
**Tipo grafico**: Multiplo (Colonne in pila 100% + Colonne+Linea + Colonne in pila)  
**Tempo stimato**: 40 minuti  
**Tema**: Attività fisica, sonno, equilibrio digitale  
**Competenze**: Composizione percentuali, confronti realtà-obiettivi, analisi comportamenti

---

## 🎯 Obiettivo

Analizzare tre pilastri di uno stile di vita sano - attività fisica, sonno adeguato e uso equilibrato della tecnologia - per comprendere quanto i nostri comportamenti reali si discostano dalle raccomandazioni scientifiche e quali azioni intraprendere.

## 📖 Scenario

Lavori come consulente per il Ministero della Salute nel programma "Guadagnare Salute". Devi preparare materiali per sensibilizzare studenti e famiglie sull'importanza di movimento, riposo e uso consapevole degli schermi, mostrando con dati oggettivi dove siamo lontani dagli standard ottimali.

## 📊 Dati Forniti

### Dataset 1: Attività Fisica Settimanale per Età

Copia in celle A1:F8:

```
Fascia_Età	Sedentari%	Occasionali%	Regolari%	Atleti%
6-10 anni	12	28	45	15
11-14 anni	18	32	38	12
15-18 anni	25	35	32	8
19-30 anni	32	38	24	6
31-50 anni	38	35	22	5
51-65 anni	42	33	20	5
66+ anni	48	30	18	4
```

**Definizioni**:
- **Sedentari**: <30 min/settimana
- **Occasionali**: 30-90 min/settimana
- **Regolari**: 150+ min/settimana (raccomandato OMS)
- **Atleti**: 300+ min/settimana

### Dataset 2: Ore Sonno - Reali vs Raccomandate

Copia in celle H1:K8:

```
Fascia_Età	Sonno_Reale	Sonno_Raccomandato	Deficit
6-10 anni	9,2	10,5	-1,3
11-14 anni	8,1	9,5	-1,4
15-18 anni	7,2	9,0	-1,8
19-30 anni	6,8	8,0	-1,2
31-50 anni	6,5	7,5	-1,0
51-65 anni	6,8	7,5	-0,7
66+ anni	7,5	7,5	0,0
```

**Nota**: Raccomandazioni American Academy of Sleep Medicine  
**Problema**: Tutte le fasce (tranne anziani) dormono **meno** del necessario

### Dataset 3: Screen Time Giovani 11-19 Anni (Ore/Giorno)

Copia in celle M1:R4:

```
Attività	Feriali	Weekend	Media_Settimanale
Social_Media	2,8	4,2	3,2
Gaming	1,5	3,8	2,1
Studio_Digitale	2,2	1,5	2,0
Video_Streaming	1,8	3,5	2,3
Messaggistica	1,2	1,5	1,3
Totale	9,5	14,5	10,9
```

**Raccomandazione pediatri**: Max 2 ore/giorno tempo libero digitale  
**Realtà**: Media 10,9 ore/giorno (5x limite!)

---

## ✅ Requisiti

### Grafico 1: Attività Fisica - Composizione Percentuale

1. **Tipo**: Grafico a colonne in pila al 100%
2. **Titolo**: "Livello di Attività Fisica per Fascia d'Età"
3. **Sottotitolo**: "La sedentarietà aumenta drammaticamente con l'età"
4. **Colonne**: Una per fascia d'età, divisa in 4 segmenti (100%)
5. **Colori** (semantici):
   - Sedentari: Rosso (#EA4335) - problema
   - Occasionali: Arancione (#FBBC04) - insufficiente
   - Regolari: Verde chiaro (#7CB342) - buono
   - Atleti: Verde scuro (#2E7D32) - ottimo
6. **Etichette**: Percentuale su ogni segmento (se spazio >5%)
7. **Legenda**: Visibile, con definizioni
8. **Annotazione**: Testo "OMS: minimo 150 min/sett" in verde

### Grafico 2: Sonno - Gap Realtà vs Raccomandazioni

1. **Tipo**: Grafico combinato (colonne + linea)
2. **Titolo**: "Ore di Sonno: Realtà vs Raccomandazioni OMS"
3. **Sottotitolo**: "Deficit cronico in tutte le fasce d'età (tranne anziani)"
4. **Colonne**: Sonno_Reale (asse sinistro)
5. **Linea**: Sonno_Raccomandato (asse sinistro, stessa scala)
6. **Colori**:
   - Colonne reale: Blu chiaro (#81D4FA)
   - Linea raccomandato: Verde scuro (#2E7D32), spessore 3px
   - Zona deficit: Riempimento rosso trasparente tra colonna e linea
7. **Etichette**: Valori ore + deficit in rosso
8. **Asse Y**: "Ore di Sonno", 0-12 ore
9. **Marcatori**: Cerchi grandi sulla linea

### Grafico 3: Screen Time Giovani - Composizione Attività

1. **Tipo**: Grafico a colonne in pila (non percentuale, valori assoluti)
2. **Titolo**: "Screen Time Giovani 11-19 Anni per Attività"
3. **Sottotitolo**: "10,9 ore/giorno media - 5 volte il limite raccomandato"
4. **Colonne**: 3 (Feriali, Weekend, Media_Settimanale)
5. **Segmenti**: 5 attività impilate
6. **Colori**:
   - Social Media: Blu (#4285F4)
   - Gaming: Rosso (#EA4335)
   - Studio Digitale: Verde (#34A853) - unico positivo
   - Video Streaming: Arancione (#FF6D01)
   - Messaggistica: Giallo (#FBBC04)
7. **Etichette**: Ore su ogni segmento
8. **Asse Y**: "Ore al Giorno", 0-16
9. **Annotazione**: Linea rossa orizzontale a 2h = "Limite raccomandato (tempo libero)"

---

## 🤔 Domande di Analisi Critica

### Grafico 1 - Attività Fisica:
1. Quale fascia d'età è più sedentaria? Quale più attiva?
2. Calcola: Quanti adolescenti 15-18 rispettano i 150 min/sett OMS?
3. Perché l'attività fisica crolla con l'età? Cause sociali/culturali?
4. Quali politiche potrebbero invertire il trend sedentarietà?

### Grafico 2 - Sonno:
1. Chi soffre del deficit di sonno maggiore in ore? In percentuale?
2. Gli anziani dormono abbastanza: perché solo loro?
3. Calcola l'impatto del deficit cronico: Ore perse all'anno per un 15-18enne
4. Cosa provoca la privazione cronica di sonno su salute e apprendimento?

### Grafico 3 - Screen Time:
1. Weekend vs feriali: Quanto aumenta lo screen time? Perché?
2. Social e gaming totalizzano quante ore? Sono necessarie?
3. Studio digitale è 2h: È troppo o inevitabile nell'era digitale?
4. Come ridurre screen time senza demonizzare la tecnologia?

---

## 💡 Riflessioni Educative

Questo esercizio ci porta a riflettere su:

- **Salute integrata**: Movimento, sonno, equilibrio digitale sono interconnessi
- **Stili vita moderni**: Tecnologia e sedentarietà creano "pandemia silenziosa"
- **Adolescenza critica**: Abitudini consolidate ora durano tutta la vita
- **Responsabilità condivisa**: Famiglia, scuola, politica devono collaborare
- **Consapevolezza**: Misurare per conoscere, conoscere per cambiare
- **Piccoli passi**: Non serve perfezione, bastano miglioramenti graduali

---

<details>
<summary><strong>📝 Soluzione Completa</strong></summary>

## Grafico 1: Attività Fisica

### Preparazione Dati

Verifica che le percentuali sommino a 100 per ogni riga:
```
12+28+45+15 = 100 ✓
18+32+38+12 = 100 ✓
...
```

### Creazione Grafico

1. Seleziona A1:F8
2. Inserisci → Grafico → Istogramma a colonne in pila al 100%
3. **Configurazione base**:
   - Asse X: Fascia_Età
   - Serie: 4 segmenti (Sedentari, Occasionali, Regolari, Atleti)

**Personalizza colori semantici**:
- Sedentari: Rosso #EA4335
- Occasionali: Arancione #FBBC04
- Regolari: Verde chiaro #7CB342
- Atleti: Verde scuro #2E7D32

**Etichette**:
- Mostra percentuale su ogni segmento
- Nascondi se <5% (poco spazio)
- Font: Bianco bold per contrasto

**Titolo**: `Livello di Attività Fisica per Fascia d'Età`
**Sottotitolo**: `La sedentarietà aumenta drammaticamente con l'età`

**Asse Y**: "Popolazione (%)", 0-100%

**Annotazione**:
Aggiungi casella testo:
"✓ OMS: Minimo 150 min/settimana (Regolari + Atleti)"
Colore verde, posizione alta destra

**Legenda**: Destra, con icone grandi

### Risultato Atteso

```
%
100│┌──────────────────────────────┐
   ││        Atleti (4%)           │ ← 66+
 90││─────────────────────────────┬┤
   ││    Regolari (18%)           ││
 80││                             ││
   ││                             ││
 70││─────────────────────────────││
   ││                             ││
 60││  Occasionali (30%)          ││
   ││                             ││
 50││─────────────────────────────││
   ││                             ││
 40││                             ││
   ││  Sedentari (48%)            ││
 30││                             ││
   │└─────────────────────────────┴┘
   │
   │┌─────┐  ← 6-10 anni
   ││Atl. │
   ││15% ││
   ││────││
   ││Reg.││
   ││45% ││
   ││────││
   ││Occ.││
   ││28% ││
   ││────││
   ││Sed.││
   ││12% ││
   │└────┘
   └────────────────────────→
    6-10  15-18  31-50  66+
```

**Insight visivi**:
- **Inversione drammatica**: 
  - 6-10 anni: 60% attivi (Regolari+Atleti)
  - 66+ anni: 22% attivi
- **Sedentarietà quadrupla**: 12% → 48%
- **Adolescenti (15-18)**: Solo 40% raggiunge 150 min OMS
- **Calo netto atleti**: 15% → 4%

## Grafico 2: Gap Sonno

### Creazione Grafico

1. Seleziona H1:K8 (includi Deficit per calcoli)
2. Inserisci → Grafico → Combinato
3. **Configurazione**:
   - Sonno_Reale: Colonne
   - Sonno_Raccomandato: Linea
   - Stessa scala Y (non doppio asse)

**Personalizza Colonne (Reale)**:
- Colore: Blu chiaro #81D4FA
- Bordo: Blu scuro #1976D2, 2px
- Etichette: Valore ore
- Spaziatura: 50%

**Personalizza Linea (Raccomandato)**:
- Colore: Verde scuro #2E7D32
- Spessore: 3px
- Marcatori: Cerchi 10px, riempimento verde
- Etichette: Valore ore

**Evidenzia Deficit**:
- Area tra colonna e linea: Riempimento rosso trasparente 30%
- Etichetta deficit: Testo rosso sopra colonna (es: "-1,8h")

**Titolo**: `Ore di Sonno: Realtà vs Raccomandazioni OMS`
**Sottotitolo**: `Deficit cronico in tutte le fasce d'età (tranne anziani)`

**Assi**:
- X: Fascia_Età
- Y: "Ore di Sonno per Notte", 0-12

**Legenda**: 
- Colonne blu: "Sonno Reale"
- Linea verde: "Sonno Raccomandato"

### Risultato Atteso

```
Ore
12│
   │
11│         ●────
   │        ╱     ╲
10│       ╱   ┌─┐ ╲●────
   │      │   │ │  │    ╲
 9│     ●   │ │  │     ●───●───●
   │    ╱│   │ │  │ │   │   │   │
 8│   ╱ │   │ │  │ │   │   │   │
   │  ╱  └─┐ │ └─┐│└─┐ │┌─┐│┌─┐│┌─┐●
 7│ ╱  -1,3│ │-1,4││-1,8││-1,2││-1,0││-0,7││ 0
   │╱      └─┘   └┘   └┘└───┘└───┘└───┘└─┘
 6│
   └──────────────────────────────────────→
    6-10  11-14  15-18  19-30  31-50  51-65  66+

    █ Reale  ●─ Raccomandato  ░ Deficit
```

**Insight visivi**:
- **Gap rosso evidente** per tutti tranne 66+
- **Peggiore**: 15-18 anni (-1,8h = -20% fabbisogno!)
- **Unici OK**: Anziani (hanno tempo, ritmi naturali)
- **Adolescenti**: 7,2h invece di 9h (2 ore perse ogni notte)

## Grafico 3: Screen Time Giovani

### Creazione Grafico

1. Seleziona M1:R4 (escludendo riga Totale o creala separata)
2. Inserisci → Grafico → Istogramma a colonne in pila
3. **Configurazione**:
   - Asse X: Tipo giorno (Feriali, Weekend, Media)
   - Serie: 5 attività impilate

**Personalizza colori**:
- Social Media: Blu #4285F4
- Gaming: Rosso #EA4335
- Studio Digitale: Verde #34A853
- Video Streaming: Arancione #FF6D01
- Messaggistica: Giallo #FBBC04

**Etichette**:
- Mostra ore su ogni segmento
- Totale sopra colonna (9,5 / 14,5 / 10,9)

**Linea Limite**:
Crea serie helper con valore 2 (limite raccomandato tempo libero).
Aggiungi come linea:
- Colore: Rosso #D32F2F
- Spessore: 3px
- Stile: Tratteggiata
- Etichetta: "Limite raccomandato (tempo libero)"

**Titolo**: `Screen Time Giovani 11-19 Anni per Attività`
**Sottotitolo**: `10,9 ore/giorno media - 5 volte il limite raccomandato`

**Asse Y**: "Ore al Giorno", 0-16

**Legenda**: Destra, ordine come impilato

### Risultato Atteso

```
Ore/giorno
16│
   │
14│         ┌────┐
   │         │Msg │
12│         │1,5 │
   │         ├────┤
10│         │Vid │  ┌────┐
   │ ┌────┐ │3,5 │  │Msg │
 8│ │Msg │ ├────┤  │1,3 │
   │ │1,2 │ │Stud│  ├────┤
 6│ ├────┤ │1,5 │  │Vid │
   │ │Vid │ ├────┤  │2,3 │
 4│ │1,8 │ │Game│  ├────┤
   │ ├────┤ │3,8 │  │Stud│
 2│─│Stud│─├────┤─│2,0 │─ Limite
   │ │2,2 │ │Soc │  ├────┤
 0│ └────┘ │4,2 │  │Game│
   │        └────┘  │2,1 │
   │                ├────┤
   │                │Soc │
   │                │3,2 │
   └────────────────┴────┴──→
     Feriali  Weekend  Media

     9,5h     14,5h    10,9h
```

**Insight visivi**:
- **Weekend esplode**: +53% vs feriali (14,5h vs 9,5h)
- **Social + Gaming**: 3,2+2,1 = 5,3h/giorno (49% tempo)
- **Studio digitale**: 2h inevitabili (scuola digitale)
- **Tempo libero**: 8,9h/giorno (4,5x limite 2h!)
- **Totale**: 10,9h = 68% tempo sveglio (16h)!

## Risposte Domande di Analisi

### Grafico 1 - Attività Fisica

1. **Più sedentaria e più attiva?**
   - **Più sedentaria**: 66+ anni (48% sedentari)
     - Limiti fisici (artrite, equilibrio)
     - Pensione: Meno obblighi movimento
     - Cultura: "Anziani devono riposare"
   - **Più attiva**: 6-10 anni (60% Regolari+Atleti)
     - Energia naturale bambini
     - Educazione fisica scuola
     - Sport extra-scolastici (calcio, nuoto)
     - Gioco libero (ancora presente)

2. **Adolescenti 15-18 che rispettano OMS?**
   - Regolari + Atleti = 32% + 8% = **40%**
   - Solo **2 su 5** adolescenti si muovono abbastanza
   - **60% sotto soglia** (sedentari + occasionali)
   - Su 2,5M adolescenti italiani → 1,5M inattivi!

3. **Perché attività fisica crolla con età?**
   
   **Cause 11-18 anni (adolescenza)**:
   - Carico studio aumenta (compiti, maturità)
   - Sport diventa competitivo (chi è "scarso" abbandona)
   - Confronto corpo (insicurezza, spogliatoi)
   - Schermi sostituiscono movimento (social, gaming)
   - Trasporti: Auto/scooter vs bici/piedi
   
   **Cause 19-50 anni (adulti)**:
   - Lavoro sedentario (ufficio, 8h seduti)
   - Mancanza tempo percepita ("troppo impegnato")
   - Famiglia (figli assorbono energie)
   - Palestre costose (€40-60/mese)
   - Città non walkable (auto necessaria)
   
   **Cause 51+ anni (anziani)**:
   - Acciacchi fisici (dolori, paure cadute)
   - Cultura riposo ("ho lavorato, merito relax")
   - Solitudine (nessuno con cui fare attività)
   - Mancano programmi specifici età

4. **Politiche per invertire trend?**
   
   **Scuola**:
   - Educazione fisica quotidiana (non 2h/settimana)
   - Sport di classe, non competitivo
   - Pedibus: Andare a scuola a piedi/bici
   
   **Urbane**:
   - Piste ciclabili sicure capillari
   - Parchi e aree gioco di quartiere
   - Città 30 km/h (sicurezza pedoni)
   - Palestre pubbliche gratuite/economiche
   
   **Lavoro**:
   - Incentivi aziende per attività dipendenti
   - Pause attive (10 min stretching ogni 2h)
   - Bike-to-work bonus (€0,25/km bici)
   
   **Culturali**:
   - Campagne "Attivi = Felici"
   - Prescrizione medica esercizio fisico
   - Nonni attivi = modello per nipoti

### Grafico 2 - Sonno

1. **Maggior deficit ore e percentuale?**
   - **Ore**: 15-18 anni → -1,8 ore (-20% fabbisogno)
     - Dormono 7,2h invece di 9h
     - Perdono 109 minuti ogni notte
   - **Percentuale**: 15-18 anni → -20%
     - Ma anche 11-14 anni (-14,7%) e 6-10 anni (-12,4%)
   - **Infanzia/adolescenza più colpite** (fase crescita!)

2. **Solo anziani dormono abbastanza - perché?**
   - **Fattori positivi**:
     - No sveglia (pensione, flessibilità orari)
     - Ritmi circadiani naturali (letto presto, sveglia alba)
     - Meno stress lavorativo/sociale
     - Pisolino pomeridiano (recupero)
   - **Ma**: Qualità sonno spesso peggiore (risvegli notturni)
   - **Tutti gli altri**: Svegli artificiale (sveglia) tronca sonno

3. **Impatto deficit 15-18enne - ore perse anno?**
   - Deficit: 1,8 ore/notte
   - 365 notti/anno × 1,8h = **657 ore/anno perse**
   - = **27,4 giorni** completi di sonno persi!
   - Equivalente: 4 settimane consecutive senza dormire
   - Su 3 anni liceo: **81 giorni** persi (3 mesi!)

4. **Conseguenze privazione cronica sonno?**
   
   **Salute fisica**:
   - Sistema immunitario debole (più malattie)
   - Obesità (ormoni fame alterati: +grelina, -leptina)
   - Diabete tipo 2 (insulino-resistenza)
   - Cuore (ipertensione, +20% rischio infarto)
   
   **Salute mentale**:
   - Ansia e depressione (+60% rischio)
   - Irritabilità, sbalzi umore
   - Burnout scolastico
   
   **Apprendimento**:
   - Memoria consolidamento durante sonno REM
   - Deficit → -40% capacità apprendere nuovo
   - Concentrazione ridotta (-30% performance test)
   - Creatività e problem-solving compromessi
   
   **Comportamenti**:
   - Incidenti (+200% se <6h sonno)
   - Assunzione rischi (impulsività)
   - Uso sostanze (alcol, droghe per compensare)

### Grafico 3 - Screen Time

1. **Aumento weekend e cause?**
   - Feriali: 9,5h → Weekend: 14,5h
   - **Aumento: +5 ore/giorno (+53%)**
   - **Cause weekend**:
     - No scuola: 6-8h libere in più
     - Sveglia tardi → Stanno alzati fino tardi
     - Noia: Casa, nulla da fare → schermi
     - Social: Tutti amici online contemporaneamente
     - Gaming: Sessioni lunghe (2-4h continue)
     - Binge-watching: Serie TV (3-6 episodi)
     - Genitori: Meno controllo weekend (stanchezza)

2. **Social + Gaming - ore e necessità?**
   - Social: 3,2h/giorno
   - Gaming: 2,1h/giorno
   - **Totale: 5,3 ore/giorno** (49% screen time)
   - **Sono necessarie?**
     - **Pro**: Socializzazione digitale (amici lontani), relax
     - **Contro**: Tempo sottratto a movimento, sonno, studio, relazioni reali
     - **Verità**: >1h social correlata a ansia/depressione
     - **Gaming**: <1h OK, >2h problematico (dipendenza)
     - **Risposta**: 1h social + 1h gaming = sufficiente (ridurre 63%)

3. **Studio digitale 2h - giudizio?**
   - 2 ore/giorno = **Inevitabile nell'era digitale**
   - **Scuola digitale**:
     - Registro elettronico
     - Compiti online (classroom, email)
     - Ricerche internet
     - Videolezioni (DAD residuale)
   - **Non è problema**: Uso produttivo, inevitabile
   - **Ma**: Occhi affaticati → Regola 20-20-20
     - Ogni 20 min, guarda 20 secondi a 20 piedi (6m)
   - **Soluzione**: Non ridurre studio, ridurre tempo libero digitale

4. **Ridurre screen time senza demonizzare?**
   
   **Approccio bilanciato**:
   - Tecnologia = strumento, non nemico
   - Distinguere: Uso produttivo (studio) vs passivo (scroll)
   - Non vietare, educare a uso consapevole
   
   **Strategie pratiche**:
   
   **Limiti intelligenti**:
   - App time-limit (iOS Screen Time, Android Digital Wellbeing)
   - 1h social, 1h gaming max/giorno
   - No schermi 1h prima letto (melatonina)
   - No smartphone a tavola (famiglia)
   
   **Alternative attraenti**:
   - Sport di squadra (amici IRL)
   - Hobby manuali (musica, arte, cucina)
   - Natura (trekking, campeggio)
   - Volontariato (scopo, comunità)
   
   **Modelli genitori**:
   - Genitori primi a ridurre schermi
   - Serate giochi da tavolo (no TV/phone)
   - Uscite famiglia attive
   
   **Scuola**:
   - Educazione digitale (riconoscere manipolazione)
   - Progetti pratici vs teoria
   - Sport/arte valorizzati come materie core
   
   **Design etico**:
   - Social: Disattivare notifiche, no autoplay
   - Gaming: No microtransazioni predatorie ragazzi
   - Regolamentare dark patterns (design addictive)

## Riflessioni Finali

**Messaggi chiave**:
1. 🏃 **Sedentarietà pandemica**: 60% adolescenti inattivi, salute futura a rischio
2. 😴 **Debito sonno**: -27 giorni/anno adolescenti, impatta tutto (salute, scuola, umore)
3. 📱 **Schermi onnipresenti**: 11h/giorno giovani, tempo sottratto a vita reale
4. ⏱️ **Tutto interconnesso**: Schermi → Meno movimento + Meno sonno → Salute peggiore
5. 🎯 **Piccoli cambiamenti**: Non serve perfezione, +30 min movimento + 1h sonno + -3h schermi = trasformazione
6. 👨‍👩‍👧 **Responsabilità condivisa**: Individuo + Famiglia + Scuola + Società

**Azioni concrete studenti**:
- 🏃 **Movimento**: 30 min/giorno (anche solo camminare a scuola)
- 😴 **Sonno**: Letto sempre stessa ora (anche weekend ±1h)
- 📱 **Schermi**: App time-limit, no phone 1h pre-letto
- 🎨 **Hobby offline**: Riscopri passioni manuali
- 👥 **Socialità IRL**: Vedi amici di persona, non solo chat
- 🧘 **Mindfulness**: 10 min/giorno meditazione/respirazione

**Azioni concrete famiglie**:
- 🍽️ **Pasti senza schermi**: Tavola = momento qualità
- 🏠 **Zone phone-free**: Camere letto, bagni
- 🚲 **Mobilità attiva**: Scuola a piedi/bici se possibile
- 🌳 **Weekend natura**: Almeno 1 uscita fuori ogni 2 settimane
- 💤 **Routine sonno**: Orari coerenti anche weekend
- 🎮 **Gaming sociale**: Se gaming, almeno con amici (no solitario)

**Domande per riflettere**:
- Quante ore mi muovo veramente ogni settimana?
- Dormo abbastanza? Come mi sento al risveglio?
- Quanto tempo passo su schermi senza accorgermene?
- Cosa vorrei fare se non avessi smartphone per 1 giorno?
- Il mio corpo è un dono: Lo sto curando?

</details>

---

## 🚀 Varianti e Approfondimenti

### Variante A: Test Forma Fisica Scuola
Confronta risultati test nazionale fitness studenti 2000 vs 2025:
```
Test	Anno_2000	Anno_2025	Variazione%
Corsa 1000m (min)	4:20	5:05	-17%
Flessioni (n°)	28	18	-36%
Salto lungo (cm)	185	162	-12%
Addominali 1min	45	32	-29%
```
Colonne raggruppate: Declino allarmante capacità fisiche.

### Variante B: Correlazione Sonno-Rendimento
```
Ore_Sonno	Voto_Medio	Assenze_Anno
<6h	6,2	18
6-7h	6,8	12
7-8h	7,5	7
8-9h	8,1	5
>9h	7,8	6
```
Scatter plot: Sonno ottimale = rendimento migliore.

### Variante C: Attività Fisica e Benessere Psicologico
```
Attività_Settimanale	Felicità_/10	Ansia_Bassa%	Autostima_/10
Sedentari	5,8	32	5,2
Occasionali	6,5	48	6,1
Regolari	7,6	68	7,3
Atleti	8,2	76	7,8
```
Grafico radar: Movimento = beneficio totale.

### Variante D: Effetti Limitazione Schermi (Studio Sperimentale)
Gruppo 100 ragazzi, limite 2h/giorno per 3 mesi:
```
Metrica	Pre	Post	Variazione
Sonno ore	7,1	8,2	+1,1h
Attività fisica min/sett	85	145	+71%
Voto medio	7,2	7,8	+8,3%
Felicità /10	6,5	7,6	+17%
```
Colonne prima/dopo: Limiti funzionano!

---

## 🔗 Risorse Approfondimento

### Attività Fisica:
- **OMS** (raccomandazioni movimento): www.who.int/physical-activity
- **Ministero Salute** (Guadagnare Salute): www.guadagnaresalute.it
- **Sport e Salute SpA**: www.sportesalute.eu

### Sonno:
- **Fondazione per la Ricerca sul Sonno**: www.sonnomed.it
- **National Sleep Foundation**: www.sleepfoundation.org
- **App monitoraggio**: Sleep Cycle, AutoSleep

### Equilibrio Digitale:
- **Centro Studi Dipendenze Digitali**: www.dipendenzedigitali.it
- **Common Sense Media** (guide genitori): www.commonsensemedia.org
- **App controllo screen time**: 
  - iOS: Screen Time (integrata)
  - Android: Digital Wellbeing, ActionDash
  - Multi-piattaforma: Freedom, Forest

### Guide Pratiche:
- **"Sonno Adolescenti"** - Guida SIPPS
- **"Movimento Bambini"** - Linee Guida SIP
- **"Tecnologia Consapevole"** - Manifesto Parole O_Stili

---

**Esercizio Precedente**: [Esercizio 16 - Educazione Civica](esercizio_16_educazione_civica.md)  
**Prossimo Esercizio**: [Esercizio 18 - Dashboard Sociale](esercizio_18_dashboard_sociale.md)
