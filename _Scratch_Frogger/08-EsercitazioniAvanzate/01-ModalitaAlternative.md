# Modalità di gioco alternative

## Introduzione

Le modalità di gioco alternative rappresentano un'eccellente opportunità per espandere il tuo progetto Frogger e offrire ai giocatori esperienze diverse e stimolanti. In questa esercitazione, esploreremo come implementare diverse varianti del gameplay classico, aggiungendo profondità e rigiocabilità al tuo gioco.

## Obiettivi di apprendimento

1. Comprendere come progettare e implementare diverse modalità di gioco
2. Imparare a gestire timer e contatori per modalità a tempo
3. Sviluppare sistemi di difficoltà progressiva
4. Creare obiettivi speciali e condizioni di vittoria alternative

## Modalità a tempo

La modalità a tempo aggiunge un elemento di urgenza al gameplay, sfidando il giocatore a completare livelli entro un limite di tempo prestabilito.

### Implementazione del timer

1. **Creazione delle variabili necessarie**:
   ```
   Crea una variabile [tempo_rimanente]
   Crea una variabile [tempo_iniziale]
   ```

2. **Inizializzazione del timer**:
   ```
   Quando si clicca su ⚑
   Porta [tempo_iniziale] a (30)
   Porta [tempo_rimanente] a (tempo_iniziale)
   ```

3. **Aggiornamento del timer**:
   ```
   Quando si clicca su ⚑
   Ripeti fino a quando <(tempo_rimanente) = (0)>
     Cambia [tempo_rimanente] di (-1)
     Attendi (1) secondi
   Fine
   Invia a tutti [tempo_scaduto]
   ```

4. **Gestione del game over per tempo scaduto**:
   ```
   Quando ricevo [tempo_scaduto]
   Se <non <(vittoria) = (1)>>
     Invia a tutti [game_over]
   Fine
   ```

### Sfide aggiuntive per la modalità a tempo

- **Timer bonus**: Aggiungi oggetti speciali che, se raccolti, aumentano il tempo disponibile
- **Penalità di tempo**: Implementa ostacoli che, se colpiti, riducono il tempo disponibile
- **Tempo variabile per livello**: Regola automaticamente il tempo disponibile in base alla difficoltà del livello

## Livelli con obiettivi speciali

Questi livelli vanno oltre il semplice "attraversa e raggiungi la meta" aggiungendo obiettivi secondari che il giocatore deve completare.

### Implementazione di oggetti collezionabili

1. **Creazione degli sprite collezionabili**:
   - Disegna o importa sprite per rappresentare gli oggetti da raccogliere (monete, gemme, ecc.)
   - Posizionali strategicamente nel livello

2. **Gestione della raccolta**:
   ```
   Quando si clicca su ⚑
   Mostra
   Ripeti fino a quando <sta toccando [Rana v]?>
     Attendi (0.1) secondi
   Fine
   Nascondi
   Cambia [punteggio] di (10)
   Invia a tutti [oggetto_raccolto]
   ```

3. **Conteggio degli oggetti e condizioni di vittoria**:
   ```
   Quando si clicca su ⚑
   Porta [oggetti_totali] a (5)
   Porta [oggetti_raccolti] a (0)
   
   Quando ricevo [oggetto_raccolto]
   Cambia [oggetti_raccolti] di (1)
   Se <(oggetti_raccolti) = (oggetti_totali)>
     Invia a tutti [tutti_oggetti_raccolti]
   Fine
   ```

### Idee per obiettivi speciali

- **Raccogli tutti gli oggetti**: Il giocatore deve raccogliere tutti gli oggetti prima di completare il livello
- **Salva altri personaggi**: Aggiungi altri personaggi che il giocatore deve raggiungere e salvare
- **Attiva interruttori**: Posiziona interruttori che il giocatore deve attivare per aprire un passaggio
- **Evita zone proibite**: Definisci aree che il giocatore deve evitare completamente

## Modalità endless con difficoltà progressiva

La modalità endless (infinita) sfida il giocatore a sopravvivere il più a lungo possibile in un livello che diventa progressivamente più difficile.

### Implementazione della difficoltà progressiva

1. **Creazione delle variabili di difficoltà**:
   ```
   Crea una variabile [livello_difficolta]
   Crea una variabile [velocita_base]
   Crea una variabile [frequenza_ostacoli]
   ```

2. **Inizializzazione e incremento della difficoltà**:
   ```
   Quando si clicca su ⚑
   Porta [livello_difficolta] a (1)
   Porta [velocita_base] a (3)
   Porta [frequenza_ostacoli] a (2)
   Ripeti fino a quando <(vite) = (0)>
     Attendi (20) secondi
     Cambia [livello_difficolta] di (1)
     Cambia [velocita_base] di (0.5)
     Se <(frequenza_ostacoli) > (0.5)>
       Cambia [frequenza_ostacoli] di (-0.1)
     Fine
     Invia a tutti [aumenta_difficolta]
   Fine
   ```

3. **Adattamento degli ostacoli alla difficoltà**:
   ```
   Quando ricevo [aumenta_difficolta]
   Porta [mia velocità] a (velocita_base)
   ```

### Elementi da considerare per la modalità endless

- **Sistema di punteggio**: Implementa un sistema che premi il tempo di sopravvivenza e le azioni del giocatore
- **Power-up temporanei**: Aggiungi oggetti che forniscono abilità speciali temporanee
- **Ostacoli casuali**: Genera ostacoli in posizioni casuali per aumentare l'imprevedibilità
- **Eventi speciali**: Crea eventi che si verificano casualmente (tempeste, notte, ecc.) che cambiano temporaneamente le meccaniche di gioco

## Esercitazioni pratiche

### Esercizio 1: Modalità a tempo base

Implementa una modalità a tempo semplice in cui il giocatore deve completare un livello entro 30 secondi. Assicurati di visualizzare chiaramente il tempo rimanente e di fornire un feedback quando il tempo sta per scadere.

### Esercizio 2: Livello con oggetti collezionabili

Crea un livello in cui il giocatore deve raccogliere almeno 3 oggetti prima di poter completare il livello. Posiziona gli oggetti in luoghi che richiedono strategie diverse per essere raggiunti.

### Esercizio 3: Modalità endless semplice

Implementa una versione base della modalità endless in cui la velocità degli ostacoli aumenta gradualmente nel tempo. Aggiungi un sistema di punteggio che tenga traccia del tempo di sopravvivenza.

## Sfide avanzate

1. **Modalità multiobiettivo**: Combina diverse modalità (tempo + oggetti collezionabili)
2. **Sistema di livelli dinamici**: Crea un sistema che generi livelli procedurali con difficoltà crescente
3. **Modalità cooperativa**: Adatta una delle modalità alternative per il gioco cooperativo a due giocatori

## Conclusione

Le modalità di gioco alternative aggiungono profondità e varietà al tuo progetto Frogger, aumentando significativamente la rigiocabilità e l'interesse dei giocatori. Sperimenta con diverse combinazioni di regole e meccaniche per creare esperienze uniche e coinvolgenti.

## Risorse aggiuntive

- Esplora giochi arcade classici per ispirazione su diverse modalità di gioco
- Studia esempi di progetti Scratch che implementano modalità di gioco alternative
- Chiedi feedback ad altri giocatori per capire quali modalità risultano più divertenti

[Torna all'indice del modulo](./README.md) | [Vai all'esercitazione successiva](./02-IntelligenzaArtificiale.md)