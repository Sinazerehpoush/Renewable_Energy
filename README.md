<div align="center">

# Green Data Center Polygeneration System Design & Feasibility
### Hybrid Solar PV, Wind, BESS, Cascaded Thermal Recovery & Seawater Desalination

[![Institution - Sharif University of Technology](https://img.shields.io/badge/Sharif_University_of_Technology-Department_of_Mechanical_Engineering-003366?style=for-the-badge&logo=googlescholar&logoColor=white)](http://mech.sharif.edu/)
[![Domain - Renewable Polygeneration](https://img.shields.io/badge/Systems-Polygeneration_%7C_Net--Positive-green?style=for-the-badge)](#project-overview)
[![Documentation - LaTeX](https://img.shields.io/badge/Typeset-LaTeX-008080?style=for-the-badge&logo=latex&logoColor=white)](./report/Renewable_Energy.tex)
[![Standard - Tier III Data Center](https://img.shields.io/badge/Standard-Uptime_Tier_III-darkred?style=for-the-badge)](#baseline-facility-specifications)

<p align="center">
  <b>A comprehensive techno-economic design and thermodynamic feasibility study for an off-grid, net-positive green data center in Chabahar, Iran.</b>
</p>

[View Full Report (PDF)](./Renewable_Energy.pdf) 

</div>

---

## Table of Contents
- [Project Overview](#project-overview)
- [Deployment Site Climatic Assessment (Chabahar)](#deployment-site-climatic-assessment-chabahar)
- [Baseline Facility Specifications](#baseline-facility-specifications)
- [Renewable Power Generation & Storage](#renewable-power-generation--storage)
  - [Solar Photovoltaic Plant (8.0 MWp)](#1-solar-photovoltaic-plant-80-mwp)
  - [Wind Power Plant (4.0 MW)](#2-wind-power-plant-40-mw)
  - [Battery Energy Storage System (28.0 MWh BESS)](#3-battery-energy-storage-system-280-mwh-bess)
- [Cascaded Waste Heat Recovery & Polygeneration](#cascaded-waste-heat-recovery--polygeneration)
  - [Organic Rankine Cycle (ORC)](#1-organic-rankine-cycle-orc-power-recovery)
  - [Absorption Chilling System](#2-single-effect-absorption-chilling)
  - [Thermal Desalination (MED-TVC) & Marine Rejection](#3-thermal-desalination-med-tvc--marine-rejection)
- [Facility Energy Balance & Water Sustainability](#facility-energy-balance--water-sustainability)
- [Capital & Operational Expenditure (CapEx / OpEx)](#capital--operational-expenditure-capex--opex)
- [Techno-Economic Appraisal & Policy Sensitivity](#techno-economic-appraisal--policy-sensitivity)
- [Conceptual Layout & System Architecture](#conceptual-layout--system-architecture)
- [Repository Structure](#repository-structure)

---

## Project Overview

Modern high-density data centers represent energy-intensive nodes that consume up to 2.0% of global electricity generation while rejecting immense quantities of high-grade waste heat into the environment via water-intensive cooling towers.

This project engineers a fully self-sustained, **Net-Positive Green Data Center** located in the coastal city of **Chabahar, Iran** ($25.29^\circ\text{N}$, $60.64^\circ\text{E}$):
* **100% Renewable Power Supply:** Synergistic solar PV and wind generation backed by containerized LFP battery storage.
* **Cascaded Waste Heat Polygeneration:** Direct-to-chip liquid cooling heat ($2{,}000\text{ kW}_{th}$ at $55\text{--}60^\circ\text{C}$) sequentially driving secondary power recovery (ORC), thermally activated cooling (Absorption Chiller), and on-site seawater desalination (MED-TVC).
* **Zero Municipal Water Footprint:** Complete elimination of external freshwater reliance, saving $70{,}000\text{ m}^3/\text{year}$ of water relative to evaporative cooling infrastructure.

---

## Deployment Site Climatic Assessment (Chabahar)

Chabahar provides exceptional solar irradiance and coastal monsoon wind regimes that exhibit strong diurnal and seasonal complementarity:

| Climatic Parameter | Annual Value | Engineering Significance |
| :--- | :---: | :--- |
| **Global Horizontal Irradiance (GHI)** | **$5.87\text{ kWh/m}^2/\text{day}$** | >300 cloudless days/year; peak irradiance during midday hours |
| **Direct Normal Irradiance (DNI)** | **$5.24\text{ kWh/m}^2/\text{day}$** | High beam fraction suitable for high-efficiency bifacial tracking |
| **Mean Annual Ambient Temperature** | **$28^\circ\text{C}$** | Maximum ambient temperatures reach $34^\circ\text{C}$ in summer (Tir) |
| **Mean Wind Speed ($100\text{ m}$ Hub Height)** | **$6.5\text{ m/s}$** | Sustained coastal sea-breezes and monsoon currents |
| **Wind Power Density** | **$280\text{ W/m}^2$** | Class IIIA regime; peak wind velocity from Khordad to Shahrivar |
| **Weibull Shape ($k$) / Scale ($c$)** | **$k = 2.1$, $c = 7.3\text{ m/s}$** | Favorable wind velocity distribution for utility-scale conversion |

---

## Baseline Facility Specifications

The power distribution and IT thermal envelope conform to **Uptime Institute Tier III** continuous-availability requirements:

| Facility Parameter | Design Value | Units / Standard |
| :--- | :---: | :--- |
| **Continuous IT Compute Load ($P_{load}$)** | **2.0** | MW continuous |
| **Server Rack Topology** | **100 Racks** ($20\text{ kW/rack}$) | High-density compute racks |
| **Continuous Facility Auxiliary Load** | **269.75** | kW (pumps, desalination, lighting, EMS) |
| **Aggregate Facility Electrical Draw** | **2,269.75** | kW continuous |
| **Internal Power Distribution** | **400 VAC, 50 Hz** | 3-Phase distribution busbars |
| **Target Availability Rating** | **99.982%** | Tier III concurrently maintainable |

---

## Renewable Power Generation & Storage

### 1. Solar Photovoltaic Plant (8.0 MWp)
* **PV Architecture:** 14,700 units of **545 Wp Mono-PERC Bifacial modules** (conversion efficiency 21.3%) with single-axis horizontal tracking.
* **Footprint & Layout:** Active panel area of $37{,}970\text{ m}^2$; with a Ground Cover Ratio ($GCR = 0.35$), total land footprint is **10.7 hectares**.
* **Central Inverters:** $4 \times 2.5\text{ MW}$ transformer-coupled inverter blocks.
* **Annual Output:** **$19.23\text{ GWh/year}$** (accounting for +22% tracker and +15% rear bifacial gain).

### 2. Wind Power Plant (4.0 MW)
* **Turbine Technology:** 2 units of **Vestas V110-2.0 MW** Class IIIA turbines ($110\text{ m}$ rotor diameter, $95\text{ m}$ hub height, cut-in $3.0\text{ m/s}$).
* **Micrositing & Buffer:** $4D$ crosswind ($440\text{ m}$) $\times$ $7D$ downwind ($770\text{ m}$) spacing to eliminate wake aerodynamic losses, requiring a total buffer footprint of **67.8 hectares** (physical foundation footprint $<1\%$).
* **Annual Output:** **$11.21\text{ GWh/year}$** at an annual Capacity Factor (CF) of **32%**.

### 3. Battery Energy Storage System (28.0 MWh BESS)
* **Chemistry:** Lithium Iron Phosphate (**LFP** / $\text{LiFePO}_4$) selected for extreme thermal safety ($>6{,}000$ cycle life).
* **Sizing Basis:** Sized to bridge a 6-hour calm night outage ($13{,}800\text{ kWh}$ net), derated for 80% Depth of Discharge (DoD), 92% AC-AC roundtrip efficiency, and 1.15 cell aging buffer.
* **Packaging:** 20 standard 40-ft High-Cube ISO containers ($1.4\text{ MWh}$ per container), coupled to **7.0 MW bi-directional PCS inverters** occupying 0.15 ha.

---

## Cascaded Waste Heat Recovery & Polygeneration

The $2{,}000\text{ kW}_{th}$ waste heat extracted by direct-to-chip liquid cooling manifolds at $55\text{--}60^\circ\text{C}$ is sequentially cascaded through three functional thermodynamic processes:

```text
[IT Rack Waste Heat: 2,000 kWth @ 55-60°C]
                  │
                  ▼
┌────────────────────────────────────────────────────────┐
│  Stage 1: Low-Temperature ORC Power Skid (500 kWth)     │ ──► [50 kWe Net Electricity]
└────────────────────────────────────────────────────────┘
                  │ Residual: 1,500 kWth
                  ▼
┌────────────────────────────────────────────────────────┐
│  Stage 2: Single-Effect Absorption Chiller (1,200 kWth)│ ──► [900 kWc Chilled Water @ 7°C]
└────────────────────────────────────────────────────────┘
                  │ Residual: 300 kWth
                  ▼
┌────────────────────────────────────────────────────────┐
│  Stage 3: MED-TVC Desalination Unit (300 kWth)         │ ──► [150 m³/day Distillate Water]
└────────────────────────────────────────────────────────┘
                  │ Residual: 200 kWth
                  ▼
┌────────────────────────────────────────────────────────┐
│  Stage 4: Seawater Terminal Plate Heat Exchanger       │ ──► [Safe Marine Discharge, ΔT < 5°C]
└────────────────────────────────────────────────────────┘
