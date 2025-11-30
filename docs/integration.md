# Integration Guide

## Video Platforms

### Microsoft Teams
- **API:** Graph API + Bot Framework
- **Auth:** Azure AD OAuth
- **Features:** Live transcription, recording access
- **Setup:** Register Teams app in Azure AD

### Zoom
- **API:** Zoom API + Webhooks
- **Auth:** OAuth 2.0
- **Features:** Recording transcription
- **Setup:** Create Zoom app, configure webhooks

### Google Meet
- **API:** Google Workspace APIs
- **Auth:** OAuth 2.0
- **Features:** Recording from Drive
- **Setup:** Enable APIs in Google Cloud

## Task Management

### Microsoft Planner
```yaml
planner:
  enabled: true
  plan_id: ${PLANNER_PLAN_ID}
  bucket_id: ${PLANNER_BUCKET_ID}
  auto_create_tasks: true
```

### Jira
```yaml
jira:
  enabled: true
  url: https://your-org.atlassian.net
  project: ACTIONS
  issue_type: Task
```

## Document Storage

### SharePoint
```yaml
sharepoint:
  enabled: true
  site: /sites/Meetings
  library: Minutes
  folder_structure: /{year}/{month}/{meeting_name}
```

## Configuration Example

```yaml
# config/integrations.yaml
teams:
  enabled: true
  tenant_id: ${AZURE_TENANT_ID}
  client_id: ${TEAMS_CLIENT_ID}
  client_secret: ${TEAMS_CLIENT_SECRET}
  bot_id: ${BOT_ID}

transcription:
  provider: azure  # or aws
  language: en-GB
  speaker_count: auto

actions:
  sync_to: planner
  reminder_days: [3, 1]

storage:
  provider: sharepoint
  retention_days: 365
```
