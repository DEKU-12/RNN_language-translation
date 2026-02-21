# RNN Language Translation Suite (Speech ↔ Text + English→French)

This repository contains a small NLP suite that covers:
1) **Speech-to-Text (ASR)**  
2) **English → French Translation using Seq2Seq LSTM**  
3) **Text-to-Speech (TTS)**  

Together, these notebooks can be used as a simple end-to-end concept:  
**Speak English → convert to text → translate to French → generate French speech**.

## Files in this repo
- `Eng_To_French_Translation_LSTM.ipynb` — Seq2Seq LSTM model for English→French translation
- `eng_-french.csv` — parallel dataset used for translation training
- `Speech to Text.ipynb` — converts speech/audio into text (ASR)
- `text_to_speech.ipynb` — converts text into speech audio (TTS)

## 1) English → French Translation (Seq2Seq LSTM)
### What it does
- Loads paired English/French sentences from `eng_-french.csv`
- Cleans + tokenizes text
- Converts words to sequences and pads to equal lengths
- Builds an **encoder–decoder LSTM (Seq2Seq)** model
- Trains the model and runs inference to translate new English sentences

### Why it matters
Seq2Seq LSTMs are a classic approach to neural machine translation and are useful for learning how encoder–decoder architectures work before moving to Transformers.

## 2) Speech to Text (ASR)
### What it does
- Accepts audio input (file and/or microphone depending on your notebook setup)
- Performs preprocessing required by the ASR library/model
- Outputs a text transcript

### Use case
Convert spoken English to text so it can be fed into the translation model.

## 3) Text to Speech (TTS)
### What it does
- Takes a text input string
- Generates spoken audio output (mp3/wav depending on your notebook)
- Saves and/or plays the generated speech

### Use case
Convert the translated French text into speech output.

## Tech stack (typical)
Because these are notebooks, exact dependencies depend on what you used inside them, but this project commonly uses:
- Python + Jupyter Notebook
- Deep learning: TensorFlow/Keras (for Seq2Seq LSTM)
- Data: Pandas, NumPy
- ASR: (SpeechRecognition / Whisper / Transformers, depending on notebook)
- TTS: (gTTS / pyttsx3 / Coqui-TTS, depending on notebook)

## How to run (recommended)
### 1) Create environment
```bash
python -m venv .venv
# mac/linux
source .venv/bin/activate
# windows
# .venv\Scripts\activate
