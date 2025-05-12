# NurseSpeak - German Pronunciation Practice

## Overview

**NurseSpeak** is a web app designed to help healthcare professionals improve their German pronunciation. Users select a phrase, record their voice, and receive feedback on their pronunciation accuracy using AI-driven speech analysis.

---

## Tech Stack

- **Python**: Core language for backend logic and processing.
- **Gradio**: For building the interactive web interface.
- **Transformers (Hugging Face)**: Wav2Vec2 for German speech-to-text transcription (`facebook/wav2vec2-large-xlsr-53-german`).
- **Sentence Transformers**: For semantic similarity scoring (`paraphrase-multilingual-MiniLM-L12-v2`).
- **Torchaudio**: Audio processing and resampling.
- **Levenshtein**: For calculating string similarity.
- **gTTS & Pydub**: To generate reference audio files for phrases.
- **Matplotlib**: For plotting user progress.
- **NumPy & Soundfile**: For audio data handling.

---

## Challenges Faced

- **Model Compatibility**: Ensuring the Wav2Vec2 model runs on CPU for broader compatibility, as GPU support isn’t guaranteed in all environments.
- **Audio Processing**: Handling variable input audio formats (e.g., stereo vs. mono, different sample rates) required robust resampling and conversion logic.
- **Accuracy of Transcription**: The Wav2Vec2 model sometimes struggled with noisy recordings or non-native accents, affecting feedback quality.
- **File Management**: Generating and managing reference audio files dynamically while ensuring cleanup of temporary files.
- **Gradio Deployment**: Port conflicts during Gradio interface launch required fallback options for port selection.

---

## Requirements to Go Live

- **Dependencies**:  
  Install all required packages:  
  ```bash
  pip install gradio transformers torchaudio torch python-Levenshtein sentence-transformers gtts pydub soundfile numpy matplotlib
