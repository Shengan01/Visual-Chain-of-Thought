# Medical Imaging Technical Glossary

A comprehensive glossary of technical terms, abbreviations, and expert vocabulary for medical image analysis and diagnostic reasoning in the MedCoT project.

---

## Abbreviations & Acronyms

| Abbreviation | Full Term | Definition |
|--------------|-----------|------------|
| **AP** | Anteroposterior | X-ray projection from front to back |
| **BIRADS** | Breast Imaging Reporting and Data System | Standardized mammography classification (0-6) |
| **CBCT** | Cone Beam Computed Tomography | 3D imaging using cone-shaped X-ray beam |
| **CoT** | Chain-of-Thought | Step-by-step reasoning process in LLMs |
| **CT** | Computed Tomography | Cross-sectional imaging using X-rays |
| **CXR** | Chest X-Ray | Radiograph of the thoracic cavity |
| **DWI** | Diffusion-Weighted Imaging | MRI sequence detecting water molecule diffusion |
| **FLAIR** | Fluid-Attenuated Inversion Recovery | MRI sequence suppressing CSF signal |
| **FP** | Fundus Photography | Imaging of the retina through the pupil |
| **GBM** | Glioblastoma Multiforme | Most aggressive primary brain tumor |
| **HU** | Hounsfield Unit | CT density measurement scale |
| **ICP** | Intracranial Pressure | Pressure inside the skull |
| **LoRA** | Low-Rank Adaptation | Parameter-efficient fine-tuning method |
| **LVLM** | Large Vision-Language Model | Multimodal model processing images + text |
| **MRI** | Magnetic Resonance Imaging | Imaging using magnetic fields and radio waves |
| **OCT** | Optical Coherence Tomography | Cross-sectional retinal imaging |
| **PA** | Posteroanterior | X-ray projection from back to front (standard CXR) |
| **PEFT** | Parameter-Efficient Fine-Tuning | Training methods that update few parameters |
| **QA** | Question-Answer | Basic unit of VQA data |
| **QLoRA** | Quantized Low-Rank Adaptation | LoRA with 4-bit quantization |
| **ROI** | Region of Interest | Specific area of an image for analysis |
| **SFT** | Supervised Fine-Tuning | Training on labeled examples |
| **T1W** | T1-Weighted | MRI sequence emphasizing tissue relaxation |
| **T2W** | T2-Weighted | MRI sequence emphasizing water content |
| **US** | Ultrasound | Imaging using sound waves |
| **VLM** | Vision-Language Model | Model for joint image-text understanding |
| **VQA** | Visual Question Answering | Task of answering questions about images |

---

## Imaging Modalities (OmniMedVQA Coverage)

| Modality | Abbreviation | Primary Use | Image Characteristics |
|----------|--------------|-------------|----------------------|
| **X-Ray** | XR | Bones, chest, abdomen | Grayscale, projection imaging, superimposed structures |
| **Computed Tomography** | CT | Cross-sectional anatomy, trauma | Grayscale, axial/coronal/sagittal, HU density values |
| **Magnetic Resonance** | MRI | Soft tissue, brain, spine | Multiple sequences (T1, T2, FLAIR, DWI), high contrast |
| **Ultrasound** | US | Obstetrics, abdomen, vascular | Real-time, grayscale + Doppler, operator-dependent |
| **Dermoscopy** | Der | Skin lesions | Color, magnified, specific structures (network, globules) |
| **Endoscopy** | End | GI tract, airways | Color, intraluminal view, mucosal detail |
| **Fundus Photography** | FP | Retina, optic disc | Color, wide/narrow field, specific landmarks |
| **Microscopy** | Mic | Histopathology, cytology | Stained cells (H&E, IHC), multiple magnifications |
| **OCT** | OCT | Retinal layers | Cross-sectional, layer segmentation |
| **Digital Photography** | DP | Clinical photos, wounds | Color, macro, standardized lighting |
| **Infrared Reflectance** | IRI | Retinal imaging | Near-infrared wavelength |
| **Colposcopy** | Co | Cervical examination | Magnified, after acetic acid/iodine application |

---

## Anatomical Terminology

### Body Regions

| Term | Definition |
|------|------------|
| **Thorax** | Chest cavity containing heart and lungs |
| **Mediastinum** | Central thoracic compartment |
| **Costophrenic angle** | Junction of diaphragm and chest wall |
| **Hilum** | Root of the lung (vessels, bronchi) |
| **Parenchyma** | Functional tissue of an organ |
| **Peritoneum** | Membrane lining abdominal cavity |
| **Retroperitoneum** | Space behind the peritoneum |
| **Sella turcica** | Bony seat of the pituitary gland |

### Orientation & Views

