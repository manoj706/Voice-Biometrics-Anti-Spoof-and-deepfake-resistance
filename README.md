# Voice Biometrics: Anti-Spoof and Deepfake Resistance

## Project Overview

This project implements a **Voice Biometric Authentication System** designed to verify speaker identity while detecting spoofed, replayed, or deepfake audio attacks. The system combines speaker verification using deep learning embeddings with acoustic feature-based anti-spoof detection.

The goal is to demonstrate how AI-based voice biometrics can improve security in authentication systems by ensuring that the voice input is both from the correct speaker and from a real human source.

> This project was developed as part of an **Applied Learning Project (ALP)**.

---

## Key Features

### 🎙️ Speaker Verification
- Uses **ECAPA-TDNN** speaker embeddings from SpeechBrain
- Computes cosine similarity between reference and test voice

### 🛡️ Anti-Spoof Detection
- Detects replay attacks, synthetic speech, and deepfake voices
- Uses multi-feature acoustic analysis including:
  - MFCC delta variance
  - Pitch jitter
  - Spectral flux
  - Zero crossing rate variance
  - Harmonic-to-Noise Ratio (HNR)
  - Spectral rolloff variation

### ✅ Audio Quality Validation
- Signal-to-Noise Ratio estimation
- RMS level check
- Voice activity detection

### 📊 Visualization
- Spectrogram analysis
- MFCC feature comparison
- Similarity and spoof score graphs

### 📝 Logging
- Authentication results stored in a JSON log file
- Timestamped authentication records

---

## System Architecture

```
Microphone Input
        │
        ▼
Audio Recording
        │
        ▼
Audio Quality Check
        │
        ▼
Speaker Embedding Extraction
      (ECAPA-TDNN)
        │
        ▼
Cosine Similarity
        │
        ▼
Anti-Spoof Detection
(Acoustic Feature Analysis)
        │
        ▼
Decision Engine
        │
        ▼
Access Granted / Access Blocked
```

---

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core language |
| PyTorch | Deep learning framework |
| SpeechBrain | ECAPA-TDNN speaker embeddings |
| Torchaudio | Audio processing |
| Librosa | Acoustic feature extraction |
| NumPy | Numerical computation |
| Matplotlib | Visualization |
| SciPy | Signal processing |

---

## Dataset

### Speaker Verification Model
The pretrained ECAPA-TDNN model is trained on:
- **VoxCeleb1**
- **VoxCeleb2**

These datasets contain over **1 million speech samples** from more than **6,000 speakers** collected from real-world environments.

### Demo Dataset
The system uses live microphone recordings during execution:
- `ref.wav` – reference speaker recording
- `test.wav` – authentication attempt recording

---

## Installation

**1. Clone the repository:**
```bash
git clone https://github.com/yourusername/Voice-Biometrics-Anti-Spoof-and-deepfake-resistance.git
cd Voice-Biometrics-Anti-Spoof-and-deepfake-resistance
```

**2. Create a virtual environment:**
```bash
python -m venv venv
```

**3. Activate the environment:**

- Windows:
```bash
venv\Scripts\activate
```

- Linux / Mac:
```bash
source venv/bin/activate
```

**4. Install dependencies:**
```bash
pip install torch torchaudio speechbrain librosa matplotlib sounddevice scipy numpy
```

---

## Running the Project

```bash
python main.py
```

**Steps during execution:**
1. Record reference voice
2. Record test voice
3. Extract speaker embeddings
4. Perform spoof detection
5. Generate authentication decision
6. Display analysis visualization

---

## Example Output

```
VOICE AUTHENTICATION REPORT

Audio Quality ............. OK
Similarity Score .......... 86.24%
Speaker Decision .......... SAME SPEAKER

Spoof Score ............... 21.63%
Liveness Decision ......... AUTHENTIC VOICE

FINAL RESULT: ACCESS GRANTED
```

---

## Visualization

The system generates analysis plots saved as `auth_result.png`, including:
- Reference voice spectrogram
- Test voice spectrogram
- MFCC feature comparison
- Similarity and spoof score gauges

---

## Future Improvements

- [ ] Deep learning based anti-spoof model
- [ ] Mobile or web application integration
- [ ] Real-time streaming authentication
- [ ] Larger dataset evaluation
- [ ] ROC curve performance analysis

---

## Applications

Voice biometric authentication systems can be used in:
- 🏦 Banking security
- 🔐 Voice-based login systems
- 🤖 Smart assistants
- 🚪 Secure access control
- 🕵️ Fraud detection
- 🎭 Deepfake voice detection

---

## Authors

**DSN Sathvik, Anireddy Manoj Kumar Reddy, Barath Sai Kumar J., Huzafiaa Shaik, Erla Krishna Chaitanya**
