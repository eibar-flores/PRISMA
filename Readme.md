![Logo](./prisma/static/logo1.png) 
# PRISMA App

PRISMA is a Jupyter-based app for high-throughput analysis of spectra. The app addresses the need of researchers working in spectroscopy to analyze large numbers of spectra quickly, simply and reproducibly - whether they are code-savvy or not. PRISMA consists of both Python-based code for analysis of spectra and a user-friendly Graphical User Interface (GUI) built with the ipywidgets module. 

# License
* Which License to use?
    * My dependencies: python, numpy, scipy, bqplot, jupyter lab, ipywidgets

# Installation
## Users unfamiliar with Python
* First donwload and install [Miniconda](https://docs.conda.io/en/latest/miniconda.html). Miniconda is a Python distribution (Python + other useful tools) that enables to run Python code, manage and install third-party packages. Miniconda is conveninent to quickly set up everything you need to run Python programs, including PRISMA.
> **Note**: Make sure that Miniconda installs in the default folder `C:\Users\your_user_name\Miniconda3`. This will enable installing PRISMA smoothly.
* Go to the github page of the [PRISMA project](https://github.com/eibfl-dtu/PRISMA)
* Click on the green button *Code* and Download ZIP
* Unzip the file and navigate to the main files
* Double click the *install_environment.bat* file. A terminal (small black window with Matrix-style fonts) will appear and run the commands automatically. Just wait until it closes alone. This file will automatically run the necessary commmands to set up PRISMA.  

Thats it! You are ready to go. To launch the app, double-click on *launch_prisma.bat*. A browser tab will open and load the app.

## Python-savvy users
* TO DO: PACKAGE AND DISTRIBUTE PRISMA IN PIP

# Use
The general workflow to use the app consist of:
1. Select a pipeline, i.e. the type of analysis
2. Load raw data
3. Explore processing parameters
4. Apply optimal parameters to all spectra
5. Export the results  

The results are exported as .csv files ready for plotting.

![General Workflow](./prisma/static/general_workflow.png)



# Code structure
PRIMSA code is built in three separate layers:
1. **The models**: main analysis code operating on spectrum objects, e.g. baseline correction, trimming, peak fitting, etc.  
2. **The views**: reusable GUI elements built with ipywidgets.
3. **The pipelines**: tailored code rendering a group of views together to create an app. The pipelines also control the flux of data between widgets and analysis code.  


The **models** are built around the `spectrum` object, which is instatiated from:  
* a 1D numpy array of indexes (energies, wavenumbers, etc.)
* a 1D numpy array of counts
* a dictionary of metadata  

Every analysis functionality takes as inputs a `spectrum` and parameters, and returns a new 'processed' `spectrum` object as output. All relevant parameters to reproduce the analysis (e.g. input parameters, side-results, etc.) are stored as metadata in the output spectrum.  
![IO](./prisma/static/spectrum_io.png)    

See the API documentation for more details.

# Cite

# Contact
Eibar Flores  
Technical University Denmark  
eibfl@dtu.dk


