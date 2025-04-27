# Interfacce utente per punteggi e livelli

## Importanza delle interfacce utente

Le interfacce utente (UI) sono un elemento fondamentale nei videogiochi che permettono al giocatore di interagire con il gioco e di ricevere informazioni importanti. Nel contesto dei punteggi e dei livelli, una buona interfaccia utente deve comunicare chiaramente al giocatore il suo punteggio attuale, il livello in cui si trova e altre informazioni rilevanti. In questa sezione, esploreremo come creare interfacce utente efficaci per punteggi e livelli nel nostro gioco Frogger utilizzando Scratch.

## Elementi di una buona interfaccia utente

### 1. Chiarezza e leggibilità

Un'interfaccia utente efficace deve essere chiara e leggibile, con testo di dimensioni adeguate e colori contrastanti:

```
Quando si preme bandiera verde
# Configura il testo per massima leggibilità
Porta dimensione a (150)%
Imposta effetto [colore v] a (0)
Imposta effetto [fantasma v] a (0)
```

### 2. Posizionamento strategico

Gli elementi dell'interfaccia devono essere posizionati in modo da non interferire con il gameplay, ma rimanere facilmente visibili:

```
Quando si preme bandiera verde
# Posiziona l'indicatore del punteggio in alto a sinistra
Vai a x: (-200) y: (170)
# Posiziona l'indicatore del livello in alto al centro
Vai a x: (0) y: (170)
# Posiziona l'indicatore delle vite in alto a destra
Vai a x: (200) y: (170)
```

### 3. Feedback immediato

L'interfaccia deve fornire un feedback immediato quando il punteggio o il livello cambiano:

```
Quando ricevo [aggiorna_punteggio v]
# Effetto visivo per evidenziare il cambiamento
Ripeti (3)
  Cambia effetto [luminosità v] di (25)
  Attendi (0.05) secondi
  Cambia effetto [luminosità v] di (-25)
  Attendi (0.05) secondi
Fine
```

## Implementazione in Scratch

### 1. Indicatore del punteggio

Possiamo creare un indicatore del punteggio utilizzando uno sprite di testo:

```
Quando si preme bandiera verde
# Configura l'indicatore del punteggio
Vai a x: (-200) y: (170)
Per sempre
  # Aggiorna il testo con il punteggio attuale
  Dire unione [Punteggio: ] (punteggio)
Fine
```

### 2. Indicatore del livello

Similmente, possiamo creare un indicatore del livello:

```
Quando si preme bandiera verde
# Configura l'indicatore del livello
Vai a x: (0) y: (170)
Per sempre
  # Aggiorna il testo con il livello attuale
  Dire unione [Livello: ] (livello)
Fine
```

### 3. Indicatore delle vite

Per l'indicatore delle vite, possiamo utilizzare un approccio più visuale, mostrando icone invece di numeri:

```
Quando si preme bandiera verde
# Configura l'indicatore delle vite
Vai a x: (200) y: (170)
Per sempre
  # Cancella le icone precedenti
  Cancella tutto
  # Disegna un'icona per ogni vita rimanente
  Ripeti (vite)
    Aggiungi timbro
    Cambia x di (20)
  Fine
Fine
```

## Interfacce avanzate

### 1. Animazioni per i cambiamenti di punteggio

Possiamo aggiungere animazioni che rendono più evidenti i cambiamenti di punteggio:

```
Quando ricevo [punti_guadagnati v]
# Crea un'animazione per i punti guadagnati
Vai a x: (x position di [rana v]) y: (y position di [rana v])
Dire unione [+] (punti_guadagnati) per (2) secondi
Cambia effetto [fantasma v] di (10)
Scivola in (1) secondi a x: (x position) y: (y position + 50)
Nascondi
```

### 2. Barra di progresso per il livello

Possiamo creare una barra di progresso che mostra l'avanzamento nel livello attuale:

```
Quando si preme bandiera verde
# Configura la barra di progresso
Vai a x: (-240) y: (-170)
Porta dimensione a (100)%
Per sempre
  # Calcola la percentuale di completamento
  Imposta [percentuale_completamento v] a ((tane_completate) / (5) * 100)
  # Aggiorna la lunghezza della barra
  Porta dimensione x a (percentuale_completamento)%
Fine
```

### 3. Menu di pausa

Possiamo implementare un menu di pausa che mostra informazioni sul punteggio e sul livello:

