# HeadSnap AI API Documentation

> **Note:** The public API is planned for v1.2.0. This document describes the proposed interface.

## Authentication

```bash
curl -H "Authorization: Bearer YOUR_API_KEY"      https://api.headsnap.ai/v1/generate
```

## Endpoints

### POST /v1/generate

Generate a professional headshot from a photo.

**Request:**
```json
{
  "image": "base64_encoded_image",
  "style": "linkedin",
  "background": "studio",
  "retouching": {
    "skin": true,
    "teeth": true,
    "eyes": true
  },
  "upscale": 2
}
```

**Response:**
```json
{
  "id": "gen_abc123",
  "image_url": "https://cdn.headsnap.ai/gen_abc123.png",
  "metadata": {
    "style": "linkedin",
    "width": 1024,
    "height": 1024
  }
}
```

### GET /v1/styles

List available style presets.

**Response:**
```json
{
  "styles": [
    { "id": "linkedin", "name": "LinkedIn Pro", "description": "..." },
    { "id": "executive", "name": "Executive", "description": "..." }
  ]
}
```

## Rate Limits

| Tier | Requests/min | Max Resolution |
|------|-------------|----------------|
| Free | 10 | 512×512 |
| Pro | 100 | 1024×1024 |
| Enterprise | Unlimited | 2048×2048 |

## Error Codes

| Code | Description |
|------|-------------|
| 400 | Invalid request parameters |
| 401 | Invalid or missing API key |
| 429 | Rate limit exceeded |
| 500 | Internal server error |
