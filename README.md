# CODES REPOSITORY FOR THE MASTER THESIS:
**“Heat wave and heat stress space-time pattern analysis in Lombardy using climate reanalysis data”**  
Author: *Filippo Bissi*  
Advisor: *Prof. Maria Antonia Brovelli*  
Co-Advisor: *Dr. Alberto Vavassori and Matej Žgela, PhD Candidate*  
Academic year: *2024/2025*  
Politecnico di Milano — MSc Geoinformatics Engineering

---

## Overview

This repository contains the full set of Python codes developed and used for the analyses presented in the MSc thesis:  
**“Heat wave and heat stress space-time pattern analysis in Lombardy using climate reanalysis data”**.

The aim of the thesis was to investigate the long-term trends of heat waves (HW) and heat stress (HS) conditions in the Lombardy region (Northern Italy), using the **VHR-REA_IT climate reanalysis dataset** (hourly, 2.2 km resolution, 1981–2023, dynamically downscaled from ERA5 by CMCC).

The methodological framework includes:

- Heat wave detection based on location-specific temperature trends  
- Calculation of four HS indices: **Humidex (HU), Wet-Bulb Globe Temperature (WBGT), Universal Thermal Climate Index (UTCI), Lethal Heat Stress Index (LHSI)**  
- Generation of spatial exceedance maps and trends  
- Extraction of statistical descriptors for interpretation of spatial-temporal dynamics of thermal discomfort  
- Visualization outputs as used in the thesis (Chapter 5 "Results & conclusions", Figures 27–29, Tables 6–7)

---

## Structure of the repository

The provided codes are organized by analytical step, reflecting the workflow presented in Chapter 4 of the thesis (“Methodology”) and cited in several parts of the "Results" chapter 5 :

- **00_data_download.py**  
  Scripts for downloading and organizing the VHR-REA_IT NetCDF files, using the cdsapi Python library.

- **01_data_exploration.py**  
  Initial data analysis of temperatures, trends, spatialization.

- **02_pixelwise_threshods_extraction.py**  
  Algorithms for calculating pixelwise climatological thresholds based on the historical distribution of daily maximum temperatures. The resulting thresholds are used to detect heat wave events and to compute exceedances for heat stress indices.

- **03_heatwaves_identification_advanced.py**  
  Scripts for identifying heat wave events based on pixelwise climatological thresholds, applying the definition of HWs as periods of ≥ 3 consecutive days above threshold. The script generates event-based datasets used for statistical analysis and interpretation of HW frequency, duration, and intensity.

- **04_specific_events_analysis.py**  
  Scripts for selecting and analyzing specific heat wave events. The script extracts the daily time series for selected dates and calculates spatial statistics (mean, median, percentiles) for each HS index, generating the comparative maps and analyses presented in Chapter 5.4.

- **05_entire_period_analysis.py**  
  Scripts for extracting the average frequency of days exceeding HS thresholds across four decades and performing a detailed regression-based trend analysis. The script generates pixelwise decadal trends, smoothed spatial patterns, and comprehensive statistical summaries used to characterize the evolution of hazardous heat stress conditions (Chapter 5.5, Table 7, Figure 29). The procedure combines multi-decade exceedance aggregation with linear modeling to support an advanced understanding of temporal and spatial dynamics.

---

## Notes

- The codes are designed for full reproducibility and can be adapted to other regions of Italy using the VHR-REA_IT dataset.  
- The methods are scalable to a national or continental level if ERA5 or similar climate datasets are employed.  
- The full pipeline has been tested on the Lombardy region (1981–2023), with the spring / summer period (April-September) used for HS indices, and the entire year considered for HW analysis.  
- The scripts rely on commonly used Python packages, such as **xarray, pandas, numpy, matplotlib, scipy, tqdm**.

---

## Citation

If you use or adapt this code, please cite:

*Bissi, F. (2025). Decoding four decades of heat stress trends in Lombardy with heat waves and heat stress metrics. MSc Thesis, Politecnico di Milano. Supervisor: Prof. Maria Antonia Brovelli.*

This repository is shared for academic and research purposes.
Feel free to reuse and adapt the code with proper citation (see above)!
Your questions or feedback are helpful, glad to answer you: filippo_bissi@outlook.it.
Pull requests are welcome!

---
