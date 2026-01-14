# Display Technology Technical Glossary

A comprehensive glossary of technical terms, abbreviations, and expert vocabulary for display panel analysis and defect diagnosis.

---

## Abbreviations & Acronyms

| Abbreviation | Full Term | Definition |
|--------------|-----------|------------|
| **a-Si** | Amorphous Silicon | Non-crystalline silicon used in traditional TFT backplanes; lower electron mobility than LTPS or IGZO |
| **ABL** | Automatic Brightness Limiter | OLED protection circuit that reduces brightness to prevent burn-in and thermal damage |
| **BLU** | Backlight Unit | Light source assembly behind LCD panel, typically LED edge-lit or direct-lit |
| **CCFL** | Cold Cathode Fluorescent Lamp | Legacy backlight technology using fluorescent tubes; replaced by LED |
| **COF** | Chip On Film | Driver IC mounting method using flexible circuit film |
| **COG** | Chip On Glass | Driver IC directly bonded to glass substrate |
| **DBEF** | Dual Brightness Enhancement Film | 3M optical film that recycles polarized light to increase brightness |
| **DC** | Direct Current | Continuous electrical current; DC dimming adjusts brightness via voltage |
| **eDP** | Embedded DisplayPort | High-speed digital interface for internal display connections |
| **EMI** | Electromagnetic Interference | Electrical noise affecting signal integrity |
| **ESD** | Electrostatic Discharge | Sudden current flow from static electricity; damages sensitive components |
| **FPC** | Flexible Printed Circuit | Bendable circuit board connecting display components |
| **FRC** | Frame Rate Control | Temporal dithering technique to simulate higher color depth |
| **IGZO** | Indium Gallium Zinc Oxide | Advanced TFT semiconductor with high mobility and low leakage |
| **IPS** | In-Plane Switching | LCD technology with wide viewing angles; LC molecules rotate parallel to substrate |
| **ITO** | Indium Tin Oxide | Transparent conductive material for electrodes and touch sensors |
| **LC** | Liquid Crystal | Organic molecules that change orientation under electric field |
| **LTPS** | Low-Temperature Polysilicon | High-performance TFT backplane technology; enables higher PPI |
| **LUT** | Look-Up Table | Pre-calculated values for gamma correction or overdrive |
| **LVDS** | Low-Voltage Differential Signaling | Display interface transmitting video data to T-CON |
| **OCA** | Optically Clear Adhesive | Transparent adhesive for bonding touch panel to display |
| **OLED** | Organic Light-Emitting Diode | Self-emissive display technology using organic compounds |
| **PI** | Polyimide | Polymer film used for alignment layers and flexible substrates |
| **PPI** | Pixels Per Inch | Display resolution density metric |
| **PSU** | Power Supply Unit | Converts AC mains to DC voltages required by display |
| **PWM** | Pulse Width Modulation | Brightness control via rapid on/off cycling |
| **RCA** | Root Cause Analysis | Systematic problem-solving methodology |
| **TAB** | Tape Automated Bonding | Driver IC connection method using tape carrier |
| **T-CON** | Timing Controller | Board that processes video signal and controls panel timing |
| **TFE** | Thin Film Encapsulation | Multi-layer barrier protecting OLED from moisture/oxygen |
| **TFT** | Thin-Film Transistor | Transistor controlling each pixel; acts as switch |
| **VA** | Vertical Alignment | LCD technology with high contrast; LC molecules tilt vertically |
| **VDD** | Voltage Drain Drain | Positive power supply rail |
| **VRAM** | Video Random Access Memory | GPU memory for frame buffer storage |

---

## Panel Technologies

### LCD Panel Types

| Term | Definition |
|------|------------|
| **TN (Twisted Nematic)** | Oldest LCD technology; fast response but poor viewing angles and color |
| **IPS (In-Plane Switching)** | Wide viewing angles, accurate colors; slower response than TN |
| **VA (Vertical Alignment)** | High contrast ratio, deep blacks; slower response, viewing angle color shift |
| **MVA (Multi-domain VA)** | VA variant with improved viewing angles via multiple LC domains |
| **PVA (Patterned VA)** | Samsung's VA variant with enhanced contrast |
| **AHVA (Advanced Hyper-Viewing Angle)** | AUO's IPS-like technology |
| **ADS (Advanced Super Dimension Switch)** | BOE's IPS-equivalent technology |

### OLED Technologies

