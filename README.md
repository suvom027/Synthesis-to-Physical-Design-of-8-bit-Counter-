#  Synthesis to Physical Design of 8-bit Counter (RTL to GDSII Flow)

This repository documents the **Synthesis-to-Physical-Design flow** of an 8-bit counter implemented in **45nm CMOS technology**.  
The process includes **synthesis, floorplanning, placement, clock tree synthesis (CTS), routing, and verification**, leading to a **fabrication-ready GDSII layout**.

---

##  Project Overview

The project focuses on the **back-end stages** of VLSI design — starting from a synthesized gate-level netlist to the final physical layout.  
The counter design was chosen for its simplicity, making it ideal to demonstrate the complete process of timing optimization, placement, routing, and DRC/LVS verification.

---

##  Design Flow Summary

| Stage | Tool Used | Description |
|--------|------------|-------------|
| **Logic Synthesis** | Cadence Genus | Converts RTL code to gate-level netlist using 45nm standard cell library |
| **Floorplanning** | Cadence Innovus | Defines the chip core area, IO placement, and power planning |
| **Placement** | Cadence Innovus | Places standard cells efficiently to meet timing and area goals |
| **Clock Tree Synthesis (CTS)** | Cadence Innovus | Distributes the clock signal with minimal skew and delay |
| **Routing** | Cadence Innovus | Connects all standard cells according to netlist connectivity |
| **Verification (DRC/LVS)** | Innovus / Calibre | Ensures geometry and connectivity correctness of the final layout |

---

##  Synthesis Results

The synthesis was performed using **Cadence Genus** with a **45nm standard cell library**.  
The RTL description was successfully converted into a **gate-level netlist**, meeting all timing and area requirements.

| Metric | Value |
|---------|--------|
| **Worst Negative Slack (WNS)** | 7657 ps |
| **Total Cell Area** | 775 |
| **Dynamic Power** | 10378.253 nW |
| **Leakage Power** | 23.165 nW |

<p align="center">
  <img src="report/pic/Synthesis.png" width="750" alt="Gate-Level Schematic after Synthesis">
</p>

**Analysis:**  
The synthesis results show a clean design with no timing violations.  
The counter achieved low power consumption and compact cell area, suitable for small-scale integration.

---

##  Physical Design Implementation

The **Physical Design** was carried out in **Cadence Innovus**, following the standard digital ASIC back-end flow.

### 🔹 Floorplanning
- Defined core and die area.
- Allocated power and ground rings.
- Assigned IO and standard cell placement regions.

### 🔹 Placement
- All standard cells were placed based on timing and congestion analysis.
- Achieved an optimized layout with balanced wire length.

### 🔹 Clock Tree Synthesis (CTS)
- Constructed a balanced clock tree to minimize skew.
- Verified clock latency within acceptable limits.

### 🔹 Routing
- Global and detailed routing completed with no open or short circuits.
- Design Rule Check (DRC) passed successfully.

<p align="center">
  <img src="report/pic/phydesign.png" width="800" alt="Physical Design Layout (Floorplan, Placement, Routing)">
</p>

**Observation:**  
All stages — from floorplanning to routing — were completed successfully.  
No congestion or overlap was observed, and post-route timing met the design specifications.

---

##  Verification

Verification was performed to ensure the final layout was **error-free and fabrication-ready**.

### 🔸 Geometry Verification (DRC)
All geometrical design rules were verified and passed successfully.

<p align="center">
  <img src="report/pic/Geometry Verification.png" width="700" alt="DRC Clean Verification">
</p>

### 🔸 Connectivity Verification (LVS)
The layout and schematic were compared to confirm logical connectivity consistency.

<p align="center">
  <img src="report/pic/Connectivity Verification.png" width="700" alt="LVS Clean Verification">
</p>

**Verification Summary:**
| Check | Result |
|--------|---------|
| **Design Rule Check (DRC)** | 0 Violations |
| **Layout vs Schematic (LVS)** | Clean Match |

Both DRC and LVS were clean, confirming that the physical layout correctly represents the synthesized circuit.

---

##  Conclusion

The **Synthesis to Physical Design** implementation of an 8-bit counter was completed successfully using **Cadence Genus and Innovus** tools.  
All steps — from synthesis to layout verification — were performed with **zero violations**.  
The design achieved:
- Clean geometry and connectivity verification (DRC/LVS passed)
- Compact layout with minimal area and power consumption
- Fabrication-ready GDSII output file  

This project provided practical insight into the **complete back-end ASIC design process**, reinforcing the understanding of physical implementation in **45nm VLSI technology**.



---

## 👨‍💻 Author

**Suvom Karmakar**  
Department of Electrical and Electronic Engineering  
United International University (UIU)  
**Student ID:** 021 221 027  

---
