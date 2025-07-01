# Gender Recognition with Deep Learning

Questo progetto implementa un sistema di riconoscimento del genere (maschio/femmina) da immagini utilizzando una rete neurale convoluzionale (CNN) in Python tramite TensorFlow/Keras. Il cuore del progetto è il notebook Jupyter `TestESAME WinFINALE.ipynb`.

## Struttura del progetto

- `TestESAME WinFINALE.ipynb`: Notebook principale che contiene tutto il codice per il caricamento dati, preprocessing, definizione e addestramento del modello, validazione, test e visualizzazione dei risultati.
- `Dataset ESAME Gender.zip`: Archivio contenente le immagini suddivise in cartelle per training, validation e test. Il dataset (10.000 immagini annotate in formato cartelle: Female, Male) va scaricato separatamente da [Roboflow Universe](https://universe.roboflow.com/seeed-studio-e2fso/gender-8vbxd).
- `requirements.txt`: File con tutte le dipendenze Python necessarie.

## Descrizione del notebook

Il notebook segue questi passaggi principali:

### 1. Import delle librerie
Importa tutte le librerie necessarie per la manipolazione delle immagini, la costruzione del modello, la visualizzazione e la valutazione delle performance.

### 2. Caricamento e preparazione dei dati
- **Funzione `carica_immagini`**: Carica le immagini da una directory, assegna le etichette in base alla sottocartella e restituisce immagini, etichette e una mappa delle etichette.
- **Preprocessing**: Le immagini vengono ridimensionate e normalizzate tramite la funzione `preprocess_images`.
- I dati vengono suddivisi in training, validation e test set.

### 3. Definizione del modello
- **Funzione `create_model`**: Crea una CNN sequenziale con due strati convoluzionali, max pooling, flatten, dense, dropout e softmax finale.
- Il modello viene compilato con ottimizzatore Adam, funzione di perdita `sparse_categorical_crossentropy` e metrica `accuracy`.

### 4. Addestramento e validazione
- **K-Fold Cross-Validation**: Utilizza la validazione incrociata (KFold) per stimare la robustezza del modello su diversi split dei dati.
- **Training finale**: Il modello viene addestrato su tutto il training set e validato sul validation set.

### 5. Valutazione e visualizzazione
- **Test finale**: Il modello viene valutato sul test set e viene stampata l'accuracy.
- **Visualizzazione predizioni**: Vengono mostrate alcune immagini del test set con la predizione del modello e la classe reale.
- **Matrice di confusione**: Viene calcolata e visualizzata la matrice di confusione per analizzare le performance sulle classi.
- **Grafici di training/validation**: Vengono mostrati i grafici di accuracy e loss durante l'addestramento.

## Come utilizzare il progetto

1. **Scaricare il dataset**: Vai su [https://universe.roboflow.com/seeed-studio-e2fso/gender-8vbxd] e scarica il dataset (10.000 immagini annotate in formato cartelle: Female, Male). Segui le istruzioni di Roboflow per l'esportazione. Estrai le immagini nelle cartelle `train`, `valid` e `test`, ciascuna con sottocartelle per ogni classe (es. `M`, `F`).
2. **Modificare i percorsi**: All'inizio del notebook, aggiornare i percorsi delle cartelle in base alla propria struttura locale.
3. **Installare le dipendenze**: Eseguire `pip install -r requirements.txt`.
4. **Eseguire il notebook**: Aprire ed eseguire tutte le celle del notebook per addestrare e valutare il modello.

## Dipendenze principali
- Python 3.8+
- numpy
- opencv-python
- tensorflow
- keras
- scikit-learn
- matplotlib

Tutte le dipendenze sono elencate in `requirements.txt`.

## Output del notebook
- Numero di immagini caricate per ciascun set
- Mappa delle etichette
- Andamento di accuracy e loss durante l'addestramento
- Risultati della cross-validation
- Accuracy finale sul test set
- Visualizzazione predizioni su immagini di test
- Matrice di confusione e classification report


## Informazioni sul dataset

Il dataset è stato esportato tramite roboflow.com il 22 settembre 2023 alle 10:50 AM GMT.

Roboflow è una piattaforma end-to-end per la computer vision che permette di:
* collaborare su progetti di computer vision
* raccogliere e organizzare immagini
* annotare e creare dataset
* esportare, addestrare e deployare modelli
* usare active learning per migliorare il dataset nel tempo

Per notebook di training all'avanguardia utilizzabili con questo dataset, visita: https://github.com/roboflow/notebooks

Per trovare oltre 100.000 altri dataset e modelli pre-addestrati, visita: https://universe.roboflow.com

**Dettagli tecnici:**
- Il dataset include 10.000 immagini.
- Le classi Female e Male sono annotate in formato cartelle.
- Pre-processing applicato: auto-orientamento dei pixel (con rimozione EXIF-orientation).
- Nessuna tecnica di image augmentation applicata.

---
Il notebook è ampiamente commentato per facilitare la comprensione di ogni passaggio.
I percorsi delle cartelle devono essere aggiornati in base alla posizione locale del dataset.

---