| Term | Definition |
|------|------------|
| **AMOLED** | Active-Matrix OLED with TFT backplane for each pixel |
| **PMOLED** | Passive-Matrix OLED; simpler but limited to small displays |
| **WOLED** | White OLED with color filters; used in LG large panels |
| **QD-OLED** | Blue OLED with quantum dot color conversion layer |
| **RGB OLED** | Direct RGB subpixel emission; used in Samsung mobile displays |
| **Tandem OLED** | Stacked emission layers for higher brightness and longevity |

---

## Display Components

### Optical Stack

| Term | Definition |
|------|------------|
| **Polarizer** | Optical filter allowing only specific light polarization to pass |
| **Analyzer** | Second polarizer rotated 90° from first; controls light transmission |
| **Retardation Film** | Compensates for viewing angle color shift |
| **Diffuser** | Spreads light evenly from backlight source |
| **Light Guide Plate (LGP)** | Acrylic plate distributing edge LED light across panel area |
| **Prism Sheet** | Redirects light toward viewer for improved brightness |
| **BEF (Brightness Enhancement Film)** | Prism-based film increasing on-axis brightness |
| **Reflector** | Reflects escaped light back into optical stack |
| **Cover Glass** | Protective front glass layer |

### Electronic Components

| Term | Definition |
|------|------------|
| **Source Driver IC** | Delivers voltage to data lines (vertical columns) |
| **Gate Driver IC** | Activates gate lines (horizontal rows) sequentially |
| **Gamma IC** | Generates reference voltages for grayscale levels |
| **Level Shifter** | Converts logic-level signals to pixel-driving voltages |
| **PMIC (Power Management IC)** | Generates and regulates multiple voltage rails |
| **Backlight Driver** | Controls LED current for brightness adjustment |
| **Inverter** | Converts DC to high-voltage AC for CCFL backlights |

### TFT Backplane

| Term | Definition |
|------|------------|
| **Gate Line** | Horizontal conductor activating row of TFTs |
| **Data Line** | Vertical conductor carrying pixel voltage |
| **Storage Capacitor (Cs)** | Maintains pixel voltage between refresh cycles |
| **Pixel Electrode** | ITO pad applying voltage across LC layer |
| **Common Electrode** | Reference electrode for LC cell |
| **Vcom** | Common electrode voltage; critical for image quality |

---

## Defect Terminology

### Visual Defects

| Term | Definition |
|------|------------|
| **Mura** | Japanese for "unevenness"; non-uniform brightness or color regions |
| **Blob Mura** | Irregular patch-shaped uniformity defect |
| **Line Mura** | Striped pattern uniformity defect |
| **Clouding** | Visible light patches on dark content; often pressure-related |
| **Flashlighting** | Light leakage from panel edges resembling flashlight beam |
| **IPS Glow** | Characteristic silver/purple glow at angles; inherent to IPS |
| **Newton Rings** | Concentric interference patterns from air gap contact |
| **Burn-in** | Permanent image retention from organic material degradation |
| **Image Retention** | Temporary ghost image; reversible unlike burn-in |
| **Cross-talk** | Signal interference causing ghost images |
| **Ghosting** | Trailing or shadow images from slow pixel response |
| **Coronas** | Bright halos from overdrive overshoot; inverse ghosting |
| **Color Banding** | Visible steps in gradients instead of smooth transitions |
| **Posterization** | Extreme banding reducing color gradation |

### Pixel Defects

| Term | Definition |
|------|------------|
| **Dead Pixel** | Pixel permanently off (black) |
| **Stuck Pixel** | Pixel permanently on (colored) |
| **Hot Pixel** | Pixel abnormally bright; always white |
| **Sub-pixel Defect** | Single R, G, or B element malfunction |
| **Cluster Defect** | Group of adjacent defective pixels |

### Manufacturing Defects

| Term | Definition |
|------|------------|
| **Particle Contamination** | Foreign matter trapped during fabrication |
| **Photoresist Residue** | Incomplete removal of photolithography mask material |
| **Metal Bridging** | Unintended connection between conductors |
| **Open Circuit** | Break in conductor preventing current flow |
| **Short Circuit** | Unintended connection causing current bypass |
| **Delamination** | Layer separation within display stack |
| **Cell Gap Variation** | Non-uniform LC layer thickness |

---

## Manufacturing Processes

