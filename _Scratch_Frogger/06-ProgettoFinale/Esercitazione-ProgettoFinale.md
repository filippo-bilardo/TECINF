# Esercitazione Pratica: Progetto Finale Frogger

## Introduzione

Questa esercitazione pratica ti guiderà passo dopo passo nella creazione del progetto finale Frogger, integrando tutti gli elementi che hai imparato durante il corso. Seguendo queste istruzioni, realizzerai un gioco completo e funzionante che potrai personalizzare e condividere.

## Prerequisiti

- Aver completato le esercitazioni precedenti del corso
- Conoscenza base di Scratch e dei suoi blocchi
- Comprensione dei concetti di movimento, collisioni e punteggio

## Materiali Necessari

- Computer con accesso a Scratch (online o offline)
- File delle esercitazioni precedenti per riferimento
- Risorse grafiche e audio (fornite o personalizzate)

## Obiettivi dell'Esercitazione

- Creare un gioco Frogger completo e funzionante
- Integrare tutti i componenti sviluppati nelle precedenti esercitazioni
- Implementare un sistema di livelli progressivi
- Aggiungere elementi di personalizzazione
- Ottimizzare il codice per prestazioni migliori

## Istruzioni Passo-Passo

### Fase 1: Configurazione Iniziale del Progetto

1. **Crea un nuovo progetto Scratch**
   - Apri Scratch e crea un nuovo progetto
   - Salvalo con il nome "Frogger Finale"

2. **Importa le risorse necessarie**
   - Crea o importa lo sprite della rana protagonista
   - Prepara gli sprite per veicoli, tronchi e altri ostacoli
   - Crea o importa lo sfondo con strada e fiume

3. **Configura le variabili globali**
   ```
   Crea le seguenti variabili:
   - "vite" (inizializzata a 3)
   - "punteggio" (inizializzata a 0)
   - "livello" (inizializzata a 1)
   - "tempo" (per il conto alla rovescia)
   - "record" (per salvare il punteggio più alto)
   ```

### Fase 2: Implementazione del Protagonista

1. **Programma il movimento della rana**
   ```scratch
   quando si preme [freccia su v]
   punta in direzione (0)
   fai (10) passi
   
   quando si preme [freccia giù v]
   punta in direzione (180)
   fai (10) passi
   
   quando si preme [freccia sinistra v]
   punta in direzione (-90)
   fai (10) passi
   
   quando si preme [freccia destra v]
   punta in direzione (90)
   fai (10) passi
   ```

2. **Implementa il controllo dei bordi**
   ```scratch
   quando si clicca sulla bandiera verde
   per sempre
     se <(x position) < [-230]> allora
       porta x a (-230)
     fine
     se <(x position) > [230]> allora
       porta x a (230)
     fine
     se <(y position) < [-170]> allora
       porta y a (-170)
     fine
     se <(y position) > [170]> allora
       porta y a (170)
     fine
   fine
   ```

3. **Crea l'animazione del movimento**
   ```scratch
   quando si preme [freccia su v]
   cambia costume in [rana_su v]
   
   quando si preme [freccia giù v]
   cambia costume in [rana_giu v]
   
   quando si preme [freccia sinistra v]
   cambia costume in [rana_sinistra v]
   
   quando si preme [freccia destra v]
   cambia costume in [rana_destra v]
   ```

### Fase 3: Implementazione degli Ostacoli

1. **Crea i veicoli sulla strada**
   - Per ogni tipo di veicolo:
   ```scratch
   quando si clicca sulla bandiera verde
   vai a x: (-240) y: (posizione y della corsia)
   per sempre
     cambia x di (velocità)
     se <(x position) > [240]> allora
       vai a x: (-240) y: (posizione y della corsia)
     fine
     attendi (0.1) secondi
   fine
   ```

2. **Crea i tronchi e le tartarughe nel fiume**
   - Per ogni tronco o tartaruga:
   ```scratch
   quando si clicca sulla bandiera verde
   vai a x: (240) y: (posizione y della corsia d'acqua)
   per sempre
     cambia x di (velocità negativa)
     se <(x position) < [-240]> allora
       vai a x: (240) y: (posizione y della corsia d'acqua)
     fine
     attendi (0.1) secondi
   fine
   ```

