# Ostacoli e collisioni

## Descrizione dell'esercitazione

In questa terza esercitazione, ci concentreremo sulla creazione di ostacoli e sull'implementazione del sistema di collisioni nel nostro gioco Frogger. Impareremo come creare veicoli e altri ostacoli che si muovono attraverso lo schermo, come rilevare quando la rana collide con questi ostacoli, e come implementare un sistema di vite per gestire queste collisioni. Questi elementi sono fondamentali per creare la sfida principale del gioco.

## Indice degli argomenti teorici

1. [Creazione e gestione degli sprite ostacoli](./01-CreazioneOstacoli.md)
2. [Algoritmi di movimento per gli ostacoli](./02-MovimentoOstacoli.md)
3. [Rilevamento delle collisioni](./03-RilevamentoCollisioni.md)
4. [Sistema di vite e game over](./04-SistemaVite.md)
5. [Ottimizzazione delle collisioni](./05-OttimizzazioneCollisioni.md)

## Obiettivi dell'esercitazione

- Creare diversi tipi di ostacoli (veicoli, tronchi, tartarughe)
- Implementare il movimento automatico degli ostacoli
- Sviluppare un sistema di rilevamento delle collisioni
- Implementare un contatore di vite e la logica di game over
- Creare effetti visivi per le collisioni

## Istruzioni passo-passo

### 1. Creazione degli ostacoli

1. Apri il progetto "Frogger - Parte 2" creato nella precedente esercitazione
2. Salva una nuova versione chiamata "Frogger - Parte 3"
3. Crea nuovi sprite per rappresentare i veicoli (auto, camion, ecc.)
4. Posiziona gli ostacoli nelle corsie appropriate dello sfondo

### 2. Movimento degli ostacoli

1. Implementa script per far muovere gli ostacoli orizzontalmente
2. Configura velocità diverse per i vari tipi di ostacoli
3. Aggiungi la logica per far riapparire gli ostacoli dall'altro lato dello schermo quando escono
4. Implementa direzioni di movimento opposte per corsie alternate

### 3. Rilevamento delle collisioni

1. Aggiungi blocchi per rilevare quando la rana tocca un ostacolo
2. Crea una variabile per tenere traccia delle vite rimanenti
3. Implementa la logica per ridurre le vite quando avviene una collisione
4. Fai tornare la rana alla posizione iniziale dopo una collisione

### 4. Sistema di vite e game over

1. Crea una visualizzazione grafica per le vite rimanenti
2. Implementa la logica di game over quando le vite arrivano a zero
3. Aggiungi una schermata di game over o un messaggio appropriato
4. Implementa un sistema per riavviare il gioco dopo il game over

### 5. Effetti visivi per le collisioni

1. Aggiungi effetti grafici quando la rana collide con un ostacolo
2. Implementa un breve ritardo o un'animazione prima di riposizionare la rana
3. Aggiungi effetti sonori per le collisioni

## Sfide aggiuntive

- Implementa diversi tipi di ostacoli con comportamenti unici
- Crea un sistema di difficoltà crescente aumentando la velocità degli ostacoli nel tempo
- Aggiungi zone sicure dove la rana può riposare senza rischio di collisioni
- Implementa un sistema di invincibilità temporanea dopo una collisione

## Concetti di programmazione utilizzati

- Creazione e gestione di più sprite
- Algoritmi di movimento automatico
- Rilevamento delle collisioni
- Gestione degli stati di gioco (vite, game over)
- Effetti visivi e feedback all'utente

## Navigazione del Corso
- [📑 Indice](../README.md)
- [⬅️ Movimento e controllo](../02-MovimentoEControllo/README.md)
- [➡️ Animazioni e suoni](../04-AnimazioniESuoni/README.md)