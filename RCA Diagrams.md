# Root Cause Analysis (RCA) Diagrams for Display Defects

This document contains diagnostic flowcharts following the Chain-of-Thought pattern:
**Visual Observation → Structural Analysis → Root Cause Hypothesis (Manufacturing Process)**

Each diagram shows how a single symptom can branch into multiple possible causes, reflecting real-world diagnostic complexity.

---

## 1. Vertical Line on Panel

```mermaid
flowchart TD
    A["Symptom: Vertical Line on Panel"] --> B{"Line Characteristics?"}
    
    B -->|"Perfectly straight, 1 sub-pixel wide"| C["Data Line Defect"]
    B -->|"Irregular, varying width"| D["Physical Damage"]
    B -->|"Appears only at certain colors"| E["Sub-pixel Specific Issue"]
    
    C --> C1{"Location on panel?"}
    C1 -->|"Near edge"| C2["TAB Bonding Failure"]
    C1 -->|"Middle of panel"| C3["ITO Metallization Break"]
    
    C2 --> C2a["Cause: Tape Automated Bonding process error"]
    C2 --> C2b["Cause: Mechanical stress during assembly"]
    
    C3 --> C3a["Cause: Photolithography defect"]
    C3 --> C3b["Cause: Particle contamination during deposition"]
    
    D --> D1["Cause: Ribbon cable damage"]
    D --> D2["Cause: Pressure crack in glass substrate"]
    
    E --> E1["Cause: Color filter misalignment"]
    E --> E2["Cause: Single sub-pixel column driver failure"]
```

---

## 2. Horizontal Line on Panel

```mermaid
flowchart TD
    A["Symptom: Horizontal Line on Panel"] --> B{"Line Behavior?"}
    
    B -->|"Static, always visible"| C["Gate Line Defect"]
    B -->|"Flickering or intermittent"| D["Connection Issue"]
    B -->|"Only visible during scrolling"| E["Timing Issue"]
    
    C --> C1{"Line appearance?"}
    C1 -->|"Bright line"| C2["Gate line short to VDD"]
    C1 -->|"Dark line"| C3["Gate line open circuit"]
    
    C2 --> C2a["Cause: Metal bridging during etching"]
    C3 --> C3a["Cause: Gate metal corrosion"]
    C3 --> C3b["Cause: Photoresist residue causing discontinuity"]
    
    D --> D1["Cause: Loose FPC connector"]
    D --> D2["Cause: Cold solder joint on driver IC"]
    
    E --> E1["Cause: Gate driver timing mismatch"]
    E --> E2["Cause: T-CON board malfunction"]
```

---

## 3. Dead/Dark Spots on Display

```mermaid
flowchart TD
    A["Symptom: Dark Spot on Display"] --> B{"Spot characteristics?"}
    
    B -->|"Single pixel, fixed location"| C["Pixel Defect"]
    B -->|"Cluster of pixels"| D["Localized Damage"]
    B -->|"Growing over time"| E["Progressive Degradation"]
    B -->|"Irregular shape"| F["Contamination"]
    
    C --> C1["Cause: TFT transistor failure"]
    C --> C2["Cause: Pixel electrode defect during ITO patterning"]
    
    D --> D1{"Panel type?"}
    D1 -->|"LCD"| D2["Cause: Liquid crystal leakage from seal failure"]
    D1 -->|"OLED"| D3["Cause: Organic layer delamination"]
    
    E --> E1{"Panel type?"}
    E1 -->|"LCD"| E2["Cause: Backlight LED degradation"]
    E1 -->|"OLED"| E3["Cause: TFE failure → moisture ingress → organic oxidation"]
    
    F --> F1["Cause: Particle trapped during cell assembly"]
    F --> F2["Cause: Polarizer contamination"]
```

---

## 4. Mura (Uniformity Error)

```mermaid
flowchart TD
    A["Symptom: Cloud-like Brightness Variations"] --> B{"Pattern type?"}
    
    B -->|"Blob Mura - irregular patches"| C["Cell Gap Variation"]
    B -->|"Line Mura - striped pattern"| D["Coating Defect"]
    B -->|"Corner/Edge Mura"| E["Mechanical Stress"]
    B -->|"Visible only at angles"| F["Optical Film Issue"]
    
    C --> C1["Cause: Uneven spacer distribution"]
    C --> C2["Cause: Liquid crystal fill volume variation"]
    C --> C3["Cause: Temperature gradient during LC injection"]
    
    D --> D1["Cause: Alignment layer rubbing inconsistency"]
    D --> D2["Cause: Photoresist coating thickness variation"]
    
    E --> E1["Cause: Frame pressure on panel"]
    E --> E2["Cause: Backlight diffuser sheet deformation"]
    E --> E3["Cause: Thermal expansion mismatch"]
    
    F --> F1["Cause: DBEF film scratches"]
    F --> F2["Cause: Prism sheet misalignment"]
```

