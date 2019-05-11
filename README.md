# `Multivariate-Time-Series-Forecasting-with-LSTMs-in-Keras-for-CORN-SWEET-Terminal-Market-Price`
street-sign-classifier
This project fulfills the requirements for UMSL's CS5390 project. It implements a street sign classifier using deep learning.

Report
The original report for this project can be viewed here.

The update to the original report can be viewed here.

Prerequisites
This project uses conda for package management. If you do not already have conda installed on your system, you can get it by installing Miniconda or Anaconda.
This project is written in Python 3.6. Make sure you have this version of Python (or greater) installed on your system.
Quick Start
Note: This section only works for Mac and Linux machines. If you are on Windows, you can try using the WSL. Otherwise, use the Manual Start section instead.

To automatically download the data and dependencies and run the Jupyter notebooks for this project, run the following command:

./start
This should open the Jupyter file explorer in a new browser tab. Once it does, try navigating to the notebooks/ directory. From here, you can open and run the EDA (eda.ipynb) or Keras model (models/*.ipynb) notebooks.

Manual Start
Download image dataset:
./download_data.py
Create the virtual environment:
conda env create -f environment.yml
Start the virtual environment:
conda activate street-sign-classifier
Start the Jupyter notebook:
jupyter notebook
Command Reference
Download Data & Dependencies, and Start Jupyter

./start # Only works on Mac and Linux machines
Download Datasets to ./data

./download_data.py
Start Jupyter

jupyter notebook
Generate PDF Reports

./report
Conda Virtual Environment Commands

# Create the environment
