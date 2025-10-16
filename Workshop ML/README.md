[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1h9dKb7naK8vVfGS-txSsyfPWkA2VnooM?usp=sharing)

# Workshop Machine Learning - ColorIAmo Messina 🎨

Questo repository contiene materiale didattico per un workshop sul Machine Learning applicato alla colorazione automatica di immagini in bianco e nero.

## 📂 Struttura del Progetto

```
workshop_ML_SIS/
├── asset          # slide e materiali vari
├── img          # immagini utilizzate per il workshop
├── Full.ipynb          # Notebook Jupyter completo
├── Live.ipynb               # Notebook Jupyter per il workshop
└── README.md                    # Questo file
```

## 📋 Indice

- [Descrizione del Progetto](#-descrizione-del-progetto)
- [Requisiti di Sistema](#-requisiti-di-sistema)
- [Installazione](#-installazione)
- [Utilizzo](#-utilizzo)
- [Struttura del Notebook](#-struttura-del-notebook)
- [Dettagli Tecnici](#-dettagli-tecnici)
- [Esempi e Risultati](#-esempi-e-risultati)
- [Note Importanti](#-note-importanti)
- [Contributi](#-contributi)

## 🎯 Descrizione del Progetto

Il progetto dimostra due approcci distinti per colorare immagini storiche in bianco e nero:

### 1️⃣ Approccio Tradizionale (Python Puro) 🐍
Utilizza **Python** e la libreria **PIL/Pillow** per colorare manualmente le immagini basandosi sulla posizione dei pixel e su regole predefinite.

**Caratteristiche:**
- Colorazione basata su coordinate e luminanza dei pixel
- Approccio deterministico e controllabile
- Ideale per comprendere i fondamenti dell'elaborazione immagini
- Non richiede training di modelli

### 2️⃣ Approccio Deep Learning (Reti Neurali) 🧠
Utilizza **TensorFlow/Keras** per addestrare un **Autoencoder Convoluzionale** che impara a colorare automaticamente le immagini.

**Caratteristiche:**
- Rete neurale profonda (CNN-based Autoencoder)
- Addestramento sul dataset CIFAR-10
- Approccio data-driven che impara dai dati
- Generalizzabile a diverse tipologie di immagini

### 3️⃣ Approccio Generative AI (Google Gemini) 🎨
Utilizza un modello di AI Generativa multimodale, nello specifico **Google Gemini**, per eseguire la colorazione tramite un semplice prompt testuale.

**Caratteristiche:**
- Approccio **Zero-Shot**: non richiede alcun addestramento.
- **Multimodale**: comprende sia l'immagine (input) che il testo (prompt).
- **Qualità elevata**: sfrutta un modello pre-addestrato su una vastissima quantità di dati.
- **Semplicità**: richiede solo poche righe di codice per la chiamata API.

## 💻 Requisiti di Sistema

### Software Necessario
- **Python** 3.7 o superiore
- **Jupyter Notebook** o **Google Colab**
- **pip** (gestore pacchetti Python)
- Una **chiave API per Google Gemini**.

### Librerie Python Richieste

```python
# Elaborazione Immagini
Pillow (PIL)           # >= 9.0.0

# Deep Learning
tensorflow             # >= 2.12.0
keras                  # >= 2.12.0 (incluso in TensorFlow 2.x)

# Generative AI
google-generativeai    # >= 0.3.0

# Computazione Scientifica e Visualizzazione
numpy                  # >= 1.21.0
matplotlib             # >= 3.5.0
```

### Requisiti Hardware

#### Per l'Approccio Python Puro:
- **CPU:** Qualsiasi processore moderno
- **RAM:** 2 GB minimo
- **Storage:** 100 MB

#### Per il Deep Learning:
- **CPU:** Multi-core moderno (raccomandato)
- **GPU:** Opzionale ma fortemente consigliata (CUDA-compatible)
  - NVIDIA GPU con supporto CUDA
  - Accelera significativamente il training
- **RAM:** 8 GB minimo, 16 GB raccomandato
- **Storage:** 5 GB (per dataset e modelli)

#### Per la Generative AI:

  - **Connessione Internet** per accedere all'API di Gemini.

## 🔧 Installazione

### Metodo 1: Installazione Locale

1. **Clona o scarica il repository:**
```bash
git clone <repository-url>
cd workshop_ML
```

2. **Crea un ambiente virtuale (raccomandato):**
```bash
# macOS/Linux
python3 -m venv venv
source venv/bin/activate

# Windows
python -m venv venv
venv\Scripts\activate
```

3. **Installa le dipendenze:**
```bash
pip install --upgrade pip
pip install pillow tensorflow numpy matplotlib jupyter google-generativeai
```

4. **Verifica l'installazione:**
```bash
python -c "import PIL, tensorflow, numpy, matplotlib, google-generativeai; print('✅ Tutte le librerie installate correttamente!')"
```

### Metodo 2: Google Colab (Consigliato per Principianti)

1. Apri [Google Colab](https://colab.research.google.com/)
2. Carica il file `Workshop - ML.ipynb`
3. Le librerie principali sono già pre-installate. Per Gemini, potrebbe essere necessario eseguire `!pip install google-generativeai`.
4. Esegui le celle una per una

**Vantaggi di Colab:**
- ✅ Nessuna configurazione locale
- ✅ GPU gratuita disponibile
- ✅ Ambiente pre-configurato
- ✅ Salvato automaticamente su Google Drive

## 🚀 Utilizzo

### Opzione A: Jupyter Notebook (Interattivo)

1. **Avvia Jupyter:**
```bash
jupyter notebook
```

2. **Apri il notebook:**
   - Naviga alla cartella `workshop_ML`
   - Apri `Workshop - ML.ipynb`

3. **Esegui le celle:**
   - Esegui le celle in ordine sequenziale
   - Usa `Shift + Enter` per eseguire una cella

### Opzione B: Script Python (Standalone)

1. **Esegui lo script:**
```bash
python workshop_ml.py
```

2. **Modifica i percorsi delle immagini:**
```python
# Nel file workshop_ml.py, modifica queste righe:
colora_vista_porto_messina(
    "/percorso/tua/immagine_bn.jpg",
    "/percorso/output/immagine_colorata.jpg"
)
```

## 📚 Struttura del Notebook

Il notebook è organizzato in sezioni progressive:

### 🐍 Parte 1: Python Tradizionale

#### **Fase 1: Setup e Configurazione**
```python
from PIL import Image
import math
```

#### **Fase 2: Funzione di Colorazione Manuale**
```python
def colora_vista_porto_messina(percorso_immagine_bn, percorso_immagine_colorata):
    # Logica di colorazione
    pass
```

**Passaggi della Colorazione:**

1. **Caricamento Immagine** (`Image.open()`)
2. **Conversione RGB** (`.convert("RGB")`)
3. **Colorazione per Zone:**
   - 🌤️ **Cielo** (30% superiore)
   - ⛰️ **Monti Peloritani** (sfondo, 25-40%)
   - 🏛️ **Palazzata** (edifici, 35-50%)
   - 🌊 **Mare/Stretto** (45-85%)
   - 🚢 **Battello a Vapore** (sinistra-centro)
   - ⛵ **Nave a Vela** (destra)
   - 💧 **Riflessi sull'Acqua**
   - 🌅 **Primo Piano** (parte inferiore)

4. **Salvataggio Risultato** (`.save()`)

#### **Fase 3: Esecuzione**
```python
colora_vista_porto_messina(
    "/content/vista_messina.jpg",
    "/content/vista_messina_colorata.jpg"
)
```

### 🧠 Parte 2: Deep Learning

#### **Fase 1: Importazione Librerie**
```python
import numpy as np
import matplotlib.pyplot as plt
import tensorflow as tf
from tensorflow.keras.layers import Input, Conv2D, MaxPooling2D, UpSampling2D
from tensorflow.keras.models import Model
from tensorflow.keras.datasets import cifar10
```

#### **Fase 2: Caricamento Dataset CIFAR-10**
```python
(x_train_color, _), (x_test_color, _) = cifar10.load_data()
```

**Dataset:**
- 📦 60,000 immagini totali
- 🖼️ 50,000 training set
- 🧪 10,000 test set
- 📐 Dimensione: 32×32 pixel RGB

**Preparazione Dati:**
```python
# Normalizzazione (0-255 → 0-1)
x_train_color = x_train_color.astype('float32') / 255.0

# Conversione in scala di grigi
x_train_gray = tf.image.rgb_to_grayscale(x_train_color)
```

#### **Fase 3: Architettura dell'Autoencoder**

```
INPUT (32×32×1 grayscale)
    ↓
┌─────────────────────┐
│   ENCODER           │
├─────────────────────┤
│ Conv2D (64 filters) │
│ MaxPooling2D        │
│ Conv2D (128 filters)│
│ MaxPooling2D        │
└─────────────────────┘
    ↓ (8×8×128)
┌─────────────────────┐
│   DECODER           │
├─────────────────────┤
│ Conv2D (128 filters)│
│ UpSampling2D        │
│ Conv2D (64 filters) │
│ UpSampling2D        │
│ Conv2D (3 filters)  │ ← Output RGB
└─────────────────────┘
    ↓
OUTPUT (32×32×3 color)
```

**Codice Rete:**
```python
# Input
input_img = Input(shape=(32, 32, 1))

# Encoder
x = Conv2D(64, (3, 3), activation='relu', padding='same')(input_img)
x = MaxPooling2D((2, 2), padding='same')(x)
x = Conv2D(128, (3, 3), activation='relu', padding='same')(x)
encoded = MaxPooling2D((2, 2), padding='same')(x)

# Decoder
x = Conv2D(128, (3, 3), activation='relu', padding='same')(encoded)
x = UpSampling2D((2, 2))(x)
x = Conv2D(64, (3, 3), activation='relu', padding='same')(x)
x = UpSampling2D((2, 2))(x)
decoded = Conv2D(3, (3, 3), activation='sigmoid', padding='same')(x)

# Modello completo
autoencoder = Model(input_img, decoded)
autoencoder.compile(optimizer='adam', loss='mean_squared_error')
```

**Parametri Totali:** ~298,000

#### **Fase 4: Addestramento**
```python
autoencoder.fit(
    x_train_gray,      # Input: immagini B/N
    x_train_color,     # Target: immagini a colori
    epochs=20,         # 20 passate sul dataset
    batch_size=128,    # 128 immagini per batch
    shuffle=True,      # Mescola i dati
    validation_data=(x_test_gray, x_test_color)
)
```

**Metriche di Training:**
- Loss iniziale: ~0.023
- Loss finale: ~0.006
- Tempo: ~140-150 secondi (con GPU)

#### **Fase 5: Test e Visualizzazione**
```python
decoded_imgs = autoencoder.predict(x_test_gray)

# Visualizzazione 10 immagini
# Riga 1: Originale B/N
# Riga 2: Colorata da rete
# Riga 3: Originale a colori (riferimento)
```

### 🎨 Parte 3: Generative AI

#### **Fase 1: Importazione e Setup API**

```python
from google import genai
from google.colab import userdata

api_key = userdata.get('GEMINI_API_KEY')
client = genai.Client(api_key=api_key)
```

#### **Fase 2: Preparazione Input**

```python
prompt = "Colora questa foto"
image = Image.open('vista_messina.jpg')
```

#### **Fase 3: Chiamata al Modello Gemini**

```python
response = client.models.generate_content(
    model="gemini-2.5-flash-image-preview",
    contents=[prompt, image],
)
```

#### **Fase 4: Gestione e Salvataggio Risultato**

```python
# Estrae e salva l'immagine generata
image = Image.open(BytesIO(part.inline_data.data))
image.save("generated_image.png")
```

## 🔬 Dettagli Tecnici

### Approccio Python: Logica di Colorazione

**Metodo basato su Luminanza:**
```python
luminance = (0.299 * r + 0.587 * g + 0.114 * b)
```

**Colorazione Cielo:**
```python
if luminance > 180:  # Nuvole chiare
    img_colorata.putpixel((x, y), (230, 235, 240))
elif luminance > 100:  # Cielo medio
    img_colorata.putpixel((x, y), (135, 206, 235))
```

**Colorazione Mare:**
```python
wave_factor = math.sin(x * 0.05) * 0.2 + 0.8
blue = int(120 + depth_factor * 40 * wave_factor)
```

### Deep Learning: Teoria dell'Autoencoder

**Concetto:**
- 🗜️ **Encoder:** Comprime l'immagine in una rappresentazione ridotta
- 🔄 **Bottleneck:** Rappresentazione compatta (8×8×128)
- 📤 **Decoder:** Ricostruisce l'immagine a colori

**Vantaggi:**
- ✅ Apprende automaticamente le features
- ✅ Non richiede regole hard-coded
- ✅ Generalizza a nuove immagini

**Limitazioni:**
- ❌ Richiede grandi dataset
- ❌ Computazionalmente intensivo
- ❌ Risultati non sempre deterministici

### Loss Function

La rete minimizza l'**errore quadratico medio (MSE):**

```python
MSE = (1/n) Σ(y_true - y_pred)²
```

Dove:
- `y_true` = immagine a colori originale
- `y_pred` = immagine colorata dalla rete

## 📊 Esempi e Risultati

### Output Atteso

#### Python Puro:
```
📏 Dimensioni immagine: 800x600
🎨 Inizio colorazione manuale...
1 > Colorando il cielo...
2 > Colorando i Monti Peloritani...
3 > Colorando la Palazzata...
4 > Colorando lo Stretto di Messina...
5 > Colorando il battello a vapore...
6 > Colorando la nave a vela...
7 > Aggiungendo riflessi sull'acqua...
8 > Colorando il primo piano...

✅ Immagine colorata salvata con successo!
```

#### Deep Learning:
```
Caricamento del dataset CIFAR-10...
Forma dei dati di addestramento: (50000, 32, 32, 3)
Forma dei dati di test: (10000, 32, 32, 3)

Epoch 1/20: loss: 0.0229 - val_loss: 0.0099
Epoch 2/20: loss: 0.0092 - val_loss: 0.0085
...
Epoch 20/20: loss: 0.0062 - val_loss: 0.0061

Addestramento completato! ✅
```

#### Generative AI:

```
Certamente! Ecco la foto colorata:
(Viene visualizzata o salvata l'immagine generata)
```

### Confronto Qualitativo

| Aspetto | Python Puro | Deep Learning | Generative AI (Gemini) |
|---|---|---|---|
| **Velocità** | ⚡ Veloce | 🐌 Lento (training) | 🚀 Molto Veloce (inferenza) |
| **Precisione** | 🤔 Variabile (zone note) | 🤔 Variabile | 🎯 Alta, realistica |
| **Generalizzazione** | ❌ Bassa | ✅ Alta | ✅ Altissima |
| **Controllo** | ✅ Totale | ❌ Limitato | 🔧 Controllabile (via prompt) |
| **Apprendimento** | 📖 Didattico | 🎓 Avanzato | 🌐 Moderno, basato su API |

## ⚠️ Note Importanti

### Limitazioni e Considerazioni

1. **Performance:**
   - Il training su CPU può richiedere molto tempo (~30-60 min)
   - GPU consigliata per training rapido (~2-3 min)

2. **Memoria:**
   - Il dataset CIFAR-10 richiede ~200 MB
   - Il modello caricato in memoria ~1.2 GB

3.  **API di Gemini:**

      * L'esecuzione della sezione di AI Generativa richiede una **chiave API valida** per Google Gemini.
      * È necessaria una **connessione Internet** attiva per comunicare con il modello.

4. **Risultati:**
   - La qualità dipende dall'immagine di input
   - Immagini storiche potrebbero avere risultati imprevedibili
   - Il modello è addestrato su CIFAR-10 (oggetti generici)

5. **Compatibilità:**
   - TensorFlow richiede Python 3.7-3.11
   - Alcune versioni potrebbero avere problemi su Apple Silicon (M1/M2)

### Troubleshooting Comune

**Problema:** `ModuleNotFoundError: No module named 'tensorflow'` o `'google.generativeai'`

```bash
pip install tensorflow google-generativeai
```

**Problema:** Out of Memory durante il training
```python
# Riduci il batch_size
batch_size=64  # invece di 128
```

**Problema:** Training troppo lento
```python
# Riduci epochs o usa GPU
epochs=10  # invece di 20
```

**Problema:** PIL/Pillow non trova l'immagine
```python
# Usa percorsi assoluti
percorso = "/percorso/completo/alla/immagine.jpg"
```
**Problema:** `google.auth.exceptions.PermissionDenied: API key not valid.`

```python
# Assicurati che la tua chiave API di Gemini sia corretta e configurata
# correttamente come "Secret" in Google Colab.
```

## 🤝 Contributi

I contributi sono benvenuti! Se desideri migliorare questo workshop:

1. Fork il repository
2. Crea un branch per le modifiche
3. Invia una pull request

**Idee per Miglioramenti:**
- 🎨 Aggiungere altri metodi di colorazione
- 📊 Visualizzazioni interattive
- 🧪 Esperimenti con architetture diverse
- 📝 Documentazione aggiuntiva
- 🌐 Traduzione in altre lingue

## 📧 Contatti

Per domande, suggerimenti o segnalazioni:

- 📧 Email: r.figliozzi@datamasters.it
- 🐙 GitHub: [RiccardoFigliozzi](https://github.com/RiccardoFigliozzi)
- 💼 LinkedIn: [Riccardo Figliozzi ✨](https://www.linkedin.com/in/riccardo-figliozzi/)

---

## 🎓 Risorse Aggiuntive

### Per Approfondire

**Python e PIL:**
- [Documentazione Pillow](https://pillow.readthedocs.io/)
- [Tutorial Image Processing](https://realpython.com/image-processing-with-the-python-pillow-library/)

**TensorFlow e Keras:**
- [TensorFlow Tutorials](https://www.tensorflow.org/tutorials)
- [Keras Documentation](https://keras.io/guides/)
- [Deep Learning Book](https://www.deeplearningbook.org/)

**Autoencoders:**
- [Building Autoencoders in Keras](https://blog.keras.io/building-autoencoders-in-keras.html)
- [Intro to Autoencoders](https://www.tensorflow.org/tutorials/generative/autoencoder)

**CIFAR-10 Dataset:**
- [Official CIFAR-10 Page](https://www.cs.toronto.edu/~kriz/cifar.html)
- [Dataset Description](https://www.tensorflow.org/api_docs/python/tf/keras/datasets/cifar10)

**Generative AI e Gemini:**

  - [Google AI Studio](https://aistudio.google.com/) (per ottenere una chiave API)
  - [Documentazione Gemini API](https://ai.google.dev/docs)
  - [Guida rapida a Gemini con Python](https://ai.google.dev/tutorials/python_quickstart)

---

## 🌟 Ringraziamenti

Grazie per aver utilizzato questo workshop! Se ti è stato utile, considera di:
- ⭐ Dare una stella al repository
- 🔄 Condividere con altri studenti
- 💬 Lasciare feedback

**Buon apprendimento! 🚀🧠**

---

*Ultimo aggiornamento: Ottobre 2025*
