# 🌡️ Thermal Analysis of SMA and SMB Diodes using ANSYS Icepak

> Simulation-based thermal analysis of SMA and SMB diode packages in ANSYS Icepak — investigating the effect of silicon die size and geometry on junction temperature, heat distribution, and long-term device reliability.

**Lab:** Emerging Devices & System's Lab (EDSL Group & NanoDC Lab)  
**Supervisor:** Prof. Sandip Lashkare, Electrical Engineering, IIT Gandhinagar  
**Presented by:** G. Yashan Kumar, PhD Scholar, Electrical Engineering, IIT Gandhinagar  
**Date:** 13th November 2025

| Member        | Roll No.  |
|---------------|-----------|
| Akhil Soni    | 24110022  |
| Rishit Verma  | 24110298  |

---

## 📌 Motivation

SMA packaged diodes are widely used in power electronics and circuit protection, and experience significant heat generation during surge events. Key concerns driving this study:

- Excessive junction temperature leads to reduced reliability, thermal runaway, and premature device failure
- Silicon die size & geometry directly influence thermal resistance and heat spreading capability
- Understanding how die dimensions and shapes affect temperature distribution is critical for optimizing package design and improving device reliability

**Objective:** To analyze the effect of different silicon die sizes and shapes on the thermal behavior of SMA and SMB packages using ANSYS Icepak.

---

## 🧪 Simulation Setup

**Tool:** ANSYS Icepak 2024 R2  
**Power pulse applied:** 600 W with a 10/1000 μs waveform (per Vishay datasheet)  
**Ambient temperature:** 25°C  

### Material Properties Used

| Material | Conductivity K (W/mK) | Thermal Capacity CP (J/kg K) | Density (kg/m³) |
|---|---|---|---|
| Epoxy Mold Compound | 0.72 | 794 | 2020 |
| Silicon (at 25°C) | 148 | 712 | 2328.9 |
| SnPb Solder | 50 | 150 | 8500 |
| Silver Filled Die Attach | 2.09 | 714 | 3560 |
| CU Lead Frame | 360 | 380 | 8890 |
| FR-4 | 0.35 | 878.6 | 1938 |
| Air | 0.03 | 1007 | 1.16 |

---

## 📦 SMA Package Analysis

### Effect of Die Size (Cuboidal)

Four die sizes were simulated at constant 0.3mm thickness:

| Die Size | Peak Max Temp (°C) | Observation |
|---|---|---|
| 0.8 × 0.8 mm | ~700 | Hotspot highly concentrated, slower cooling |
| 1.2 × 1.2 mm | ~400 | Moderate spread, standard reference case |
| 1.4 × 1.4 mm | ~250 | Better heat spreading |
| 1.65 × 1.65 mm | ~200 | Most uniform distribution |

**Key finding:** Increasing die size leads to more effective and even heat transfer. Smaller dies show high temperatures over a greater relative area, increasing mold breakdown risk over long-term operation. Larger dies heat the lead pad more quickly due to higher surface area, but overall junction temperature is lower.

### Effect of Die Shape (Size-Constant Comparison)

Compared a cuboidal die (1.2 × 1.2 × 0.3 mm) with a cylindrical die of the **same surface area**:

| Property | Cuboidal Die | Cylindrical Die |
|---|---|---|
| Surface Area | 4.32 mm² | 4.32 mm² |
| Face Area | 1.44 mm² | 1.49 mm² |
| Radius | — | 0.693 mm |

**Key finding:** Heat is transferred more uniformly in the cylindrical die due to the absence of corners. The cylinder presents less surface area to surroundings, resulting in reduced heat loss. However, peak temperature is slightly higher due to the smaller exposed face.

---

## 📦 SMB Package Analysis
- Silicon die: **1.5 × 1.5 × 0.3 mm** — larger than SMA, offers better thermal stability
- Same 600W peak pulse (10/1000 μs) applied for direct comparison
- Same hotspot generation pattern observed at the top of the silicon die
- Larger die pad provides greater heat flow path → temperature decreases more quickly

### SMB Die Size Comparison

| Die Size | Peak Max Temp (°C) | Cooling Rate |
|---|---|---|
| 0.8 × 0.8 mm | ~950 | Slowest |
| 1.2 × 1.2 mm | ~400 | Moderate |
| 1.5 × 1.5 mm | ~250 | Fastest |
| Cylinder (equiv. area) | ~300 | Uniform |

---

## ⚖️ SMA vs SMB Diode Comparison

| Parameter | SMA Diode | SMB Diode |
|---|---|---|
| Die Size | 1.2 × 1.2 × 0.3 mm | 1.5 × 1.5 × 0.3 mm |
| Thermal Performance | Higher temperature, less efficient dissipation | Better thermal stability, efficient dissipation |
| Heat Distribution | Concentrated over smaller area | Spreads more uniformly |
| Surface Area Effect | Higher thermal resistance | Lower thermal resistance |
| Cooling Behavior | Slower cooling | Faster cooling due to larger die pad |
| Reliability | Higher overheating risk | More reliable for long-term operation |

**Conclusion:** SMB diodes provide superior thermal performance due to their larger die size and surface area, resulting in better heat dissipation and device reliability.

---
## 📦 Project Files

Download full ANSYS project files here:  
👉 https://github.com/Rishit61933/Thermal-Analysis-of-SMA-and-SMB-Diodes-using-ANSYS-Icepak/releases

---

## 🔮 Future Work

- Calculate quantitative thermal resistances for each configuration
- Determine maximum safe power supply to avoid PCB solder melting
- Extend analysis to 4000W at 8/20 μs waveform
- Investigate forced convection cooling, heat sinks, and thermal vias in PCB
- Explore alternative die attach materials, solders, and mold compounds with higher thermal conductivity

---

## 📚 References

1. [Diodes Inc. — SMA Package Datasheet](https://www.diodes.com)
2. [Vishay — SMB Package Datasheet & Power Pulse Ratings](https://www.vishay.com)
3. ANSYS Icepak 2024 R2 — Thermal Simulation Software
