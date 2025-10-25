# Agents

This directory contains agent definitions for automated workflows.

## Available Agents

### Image Generator (Dashboard Mockup)

**File:** `image-generator-dashboard-mockup.json`

**Description:** Generates a Dashboard Mockup (Agents Management) as PNG/SVG; can be triggered manually or via webhook.

**Triggers:**
- Manual
- Webhook

**Inputs:**
| Parameter | Type    | Default | Options       | Description                    |
|-----------|---------|---------|---------------|--------------------------------|
| theme     | string  | light   | light, dark   | Theme for the dashboard        |
| width     | integer | 1920    | -             | Width of the generated image   |
| height    | integer | 1080    | -             | Height of the generated image  |
| language  | string  | de      | -             | Language for microcopy         |

**Workflow Steps:**
1. **generate_prompt** - Sets up the detailed design prompt for the UI/visual designer
2. **image_gen** - Generates the image using the specified model (e.g., Stable Diffusion)
3. **postprocess** - Converts to SVG and saves to repository
4. **notify** - Sends notification to the design channel

**Output:**
- PNG image (1920×1080 by default)
- SVG export with named layers
- Saved to `designs/agents-mockup.png`

**Design Specifications:**
- **Style:** Modern Flat Design with clear hierarchy, rounded cards, subtle shadow depth
- **Layout:**
  - Top navigation bar (logo/name: 'Agents')
  - Left sidebar (icons + labels: Overview, Agents, Logs, Settings)
  - Main area with two columns:
    - Left 60%: Agent list + detail card
    - Right 40%: Workflow + metrics
- **Color Palette:**
  - #0F172A (dark blue)
  - #10B981 (green)
  - #F59E0B (amber)
  - #FFFFFF (white)
  - #F3F4F6 (light gray)
- **Typography:** Inter font (H1 20–24px, Body 14px)
- **Language:** German (DE) microcopy
- **Variants:** Light/Dark themes, Mobile (375×812)

**Usage Example:**
```json
{
  "theme": "dark",
  "width": 1920,
  "height": 1080,
  "language": "de"
}
```