---

## 5. Color Abnormalities

```mermaid
flowchart TD
    A["Symptom: Color Issues"] --> B{"Type of color problem?"}
    
    B -->|"Yellow/Brown tint overall"| C["Aging/Degradation"]
    B -->|"Color cast in specific regions"| D["Local Defect"]
    B -->|"Rainbow patterns"| E["Interference Issue"]
    B -->|"Color shift at angles"| F["Normal IPS/VA behavior"]
    
    C --> C1{"Panel type?"}
    C1 -->|"LCD"| C2["Cause: Polarizer yellowing from UV exposure"]
    C1 -->|"OLED"| C3["Cause: Blue emitter degradation faster than R/G"]
    
    D --> D1["Cause: Color filter layer damage"]
    D --> D2["Cause: Backlight LED color temperature drift"]
    
    E --> E1["Cause: Air gap in optical bonding"]
    E --> E2["Cause: Newton rings from touch panel assembly"]
    E --> E3["Cause: Color filter pigment crystallization"]
    
    F --> F1["Expected: LC molecular orientation causes angular dependency"]
```

---

## 6. Flickering Display

```mermaid
flowchart TD
    A["Symptom: Display Flickering"] --> B{"Flicker pattern?"}
    
    B -->|"Entire screen flickers"| C["Power/Backlight Issue"]
    B -->|"Partial screen flickers"| D["Driver Issue"]
    B -->|"Flicker at low brightness"| E["PWM Dimming"]
    B -->|"Flicker during touch"| F["EMI Issue"]
    
    C --> C1["Cause: Failing backlight inverter"]
    C --> C2["Cause: Capacitor degradation in power supply"]
    C --> C3["Cause: Loose power connector"]
    
    D --> D1["Cause: T-CON board malfunction"]
    D --> D2["Cause: Source driver IC partial failure"]
    D --> D3["Cause: LVDS cable signal integrity issue"]
    
    E --> E1["Cause: Low PWM frequency - perceivable by sensitive eyes"]
    E --> E2["Cause: DC dimming threshold too low"]
    
    F --> F1["Cause: Insufficient grounding"]
    F --> F2["Cause: Touch controller interference with display signals"]
```

---

## 7. Image Retention / Burn-in

```mermaid
flowchart TD
    A["Symptom: Ghost Image Visible"] --> B{"Persistence duration?"}
    
    B -->|"Fades after minutes"| C["Temporary Retention - LCD"]
    B -->|"Permanent"| D["Permanent Burn-in"]
    B -->|"Visible only on certain backgrounds"| E["Partial Degradation"]
    
    C --> C1["Cause: Ion migration in LC layer"]
    C --> C2["Cause: DC offset buildup from static image"]
    C --> C3["Recovery: Inversion driving / screen refresh"]
    
    D --> D1{"Panel type?"}
    D1 -->|"LCD"| D2["Cause: Polarizer molecular alignment change"]
    D1 -->|"OLED"| D3["Cause: Organic emitter material degradation"]
    D1 -->|"Plasma"| D4["Cause: Phosphor wear"]
    
    D3 --> D3a["Root: Blue OLED shorter lifespan"]
    D3 --> D3b["Root: Uneven current density over time"]
    
    E --> E1["Cause: Partial pixel capacitance degradation"]
    E --> E2["Cause: TFT threshold voltage shift"]
```

---

## 8. Touch Responsiveness Issues

