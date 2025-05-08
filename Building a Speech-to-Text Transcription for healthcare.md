# Real-Time Speech-to-Text Transcription System for Healthcare with Noise Robustness

This Python project implements a real-time speech-to-text transcription system designed specifically for healthcare environments. It uses OpenAI’s Whisper model for transcription and includes noise robustness, medical term normalization, and critical keyword detection.

## Features

- **Real-time microphone recording**
- **Speech-to-text transcription** using Whisper (`base` model)
- **Noise robustness** with live audio stream handling
- **Normalization of medical terms** (e.g., "bp" → "blood pressure")
- **Keyword detection** for important healthcare alerts
- **Automatic logging** of transcriptions with timestamps

## Installation

1. **Clone this repository**:
   ```bash
   git clone https://github.com/your-username/healthcare-stt-whisper.git
   cd healthcare-stt-whisper
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **(Optional) Set up a virtual environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

## Usage

Run the main script:

```bash
python main_healthcare.py
```

### Output

The system will:
- Listen to audio in 5-second intervals
- Transcribe the speech
- Normalize common medical shorthand
- Detect and print alerts for keywords (e.g., "emergency", "blood pressure")
- Save all transcriptions in `transcription_log.txt`

### Sample Console Output

```
[INFO] Recording started. Speak now...
Transcription:
The patient's blood pressure is 130 over 85 and shows signs of diabetic condition.
------------------------------------------------------------
[ALERT] Detected medical terms: blood pressure, diabetic
```

## Example Medical Term Normalization

| Detected Term     | Normalized Term     |
|-------------------|---------------------|
| bp                | blood pressure      |
| sugar level       | glucose level       |
| ekg               | ECG                 |
| covid             | COVID-19            |
| diabetes type 1   | Type 1 Diabetes     |

## File Structure

```
healthcare-stt-whisper/
├── main_healthcare.py         # Main Python script
├── requirements.txt           # Dependencies
├── README.md                  # Documentation
├── transcription_log.txt      # Auto-created log of transcriptions
└── .gitignore                 # Common ignored files
```

## Requirements

- Python 3.7+
- whisper
- numpy
- sounddevice
- soundfile
- torch

## License

This project is open-source and licensed under the [MIT License](LICENSE).

---

**Developed for use in healthcare transcription, telemedicine support, and voice-powered diagnostics.**