| Term | Definition |
|------|------------|
| **Photolithography** | Patterning process using light-sensitive resist and masks |
| **Etching** | Removing material to create patterns (wet or dry) |
| **Deposition** | Adding thin film layers (sputtering, CVD, evaporation) |
| **Rubbing** | Mechanical alignment layer treatment for LC orientation |
| **Photo-alignment** | Non-contact UV alignment layer treatment |
| **Cell Assembly** | Bonding substrates and injecting liquid crystal |
| **ODF (One Drop Fill)** | LC dispensing method for large panels |
| **Vacuum Injection** | Legacy LC filling method via capillary action |
| **Lamination** | Bonding optical films to display |
| **TAB Bonding** | Attaching driver ICs via tape carrier |
| **ACF (Anisotropic Conductive Film)** | Adhesive with directional conductivity for bonding |
| **Module Assembly** | Integrating panel, backlight, and electronics |

---

## Signal Processing Terms

| Term | Definition |
|------|------------|
| **Gamma Correction** | Non-linear mapping for perceptually uniform brightness |
| **Overdrive** | Voltage boost for faster pixel transitions |
| **Undershoot/Overshoot** | Overdrive target error causing inverse ghosting |
| **Frame Inversion** | Polarity alternation to prevent DC image sticking |
| **Dot Inversion** | Per-pixel polarity pattern for image quality |
| **Column Inversion** | Per-column polarity alternation |
| **Hold-Type Blur** | Motion blur from sample-and-hold display operation |
| **BFI (Black Frame Insertion)** | Inserting black frames to reduce motion blur |
| **VRR (Variable Refresh Rate)** | Dynamic refresh matching source frame rate |
| **MEMC** | Motion Estimation/Motion Compensation; frame interpolation |

---

## Electrical Parameters

| Term | Definition |
|------|------------|
| **Threshold Voltage (Vth)** | Minimum gate voltage to turn on TFT |
| **Ion/Ioff Ratio** | TFT on-state to off-state current ratio; higher is better |
| **Leakage Current** | Unwanted current flow through off-state TFT |
| **Parasitic Capacitance** | Unintended capacitance between conductors |
| **Cgd** | Gate-to-drain capacitance; causes feedthrough |
| **Kickback Voltage** | Voltage shift from gate signal coupling to pixel |
| **Flicker** | Visible brightness oscillation from incomplete DC balancing |
| **Feed-through** | Signal coupling from gate to pixel electrode |

---

## Expert Diagnostic Phrases

Use these phrases instead of simple descriptions:

| Instead of | Use |
|------------|-----|
| "Black screen" | "Complete backlight failure with intact video signal path" |
| "Lines on screen" | "Gate line discontinuity manifesting as horizontal artifact" |
| "Dead pixels" | "TFT switching failure resulting in persistent dark state" |
| "Color looks wrong" | "Chromatic aberration consistent with T-CON gamma LUT corruption" |
| "Dim screen" | "Backlight luminance degradation indicating LED driver current limiting" |
| "Ghost image" | "Residual signal persistence suggesting ion migration in LC layer" |
| "Screen flickers" | "Temporal luminance instability from Vcom drift or PWM frequency interaction" |
| "Burn-in visible" | "Differential organic emitter degradation from static content exposure" |
| "Uneven brightness" | "Spatial luminance non-uniformity attributable to cell gap variation" |
| "Screen cracked" | "Substrate fracture with characteristic radial propagation from impact point" |
| "Touch not working" | "Capacitive sensing failure indicating ITO trace discontinuity" |
| "Colors look faded" | "Reduced color gamut coverage from polarizer spectral degradation" |

---

## Measurement Units & Specifications

| Term | Definition |
|------|------------|
| **cd/m²** | Candela per square meter; brightness (luminance) unit |
| **nit** | Equivalent to cd/m²; common brightness term |
| **Delta E (ΔE)** | Color accuracy metric; <2 is imperceptible |
| **Contrast Ratio** | Ratio of white to black luminance |
| **Response Time** | Pixel transition speed; GtG (gray-to-gray) most relevant |
| **MPRT** | Moving Picture Response Time; effective motion blur |
| **Color Gamut** | Range of reproducible colors (sRGB, P3, Rec.2020) |
| **Bit Depth** | Color precision per channel (8-bit = 256 levels) |
| **Refresh Rate** | Screen updates per second (Hz) |
| **Input Lag** | Delay from signal input to display output |

---

## Quality Standards

| Term | Definition |
|------|------------|
| **Class 0** | Zero pixel defects allowed |
| **Class I** | Limited pixel defects per ISO 13406-2 |
| **Pixel Policy** | Manufacturer's defect tolerance specification |
| **AOI (Automated Optical Inspection)** | Machine vision defect detection |
| **Panel Grading** | Sorting panels by quality (A, B, C grade) |
| **Binning** | Grouping components by measured characteristics |
