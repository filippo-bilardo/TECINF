# Guida di Riferimento Rapido: Frogger

## Panoramica del Gioco

Frogger è un classico gioco arcade in cui il giocatore controlla una rana che deve attraversare una strada trafficata e un fiume pericoloso per raggiungere delle aree sicure. Questo documento serve come riferimento rapido per i concetti chiave implementati nel progetto finale.

## Componenti Principali

### 1. Protagonista (Rana)

**Funzionalità principali:**
- Movimento in quattro direzioni (su, giù, sinistra, destra)
- Collisioni con veicoli, acqua e piattaforme
- Sistema di vite

**Blocchi di codice essenziali:**
```scratch
# Movimento base
quando si preme [freccia su v]
punta in direzione (0)
fai (10) passi

# Controllo collisioni
se <sta toccando [veicolo v]> allora
  invia [perdi vita v]
fine
```

### 2. Ostacoli

**Tipi di ostacoli:**
- Veicoli (auto, camion, moto)
- Acqua (pericolosa al contatto diretto)
- Piattaforme (tronchi, tartarughe)

**Comportamento degli ostacoli:**
```scratch
# Movimento base degli ostacoli
quando si clicca sulla bandiera verde
per sempre
  cambia x di (velocità)
  se <(x position) > [240]> allora
    vai a x: (-240) y: (posizione y)
  fine
  attendi (0.1) secondi
fine
```

### 3. Sistema di Punteggio

**Elementi del punteggio:**
- Punti base per ogni area raggiunta
- Bonus tempo
- Punti extra per oggetti speciali

**Implementazione:**
```scratch
# Assegnazione punti base
quando sta toccando [area arrivo v]
cambia [punteggio v] di (100)

# Bonus tempo
cambia [punteggio v] di (tempo * 10)
```

### 4. Progressione dei Livelli

**Meccanismo di avanzamento:**
- Completamento di tutte le aree di arrivo
- Aumento della difficoltà
- Nuovi elementi di gameplay

**Implementazione:**
```scratch
# Passaggio di livello
quando ricevo [livello completato v]
cambia [livello v] di (1)
invia [aumenta difficoltà v]

# Aumento difficoltà
quando ricevo [aumenta difficoltà v]
per tutti gli sprite [veicolo v]
  cambia [velocità v] di (livello * 0.5)
fine
```

## Tecniche di Programmazione

### 1. Gestione degli Sprite

**Clonazione:**
```scratch
# Creazione di cloni
quando si clicca sulla bandiera verde
nascondi
ripeti (numero) volte
  crea clone di [me stesso v]
fine

# Comportamento dei cloni
quando vengo clonato
mostra
# Logica specifica del clone
```

**Posizionamento:**
```scratch
# Posizionamento iniziale
quando si clicca sulla bandiera verde
vai a x: (posizione x) y: (posizione y)
```

### 2. Gestione delle Collisioni

**Tipi di rilevamento:**
- `sta toccando [sprite]`
- `sta toccando il colore [colore]`
- `colore [colore1] sta toccando [colore2]`

**Ottimizzazione delle collisioni:**
```scratch
# Collisione ottimizzata
se <(distanza da [ostacolo v]) < [20]> allora
  se <sta toccando [ostacolo v]> allora
    invia [collisione v]
  fine
fine
```

### 3. Comunicazione tra Sprite

**Messaggi:**
```scratch
# Invio messaggi
invia [nome messaggio v]

# Ricezione messaggi
quando ricevo [nome messaggio v]
# Azioni da eseguire
```

**Variabili condivise:**
```scratch
# Impostazione variabile globale
imposta [variabile v] a [valore]

# Lettura variabile globale
se <(variabile) = [valore]> allora
  # Azioni da eseguire
fine
```

## Ottimizzazione e Debugging

### 1. Tecniche di Ottimizzazione

- Usa blocchi personalizzati per codice ripetitivo
- Limita i cicli "per sempre" quando possibile
- Usa la clonazione per oggetti simili
- Implementa controlli di visibilità per ridurre calcoli non necessari

### 2. Strumenti di Debugging

- Modalità passo-passo per eseguire il codice lentamente
- Variabili di debug per monitorare valori
- Blocchi "dire" temporanei per visualizzare informazioni
- Modalità turbo per testare rapidamente

## Personalizzazione

### 1. Elementi Grafici

- Costumi personalizzati per gli sprite
- Sfondi tematici
- Effetti visivi per eventi speciali

### 2. Audio

- Effetti sonori per azioni (salto, collisione, vittoria)
- Musica di sottofondo
- Feedback audio per eventi di gioco

### 3. Gameplay

- Power-up (invincibilità, vita extra, tempo extra)
- Nemici speciali
- Modalità di gioco alternative

## Riferimenti Rapidi

### Variabili Essenziali

| Variabile | Scopo |
|-----------|-------|
| vite | Tiene traccia delle vite rimanenti |
| punteggio | Registra il punteggio attuale |
| livello | Indica il livello corrente |
| tempo | Conto alla rovescia per completare il livello |
| record | Salva il punteggio più alto |

### Eventi Principali

| Evento | Scopo |
|--------|-------|
| perdi vita | Gestisce la perdita di una vita |
| livello completato | Gestisce il passaggio al livello successivo |
| game over | Gestisce la fine del gioco |
| inizia gioco | Avvia una nuova partita |

## Risorse Aggiuntive

- [Integrazione dei Componenti](./01-IntegrazioneComponenti.md)
- [Ottimizzazione del Codice](./02-OttimizzazioneCodice.md)
- [Debugging e Risoluzione dei Problemi](./03-DebuggingProblemi.md)
- [Personalizzazione e Miglioramenti](./04-PersonalizzazioneMiglioramenti.md)
- [Pubblicazione e Condivisione](./05-PubblicazioneCondivisione.md)
- [Esercitazione Pratica](./Esercitazione-ProgettoFinale.md)

## Navigazione del Corso
- [📑 Indice del Progetto Finale](./README.md)
- [⬅️ Esercitazione Pratica](./Esercitazione-ProgettoFinale.md)
- [➡️ Fine del corso](../README.md)