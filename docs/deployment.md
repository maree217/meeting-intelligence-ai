# Deployment Guide

## Prerequisites

- Azure subscription (UK South)
- Microsoft 365 tenant (for Teams)
- Azure AD app registration
- Speech Services resource

## Azure Deployment

### 1. Clone and Configure
```bash
git clone https://github.com/maree217/meeting-intelligence-ai
cd meeting-intelligence-ai
cp .env.example .env
```

### 2. Deploy Infrastructure
```bash
cd terraform/azure-uk
terraform init
terraform apply -var-file="prod.tfvars"
```

### 3. Register Teams App
```bash
# Create Azure AD app for Teams bot
az ad app create --display-name "Meeting Intelligence Bot"
# Configure permissions and bot registration
```

### 4. Configure Secrets
```bash
az keyvault secret set --vault-name $KV --name teams-secret --value $TEAMS_SECRET
az keyvault secret set --vault-name $KV --name speech-key --value $SPEECH_KEY
```

### 5. Deploy Application
```bash
az containerapp up --name meeting-intel --source .
```

### 6. Install Teams App
Deploy the bot to your Teams tenant via Teams Admin Centre.

## Verification

```bash
# Health check
curl https://your-meeting-intel.azurecontainerapps.io/health

# Test transcription
curl -X POST https://your-meeting-intel.azurecontainerapps.io/api/transcribe \
  -H "Authorization: Bearer $TOKEN" \
  -F "audio=@test-recording.wav"
```

## Monitoring

- Application Insights for logs
- Metrics for transcription volume, accuracy
- Alerts for processing failures
