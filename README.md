# Histological-Hyperspectral-Breast Cancer-Recurrence-Dataset
This project is intended to provide a basic example of how to load and perform some basic preprocessing for hyperspectral data in ENVI format using Python and MATLAB. The data used in this project corresponds to the Histological Hyperspectral Glioblastoma Dataset ([HistologyHSI-BRCA-Recurrence](https://doi.org/10.1038/s41597-024-03510-x)).

## Dataset 

This dataset contains 47 histopathological and 677 hyperspectral images from 47 patients diagnosed with breast tumors, together with their clinical data. Out of these patients, 22 had distant recurrence during the 10 years of follow-up after diagnosis. More information about the dataset can be found on:

- [HistologyHSI-BRCA-Recurrence Dataset in TCIA](https://doi.org/10.7937/Z1K6-VD17): Ortega, S., Fabelo, H., Quintana-Quintana, L., Leon, R., Plaza, M.d.l.L., Camacho, R., & Callico, G. M. (2025). Recurrent Breast Cancer: Histopathological and Hyperspectral Images Database (HistologyHSI-BRCA Recurrence Database) (Version 1) [Data set]. The Cancer Imaging Archive. https://doi.org/10.
- [Data descriptor in Scientific Data](https://doi.org/10.1038/s41597-024-03510-x): Ortega, S., Quintana-Quintana, L., Leon, R. et al. Recurrent Breast Cancer: Histopathological and Hyperspectral Images Database (HistologyHSI-BRCA Recurrence Database). Sci Data 11, 681 (2025). https://doi.org/10.1038/s41597-024-03510-x

## Usage

This repository contains the following scripts:
* `main.ipynb`: provide an basic example of how to load and perform some basic preprocessing to hyperspectral data in ENVI format using Python.
* `main.mlx`: provide an basic example of how to load and perform some basic preprocessing to hyperspectral data in ENVI format using MATLAB.

## Dependencies

1. MATLAB script requires:
   - Image Processing Toolbox Hyperspectral Imaging Library
2. Python script rquires:
   - Spectral Python (SPy). Python module for hyperspectral image processing. https://www.spectralpython.net
   - Harris, C.R., Millman, K.J., van der Walt, S.J. et al. Array programming with NumPy. Nature 585, 357–362 (2020). https://doi.org/10.1038/s41586-020-2649-2
   - J. D. Hunter, "Matplotlib: A 2D Graphics Environment," in Computing in Science & Engineering, vol. 9, no. 3, pp. 90-95, May-June 2007, doi: 10.1109/MCSE.2007.55.
   - Virtanen, P., Gommers, R., Oliphant, T.E. et al. SciPy 1.0: fundamental algorithms for scientific computing in Python. Nat Methods 17, 261–272 (2020). https://doi.org/10.1038/s41592-019-0686-2

## Documentation

See the latest documentation at the Data descriptor, published in Scientific Data: https://doi.org/10.1038/s41597-024-03510-x

## License

Copyright 2023 Samuel Ortega, Laura Quintana-Quintana, Raquel Leon, Himar Fabelo

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
