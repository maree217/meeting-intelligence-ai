# Architecture

## Overview

Meeting Intelligence Suite captures meeting audio, transcribes it using speech AI, and applies NLP to extract structure, actions, and decisions.

## Components

### Recording Connector
- **Teams Bot:** Joins meetings, captures audio stream
- **Zoom Webhook:** Receives recording completion events
- **File Import:** Upload recordings for processing

### Transcription Engine
- **Technology:** Azure Speech Services / AWS Transcribe
- **Features:** Speaker diarization, punctuation, timestamps
- **Accuracy:** 95%+ for clear audio

### NLP Analysis Engine
- **Topic Segmentation:** Aligns with agenda items
- **Action Extraction:** Identifies commitments
- **Decision Detection:** Captures formal decisions
- **Summary Generation:** Creates concise minutes

### Output Generator
- **Templates:** Formal minutes, project summaries
- **Integrations:** Push to SharePoint, Modern.gov
- **Notifications:** Email minutes, action reminders

## Data Flow

```
Meeting Audio → Transcription → NLP Analysis → Outputs
       ↓              ↓              ↓           ↓
  Recording      Transcript     Structured    Minutes,
   Storage                        Data      Actions, Decisions
```

## Security

- Audio encrypted in transit and at rest
- Transcripts stored with access controls
- Retention policies configurable
- GDPR consent management
- UK data residency