```
Quando si preme [p]
# Attiva/disattiva la pausa
Se <(in_pausa) = [falso]> allora
  Imposta [in_pausa v] a [vero]
  Invia a tutti il messaggio [pausa]
Altrimenti
  Imposta [in_pausa v] a [falso]
  Invia a tutti il messaggio [riprendi]
Fine

Quando ricevo [pausa v]
# Mostra il menu di pausa
Mostra
Dire unione [Punteggio: ] (punteggio) unione [\nLivello: ] (livello) unione [\nVite: ] (vite) unione [\n\nPremi P per riprendere] per (9999) secondi

Quando ricevo [riprendi v]
# Nascondi il menu di pausa
Nascondi
```

## Applicazione a Frogger

### 1. HUD (Heads-Up Display) per Frogger

In Frogger, possiamo implementare un HUD che mostra le informazioni essenziali durante il gameplay:

- **Punteggio**: in alto a sinistra
- **Tempo rimanente**: in alto al centro
- **Vite rimanenti**: in alto a destra
- **Livello attuale**: in basso a sinistra

```
Quando si preme bandiera verde
# Configura l'HUD
Nascondi
# Crea cloni per i diversi elementi dell'HUD
Crea clone di [me stesso v] # Punteggio
Crea clone di [me stesso v] # Tempo
Crea clone di [me stesso v] # Vite
Crea clone di [me stesso v] # Livello

Quando vengo clonato
# Configura il clone in base al suo numero
Se <(numero del clone) = [1]> allora
  # Configurazione per il punteggio
  Imposta [tipo_hud v] a [punteggio]
  Vai a x: (-200) y: (170)
Fine
Se <(numero del clone) = [2]> allora
  # Configurazione per il tempo
  Imposta [tipo_hud v] a [tempo]
  Vai a x: (0) y: (170)
Fine
# ...
Mostra

Quando si preme bandiera verde
Per sempre
  # Aggiorna il testo in base al tipo di HUD
  Se <(tipo_hud) = [punteggio]> allora
    Dire unione [Punteggio: ] (punteggio)
  Fine
  Se <(tipo_hud) = [tempo]> allora
    Dire unione [Tempo: ] (tempo)
  Fine
  # ...
Fine
```

### 2. Schermata dei punteggi migliori

Possiamo creare una schermata che mostra i punteggi migliori alla fine del gioco:

```
Quando ricevo [mostra_punteggi v]
# Configura la schermata dei punteggi migliori
Cambia sfondo in [punteggi_migliori v]
# Mostra i punteggi migliori
Vai a x: (0) y: (100)
Dire [I MIGLIORI PUNTEGGI] per (2) secondi
Vai a x: (0) y: (50)
Ripeti (5)
  Dire unione (n) unione [. ] (elemento (n) di [punteggi_migliori v]) per (2) secondi
  Cambia y di (-30)
Fine
Vai a x: (0) y: (-100)
Dire [Premi SPAZIO per giocare ancora] per (9999) secondi
```

### 3. Interfaccia di selezione dei livelli

Possiamo creare un'interfaccia che permette al giocatore di selezionare il livello da cui iniziare:

```
Quando ricevo [selezione_livelli v]
# Configura l'interfaccia di selezione dei livelli
Cambia sfondo in [selezione_livelli v]
Vai a x: (0) y: (100)
Dire [SELEZIONA UN LIVELLO] per (2) secondi
# Crea pulsanti per i livelli sbloccati
Ripeti (livello_massimo_sbloccato)
  Crea clone di [pulsante_livello v]
Fine

Quando vengo clonato
# Configura il pulsante del livello
Imposta [numero_livello v] a (numero del clone)
Vai a x: ((-100) + ((numero_livello - 1) * 50)) y: (0)
Cambia costume in (numero_livello)
Mostra

Quando si clicca questo sprite
# Avvia il livello selezionato
Imposta [livello v] a (numero_livello)
Invia a tutti il messaggio [inizia_gioco]
```

## Esercizio pratico

Implementa un HUD per il tuo gioco Frogger che mostri il punteggio, il tempo rimanente, le vite rimanenti e il livello attuale. Assicurati che l'HUD sia chiaro, leggibile e non interferisca con il gameplay.

## Sfida aggiuntiva

Implementa una schermata dei punteggi migliori che mostri i cinque punteggi più alti alla fine del gioco. Aggiungi anche un'interfaccia di selezione dei livelli che permetta al giocatore di iniziare da qualsiasi livello già sbloccato. Utilizza animazioni e effetti visivi per rendere queste interfacce più accattivanti e professionali.