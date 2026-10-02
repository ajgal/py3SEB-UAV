# py3SEB-UAV

## A Python implementation of the Three-Source Energy Balance (3SEB) model for high-resolution UAV imagery.

The UAV-based 3SEB modeling scheme builds upon both the TSEB model [Norman et al., 1995](https://www.sciencedirect.com/science/article/abs/pii/016819239502265Y) and point-based 3SEB model ([Burchard-Levine et al., 2022a](https://onlinelibrary.wiley.com/doi/abs/10.1111/gcb.16002); [2022b](https://link.springer.com/article/10.1007/s00271-022-00787-x)) frameworks by explicitly separating the ground area into intercrop canopy and soil components, allowing for energy flux partitioning in row crop systems where intercrop vegetation coexists with a primary (e.g., tree or vine) canopy. The 3SEB model incorporates an additional resistance scheme to TSEB’s parallel tree–soil resistance network by adding a third source term for the intercrop canopy. This modified parallel-series scheme allows for intercrop flux contributions to be partitioned at the sub-field scale by allocating radiative and turbulent fluxes associated with the intercrop through an additional resistance network, separate from the primary crop canopy using a contextual image classification approach to separate soil and vegetation pixels. For a more detailed explanation regarding the different 3SEB model formulations developed for high-resolution UAV imagery, please refer to Gal et al., (2026, in prep).

Within the py3SEB-UAV framework, there are three different formulations that can be used to run the model: 
1. **Priestley Taylor (3SEB-PT)**
2. **Dual Temperature (3SEB-2T)**
3. **Triple Temperature (3SEB-3T)**

These formulations differ in how the intercrop canopy and soil fluxes are solved, e.g., the temperature inputs or assumptions used for each source. Refer to Gal et al., (2026, in prep) sections 2.1.1 through 2.1.3 for 3SEB model formulation differences. Please note that this model has not been extensively validated in all cropping systems and climates.

<br>

![3SEB vs. TSEB model overview](input_data/3SEB%20v.%20TSEB%20model%20overview.png)
<br>

### What you'll need:

- [UAV-derived inputs, e.g., thermal and multispectral orthomosaics, canopy height model]
- [Meteorological inputs, e.g., air temperature, wind speed, solar radiation, vapor pressure, etc.]
- [Python] via conda (an environment file is included)

These inputs are needed for running the model without example data. The notebook will run with example data included in the py3SEB-UAV repository.

## Getting started

Run the **`py3SEB-UAV.ipynb`** Jupyter notebook in this repository. To set it up:

1. **Get the code.** Clone the repository (recommended, so you can pull updates):
```
   git clone https://github.com/crop-sensing/py3SEB-UAV.git
```
   Alternatively, download the folder as a ZIP from GitHub. You won't receive updates unless you re-download it.

2. **Create the environment.** From the repository folder (note that you will need to change the file path to your local directory):
```
   cd /path/to/py3seb-uav
   conda env create -f environment.yml
```
or with pip:
```
   cd /path/to/py3seb-uav
   pip install -r requirements.txt
```

3. **Open the notebook** and run `py3SEB-UAV.ipynb`


*Found a bug or have a code issue? Please [open an issue](https://github.com/ajgal/py3SEB-UAV/issues) so I can track it. For other questions, contact Andrew Gal at agal@ucdavis.edu.*