```mermaid
flowchart TD
    A["Symptom: Touch Not Working Properly"] --> B{"Issue type?"}
    
    B -->|"No response at all"| C["Complete Failure"]
    B -->|"Dead zones"| D["Partial Failure"]
    B -->|"Ghost touches"| E["False Positives"]
    B -->|"Delayed response"| F["Performance Issue"]
    
    C --> C1["Cause: Touch controller IC failure"]
    C --> C2["Cause: FPC disconnection"]
    C --> C3["Cause: Touch sensor layer short circuit"]
    
    D --> D1["Cause: ITO trace break in touch sensor"]
    D --> D2["Cause: Delamination of touch layer"]
    D --> D3["Cause: Localized water damage"]
    
    E --> E1["Cause: EMI from display signals"]
    E --> E2["Cause: Charger noise injection"]
    E --> E3["Cause: Contamination on touch surface"]
    
    F --> F1["Cause: Insufficient touch sampling rate"]
    F --> F2["Cause: CPU throttling affecting touch processing"]
```

---

## 9. Backlight Issues

```mermaid
flowchart TD
    A["Symptom: Backlight Abnormality"] --> B{"Symptom type?"}
    
    B -->|"No backlight at all"| C["Complete Failure"]
    B -->|"Dim backlight"| D["Partial Failure"]
    B -->|"Uneven brightness"| E["Local Issue"]
    B -->|"Yellow/Pink spots"| F["LED Degradation"]
    
    C --> C1["Cause: LED driver failure"]
    C --> C2["Cause: Backlight fuse blown"]
    C --> C3["Cause: LED string open circuit"]
    
    D --> D1["Cause: Aging LEDs"]
    D --> D2["Cause: Driver IC limiting current"]
    D --> D3["Cause: Brightness sensor malfunction"]
    
    E --> E1["Cause: Light guide plate scratch/damage"]
    E --> E2["Cause: Diffuser sheet displacement"]
    E --> E3["Cause: Individual LED in string failing"]
    
    F --> F1["Cause: Phosphor degradation in white LEDs"]
    F --> F2["Cause: Thermal damage to LED package"]
```

---

## 10. Cross-talk / Ghosting

```mermaid
flowchart TD
    A["Symptom: Ghosting/Shadow Images"] --> B{"Ghost characteristics?"}
    
    B -->|"Horizontal shadows"| C["Gate Line Coupling"]
    B -->|"Vertical shadows"| D["Data Line Coupling"]
    B -->|"Motion blur shadows"| E["Response Time Issue"]
    B -->|"Shadows from adjacent content"| F["Signal Leakage"]
    
    C --> C1["Cause: Parasitic capacitance Cgd too high"]
    C --> C2["Cause: Gate pulse feedthrough"]
    
    D --> D1["Cause: Data line to pixel capacitance"]
    D --> D2["Cause: Incomplete pixel charging"]
    
    E --> E1["Cause: Slow LC switching speed"]
    E --> E2["Cause: Overdrive undershoot"]
    
    F --> F1["Cause: Insufficient shielding between pixels"]
    F --> F2["Cause: Column inversion driving artifacts"]
```

---

## 11. No Display / Black Screen

```mermaid
flowchart TD
    A["Symptom: No Display or Black Screen"] --> B{"Any faint image under bright light?"}
    
    B -->|"Yes, faint image visible"| C["Backlight Failure"]
    B -->|"No image at all"| D["Signal/Power Issue"]
    
    C --> C1{"Backlight type?"}
    C1 -->|"LED backlight"| C2["LED Driver Failure"]
    C1 -->|"CCFL backlight"| C3["Inverter Failure"]
    
    C2 --> C2a["Cause: LED driver IC malfunction"]
    C2 --> C2b["Cause: LED string open circuit"]
    C2 --> C2c["Cause: Thermal shutdown from overheating"]
    
    C3 --> C3a["Cause: Inverter transformer failure"]
    C3 --> C3b["Cause: High voltage capacitor degradation"]
    
    D --> D1{"Power LED status?"}
    D1 -->|"Power LED off"| D2["Power Supply Issue"]
    D1 -->|"Power LED on"| D3["Signal Processing Issue"]
    
    D2 --> D2a["Cause: Blown fuse in power supply"]
    D2 --> D2b["Cause: Failed capacitors in PSU"]
    D2 --> D2c["Cause: Power connector disconnection"]
    
    D3 --> D3a["Cause: T-CON board failure"]
    D3 --> D3b["Cause: Main board malfunction"]
    D3 --> D3c["Cause: LVDS/eDP cable disconnection"]
```

---

## 12. Polarizer Defects

