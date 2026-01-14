# Computer-Vision---2024-2025---Leonardo-Bisazza---1762939
# Project 8: Invisibility Cloak for Depth Deception
### Adversarial Attacks on Monocular Depth Estimation

**Corso:** Computer Vision (Prof. Irene Amerini) - Sapienza Università di Roma  
**Anno:** Fall 2025  
**Studenti:** Leonardo Bisazza 1762939

---

## 📖 Descrizione del Progetto
[cite_start]Questo progetto esplora la vulnerabilità delle reti neurali di stima della profondità monoculare (**Monocular Depth Estimation - MDE**) agli attacchi avversari fisici[cite: 3, 5, 8].
[cite_start]Ispirandosi al concetto di "Invisibility Cloak" per i rilevatori di oggetti (YOLO), abbiamo adattato l'attacco per colpire **Depth Anything V2**, una delle architetture MDE più avanzate[cite: 8, 13].

[cite_start]L'obiettivo è generare una "patch avversaria" stampabile che, applicata su un oggetto reale (es. un frigorifero), inganni la rete facendole credere che l'oggetto sia molto più lontano (effetto "sfondamento") o invisibile[cite: 13, 14].

## 🚀 Funzionalità Principali
* [cite_start]**Training Baseline:** Fine-tuning del modello *Depth Anything V2 (Small)* sul dataset NYU Depth V2[cite: 12, 18].
* [cite_start]**Digital Attack:** Generazione di patch avversarie ottimizzate tramite EOT (Expectation-Over-Transformation) per robustezza a rotazione e scala[cite: 19].
* [cite_start]**Physical Validation:** Pipeline di test per valutare l'efficacia delle patch stampate nel mondo reale[cite: 21].
* **Portable Notebook:** Il codice è ottimizzato per Google Colab e non richiede path assoluti o mount di Google Drive.

---

## 🛠️ Istruzioni per l'Esecuzione

Il notebook è progettato per essere **autoconsistente**. Non richiede di montare il Google Drive dell'utente. I file necessari verranno richiesti interattivamente durante l'esecuzione.

### Prerequisiti
Per eseguire il progetto, avrai bisogno di due file da tenere a portata di mano sul tuo PC:
1.  `kaggle.json`: Il token API di Kaggle per scaricare il dataset NYUv2.
2.  `latest.pth`: Il checkpoint del modello addestrato (disponibile nella sezione Releases o fornito con il progetto). *Se non lo hai, il notebook scaricherà automaticamente il modello base.*

### Passaggi
1.  Apri il notebook `vision_project_Depth_Anything_V2.ipynb` in **Google Colab**.
2.  Esegui le celle in sequenza. Il notebook gestirà automaticamente l'installazione delle dipendenze.
3.  **Caricamento Kaggle Token:** Quando richiesto dalla cella di download dataset, carica il file `kaggle.json` dal tuo computer.
4.  **Caricamento Checkpoint:** Nella sezione di caricamento modello, se desideri usare i pesi addestrati da noi, seleziona l'opzione "Carica Manualmente" e carica il file `latest.pth`. Altrimenti, puoi scegliere di scaricare il modello base pre-trained.

---

## 📂 Struttura del Notebook

Il progetto segue un flusso logico sequenziale:

1.  **Environment Configuration:** Definizione variabili globali e preparazione ambiente.
2.  **Dataset Download:** Scaricamento automatico di NYU Depth V2 tramite API Kaggle.
3.  **Training Loop:** (Opzionale) Codice per il fine-tuning del modello o per riprendere il training. Salva i pesi nella cartella locale `./checkpoints`.
4.  **Adversarial Patch Generation:** Algoritmo di ottimizzazione per creare la patch digitale.
5.  **Digital Validation:** Test dell'attacco su immagini del dataset di validazione.
6.  **Physical Validation (Real World):**
    * Questa sezione permette di caricare foto scattate dal vivo (es. `con_patch.jpg` e `senza_patch.jpg`).
    * Il modello eseguirà l'inferenza e mostrerà il confronto delle mappe di profondità per valutare il successo dell'attacco fisico.

---

## 📊 Risultati e Conclusioni

Il progetto ha evidenziato una significativa differenza tra il dominio digitale e quello fisico:
* **In Silico (Digitale):** L'attacco ha successo quasi totale, creando "buchi" di profondità nell'immagine.
* **In Vivo (Fisico):** L'attacco è fortemente mitigato da due fattori:
    1.  **ISP della Fotocamera:** I filtri di denoise rimuovono il rumore avversario.
    2.  **Robustezza Contestuale:** La rete *Depth Anything* usa la geometria globale della stanza (pavimento, pareti) per correggere le anomalie locali introdotte dalla patch.

---

## 🔗 Credits & References
* Base Model: [Depth Anything V2](https://github.com/DepthAnything/Depth-Anything-V2)
* Dataset: [NYU Depth V2](https://cs.nyu.edu/~silberman/datasets/nyu_depth_v2.html)
* [cite_start]Inspiration: "Fooling automated surveillance cameras: adversarial patches to attack person detection" (Thys et al., 2019)[cite: 24].
