## Description

This README file is intended to give the user instructions on how to replicate the output from the project "Measuring US Productivity Between 1947 and 2023" produced by Selim Elbadri & Juan I. Vizcaino.


Details on the method for productivity measurement and the underlying data sources can be found in the accompanying pdf document.


## Structure

The repo contains the following files:

* **Input:** This contains the 3 underlying data files needed to produce industry-level productivity measures.
* **Notebooks:** This contains the main.ipynb file which, after running, takes the input data files and produces the output file which contains the productivity measurements.
* **Output:** This is where the output file will be saved once the main.ipynb file runs. 
* main.pdf: This contains the description of underlying data sources used as well as the strategy used to produce all variables in the output file. 
* requirements.txt: This lists the Python packages used by main.ipynb to produce the output file. 


## Instructions

After downloading the repo from GitHub, the user should save the repo in a location of their preference. The instructions below assume that the user has installed Python in their machine.

A new virtual environment must be created. The purpose of this virtual environment is to ensure that the user has all the necessary Python packages  to replicate the results. These packages are listed in requirements.txt file found in the repo. The environment can be deleted once the user is finished replicating the results.

To begin, open a terminal at the repository root. If you are using VS Code, use the built-in terminal so that the terminal starts in the repository root. Then, choose one of two options to set up the virtual environment:

Option 1 -- VENV Environment.

Type in the following in the terminal to i) generate a new VENV environment, ii) activate the environment and iii) download necessary Python packages in the new environment:

```
Python -m venv venv

Source venv/bin/active			  **NOTE: Only if LINUX/MAC user

.\venv\Scripts\activate           **NOTE: Only if WINDOWS user

pip install -r requirements.txt
```
If you are using VS code, then select the kernel that is produced by the virtual environment (.venv)

Option 2 -- CONDA Environment.


For Option 2, ensure that Anaconda is downloaded and installed first.Then, type in the following in the terminal to i) generate a new CONDA environment, ii) activate the environment and iii) download necessary Python packages in the new environment:


```
conda create -n replication-env python=3.9  **NOTE: Replace 3.9 with the user's Python version.

conda activate replication-env

pip install -r requirements.txt
```
If you are using VS Code, then select the kernel that is produced by the Conda environment (e.g., replication-env)
























