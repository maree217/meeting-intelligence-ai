# Meeting Intelligence Suite

**Status:** ✅ Production Ready | **Deployment:** Cloud, Hybrid, On-Premise

## Overview

AI-powered meeting assistant that transcribes discussions, generates minutes, extracts action items, tracks decisions, and provides meeting analytics. Integrates with Microsoft Teams, Zoom, Google Meet, and committee management systems.

## The Problem

- 5-10 hours/week spent writing meeting minutes
- Action items lost or forgotten after meetings
- Decisions not properly documented or tracked
- Inconsistent minute quality across different note-takers
- No visibility into meeting effectiveness
- Committee papers and decisions hard to find later

## The Solution

**Intelligent Meeting Management:**
- Real-time transcription with speaker identification
- Automatic minutes generation
- Action item extraction and tracking
- Decision logging with context
- Meeting analytics and insights
- Integration with task management

**Results:**
- 80% reduction in minute-writing time
- 100% action capture (vs ~60% manual)
- 50% improvement in action completion
- Full audit trail for governance
- Searchable meeting history

## How It Works

```
┌─────────────────────────────────────┐
│        Meeting Recording            │
│    Teams | Zoom | Google Meet       │
└─────────────────┬───────────────────┘
                  │
┌─────────────────▼───────────────────┐
│       Transcription Engine          │
│   Speech-to-Text | Speaker ID       │
└─────────────────┬───────────────────┘
                  │
┌─────────────────▼───────────────────┐
│         AI Analysis                 │
│  • Topic segmentation               │
│  • Action extraction                │
│  • Decision identification          │
│  • Summary generation               │
└─────────────────┬───────────────────┘
                  │
┌─────────────────▼───────────────────┐
│           Outputs                   │
│  Minutes | Actions | Decisions      │
└─────────────────────────────────────┘
```

## Features

| Feature | Description |
|---------|-------------|
| **Live Transcription** | Real-time speech-to-text with 95%+ accuracy |
| **Speaker Identification** | Automatic speaker labelling |
| **Auto Minutes** | Structured minutes in organisation format |
| **Action Extraction** | AI identifies "who will do what by when" |
| **Decision Logging** | Captures decisions with context and rationale |
| **Topic Segmentation** | Organises transcript by agenda items |
| **Meeting Analytics** | Speaking time, engagement, action trends |
| **Search** | Find past discussions by topic or keyword |

## Meeting Types Supported

| Meeting Type | Key Outputs |
|-------------|-------------|
| **Board/Committee** | Formal minutes, decisions, voting records |
| **Project Board** | Status updates, decisions, actions |
| **Team Meeting** | Informal minutes, action list |
| **Steering Group** | Governance minutes, escalations |
| **1:1s** | Discussion notes, follow-ups |
| **Workshops** | Discussion summary, agreements |

## Integration

### Video Platforms

| Platform | Integration | Features |
|----------|-------------|----------|
| Microsoft Teams | Graph API + Bot | Live transcription, recording |
| Zoom | Webhook + API | Recording transcription |
| Google Meet | Calendar + Drive | Recording transcription |
| Webex | API | Recording transcription |

### Task Management
- Microsoft Planner / To-Do (action sync)
- Jira (action → ticket creation)
- Asana (action sync)

### Document Management
- SharePoint (minutes storage)
- Modern.gov (committee publishing)
- Google Drive (storage)

## Output Formats

### Formal Minutes (Committee)
```
MEETING OF [COMMITTEE NAME]
Date: [DATE]
Present: [ATTENDEES]
Apologies: [APOLOGIES]

1. ITEM HEADING
   1.1 [Discussion summary]
   RESOLVED: [Decision text]
   ACTION: [Person] to [task] by [date]
```

### Project Meeting Summary
```
## Key Decisions
- [Decision 1]
- [Decision 2]

## Actions
| # | Action | Owner | Due |
|---|--------|-------|-----|
| 1 | [Task] | [Name]| [Date]|

## Discussion Summary
[AI-generated summary]
```

## Compliance

- ✅ **GDPR** - Consent management, data retention
- ✅ **FOI Act** - Searchable meeting records
- ✅ **Local Government Act** - Committee requirements
- ✅ **Accessibility** - WCAG 2.1 transcripts
- ✅ **Data Residency** - UK processing only

## Costs

| Organisation Size | Monthly Cost | Time Savings |
|------------------|--------------|--------------|
| Small (50 meetings/mo) | £500-1,000 | 40 hours |
| Medium (200 meetings) | £1,000-3,000 | 160 hours |
| Large (500+ meetings) | £3,000-8,000 | 400+ hours |

**ROI:** 2-3 month payback

## Implementation

| Phase | Duration | Activities |
|-------|----------|------------|
| Setup | 1 week | Platform integration, templates |
| Pilot | 2 weeks | Test with 5-10 meetings |
| Rollout | 4 weeks | Full deployment, training |

## Quick Start

```bash
git clone https://github.com/maree217/meeting-intelligence-ai
cd meeting-intelligence-ai/terraform/azure-uk
terraform init && terraform apply
```

## Configuration

```yaml
# config/meeting-intelligence.yaml
platforms:
  teams:
    enabled: true
    tenant_id: ${AZURE_TENANT_ID}
  zoom:
    enabled: false

transcription:
  language: en-GB
  speaker_identification: true
  profanity_filter: true

outputs:
  minutes_format: formal  # or summary
  action_sync: planner
  storage: sharepoint

retention:
  transcripts: 365  # days
  recordings: 90
```

## Related Solutions

- [Project Intelligence](https://github.com/maree217/project-intelligence-ai) - Project status
- [Programme Risk Monitor](https://github.com/maree217/programme-risk-ai) - Risk tracking

## License

MIT License - See [LICENSE](./LICENSE)

---

*Transform meetings into actionable intelligence | UK Public Sector | Governance-Ready*