3. **Implementa il sistema di cloni per gli ostacoli multipli**
   ```scratch
   quando si clicca sulla bandiera verde
   nascondi
   elimina tutti i cloni
   ripeti (numero di veicoli) volte
     crea clone di [me stesso v]
   fine
   
   quando vengo clonato
   mostra
   vai a x: (-240 - (n° clone * distanza tra veicoli)) y: (posizione y della corsia)
   per sempre
     cambia x di (velocità)
     se <(x position) > [240]> allora
       vai a x: (-240) y: (posizione y della corsia)
     fine
     attendi (0.1) secondi
   fine
   ```

### Fase 4: Sistema di Collisioni

1. **Implementa le collisioni con i veicoli**
   ```scratch
   quando si clicca sulla bandiera verde
   per sempre
     se <sta toccando [veicolo1 v] o <sta toccando [veicolo2 v]> o <sta toccando [veicolo3 v]>> allora
       invia [perdi vita v]
     fine
     attendi (0.1) secondi
   fine
   ```

2. **Implementa le collisioni con l'acqua e i tronchi**
   ```scratch
   quando si clicca sulla bandiera verde
   per sempre
     se <sta toccando [acqua v]> allora
       se <non <sta toccando [tronco1 v] o <sta toccando [tronco2 v]> o <sta toccando [tartaruga v]>>> allora
         invia [perdi vita v]
       fine
     fine
     attendi (0.1) secondi
   fine
   ```

3. **Gestisci il movimento sui tronchi**
   ```scratch
   quando si clicca sulla bandiera verde
   per sempre
     se <sta toccando [tronco1 v]> allora
       cambia x di (velocità tronco1)
     fine
     se <sta toccando [tronco2 v]> allora
       cambia x di (velocità tronco2)
     fine
     se <sta toccando [tartaruga v]> allora
       cambia x di (velocità tartaruga)
     fine
     attendi (0.05) secondi
   fine
   ```

### Fase 5: Sistema di Punteggio e Vite

1. **Implementa la gestione delle vite**
   ```scratch
   quando ricevo [perdi vita v]
   cambia [vite v] di (-1)
   nascondi
   riproduci suono [perdi v]
   attendi (1) secondi
   vai a x: (0) y: (-170)
   mostra
   se <(vite) = [0]> allora
     invia [game over v]
   fine
   ```

2. **Implementa il sistema di punteggio**
   ```scratch
   quando sta toccando [area arrivo v]
   cambia [punteggio v] di (100)
   cambia [punteggio v] di (tempo * 10)
   riproduci suono [vittoria v]
   attendi (1) secondi
   vai a x: (0) y: (-170)
   se <(tutte aree raggiunte) = [vero]> allora
     invia [livello completato v]
   fine
   ```

3. **Gestisci il record**
   ```scratch
   quando ricevo [game over v]
   se <(punteggio) > (record)> allora
     imposta [record v] a (punteggio)
   fine
   ```

### Fase 6: Progressione dei Livelli

1. **Implementa il passaggio di livello**
   ```scratch
   quando ricevo [livello completato v]
   cambia [livello v] di (1)
   imposta [tempo v] a (30)
   nascondi tutti gli sprite
   cambia sfondo in [livello completato v]
   attendi (3) secondi
   cambia sfondo in [gioco v]
   mostra tutti gli sprite
   invia [aumenta difficoltà v]
   ```

2. **Aumenta la difficoltà con il progredire dei livelli**
   ```scratch
   quando ricevo [aumenta difficoltà v]
   per tutti gli sprite [veicolo v]
     cambia [velocità v] di (livello * 0.5)
   fine
   per tutti gli sprite [tronco v]
     cambia [velocità v] di (livello * 0.3)
   fine
   imposta [tempo v] a (30 - (livello * 2))
   ```

### Fase 7: Interfaccia Utente e Menu

1. **Crea la schermata iniziale**
   ```scratch
   quando si clicca sulla bandiera verde
   cambia sfondo in [menu iniziale v]
   nascondi tutti gli sprite eccetto [pulsanti menu v]
   ferma [altri script in sprite v]
   ```

2. **Implementa i pulsanti del menu**
   ```scratch
   quando si clicca su questo sprite
   se <(nome) = [gioca v]> allora
     invia [inizia gioco v]
   fine
   se <(nome) = [istruzioni v]> allora
     cambia sfondo in [schermata istruzioni v]
   fine
   se <(nome) = [crediti v]> allora
     cambia sfondo in [schermata crediti v]
   fine
   ```

