# README — Codes repository for Master Thesis
**“Decoding four decades of heat stress trends in Lombardy with heat waves and heat stress metrics”**  
Author: *Filippo Bissi*  
Supervisor: *Prof. Maria Antonia Brovelli*  
Academic year: *2024/2025*  
Politecnico di Milano — MSc Geoinformatics Engineering

---

## Overview

This repository contains the full set of Python codes developed and used for the analyses presented in the MSc thesis:  
**“Decoding four decades of heat stress trends in Lombardy with heat waves and heat stress metrics”**.

The aim of the thesis was to investigate the long-term trends of heat waves (HW) and heat stress (HS) conditions in the Lombardy region (Northern Italy), using the **VHR-REA_IT climate reanalysis dataset** (hourly, 2.2 km resolution, 1981–2023, dynamically downscaled from ERA5 by CMCC).

The methodological framework includes:

- Heat wave detection based on location-specific temperature trends  
- Calculation of four HS indices: **Humidex (HU), Wet-Bulb Globe Temperature (WBGT), Universal Thermal Climate Index (UTCI), Lethal Heat Stress Index (LHSI)**  
- Generation of spatial exceedance maps and trends  
- Extraction of statistical descriptors for interpretation of spatial-temporal dynamics of thermal discomfort  
- Visualization outputs as used in the thesis (Chapter 5, Figures 27–29, Tables 6–7)

---

## Structure of the repository

The provided codes are organized by analytical step, reflecting the workflow presented in Chapter 4 of the thesis (“Methodology”) and cited in several parts of the Results section:

- **01_data_extraction.py**  
  Scripts for reading and preparing data from the VHR-REA_IT NetCDF files.

- **02_hw_detection.py**  
  Algorithms for detecting heat waves based on location-specific thresholds.

- **03_hs_indices_calculation.py**  
  Calculation of the four selected HS indices using the daily maximum temperature (Tmax), dew point temperature (TD), and other relevant variables. Thresholds are computed following the methods detailed in Chapter 4.5 and 4.6.

- **04_statistics_trend_analysis.py**  
  Linear regression analysis and calculation of decadal trends in days exceeding HS thresholds (as in Chapter 5.5, Figure 29).

- **05_visualization.py**  
  Scripts for generating the final visual outputs (maps, boxplots, statistical tables), including those presented in the main body of the thesis.

---

## Notes

- The codes are designed for full reproducibility and can be adapted to other regions of Italy using the VHR-REA_IT dataset.  
- The methods are scalable to a national or continental level if ERA5 or similar climate datasets are employed.  
- The full pipeline has been tested on the Lombardy region (1981–2023), with the summer period (June–August) used for HS indices, and the entire year considered for HW analysis.  
- The scripts rely on commonly used Python packages, such as **xarray, pandas, numpy, matplotlib, scipy, tqdm**.

---

## Citation

If you use or adapt this code, please cite:

*Bissi, F. (2025). Decoding four decades of heat stress trends in Lombardy with heat waves and heat stress metrics. MSc Thesis, Politecnico di Milano. Supervisor: Prof. Maria Antonia Brovelli.*

---
