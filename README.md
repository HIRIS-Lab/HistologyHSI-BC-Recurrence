# Histological-Hyperspectral-Breast Cancer-Recurrence Dataset
This project is intended to provide a basic example of how to load and perform some basic preprocessing for hyperspectral data in ENVI format using Python. The data used in this project corresponds to the Histological Hyperspectral Glioblastoma Dataset.

## Dataset 

This dataset contains 47 histopathological and 677 hyperspectral images from 47 patients diagnosed with breast tumors, together with their clinical data. Out of these patients, 22 had distant recurrence during the 10 years of follow-up after diagnosis. More information about the dataset can be found on:

## Usage

This repository contains the following scripts:
* `main.ipynb`: provide a basic example of how to load and perform some basic preprocessing to hispathological (.mrxs) and hyperspectral (ENVI format) data using Python.
* `overlay_tissue_areas.py`: provide a tutorial on manipulating annotations in GeoJSON format to overlay tissue compartments on a slide image using Python.
## Dependencies

Python script requires:
   - Openslide. Python module for reading whole-slide image formats. https://openslide.org/  
   - Spectral Python (SPy). Python module for hyperspectral image processing. https://www.spectralpython.net
   - Harris, C.R., Millman, K.J., van der Walt, S.J. et al. Array programming with NumPy. Nature 585, 357–362 (2020). https://doi.org/10.1038/s41586-020-2649-2
   - J. D. Hunter, "Matplotlib: A 2D Graphics Environment," in Computing in Science & Engineering, vol. 9, no. 3, pp. 90-95, May-June 2007, doi: 10.1109/MCSE.2007.55.
   - Virtanen, P., Gommers, R., Oliphant, T.E. et al. SciPy 1.0: fundamental algorithms for scientific computing in Python. Nat Methods 17, 261–272 (2020). https://doi.org/10.1038/s41592-019-0686-2


## License

Copyright 2025 Laura Quintana-Quintana, Esther Sauras-Colón, Javier Santana-Nunez, Alessio Fiorin

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
