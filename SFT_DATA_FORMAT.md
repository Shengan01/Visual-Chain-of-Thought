# SFT Training Data Format — MedCoT

Template format for supervised fine-tuning of multimodal models on medical VQA with Chain-of-Thought reasoning.

---

## JSONL Conversation Format (Qwen3-VL Compatible)

### Standard Medical VQA with CoT

```json
{
  "image": "path/to/medical_image.jpg",
  "conversations": [
    {
      "role": "user",
      "content": "Is there any abnormality visible in this chest X-ray? Provide detailed reasoning."
    },
    {
      "role": "assistant",
      "content": "**Observation**: I observe the posteroanterior chest radiograph showing the thoracic cavity. The cardiac silhouette appears within normal limits. There is an area of increased opacity in the right lower lobe.\n\n**Visual Analysis**: The opacity is homogeneous, well-defined, and located in the right costophrenic angle. There is blunting of the right costophrenic angle with a meniscus sign.\n\n**Clinical Reasoning**: The pattern of a meniscus-shaped opacity at the costophrenic angle with dependent layering is characteristic of a pleural effusion rather than consolidation or atelectasis.\n\n**Answer**: Yes, there is a right-sided pleural effusion visible in the right lower zone, evidenced by costophrenic angle blunting and the meniscus sign."
    }
  ]
}
```

### CoT Extracted from MIMIC-CXR Report

```json
{
  "image": "mimic_cxr/p10/p10000032/s50414267/02aa804e-bde0afdd-112c0b34-7bc16630-4e384014.jpg",
  "conversations": [
    {
      "role": "user",
      "content": "Analyze this chest radiograph. What are the key findings?"
    },
    {
      "role": "assistant",
      "content": "**Observation**: PA and lateral chest radiograph obtained. Heart size is top-normal. Mediastinal contours are unremarkable. Lungs are clear bilaterally.\n\n**Visual Analysis**: No focal consolidation, pleural effusion, or pneumothorax identified. The osseous structures appear intact without acute fractures.\n\n**Clinical Reasoning**: The absence of parenchymal opacities, pleural abnormalities, and mediastinal widening, combined with a borderline cardiac silhouette, suggests no acute cardiopulmonary process.\n\n**Answer**: No acute cardiopulmonary abnormality. Heart size is at the upper limits of normal, which may warrant clinical correlation."
    }
  ]
}
```

### Multi-Modality Format (OmniMedVQA)

```json
{
  "image": "omnimedvqa/dermoscopy/derm_12345.jpg",
  "modality": "Dermoscopy",
  "organ": "Skin",
  "conversations": [
    {
      "role": "user",
      "content": "What type of skin lesion is shown in this dermoscopic image?"
    },
    {
      "role": "assistant",
      "content": "**Observation**: The dermoscopic image shows a pigmented lesion with an asymmetric shape. The lesion measures approximately 8mm in diameter with irregular borders.\n\n**Visual Analysis**: I observe multiple colors including dark brown, black, and blue-gray areas. There is a blue-white veil present in the upper portion. The pigment network is atypical with irregular meshes and thick lines. Regression structures (white scar-like areas) are visible centrally.\n\n**Clinical Reasoning**: The combination of asymmetry, multiple colors (>3), blue-white veil, atypical pigment network, and regression structures scores high on the 7-point checklist for melanoma (score ≥3 indicates high suspicion). These features are inconsistent with benign nevi.\n\n**Answer**: This lesion shows dermoscopic features highly suspicious for melanoma, including atypical pigment network, blue-white veil, and regression structures. Excisional biopsy is recommended."
    }
  ]
}
```

### Closed-Ended Question Format

```json
{
  "image": "path/to/brain_mri.jpg",
  "conversations": [
    {
      "role": "user",
      "content": "Is there a mass visible in this brain MRI? Answer Yes or No with reasoning."
    },
    {
      "role": "assistant",
      "content": "**Observation**: Axial T1-weighted post-contrast MRI of the brain. There is a well-defined, ring-enhancing lesion in the right frontal lobe.\n\n**Visual Analysis**: The lesion measures approximately 3cm in diameter, shows peripheral contrast enhancement with central necrosis. There is surrounding vasogenic edema and mild mass effect with midline shift.\n\n**Clinical Reasoning**: A ring-enhancing lesion with central necrosis and surrounding edema in an adult is concerning for either a high-grade glioma (GBM) or metastatic disease. The solitary nature and location are consistent with both etiologies.\n\n**Answer**: Yes"
    }
  ]
}
```

---

## Field Descriptions

| Field | Required | Description |
|-------|----------|-------------|
| `image` | Yes | Path to medical image |
| `modality` | Optional | Imaging modality (CT, MRI, X-Ray, etc.) |
| `organ` | Optional | Anatomical region |
| `conversations` | Yes | Array of user/assistant turns |
| `role` | Yes | Either "user" or "assistant" |
| `content` | Yes | Text content with CoT reasoning |

---

## CoT Section Guidelines

| Section | Purpose | Medical Example |
|---------|---------|-----------------|
| **Observation** | Raw visual description of the image | "PA chest radiograph showing bilateral lung fields with increased opacity in the right lower lobe" |
| **Visual Analysis** | Characterize imaging findings | "The opacity is homogeneous with air bronchograms, measuring ~4cm, with well-defined margins" |
| **Clinical Reasoning** | Connect findings to differential diagnosis | "Homogeneous opacity with air bronchograms suggests consolidation. Location and pattern consistent with lobar pneumonia" |
| **Answer** | Final answer to the clinical question | "Right lower lobe pneumonia, likely bacterial" |

---

## CoT Extraction Rules from MIMIC-CXR Reports

```python
# Mapping report sections to CoT format:

REPORT_TO_COT_MAPPING = {
    "FINDINGS": {
        "maps_to": ["Observation", "Visual Analysis"],
        "extraction": "Split findings into individual observations"
    },
    "IMPRESSION": {
        "maps_to": ["Clinical Reasoning", "Answer"],
        "extraction": "First sentence = reasoning, last = conclusion"
    },
    "COMPARISON": {
        "maps_to": ["Observation"],
        "extraction": "Note temporal context if available"
    },
    "INDICATION": {
        "maps_to": ["context"],
        "extraction": "Include as clinical context in user prompt"
    }
}
```

---

## Quality Requirements

| Criterion | Requirement |
|-----------|-------------|
| **Medical Accuracy** | CoT must not hallucinate anatomical terms or diagnoses |
| **Completeness** | All 4 CoT sections must be present |
| **Terminology** | Use standard medical terminology (aligned with RadLex) |
| **Specificity** | Reference specific anatomical locations (not "somewhere in the image") |
| **Consistency** | Same finding → same reasoning path across similar images |
