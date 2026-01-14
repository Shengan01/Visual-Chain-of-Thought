# SFT Training Data Format

Template format for supervised fine-tuning of multimodal models on display defect reasoning.

---

## JSONL Conversation Format (Qwen-VL Compatible)

### Standard Single-Image Format

```json
{
  "image": "path/to/defect_image.jpg",
  "conversations": [
    {
      "role": "user",
      "content": "Analyze this display panel image for manufacturing defects. Provide a detailed reasoning path."
    },
    {
      "role": "assistant", 
      "content": "**Observation**: I observe a [defect description] located in [position] of the panel.\n\n**Visual Analysis**: The defect exhibits [characteristics: shape, color, pattern, size]. This visual signature is consistent with [defect category].\n\n**Structural Analysis**: Given the [orientation/pattern] of the defect, this indicates involvement of the [component: TFT backplane/color filter/polarizer/etc.].\n\n**Root Cause Hypothesis**: The most likely manufacturing origin is [process stage], specifically:\n1. Primary cause: [specific failure mode]\n2. Secondary possibility: [alternative cause]\n\n**Severity Assessment**: [Critical / Major / Minor] - [justification]\n\n**Recommended Action**: [inspection/repair/reject decision]"
    }
  ]
}
```

### Multi-Resolution Reasoning Format

For defects requiring zoom analysis:

```json
{
  "images": ["full_panel.jpg", "cropped_region.jpg"],
  "conversations": [
    {
      "role": "user",
      "content": "Analyze this display panel. First image shows full panel, second shows magnified defect region."
    },
    {
      "role": "assistant",
      "content": "**Global View Analysis**: Scanning the full panel, I identify a suspicious region at [coordinates/position].\n\n**Zoom Decision**: The anomaly appears to be [initial assessment]. Magnification is required for pixel-level analysis.\n\n**High-Resolution Analysis**: At higher magnification, I observe [detailed characteristics visible only at zoom].\n\n**Refined Diagnosis**: Based on combined global context and local detail analysis:\n- Defect Type: [specific type]\n- Root Cause: [manufacturing process]\n- Confidence: [High/Medium/Low]"
    }
  ]
}
```

---

## Field Descriptions

| Field | Required | Description |
|-------|----------|-------------|
| `image` / `images` | Yes | Path(s) to defect image(s) |
| `conversations` | Yes | Array of user/assistant turns |
| `role` | Yes | Either "user" or "assistant" |
| `content` | Yes | Text content with CoT reasoning |

---

## CoT Section Guidelines

| Section | Purpose | Example |
|---------|---------|---------|
| **Observation** | Raw visual description | "I observe a dark vertical line spanning the left third of the panel" |
| **Visual Analysis** | Characterize defect features | "The line is perfectly straight, 1 sub-pixel wide, consistent across all colors" |
| **Structural Analysis** | Map to panel components | "This indicates a Data Line issue in the TFT backplane" |
| **Root Cause Hypothesis** | Manufacturing process link | "TAB bonding failure at edge connection" |
| **Severity Assessment** | Production impact | "Critical - panel non-functional, production stop required" |
| **Recommended Action** | Next steps | "Reject panel, escalate to bonding station QC" |
