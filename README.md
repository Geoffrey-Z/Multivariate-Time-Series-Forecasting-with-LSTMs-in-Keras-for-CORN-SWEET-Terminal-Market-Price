# `Multivariate-Time-Series-Forecasting-with-LSTMs-in-Keras-for-CORN-SWEET-Terminal-Market-Price`

This project fulfills the requirements for [UMSL's CS5390 project](https://github.com/badriadhikari/2019-Spring-DL/tree/master/project_guidelines). It implements a sweet corn termical market price forecasting using LSTMs in Keras.

## Report

First run monthly price 

The original report for this project can be viewed [here](https://github.com/Hopding/street-sign-classifier/blob/master/notebooks/report.md).

The update to the original report can be viewed [here](https://github.com/Hopding/street-sign-classifier/blob/master/notebooks/report_update.md).

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




## Datasets
- DATA Sause: [USDA - Fruit and Vegetable - Terminal Market Price - Reports](https://marketnews.usda.gov/mnp/fv-report?commAbr=CORN&rowDisplayMax=25&startIndex=1&repType=termPriceWeekly&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&repTypeChanger=termPriceWeekly&type=termPrice&locChoose=commodity&locAbrfrom=HX&locAbrlength=1&locAbr=&commodityClass=allcommodity&y=15&y=15&y=11&y=11&y=13&y=15&y=14&y=8&y=0&y=9&y=9&y=11&y=7&y=8&y=12&x=32&x=28&x=27&x=52&x=36&x=40&x=40&x=24&x=34&x=50&x=28&x=52&x=25&x=23&x=43&locAbrPass=ALL%7C%7C&refine=false&step3date=true&repDate=01%2F07%2F2017&endDate=12%2F29%2F2018&organic=&environment=&_environment=1&Run=Run)
- Original download file: [terminal prices sweet corn.xlsx](https://github.com/Geoffrey-Z/Multivariate-Time-Series-Forecasting-with-LSTMs-in-Keras-for-CORN-SWEET-Terminal-Market-Price/blob/master/terminal%20prices%20sweet%20corn.xlsx)
- CORN_SWEET_Price_Monthly_Univariate_Forecasting: [BI-COLOR CORN-SWEET MONTHLY PRICE 1998-2018.csv](https://github.com/Geoffrey-Z/Multivariate-Time-Series-Forecasting-with-LSTMs-in-Keras-for-CORN-SWEET-Terminal-Market-Price/blob/master/BI-COLOR%20CORN-SWEET%20MONTHLY%20PRICE%201998-2018.csv)
- CORN_SWEET_Price_Weekly_Univariate_Forecasting: [BI-COLOR CORN-SWEET WEEKLY PRICE 1998-2018.csv](https://github.com/Geoffrey-Z/Multivariate-Time-Series-Forecasting-with-LSTMs-in-Keras-for-CORN-SWEET-Terminal-Market-Price/blob/master/BI-COLOR%20CORN-SWEET%20WEEKLY%20PRICE%201998-2018.csv)
- CORN_SWEET_Price_Weekly_Multivariate_Forecasting: [BI-COLOR, WHITE, YELLOW CORN-SWEET WEEKLY PRICE 1998-2018.csv](https://github.com/Geoffrey-Z/Multivariate-Time-Series-Forecasting-with-LSTMs-in-Keras-for-CORN-SWEET-Terminal-Market-Price/blob/master/BI-COLOR%2C%20WHITE%2C%20YELLOW%20CORN-SWEET%20WEEKLY%20PRICE%201998-2018.csv)