```mermaid
flowchart TD
    A["Symptom: Polarizer-Related Visual Issue"] --> B{"Defect appearance?"}
    
    B -->|"Mirror-like distortions"| C["Polarizer Scratches/Punctures"]
    B -->|"Streak patterns"| D["Polarizer Water Lines"]
    B -->|"Small bubbles"| E["Polarizer Bubbles"]
    B -->|"Discoloration/deformation"| F["Polarizer Corrosion"]
    B -->|"Display washed out/abnormal"| G["Incorrect Polarizer Placement"]
    B -->|"Surface exposed"| H["Missing Protective Film"]
    
    C --> C1["Cause: Physical abrasion during handling"]
    C --> C2["Cause: Sharp object contact"]
    
    D --> D1["Cause: Alcohol contamination during repair"]
    D --> D2["Cause: Acetone exposure during cleaning"]
    D --> D3["Cause: Improper solvent use in rework"]
    
    E --> E1["Cause: Air trapped during lamination"]
    E --> E2["Cause: Temperature differential during bonding"]
    E --> E3["Cause: Insufficient roller pressure"]
    
    F --> F1["Cause: Chemical exposure to reactive substances"]
    F --> F2["Cause: Prolonged humidity exposure"]
    F --> F3["Cause: UV degradation over time"]
    
    G --> G1["Cause: Polarizer installed on wrong LCD side"]
    G --> G2["Cause: 90-degree rotation error"]
    
    H --> H1["Cause: Protective film torn during assembly"]
    H --> H2["Cause: Adhesive failure of protective layer"]
```

---

## 13. Physical Damage Assessment

```mermaid
flowchart TD
    A["Symptom: Physical Damage Visible"] --> B{"Damage type?"}
    
    B -->|"Broken/chipped glass"| C["Glass Fracture"]
    B -->|"Uneven glass edges"| D["Poor Glass Cutting"]
    B -->|"Scratches on conductive layer"| E["PIN Scratches"]
    B -->|"Corner damage"| F["Impact Damage"]
    
    C --> C1{"Crack pattern?"}
    C1 -->|"Spider web pattern"| C2["Cause: Point impact force"]
    C1 -->|"Linear crack"| C3["Cause: Bending stress"]
    C1 -->|"Edge-originating crack"| C4["Cause: Thermal shock or edge defect"]
    
    D --> D1["Cause: Dull cutting wheel"]
    D --> D2["Cause: Incorrect cutting speed"]
    D --> D3["Cause: Improper scribe pressure"]
    
    E --> E1["Cause: Handling damage during assembly"]
    E --> E2["Cause: Tool contact with ITO layer"]
    E --> E3["Cause: ESD damage to conductive traces"]
    
    F --> F1["Cause: Drop impact"]
    F --> F2["Cause: Pressure from mounting frame"]
    F --> F3["Cause: Transport damage"]
```

---

## 14. Light Leakage / Backlight Bleeding

```mermaid
flowchart TD
    A["Symptom: Light Bleeding from Edges/Corners"] --> B{"Location of bleeding?"}
    
    B -->|"Corner bleeding"| C["Corner Pressure Issue"]
    B -->|"Edge bleeding"| D["Frame Assembly Issue"]
    B -->|"Flashlighting pattern"| E["Diffuser Issue"]
    B -->|"Cloudy patches"| F["IPS Glow / Panel Characteristic"]
    
    C --> C1["Cause: Bezel screws overtightened"]
    C --> C2["Cause: Uneven frame pressure distribution"]
    C --> C3["Cause: Panel slightly warped"]
    
    D --> D1["Cause: Light guide plate not seated properly"]
    D --> D2["Cause: Missing or displaced light blocking tape"]
    D --> D3["Cause: Frame deformation from thermal cycling"]
    
    E --> E1["Cause: Diffuser sheet misalignment"]
    E --> E2["Cause: Diffuser film damage/wrinkle"]
    
    F --> F1["Expected: IPS technology inherent glow at angles"]
    F --> F2["Expected: VA panel corner glow normal behavior"]
```

---

## 15. Color Banding

```mermaid
flowchart TD
    A["Symptom: Visible Steps in Color Gradients"] --> B{"Banding characteristics?"}
    
    B -->|"Consistent across all content"| C["Panel Limitation"]
    B -->|"Only in specific colors"| D["Driver/Processing Issue"]
    B -->|"Varies with viewing angle"| E["Dithering Artifact"]
    
    C --> C1["Cause: 6-bit panel with FRC dithering"]
    C --> C2["Cause: Insufficient native color depth"]
    
    D --> D1["Cause: Gamma LUT quantization error"]
    D --> D2["Cause: Video processing reducing bit depth"]
    D --> D3["Cause: Source driver IC limited resolution"]
    
    E --> E1["Cause: Temporal dithering visible at certain angles"]
    E --> E2["Cause: Spatial dithering pattern perception"]
```

