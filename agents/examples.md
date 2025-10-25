# Agent Examples

This directory contains example configurations and usage patterns for the agents.

## Image Generator (Dashboard Mockup) Examples

### Example 1: Light Theme Dashboard (Default)

```json
{
  "agent": "image-generator-dashboard-mockup",
  "inputs": {
    "theme": "light",
    "width": 1920,
    "height": 1080,
    "language": "de"
  }
}
```

### Example 2: Dark Theme Dashboard

```json
{
  "agent": "image-generator-dashboard-mockup",
  "inputs": {
    "theme": "dark",
    "width": 1920,
    "height": 1080,
    "language": "de"
  }
}
```

### Example 3: Mobile Dashboard Variant

```json
{
  "agent": "image-generator-dashboard-mockup",
  "inputs": {
    "theme": "light",
    "width": 375,
    "height": 812,
    "language": "de"
  }
}
```

### Example 4: Custom Size Dashboard

```json
{
  "agent": "image-generator-dashboard-mockup",
  "inputs": {
    "theme": "dark",
    "width": 2560,
    "height": 1440,
    "language": "de"
  }
}
```

## Webhook Trigger Example

To trigger the agent via webhook, send a POST request:

```bash
curl -X POST https://your-webhook-endpoint/trigger/image-generator-dashboard-mockup \
  -H "Content-Type: application/json" \
  -d '{
    "inputs": {
      "theme": "dark",
      "width": 1920,
      "height": 1080,
      "language": "de"
    }
  }'
```

## Expected Output

The agent will:
1. Generate a detailed prompt for the UI designer
2. Create the dashboard mockup image using the specified model
3. Convert to SVG format with named layers
4. Save both PNG and SVG to the `designs/` directory
5. Send a notification to the `#design` channel

Output files:
- `designs/agents-mockup.png` (or custom name)
- `designs/agents-mockup.svg` (or custom name)
