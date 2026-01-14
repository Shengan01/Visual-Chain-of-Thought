# LCD Display Defect Taxonomy

## General Display Issues

| Defect Type | Description | Cause / Reasoning Path |
|-------------|-------------|------------------------|
| No Display or Black Screen | Screen is completely black or faint images visible under bright light | Backlight failure, power supply issue, or driver board malfunction. Faint images under bright light suggest backlight problem specifically. |
| Flickering or Dim Display | Screen brightness fluctuates or remains dim | LCD backlight repair needs or loose connections. Inspect power input and backlight inverter. |
| Distorted Colors or Contrast | Washed-out colors or poor image quality | LCD contrast issues from failing T-CON board or incorrect voltage settings. Check T-CON for burnt components or bulging capacitors. |
| Dead or Stuck Pixels | Small black or colored dots visible on screen | LCD pixel defects—may or may not be repairable. |
| Lines on Screen | Horizontal or vertical lines appearing on display | LCD driver board problems or damaged ribbon cables. |

---

## Internal Defects

| Defect Type | Description | Cause / Reasoning Path |
|-------------|-------------|------------------------|
| Internal Pollution | Black spots, stains, or fibers trapped within the LCD | Foreign contaminants entered during manufacturing or assembly. |
| Internal Scratches | Black or white lines appearing on display | Scratches on the polarizer film (PI) causing visual artifacts. |
| Color Cast | Uneven color distribution, rainbow patterns, or color stripes | Color filter inconsistencies during panel production. |
| Inconsistent Background Color | Significant color variations between different LCD screens | Manufacturing variance between batches or production runs. |

---

## Physical Damage

| Defect Type | Description | Cause / Reasoning Path |
|-------------|-------------|------------------------|
| Damaged Screen | Broken or chipped glass, corner damage | Physical impact or stress causing glass breakage or conductive layer issues. |
| Poor Glass Cutting | Uneven edges or protrusions on the glass | Imperfect cutting process during manufacturing. |
| PIN Scratches | Scratches on the conductive layer (PIN) | Handling damage leading to disconnection or conductivity problems. |

---

## Polarizer Defects

| Defect Type | Description | Cause / Reasoning Path |
|-------------|-------------|------------------------|
| Polarizer Scratches or Punctures | Mirror-like distortions or blurring on display | Physical damage to the polarizer film surface. |
| Polarizer Water Lines | Streaks appearing on display | Alcohol or acetone contamination during repair process. |
| Missing Protective Film | Torn or missing film on polarizer surface | Protective film removed or damaged, exposing polarizer. |
| Polarizer Bubbles | Small bubbles affecting display usability | Air trapped between the LCD and polarizer film during assembly. |
| Incorrect Polarizer Placement | Display appears abnormal or washed out | Polarizer film installed on wrong side of LCD. |
| Polarizer Corrosion | Discoloration or deformation of polarizer film | Chemical reactions from exposure to reactive substances. |

---

## Surface & Assembly Defects

| Defect Type | Description | Cause / Reasoning Path |
|-------------|-------------|------------------------|
| Convex Spots or Fibers | Visible bumps or fibers on display | Dust or foreign objects trapped on LCD surface during assembly. |
| Mixing of LCD Panels | Inconsistent display performance | Combining LCDs from different manufacturers or production periods with varying specifications. |

---

## Advanced Display Artifacts

| Defect Type | Description | Cause / Reasoning Path |
|-------------|-------------|------------------------|
| Mura (Uniformity Error) | Cloud-like artifacts or uneven brightness patches | Non-uniform liquid crystal distribution or backlight diffuser stress causing localized brightness variations. |
| Cross-talk | Ghosting or shadow images appearing near high-contrast edges | Parasitic capacitance between Data and Gate lines causing signal interference. |
| Light Leakage | Light "bleeding" from screen edges or corners | Mechanical pressure on panel frame compressing the liquid crystal layer unevenly. |
| Image Retention | Faint ghost image persisting after content change | Prolonged display of static content causing temporary charge buildup in liquid crystals. |
| Backlight Bleeding | Bright spots or uneven illumination, especially in corners | Poor assembly causing gaps between backlight unit and LCD panel. |
| Color Banding | Visible steps/bands in gradients instead of smooth transitions | Insufficient bit depth or poor gamma calibration in display driver. |
| Inverse Ghosting (Coronas) | Bright halos around moving objects | Overdrive circuits overcompensating pixel transitions, overshooting target values. |
| Newton Rings | Concentric interference patterns on screen | Air gap between touch panel and LCD creating optical interference. |

---

## OLED-Specific Defects

| Defect Type | Description | Cause / Reasoning Path |
|-------------|-------------|------------------------|
| OLED Dark Spot Growth | Expanding dark spots or dead areas on display | Oxidation of organic layers due to TFE (Thin Film Encapsulation) failure allowing moisture ingress. |
| OLED Burn-in | Permanent ghost images of static UI elements | Uneven degradation of organic compounds from prolonged static content display. |
| OLED Color Shift | Gradual change in color accuracy over time | Differential aging rates of red, green, and blue organic emitters. |
| OLED Uniformity Degradation | Uneven brightness across panel over time | Non-uniform pixel usage causing varied organic material degradation. |
| Green/Purple Tint at Low Brightness | Abnormal color cast visible at low brightness levels | Imbalanced sub-pixel minimum voltage thresholds or panel calibration issues. |
| OLED Panel Scratches | Fine scratches visible on screen surface | Damage to the flexible OLED substrate or cover glass during handling. |

---

## TFT Backplane Defects

| Defect Type | Description | Cause / Reasoning Path |
|-------------|-------------|------------------------|
| Gate Line Defect | Horizontal lines or bands across display | Open or shorted gate lines in TFT array preventing row activation. |
| Data Line Defect | Vertical lines or color stripes | Open or shorted data lines preventing proper pixel voltage delivery. |
| TFT Leakage | Pixel brightness decay between refresh cycles | Excessive leakage current in thin-film transistors causing charge loss. |
| Pixel Electrode Defect | Localized bright or dark spots | Defective ITO (Indium Tin Oxide) pixel electrodes from manufacturing. |