---

## 16. Inverse Ghosting (Coronas)

```mermaid
flowchart TD
    A["Symptom: Bright Halos Around Moving Objects"] --> B{"Halo characteristics?"}
    
    B -->|"Trailing bright edge"| C["Overdrive Overshoot"]
    B -->|"Leading bright edge"| D["Overdrive Timing Issue"]
    B -->|"Both edges affected"| E["Aggressive Overdrive Setting"]
    
    C --> C1["Cause: Voltage overshoot exceeding target gray level"]
    C --> C2["Cause: Overdrive LUT calibration error"]
    
    D --> D1["Cause: Predictive overdrive algorithm error"]
    D --> D2["Cause: Frame timing mismatch with LC response"]
    
    E --> E1["Cause: Factory overdrive setting too aggressive"]
    E --> E2["Cause: Temperature affecting LC viscosity"]
    E --> E3["Solution: Reduce overdrive/response time setting"]
```

---

## 17. Newton Rings

```mermaid
flowchart TD
    A["Symptom: Concentric Ring Interference Patterns"] --> B{"Ring location?"}
    
    B -->|"Under touch panel"| C["Touch Panel Air Gap"]
    B -->|"On display surface"| D["Protective Layer Issue"]
    B -->|"Visible when pressing screen"| E["Optical Bonding Issue"]
    
    C --> C1["Cause: Non-optical bonding with air gap"]
    C --> C2["Cause: Touch sensor flex causing contact"]
    C --> C3["Solution: OCA optical bonding required"]
    
    D --> D1["Cause: Screen protector air bubbles"]
    D --> D2["Cause: Protective film partial contact"]
    
    E --> E1["Cause: OCA adhesive insufficient coverage"]
    E --> E2["Cause: Dust particles in bonding layer"]
    E --> E3["Cause: Temperature-induced delamination"]
```

---

## 18. OLED-Specific Degradation

```mermaid
flowchart TD
    A["Symptom: OLED Panel Degradation"] --> B{"Degradation type?"}
    
    B -->|"Color accuracy changing"| C["OLED Color Shift"]
    B -->|"Uneven brightness over time"| D["Uniformity Degradation"]
    B -->|"Tint at low brightness"| E["Green/Purple Tint"]
    B -->|"Surface damage"| F["OLED Panel Scratches"]
    
    C --> C1["Cause: Blue emitter faster degradation"]
    C --> C2["Cause: Differential R/G/B aging rates"]
    C --> C3["Cause: High brightness usage accelerating decay"]
    
    D --> D1["Cause: Static UI elements causing local wear"]
    D --> D2["Cause: Uneven pixel usage patterns"]
    D --> D3["Cause: ABL not compensating for wear"]
    
    E --> E1["Cause: Sub-pixel minimum voltage threshold imbalance"]
    E --> E2["Cause: DC offset in black level calibration"]
    E --> E3["Cause: Panel binning/manufacturing variance"]
    
    F --> F1["Cause: Flexible substrate damage from bending"]
    F --> F2["Cause: Cover glass surface abrasion"]
    F --> F3["Cause: Pocket debris scratching screen"]
```

---

## 19. TFT Backplane Issues

```mermaid
flowchart TD
    A["Symptom: TFT-Related Pixel Issues"] --> B{"Issue pattern?"}
    
    B -->|"Pixel brightness fading"| C["TFT Leakage"]
    B -->|"Localized bright/dark spots"| D["Pixel Electrode Defect"]
    B -->|"Row not activating"| E["Gate Driver Issue"]
    B -->|"Column color issues"| F["Source Driver Issue"]
    
    C --> C1["Cause: Gate dielectric degradation"]
    C --> C2["Cause: a-Si or IGZO channel defects"]
    C --> C3["Cause: High temperature accelerating leakage"]
    
    D --> D1["Cause: ITO electrode patterning defect"]
    D --> D2["Cause: Particle contamination on electrode"]
    D --> D3["Cause: ESD damage to pixel"]
    
    E --> E1["Cause: Gate driver IC failure"]
    E --> E2["Cause: COG bonding defect"]
    
    F --> F1["Cause: Source driver IC partial failure"]
    F --> F2["Cause: Data line resistance variation"]
```

