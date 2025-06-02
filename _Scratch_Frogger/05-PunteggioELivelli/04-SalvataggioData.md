# Salvataggio dei dati di gioco

## Importanza del salvataggio dei dati

Il salvataggio dei dati di gioco è un elemento importante che permette di mantenere informazioni tra diverse sessioni di gioco, come i punteggi migliori, i livelli sbloccati o le preferenze del giocatore. In Scratch, possiamo implementare un sistema di salvataggio dei dati utilizzando le liste e la funzionalità di persistenza delle variabili cloud. In questa sezione, esploreremo come implementare un sistema di salvataggio dei dati nel nostro gioco Frogger.

## Tecniche di salvataggio in Scratch

### 1. Utilizzo delle variabili locali

Le variabili locali in Scratch vengono salvate all'interno del progetto e mantengono il loro valore anche quando il progetto viene chiuso e riaperto. Possiamo utilizzarle per salvare informazioni semplici come il punteggio migliore:

```
Quando si preme bandiera verde
# Inizializza il punteggio migliore se non esiste
Se <non <(punteggio_migliore) > [0]>> allora
  Imposta [punteggio_migliore v] a [0]
Fine

Quando ricevo [fine_gioco v]
# Aggiorna il punteggio migliore se necessario
Se <(punteggio) > (punteggio_migliore)> allora
  Imposta [punteggio_migliore v] a (punteggio)
Fine
```

### 2. Utilizzo delle liste

Le liste in Scratch ci permettono di salvare più valori in una singola struttura dati. Possiamo utilizzarle per salvare una classifica dei punteggi migliori:

```
Quando si preme bandiera verde
# Inizializza la lista dei punteggi migliori se è vuota
Se <(lunghezza di [punteggi_migliori v]) = [0]> allora
  Ripeti (10)
    Aggiungi [0] a [punteggi_migliori v]
  Fine
Fine

Quando ricevo [fine_gioco v]
# Aggiungi il punteggio attuale alla lista
Aggiungi (punteggio) a [punteggi_migliori v]
# Ordina la lista in ordine decrescente
Invia a tutti il messaggio [ordina_punteggi]
# Mantieni solo i primi 10 punteggi
Ripeti fino a quando <(lunghezza di [punteggi_migliori v]) = [10]>
  Elimina (lunghezza di [punteggi_migliori v]) da [punteggi_migliori v]
Fine
```

### 3. Utilizzo delle variabili cloud (solo su Scratch online)

Se stai utilizzando Scratch online e hai effettuato l'accesso, puoi utilizzare le variabili cloud per salvare i dati tra diverse sessioni e dispositivi. Le variabili cloud sono identificate dal simbolo ☁️:

```
Quando si preme bandiera verde
# Inizializza la variabile cloud del punteggio migliore
Se <non <(☁️ punteggio_migliore) > [0]>> allora
  Imposta [☁️ punteggio_migliore v] a [0]
Fine

Quando ricevo [fine_gioco v]
# Aggiorna il punteggio migliore cloud se necessario
Se <(punteggio) > (☁️ punteggio_migliore)> allora
  Imposta [☁️ punteggio_migliore v] a (punteggio)
Fine
```

## Implementazione in Frogger

### 1. Salvataggio dei punteggi migliori

Per il nostro gioco Frogger, possiamo implementare un sistema di salvataggio dei punteggi migliori utilizzando una lista:

```
Quando si preme bandiera verde
# Inizializza la lista dei punteggi migliori
Se <(lunghezza di [punteggi_migliori v]) = [0]> allora
  Ripeti (5)
    Aggiungi [0] a [punteggi_migliori v]
  Fine
Fine
# Mostra i punteggi migliori
Invia a tutti il messaggio [mostra_punteggi]

Quando ricevo [fine_gioco v]
# Verifica se il punteggio attuale è tra i migliori
Se <(punteggio) > (elemento (5) di [punteggi_migliori v])> allora
  # Aggiungi il punteggio alla lista
  Aggiungi (punteggio) a [punteggi_migliori v]
  # Ordina la lista in ordine decrescente
  Invia a tutti il messaggio [ordina_punteggi]
  # Mantieni solo i primi 5 punteggi
  Ripeti fino a quando <(lunghezza di [punteggi_migliori v]) = [5]>
    Elimina (lunghezza di [punteggi_migliori v]) da [punteggi_migliori v]
  Fine
  # Mostra i punteggi aggiornati
  Invia a tutti il messaggio [mostra_punteggi]
Fine
```

### 2. Salvataggio dei livelli sbloccati

Possiamo anche salvare informazioni sui livelli sbloccati, permettendo al giocatore di accedere direttamente ai livelli che ha già completato:

```
Quando si preme bandiera verde
# Inizializza la variabile del livello massimo sbloccato
Se <non <(livello_massimo_sbloccato) > [0]>> allora
  Imposta [livello_massimo_sbloccato v] a [1]
Fine

Quando ricevo [livello_completato v]
# Aggiorna il livello massimo sbloccato se necessario
Se <(livello + 1) > (livello_massimo_sbloccato)> allora
  Imposta [livello_massimo_sbloccato v] a (livello + 1)
Fine
```

### 3. Interfaccia per la selezione dei livelli

Utilizzando le informazioni sui livelli sbloccati, possiamo creare un'interfaccia che permette al giocatore di selezionare il livello da cui iniziare:

```
Quando si preme bandiera verde
# Mostra l'interfaccia di selezione dei livelli
Cambia sfondo in [selezione_livelli v]
Ripeti (livello_massimo_sbloccato)
  # Crea un pulsante per ogni livello sbloccato
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

## Considerazioni sulla privacy e la sicurezza

Quando implementi un sistema di salvataggio dei dati, è importante considerare la privacy e la sicurezza:

1. **Dati sensibili**: Evita di salvare informazioni personali o sensibili
2. **Variabili cloud**: Se utilizzi variabili cloud, ricorda che i dati sono visibili ad altri utenti che esplorano il tuo progetto
3. **Backup**: Considera la possibilità di implementare un sistema di backup dei dati importanti

## Esercizio pratico

Implementa un sistema di salvataggio dei punteggi migliori per il tuo gioco Frogger utilizzando una lista. Crea un'interfaccia che mostri i cinque punteggi migliori alla fine del gioco e aggiorni la lista quando il giocatore ottiene un nuovo punteggio alto.

## Sfida aggiuntiva

Implementa un sistema di salvataggio dei livelli sbloccati e crea un'interfaccia di selezione dei livelli che permetta al giocatore di iniziare da qualsiasi livello già sbloccato. Aggiungi anche la possibilità di inserire un nome o un nickname quando si ottiene un nuovo punteggio alto, in modo da personalizzare la classifica dei punteggi migliori.