| Term | Definition |
|------|------------|
| **Axial** | Horizontal cross-section (head-to-toe direction) |
| **Coronal** | Front-to-back cross-section |
| **Sagittal** | Side-to-side cross-section |
| **Lateral** | Side view |
| **Supine** | Lying face up |
| **Prone** | Lying face down |
| **Decubitus** | Lying on side (lateral decubitus) |

---

## Radiological Signs

| Sign | Modality | Finding It Indicates |
|------|----------|----------------------|
| **Air bronchograms** | CXR/CT | Air-filled bronchi within consolidated lung |
| **Meniscus sign** | CXR | Concave upper border of pleural effusion |
| **Silhouette sign** | CXR | Loss of normal border between structures |
| **Kerley B lines** | CXR | Short horizontal lines at lung periphery (pulmonary edema) |
| **Cephalization** | CXR | Redistribution of blood flow to upper lobes |
| **Deep sulcus sign** | CXR (supine) | Lucent costophrenic angle = pneumothorax |
| **Dural tail sign** | MRI | Linear enhancement along dura = meningioma |
| **Ring enhancement** | CT/MRI | Enhancing rim around necrotic center |
| **Butterfly pattern** | MRI | Bilateral glioma crossing corpus callosum |
| **Halo sign** | CT | Ground-glass surrounding a nodule |

---

## Diagnostic Terminology

### Finding Descriptors

| Term | Definition |
|------|------------|
| **Opacity** | Area of increased density/whiteness on X-ray/CT |
| **Lucency** | Area of decreased density/darkness |
| **Consolidation** | Airspace filled with material (fluid, pus, cells) |
| **Ground-glass opacity (GGO)** | Hazy increased opacity without obscuring vessels |
| **Mass effect** | Displacement of structures by a space-occupying lesion |
| **Midline shift** | Displacement of brain midline structures |
| **Vasogenic edema** | Brain swelling from blood-brain barrier breakdown |
| **Enhancement** | Increased signal after contrast agent injection |
| **Calcification** | Calcium deposits visible on imaging |
| **Spiculation** | Star-like projections from a mass (suggests malignancy) |

### Severity & Urgency

| Term | Definition |
|------|------------|
| **Acute** | Sudden onset, requiring immediate attention |
| **Chronic** | Long-standing finding |
| **Incidental** | Unexpected finding unrelated to clinical question |
| **Stable** | Unchanged compared to prior imaging |
| **Progressing** | Worsening compared to prior imaging |
| **Interval change** | Difference between current and prior study |

---

## Expert Diagnostic Phrases for CoT

Use these phrases instead of simple descriptions in CoT outputs:

| Instead of | Use |
|------------|-----|
| "White spot on lung" | "Focal parenchymal opacity in the right lower lobe" |
| "Heart is big" | "Cardiomegaly with cardiothoracic ratio exceeding 0.5" |
| "Fluid around lungs" | "Moderate right-sided pleural effusion with meniscus sign" |
| "Brain tumor" | "Heterogeneously enhancing intra-axial mass with surrounding vasogenic edema" |
| "Broken bone" | "Non-displaced transverse fracture of the mid-diaphysis" |
| "Swollen brain" | "Diffuse cerebral edema with effacement of sulci and basal cisterns" |
| "Eye problem" | "Proliferative diabetic retinopathy with neovascularization at the disc" |
| "Skin cancer" | "Atypical pigmented lesion with asymmetry, irregular network, and blue-white veil" |
| "Normal image" | "No acute cardiopulmonary abnormality. Clear lungs bilaterally" |

---

## VQA Question Types (OmniMedVQA)

| Question Type | Description | Example |
|---------------|-------------|---------|
| **Diagnosis** | Identify the pathology | "What is the diagnosis?" |
| **Presence/Absence** | Is something there? | "Is there a pleural effusion?" |
| **Anatomical Localization** | Where is the finding? | "In which lobe is the opacity?" |
| **Modality Recognition** | What imaging type? | "What imaging modality is this?" |
| **Anatomy Identification** | What organ/structure? | "What organ is shown?" |
| **Lesion Grading** | How severe? | "What BIRADS category?" |
| **Comparison** | Change over time? | "Has the effusion increased?" |

---

## Evaluation Metrics

| Metric | Full Name | Use In MedCoT |
|--------|-----------|---------------|
| **BLEU** | Bilingual Evaluation Understudy | CoT text quality |
| **ROUGE-L** | Recall-Oriented Understudy for Gisting Evaluation | CoT recall of key findings |
| **BERTScore** | BERT-based semantic similarity | CoT semantic accuracy |
| **Accuracy** | Exact match / F1 | VQA answer correctness |
| **Hallucination Rate** | % of clinically inaccurate statements | Medical safety |
| **CoT Completeness** | % of required reasoning sections present | Reasoning structure |
