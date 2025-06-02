# Punteggio e livelli

## Descrizione dell'esercitazione

In questa quinta esercitazione, implementeremo un sistema di punteggio e livelli nel nostro gioco Frogger. Impareremo come creare un sistema di punteggio che premia il giocatore per le azioni completate, come implementare livelli con difficoltà crescente, e come salvare i punteggi migliori. Questi elementi sono fondamentali per aumentare la rigiocabilità e la sfida del gioco.

## Indice degli argomenti teorici

1. [Sistemi di punteggio nei videogiochi](./01-SistemiPunteggio.md)
2. [Implementazione di livelli progressivi](./02-LivelliProgressivi.md)
3. [Gestione della difficoltà](./03-GestioneDifficolta.md)
4. [Salvataggio dei dati di gioco](./04-SalvataggioData.md)
5. [Interfacce utente per punteggi e livelli](./05-InterfacceUtente.md)

## Obiettivi dell'esercitazione

- Implementare un sistema di punteggio completo
- Creare livelli con difficoltà crescente
- Sviluppare un sistema per salvare i punteggi migliori
- Migliorare l'interfaccia utente per visualizzare punteggi e livelli
- Implementare meccaniche di bonus e moltiplicatori

## Istruzioni passo-passo

### 1. Sistema di punteggio base

1. Apri il progetto "Frogger - Parte 4" creato nella precedente esercitazione
2. Salva una nuova versione chiamata "Frogger - Parte 5"
3. Crea una variabile per il punteggio
4. Implementa l'incremento del punteggio quando la rana raggiunge una zona sicura

### 2. Punteggi bonus

1. Aggiungi punteggi bonus per azioni speciali (completamento rapido, percorsi difficili, ecc.)
2. Implementa moltiplicatori di punteggio per streak consecutive
3. Crea oggetti bonus che possono essere raccolti per punti extra

### 3. Implementazione dei livelli

1. Crea una variabile per tenere traccia del livello corrente
2. Implementa la logica per avanzare al livello successivo
3. Modifica la difficoltà in base al livello (velocità degli ostacoli, numero di ostacoli, ecc.)
4. Crea transizioni visive tra i livelli

### 4. Salvataggio dei punteggi migliori

1. Implementa un sistema per salvare il punteggio più alto
2. Crea una schermata per visualizzare i punteggi migliori
3. Aggiungi la possibilità di inserire le iniziali o un nome per i punteggi salvati

### 5. Interfaccia utente migliorata

1. Crea un'interfaccia per visualizzare chiaramente punteggio, livello e vite
2. Implementa animazioni per l'incremento del punteggio
3. Aggiungi indicatori visivi per il progresso del livello
4. Crea una schermata di riepilogo alla fine di ogni livello

## Sfide aggiuntive

- Implementa un sistema di achievement o obiettivi
- Crea livelli con layout e sfide uniche
- Aggiungi un sistema di potenziamenti che influenzano il punteggio
- Implementa una modalità di gioco a tempo con meccaniche di punteggio diverse

## Concetti di programmazione utilizzati

- Gestione di variabili e punteggi
- Implementazione di livelli e difficoltà progressiva
- Salvataggio e caricamento di dati
- Progettazione di interfacce utente
- Bilanciamento del gameplay

## Navigazione del Corso
- [📑 Indice](../README.md)
- [⬅️ Animazioni e suoni](../04-AnimazioniESuoni/README.md)
- [➡️ Progetto finale: Frogger completo](../06-ProgettoFinale/README.md)