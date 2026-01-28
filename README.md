# ml-whisper

Simple drop-folder transcription using the OpenAI audio transcription API.

## Setup

1. Install Python with pyenv:
   - `pyenv install 3.11.6`
   - `pyenv local 3.11.6`
2. Create and activate a virtualenv:
   - `python -m venv .venv`
   - `source .venv/bin/activate`
3. Install dependencies:
   - `pip install -r requirements.txt`
4. Create your `.env`:
   - `cp example.env .env`
   - Add your `OPENAI_API_KEY`.

## Run

Watch the default `drop/` folder and write transcripts into `output/` while moving processed audio into `processed/`:

```
python transcribe_drop.py
```

One-time pass (no watch loop):

```
python transcribe_drop.py --once
```

Optional overrides:

```
python transcribe_drop.py --drop-dir /path/to/folder --output-dir /path/to/output --processed-dir /path/to/processed --model whisper-1 --interval 3 --stable-seconds 2
```

Supported file extensions: `.mp3`, `.mp4`, `.mpeg`, `.mpga`, `.m4a`, `.wav`, `.webm`.
