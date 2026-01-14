# Computer-Vision---2024-2025---Leonardo-Bisazza---1762939
# Project 8: Invisibility Cloak for Depth Deception
### Adversarial Attacks on Monocular Depth Estimation

**Corso:** Computer Vision (Prof. Irene Amerini) - Sapienza Università di Roma  
**Anno:** Fall 2025  
**Studenti:** Leonardo Bisazza 1762939

---

## 📖 Descrizione del Progetto
Questo progetto analizza la vulnerabilità dei modelli di stima della profondità monoculare (Monocular Depth Estimation) agli attacchi avversari.
Basandosi sulle specifiche del "Project 8", abbiamo adattato il concetto di "Invisibility Cloak" (originariamente per object detection) per colpire l'architettura **Depth Anything V2**.

L'obiettivo principale è generare patch avversarie fisiche che, applicate su oggetti target (es. frigoriferi, TV), manipolino la predizione della profondità, creando effetti di "sfondamento" (aumento della distanza percepita) o occultamento.
## 🚀 Funzionalità Principali
* **Baseline Training:** Addestramento/Fine-tuning del modello sul dataset **NYU Depth V2**.
* **Digital Attack:** Generazione di patch avversarie robuste a trasformazioni (EOT).
* **Physical Validation:** Pipeline per testare l'efficacia delle patch stampate in scene reali (cucina, soggiorno) con diverse condizioni di luce.
* **Portable Code:** Notebook ottimizzato per Google Colab che gestisce automaticamente il download dei dati e dei pesi, senza dipendenze rigide da Google Drive.

---

## 🛠️ Istruzioni per l'Esecuzione

Il notebook è progettato per essere **autoconsistente**. I file necessari verranno richiesti interattivamente durante l'esecuzione.

### Prerequisiti
Assicurati di avere sul tuo PC:
1.  `kaggle.json`: Token API per scaricare il dataset NYUv2.
2.  `latest.pth`: Checkpoint del modello addestrato (opzionale, se vuoi usare i nostri pesi).

### Passaggi
1.  Apri il notebook `vision_project_Depth_Anything_V2.ipynb` in **Google Colab**.
2.  Esegui tutte le celle in sequenza.
3.  **Caricamento Kaggle Token:** Quando richiesto, carica il file `kaggle.json`.
4.  **Caricamento Checkpoint:**
    * Se possiedi il file `latest.pth`, seleziona l'opzione di caricamento manuale quando richiesto.
    * Altrimenti, il sistema scaricherà automaticamente il modello base pre-trained per permettere l'inferenza.

---

## 📂 Struttura del Notebook

1.  **Environment Configuration:** Setup variabili e clonazione repository.
2.  **Dataset Download:** Recupero dati NYU Depth V2.
3.  **Training Loop:** Codice per il training (salvataggio pesi in `./checkpoints`).
4.  **Adversarial Patch Generation:** Ottimizzazione della patch digitale.
5.  **Digital Validation:** Valutazione quantitativa sul dataset di test.
6.  **Physical Validation:**
    * Caricamento foto reali (con/senza patch).
    * Inferenza e visualizzazione Side-by-Side delle mappe di profondità.

---

## 🔗 Credits & References
* **Project Reference:** Project 8 - Computer Vision Course, Sapienza University.
* **Base Model:** [Depth Anything V2](https://github.com/DepthAnything/Depth-Anything-V2)
* **Dataset:** [NYU Depth V2](https://cs.nyu.edu/~silberman/datasets/nyu_depth_v2.html)
* **Key Paper:** Thys, S., Van Ranst, W., & Goedemé, T. (2019). "Fooling automated surveillance cameras: adversarial patches to attack person detection".