---

## 20. Internal Contamination & Scratches

```mermaid
flowchart TD
    A["Symptom: Internal Visual Defects"] --> B{"Defect appearance?"}
    
    B -->|"Black spots/stains"| C["Internal Pollution"]
    B -->|"Black or white lines"| D["Internal Scratches"]
    B -->|"Color variations between panels"| E["Inconsistent Background Color"]
    B -->|"Visible fibers"| F["Fiber Contamination"]
    
    C --> C1["Cause: Particle contamination during cell assembly"]
    C --> C2["Cause: Outgassing from sealant material"]
    C --> C3["Cause: LC fluid contamination"]
    
    D --> D1["Cause: Polarizer film (PI) scratched during handling"]
    D --> D2["Cause: Alignment layer rubbing damage"]
    D --> D3["Cause: Glass surface scratch before assembly"]
    
    E --> E1["Cause: LC batch variation"]
    E --> E2["Cause: Color filter thickness variance"]
    E --> E3["Cause: Backlight LED color temperature difference"]
    
    F --> F1["Cause: Cleanroom contamination"]
    F --> F2["Cause: Glove fiber shedding during handling"]
```

---

## 21. Surface & Assembly Defects

```mermaid
flowchart TD
    A["Symptom: Surface/Assembly Related Issues"] --> B{"Defect type?"}
    
    B -->|"Visible bumps on display"| C["Convex Spots"]
    B -->|"Visible fibers on surface"| D["Surface Fiber Contamination"]
    B -->|"Inconsistent performance"| E["Mixed LCD Panels"]
    
    C --> C1["Cause: Dust trapped on LCD surface"]
    C --> C2["Cause: Foreign particle under optical films"]
    C --> C3["Cause: Adhesive residue bump"]
    
    D --> D1["Cause: Contamination during final assembly"]
    D --> D2["Cause: Fiber from packaging material"]
    
    E --> E1["Cause: Different manufacturers mixed"]
    E --> E2["Cause: Different production batches combined"]
    E --> E3["Cause: Panel grade mixing in production"]
```

---

## 22. Distorted Colors / Contrast Issues

```mermaid
flowchart TD
    A["Symptom: Washed-out or Poor Contrast"] --> B{"Issue scope?"}
    
    B -->|"Entire display affected"| C["System-wide Issue"]
    B -->|"Gradual deterioration"| D["Component Aging"]
    B -->|"Sudden change"| E["Component Failure"]
    
    C --> C1{"Check T-CON board"}
    C1 -->|"Burnt components visible"| C2["Cause: T-CON component failure"]
    C1 -->|"Bulging capacitors"| C3["Cause: Capacitor degradation"]
    C1 -->|"No visible damage"| C4["Cause: Incorrect voltage settings"]
    
    D --> D1["Cause: Polarizer degradation from UV"]
    D --> D2["Cause: LC fluid property change over time"]
    D --> D3["Cause: Backlight color temperature drift"]
    
    E --> E1["Cause: LVDS cable partial failure"]
    E --> E2["Cause: Gamma IC malfunction"]
    E --> E3["Cause: Power rail voltage deviation"]
```

---

## RCA Pattern Summary

The diagnostic process follows this general pattern:

```mermaid
flowchart LR
    A["Visual Symptom"] --> B["Characterize Defect"]
    B --> C["Narrow Down Category"]
    C --> D["Identify Specific Failure Mode"]
    D --> E["Trace to Manufacturing Process"]
    E --> F["Root Cause Hypothesis"]
    
    style A fill:#ffcccc
    style F fill:#ccffcc
```

### Key Manufacturing Processes Referenced:
| Process | Related Defects |
|---------|-----------------|
| Photolithography | ITO patterning defects, line breaks, shorts |
| Thin Film Deposition | TFT failures, electrode defects, TFT leakage |
| TAB/COF Bonding | Edge connection failures, driver IC issues |
| Cell Assembly | Contamination, LC fill issues, gap variation, internal scratches |
| Optical Film Lamination | Mura, bubbles, Newton rings, polarizer defects |
| Glass Cutting | Edge defects, panel cracks |
| Polarizer Application | Water lines, bubbles, corrosion, placement errors |
| TFE Encapsulation (OLED) | Moisture ingress, dark spot growth, color shift |
| Final Assembly | Surface contamination, light leakage, backlight bleeding |

