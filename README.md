# Characterization of Soft Protons and Energy Loss in XMM-Newton's EPIC MOS Filters

![XMM-Newton Lockman Hole Observation](https://www.esa.int/var/esa/storage/images/esa_multimedia/images/2015/12/the_lockman_hole_in_x-rays/15729661-3-eng-GB/The_Lockman_Hole_in_X-rays.jpg)  
*XMM-Newton observation of the Lockman Hole (Credit: ESA)*

This repository hosts data and analysis for my Bachelor's Thesis in Physics at the University of Pavia. The research characterizes the **variable instrumental background** of the **XMM-Newton** space telescope, focusing on the impact of **soft protons** and their interaction with the EPIC MOS camera filters.

📚 [Thesis Draft (coming soon)](about:blank) | 💻 [Data Analysis Notebook](https://github.com/nikitodos/xmm-newton/blob/main/JupyterNotebook_forDataAnalysis_Backup.ipynb)

## Abstract
Low-energy ("soft") protons (tens of keV to MeV) are a major unpredictable background source for X-ray telescopes in high-Earth orbits (e.g., XMM-Newton, Chandra). These protons are focused by telescope mirrors and cause background flares that can reduce useful observation time by ≤40%. Understanding their origin and interactions is crucial for current missions (XMM, Chandra) and future observatories (ATHENA, SMILE).

This work:
1. Characterizes soft proton spectra using a unique **Lockman Hole** observation in **low-gain mode** (extending energy range to ∼120 keV)
2. Models energy loss through EPIC MOS filters via **SRIM Monte Carlo simulations**
3. Confirms protonic origin of flares and quantifies filter effectiveness

## Repository Structure
```
├── References/               # Key literature and documentation
│   ├── FromDataAnalysisCourse/
│   ├── OlderWorks/
│   └── XMM-Newton/
├── Simulations/              # SRIM simulation data
│   ├── SRIM_AlphasVsFilters/
│   │   ├── DataAnalysis/     # Analyzed results
│   │   └── RawData/          # Raw simulation output
│   └── SRIM_ProtonsVsFilters/
│       ├── DataAnalysis/
│       └── RawData/
└── README.md                 # This overview
```

## Key Components
### 1. SRIM Energy Loss Simulations
**Objective:** Model energy loss ($dE/dx$) of protons/alpha particles through EPIC MOS filters.  
**Parameters:**
- Energy range: 1 keV - 250 keV
- **Thin filter:** 0.16 µm polyimide + 0.04 µm Al
- **Thick filter:** 0.33 µm polypropylene + 0.11 µm Al + 0.045 µm Sn

**Output:** Empirical energy loss models for spectral fitting, essential below 0.5 MeV where Bethe-Bloch fails.

### 2. Observational Data Analysis
**Dataset:** Lockman Hole observation (May 5, 2000)  
**Strategic advantages:**
- Minimal galactic absorption (ideal "soft proton telescope")
- Simultaneous thin (MOS1) + thick (MOS2) filter usage
- Low-gain mode extending energy range to ∼120 keV

**Analysis Pipeline:**
1. **Data processing:** XMM-Newton SAS
2. **Light curve extraction:** Identification of proton flares vs. quiescent periods
3. **Image analysis:** Confirmation of extra-focal flare distribution
4. **Event filtering:** PATTERN 0-12, FLAG==0
5. **Spectral extraction:** Signal/background spectra with GTIs
6. **Diagonal response matrix:** Addresses proton-mirror interaction uncertainties

### Key Findings
- Flares confirmed as **protonic origin** via spectral fitting
- Energy loss models validated for both filters:
  - Constant loss: $C(E) = a(E + \Delta E)^{-\text{b}}$
  - Energy-dependent loss: $C(E) = a(E + \Delta E_c + c \cdot E \cdot e^{-E/E_f})^{-\text{b}}$
- Alpha particle contribution ruled out
- Thick filter shows superior proton mitigation

## How to Use This Repository
1. Access simulation data in `Simulations/` directories
2. Explore analysis procedures in the [Jupyter Notebook](https://github.com/nikitodos/xmm-newton/blob/main/JupyterNotebook_forDataAnalysis_Backup.ipynb)
3. Consult `References/` for background literature
4. Review [thesis draft (coming soon)](about:blank) for methodology details

---

*Repository maintained by Giovanni Nicola D'Aloisio | Last update: August 1st, 2025*