3. **Gestisci l'inizio del gioco**
   ```scratch
   quando ricevo [inizia gioco v]
   cambia sfondo in [gioco v]
   mostra tutti gli sprite
   imposta [vite v] a (3)
   imposta [punteggio v] a (0)
   imposta [livello v] a (1)
   imposta [tempo v] a (30)
   vai a x: (0) y: (-170)
   ```

### Fase 8: Ottimizzazione e Debugging

1. **Ottimizza gli script**
   - Sostituisci codice ripetitivo con blocchi personalizzati
   - Usa eventi specifici invece di cicli "per sempre" quando possibile
   - Limita i controlli di collisione solo quando necessario

2. **Implementa un sistema di debug**
   ```scratch
   quando si preme [d v]
   se <(modalità debug) = [falso]> allora
     imposta [modalità debug v] a [vero]
     mostra variabile [posizione x v]
     mostra variabile [posizione y v]
   altrimenti
     imposta [modalità debug v] a [falso]
     nascondi variabile [posizione x v]
     nascondi variabile [posizione y v]
   fine
   ```

### Fase 9: Personalizzazione e Miglioramenti

1. **Aggiungi effetti sonori**
   - Suoni per il movimento della rana
   - Suoni per le collisioni
   - Musica di sottofondo

2. **Implementa power-up**
   ```scratch
   quando vengo clonato
   mostra
   per sempre
     se <sta toccando [rana v]> allora
       se <(tipo) = [tempo v]> allora
         cambia [tempo v] di (10)
       fine
       se <(tipo) = [vita v]> allora
         cambia [vite v] di (1)
       fine
       se <(tipo) = [invincibilità v]> allora
         invia [attiva invincibilità v] a [rana v]
       fine
       nascondi
     fine
     cambia y di (-2)
     se <(y position) < [-180]> allora
       elimina questo clone
     fine
     attendi (0.1) secondi
   fine
   ```

3. **Aggiungi animazioni e effetti visivi**
   - Effetti per la vittoria
   - Animazioni per la perdita di una vita
   - Effetti per i power-up

## Sfide Aggiuntive

1. **Implementa una modalità a due giocatori**
   - Aggiungi una seconda rana controllata da un altro giocatore
   - Implementa un sistema di punteggio separato per ogni giocatore

2. **Crea livelli con layout diversi**
   - Progetta sfondi diversi per ogni livello
   - Varia la disposizione degli ostacoli e delle aree sicure

3. **Aggiungi nemici che inseguono la rana**
   - Crea uno sprite predatore che segue la rana
   - Implementa un algoritmo di inseguimento semplice

## Verifica e Test

1. **Controlla che tutte le funzionalità siano implementate**
   - Movimento della rana
   - Collisioni con veicoli e acqua
   - Sistema di punteggio e vite
   - Progressione dei livelli

2. **Testa il gioco con diversi scenari**
   - Cosa succede quando la rana raggiunge tutte le aree di arrivo?
   - Il gioco gestisce correttamente la perdita di tutte le vite?
   - I power-up funzionano come previsto?

3. **Ottimizza le prestazioni**
   - Il gioco funziona senza rallentamenti?
   - Ci sono script che possono essere migliorati?

## Conclusione

Complimenti! Hai creato un gioco Frogger completo e funzionante. Questo progetto finale ha integrato tutti gli elementi che hai imparato durante il corso, dalla programmazione del movimento alle collisioni, dal sistema di punteggio alla gestione dei livelli.

Ricorda che lo sviluppo di un gioco è un processo iterativo. Continua a perfezionare il tuo Frogger, aggiungi nuove funzionalità e personalizzazioni per renderlo unico. Non dimenticare di condividere la tua creazione con amici, familiari e la comunità di Scratch per ricevere feedback e ispirare altri programmatori in erba!

## Risorse Aggiuntive

- [Guida all'Integrazione dei Componenti](./01-IntegrazioneComponenti.md)
- [Tecniche di Ottimizzazione del Codice](./02-OttimizzazioneCodice.md)
- [Strategie di Debugging](./03-DebuggingProblemi.md)
- [Idee per la Personalizzazione](./04-PersonalizzazioneMiglioramenti.md)
- [Consigli per la Pubblicazione](./05-PubblicazioneCondivisione.md)

## Navigazione del Corso
- [📑 Indice del Progetto Finale](./README.md)
- [⬅️ Pubblicazione e Condivisione](./05-PubblicazioneCondivisione.md)
- [➡️ Fine del corso](../README.md)