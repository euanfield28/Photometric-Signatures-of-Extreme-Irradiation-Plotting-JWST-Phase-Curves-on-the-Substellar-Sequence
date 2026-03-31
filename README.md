Year 4 Astrophysics Project: Exoplanet & Brown Dwarf Colour-Magnitude Diagrams

Overview
This repository contains the data and data processing pipelines for my final year astrophysics project. The project compares the thermal emission of two highly irradiated substellar objects (WASP-121b and PSR J2322–2650b) against theoretical brown dwarf atmospheric models and an empirical brown dwarf sequence.

The code calculates synthetic photometry from Sonora Bobcat models and extracts observed photometry from phase curve data to construct Colour-Magnitude Diagrams (CMDs). It also uses Markov Chain Monte Carlo (MCMC) methods to fit polynomial tracks to empirical brown dwarf data.

Repository Structure

data/

    empirical/: Contains the UltracoolSheet data and Vega reference spectra. Also table containing new polynomial coefficients as well as Dupuy et al. 2012 values.

    filters/: Contains the transmission profiles for JWST, Spitzer, and 2MASS bands (.dat files).

    models/: Contains the Sonora Bobcat spectra, calculated synthetic photometry and mass-age evolutionary tracks.

    phase_curves/: Contains the observational data files (.npz and .fits) for WASP-121b and PSR J2322–2650b. Also contains their binned phase-curve synthetic photometry.

scripts/

    FYP Main Code.ipynb: The main pipeline. This notebook contains the classes to integrate spectra through filter profiles, process the exoplanet phase curves, and generate the comparative CMD plots.

    MCMC empirical sequence.ipynb: This notebook handles the empirical brown dwarf sequence. It runs an MCMC sampler (emcee) to find the optimal polynomial fits for different photometric bands and plots the resulting posteriors.

plots/

    plots in report/: all figures that are in the report
    
    complete plots not used in report/: Completed plots that I decided not to include in my report.

    draft PSR J2322-2650b phase curves/: large set of phase curves that haven't been polished for the psr companion

    WASP-121b and PSR J2322 2650b phase curves/: large set of wasp-121b and psr J2322-2650b phase curves in JWST NIRCam filters.
    
    Directory where the scripts automatically save the output PDF figures.

requirements.txt: A list of all required Python packages.

How to Run

    Clone this repository to your local machine.

    Ensure you have the required packages installed by running pip install -r requirements.txt.

    Open the notebooks inside the scripts/ folder using Jupyter.

    Run the cells sequentially. The code uses relative paths, so it automatically locates the necessary files in the data/ folder and saves the output figures directly into the plots/ folder.
