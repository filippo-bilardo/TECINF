# Ottimizzazione delle collisioni

## Importanza dell'ottimizzazione delle collisioni

In un gioco come Frogger, dove le collisioni sono un elemento fondamentale del gameplay, è essenziale ottimizzare il sistema di rilevamento delle collisioni per garantire un'esperienza di gioco fluida e reattiva. Un sistema di collisioni non ottimizzato può causare rallentamenti, comportamenti imprevisti e una scarsa esperienza utente.

## Tecniche di ottimizzazione in Scratch

### 1. Riduzione dei controlli di collisione

Uno dei modi più semplici per ottimizzare le collisioni è ridurre la frequenza dei controlli. Invece di verificare le collisioni ad ogni frame, possiamo farlo solo quando è necessario:

```
# Approccio meno efficiente
Quando si preme bandiera verde
Per sempre
  Se <sta toccando [auto v]?> allora
    # Gestione della collisione
  Fine
Fine

# Approccio più efficiente
Quando si preme [freccia su]
Punta in direzione (0)
Cambia y di (30)
# Controlla le collisioni solo dopo il movimento
Se <sta toccando [auto v]?> allora
  # Gestione della collisione
Fine
```

### 2. Utilizzo di aree di collisione semplificate

In Scratch, il rilevamento delle collisioni si basa sui pixel dei costumi degli sprite. Per migliorare le prestazioni, possiamo utilizzare costumi semplificati per il rilevamento delle collisioni:

1. Crea un costume semplificato (ad esempio, un rettangolo o un cerchio) per ogni sprite
2. Utilizza questo costume per il rilevamento delle collisioni
3. Torna al costume originale per la visualizzazione

```
Quando si preme [freccia su]
Cambia costume in [rana-collisione]
Se <sta toccando [auto v]?> allora
  # Gestione della collisione
Fine
Cambia costume in [rana-normale]
```

### 3. Collisioni basate su zone

Invece di controllare le collisioni con ogni singolo ostacolo, possiamo dividere l'area di gioco in zone e controllare in quale zona si trova la rana:

```
Quando si preme bandiera verde
Per sempre
  Se <(y position) > [0] E (y position) < [50]> allora
    Imposta [zona_corrente v] a [1]
  Fine
  Se <(y position) > [50] E (y position) < [100]> allora
    Imposta [zona_corrente v] a [2]
  Fine
  # Altre zone...
Fine

# Poi, per ogni zona, definiamo comportamenti specifici
Quando si preme bandiera verde
Per sempre
  Se <(zona_corrente) = [1]> allora
    # Controlla collisioni solo con gli ostacoli nella zona 1
  Fine
  # Altre zone...
Fine
```

## Ottimizzazione specifica per Frogger

### 1. Raggruppamento degli ostacoli

In Frogger, gli ostacoli sono spesso organizzati in corsie. Possiamo ottimizzare il rilevamento delle collisioni raggruppando gli ostacoli per corsia:

```
Quando si preme bandiera verde
Per sempre
  Se <(y position) > [0] E (y position) < [30]> allora
    # Controlla collisioni solo con gli ostacoli nella prima corsia
    Se <sta toccando [auto_corsia_1 v]?> allora
      # Gestione della collisione
    Fine
  Fine
  # Altre corsie...
Fine
```

### 2. Utilizzo di variabili per tracciare gli ostacoli

Invece di controllare continuamente le collisioni con tutti gli ostacoli, possiamo utilizzare variabili per tracciare la posizione degli ostacoli e verificare le collisioni solo quando la rana si trova nella stessa posizione:

```
# Per ogni ostacolo
Quando si preme bandiera verde
Per sempre
  Imposta [posizione_x v] a (x position)
  Imposta [posizione_y v] a (y position)
Fine

# Per la rana
Quando si preme [freccia su]
Punta in direzione (0)
Cambia y di (30)
# Controlla le collisioni solo con gli ostacoli vicini
Per ogni [ostacolo v] in [lista_ostacoli v]
  Se <(posizione_y) = (y position) E (distanza da (posizione_x)) < [30]> allora
    # Gestione della collisione
  Fine
Fine
```

### 3. Ottimizzazione delle collisioni con i tronchi e le tartarughe

In Frogger, la rana può salire sui tronchi e sulle tartarughe. Questo tipo di collisione è diverso dalle collisioni con le auto, poiché la rana deve "attaccarsi" all'oggetto anziché perdere una vita. Possiamo ottimizzare questo comportamento:

```
Quando si preme bandiera verde
Per sempre
  Se <(y position) > [100] E (y position) < [150]> allora
    # Zona del fiume
    Se <sta toccando [tronco v]?> allora
      # La rana si attacca al tronco
      Imposta [su_tronco v] a [vero]
    Altrimenti
      Imposta [su_tronco v] a [falso]
      # La rana cade in acqua
      # Gestione della perdita di vita
    Fine
  Fine
Fine

# Per il tronco
Quando si preme bandiera verde
Per sempre
  Cambia x di (2)
  Se <(su_tronco) = [vero]> allora
    # Muovi la rana insieme al tronco
    Invia a [rana v] il messaggio [muovi_con_tronco]
  Fine
Fine
```

## Esercizio pratico

Implementa alcune delle tecniche di ottimizzazione discusse nel tuo progetto Frogger. In particolare:

1. Riduci la frequenza dei controlli di collisione
2. Implementa il raggruppamento degli ostacoli per corsia
3. Ottimizza le collisioni con i tronchi e le tartarughe

## Sfida aggiuntiva

Implementa un sistema di "hitbox" personalizzate per gli sprite. Crea un costume semplificato per ogni sprite che rappresenti l'area di collisione effettiva, e utilizza questo costume per il rilevamento delle collisioni. Questo renderà le collisioni più precise e ottimizzate.

```
Quando si preme bandiera verde
Per sempre
  Se <(controllo_collisioni) = [vero]> allora
    # Cambia in costume per collisioni
    Per ogni [sprite v] in [lista_sprite v]
      Invia a [sprite v] il messaggio [usa_hitbox]
    Fine
    # Controlla collisioni
    # ...
    # Torna ai costumi normali
    Per ogni [sprite v] in [lista_sprite v]
      Invia a [sprite v] il messaggio [usa_costume_normale]
    Fine
  Fine
Fine
```