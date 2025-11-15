# n8n Account Setup Guide

This guide covers the setup process for essential accounts needed for n8n automation workflows.

## Table of Contents
- [Google Drive Setup](#google-drive-setup)
- [Groq API Key](#groq-api-key)
- [Cohere Trial Key](#cohere-trial-key)
- [Mistral API Key](#mistral-api-key)

---

## Google Drive Setup

### Issue: OAuth Access Error

When signing up with n8n using Google Drive, you may encounter an access error. This happens because n8n Cloud has not completed the Google OAuth verification process. Here's how to fix it:

### Solution Steps

#### 1. Access Google Cloud Console

1. Visit [Google Cloud Console](https://console.cloud.google.com)
2. Navigate to your project

#### 2. Add Test Users

1. Go to **OAuth consent screen**
2. Scroll down to find **Test users** section
3. Click **Add Users**
4. Enter the Gmail address you're using with n8n
5. Click **Save**

#### 3. Create OAuth Credentials

1. In the left sidebar, navigate to **APIs & Services** → **Credentials**
2. Click **Create Credentials** → **OAuth client ID**
3. Select **Application type**: Web application
4. Add the authorized redirect URI from n8n
5. Click **Create**

#### 4. Configure n8n Connection

1. Copy the **Client ID** from Google Cloud Console
2. Go to n8n and paste the Client ID
3. Copy the **Client Secret** from Google Cloud Console
4. Paste it into n8n
5. Click **Connect** or **Authorize**
6. Follow the authorization flow
7. Your Google Drive should now be connected successfully

### Notes

- Make sure you're using the same Gmail account throughout the process
- Keep your Client ID and Client Secret secure
- The connection should work immediately after proper configuration

---

## Groq API Key

Groq provides free access to open-source large language models like Llama, Gemma 2, and others.

### Setup Steps

#### 1. Create Account

1. Visit [Groq Cloud](https://console.groq.com)
2. Click on **Sign Up** or **Login**
3. You can use:
   - Email address
   - GitHub account

#### 2. Generate API Key

1. Once logged in, navigate to **API Keys** section in the sidebar
2. Click **Create API Key**
3. Give your key a descriptive name (e.g., "n8n Integration")
4. Wait for verification
5. Click **Submit**

#### 3. Save Your API Key

⚠️ **Important**: Copy and save your API key immediately. Once you close the window, you cannot retrieve it again!

1. Copy the API key
2. Store it in a secure location (password manager recommended)
3. Click **Done**

### Testing Your API Key

You can test your Groq API key using Postman or similar tools:

**Example Request:**
```bash
POST https://api.groq.com/openai/v1/chat/completions

Headers:
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json

Body:
{
  "model": "llama-3.1-8b-instant",
  "messages": [
    {
      "role": "user",
      "content": "What is machine learning?"
    }
  ]
}
```

### Available Models

To get a list of available models:

```bash
GET https://api.groq.com/openai/v1/models

Headers:
Authorization: Bearer YOUR_API_KEY
```

Popular models include:
- Llama 3.1 (various sizes)
- Gemma 2
- Mixtral
- And more

---

## Cohere Trial Key

Cohere provides free trial API keys for their language models.

### Setup Steps

#### 1. Create Account

1. Visit [Cohere Dashboard](https://dashboard.cohere.com)
2. Sign up for a free account

#### 2. Access API Keys

1. Navigate to **Dashboard** → **API Keys**
2. You'll see a message: "You're using a Cohere Free Account"

#### 3. Get Production Key

1. Click **Get your Production key** button
2. Complete the short application form
   - This helps Cohere ensure community safety
   - Required for using API without trial limitations
3. Submit the form

#### 4. Trial Keys

- **Free Usage**: Cohere's API keys and applications are free, but limited
- **Trial Keys**: 
  - Rate-limited
  - Cannot be used for commercial purposes
  - Free of charge
  - Perfect for testing and development

#### 5. Create New Trial Key

1. Click **+ New Trial key** (top right)
2. Give your key a descriptive name
3. Copy the generated key
4. Store it securely

### Usage Notes

- Trial keys are ideal for development and testing
- For production use, complete the application form
- Keep your API keys secure and never share them publicly

---

## Mistral API Key

Mistral AI provides access to powerful open-source language models.

### Setup Steps

#### 1. Create Account

1. Visit [Mistral AI Console](https://console.mistral.ai)
2. Sign up or log in
3. You'll land on the home page

#### 2. Access Workspace Settings

1. Click on your workspace name (e.g., "Default Workspace")
2. Navigate to the **API Keys** tab
3. Or directly click **API Keys** from the sidebar

#### 3. Generate API Key

1. In the API Keys dialog, click **Create new key**
2. Give your key a descriptive name
3. Click **Create**
4. Copy the API key immediately
5. Store it securely

### Workspace Management

- **Personal API Keys**: Managed in your current workspace
- **Organization API Keys**: Available through "Go to the admin console" link
- You can have multiple API keys for different purposes
- View both **Active** and **Expired** keys

### Navigation

From the sidebar menu:
- **Home**: Dashboard overview
- **Workspace**: Workspace settings
- **API Keys**: Manage your keys
- **Playground**: Test models
- **Agents**: Configure AI agents
- **Batches**: Batch processing

### Security Best Practices

- Never commit API keys to version control
- Use environment variables in n8n
- Rotate keys periodically
- Delete unused keys
- Monitor usage through the console

---

## Integration with n8n

### Storing API Keys in n8n

1. Open your n8n instance
2. Go to **Credentials**
3. Click **Add Credential**
4. Select the appropriate credential type:
   - Google Drive OAuth2
   - Groq API
   - Cohere API
   - Mistral API
5. Paste your API key
6. Give the credential a descriptive name
7. Save

### Environment Variables (Alternative)

For enhanced security, you can also store API keys as environment variables:

```bash
GROQ_API_KEY=your_groq_key_here
COHERE_API_KEY=your_cohere_key_here
MISTRAL_API_KEY=your_mistral_key_here
```

Then reference them in n8n using: `{{$env.GROQ_API_KEY}}`

---

## Troubleshooting

### Google Drive
- **Issue**: "Access blocked" error
- **Solution**: Add your email as a test user in Google Cloud Console

### API Keys Not Working
- Verify the key was copied completely
- Check for extra spaces
- Ensure the key hasn't expired
- Verify you're using the correct API endpoint

### Rate Limits
- Trial keys have usage limits
- Monitor your usage in respective dashboards
- Upgrade to production keys if needed

---

## Additional Resources

- [n8n Documentation](https://docs.n8n.io)
- [Google Cloud Console](https://console.cloud.google.com)
- [Groq Documentation](https://console.groq.com/docs)
- [Cohere Documentation](https://docs.cohere.com)
- [Mistral AI Documentation](https://docs.mistral.ai)

---

## Quick Reference

| Service | Dashboard URL | Key Type |
|---------|--------------|----------|
| Google Drive | console.cloud.google.com | OAuth Client ID/Secret |
| Groq | console.groq.com | API Key |
| Cohere | dashboard.cohere.com | Trial/Production Key |
| Mistral | console.mistral.ai | API Key |

---

**Last Updated**: November 2025

*Remember to keep all API keys secure and never share them publicly or commit them to version control systems.*