---

## Multi-Resolution Reasoning Framework

> **Problem**: Standard MLLMs resize images (e.g., to 448×448), losing critical pixel-level defect information. This framework enables reasoning across multiple resolution scales.

### When to Apply Multi-Resolution Analysis

```mermaid
flowchart TD
    A["Input: Full Panel Image"] --> B{"Defect visible at global scale?"}
    
    B -->|"Yes, clearly visible"| C["Standard RCA Path"]
    B -->|"Partially visible"| D["Multi-Resolution Analysis"]
    B -->|"Suspected but unclear"| D
    
    D --> E["Step 1: Global Localization"]
    E --> F["Step 2: Region Cropping"]
    F --> G["Step 3: High-Res Analysis"]
    G --> H["Step 4: Context Integration"]
    H --> I["Final Root Cause Diagnosis"]
    
    C --> I
    
    style D fill:#ffffcc
    style E fill:#e6f3ff
    style F fill:#e6f3ff
    style G fill:#e6f3ff
    style H fill:#e6f3ff
```

### Multi-Resolution RCA Template

```mermaid
flowchart TD
    subgraph Global["🔍 Global View (Full Panel)"]
        G1["Identify suspicious regions"]
        G2["Assess defect distribution pattern"]
        G3["Note panel location context"]
    end
    
    subgraph Crop["Crop Decision"]
        C1{"Defect type requires\nmicroscopic analysis?"}
        C1 -->|"Pixel defects"| C2["Crop: 64×64 px region"]
        C1 -->|"Line defects"| C3["Crop: 256×64 or 64×256 strip"]
        C1 -->|"Area defects (Mura)"| C4["Crop: 256×256 region"]
    end
    
    subgraph HighRes["High-Resolution Analysis"]
        H1["Sub-pixel level inspection"]
        H2["Edge sharpness analysis"]
        H3["Pattern regularity check"]
    end
    
    subgraph Integration["Context Integration"]
        I1["Combine global position + local detail"]
        I2["Cross-reference with panel schematic"]
        I3["Manufacturing process correlation"]
    end
    
    Global --> Crop --> HighRes --> Integration
```

### Example: Pixel Defect with Multi-Resolution

```mermaid
flowchart TD
    A["Global View: 'Small dark spot detected in upper-left quadrant'"]
    
    A --> B["Crop Region: 64×64 pixels centered on anomaly"]
    
    B --> C{"High-Res Observation"}
    C -->|"Single sub-pixel dark"| D1["Dead Sub-pixel"]
    C -->|"3×3 pixel cluster dark"| D2["TFT Array Defect"]
    C -->|"Irregular dark shape"| D3["Particle Contamination"]
    
    D1 --> E1["Root Cause: Source driver voltage failure\nfor single column at this position"]
    D2 --> E2["Root Cause: Gate line partial short\ncausing localized row/column failure"]
    D3 --> E3["Root Cause: Cleanroom contamination\nduring cell assembly process"]
    
    E1 --> F["Context: Upper-left position suggests\ndriver IC near edge - check COF bonding"]
    E2 --> F
    E3 --> F
    
    style B fill:#ffffcc
    style C fill:#e6f3ff
```

### Resolution Strategy by Defect Type

| Defect Category | Global View Purpose | Crop Strategy | High-Res Focus |
|-----------------|---------------------|---------------|----------------|
| Dead/Stuck Pixels | Location, clustering pattern | 32-64px around defect | Sub-pixel RGB analysis |
| Line Defects | Full line trajectory | Narrow strip along line | Edge irregularity, width consistency |
| Mura | Overall distribution | Multiple 256×256 samples | Intensity gradient analysis |
| Contamination | Count, distribution | Individual particle crops | Shape, color, transparency |
| Burn-in | Pattern recognition | UI element region | Differential degradation |

### Confidence Adjustment Rules

| Scenario | Confidence Modifier |
|----------|---------------------|
| Global + High-Res findings align | ↑ +20% confidence |
| Findings contradict | ↓ -30% confidence, request additional crops |
| High-Res reveals new details | Revise initial hypothesis |
| Edge-of-crop artifacts visible | ↓ -10%, expand crop region |
