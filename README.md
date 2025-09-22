# Measuring US Industry-Level Productivity Between 1947 and 2023.

## Description

We combine data from **US KLEMS (March 2017 Release)** [^1], the **BEA–BLS Integrated Industry-Level Production Accounts** for 1947–2016 [^2], and the **BEA–BLS Integrated Industry-Level Production Accounts** for 44 industries (1947–2023) and 63 industries (1963–2023) [^3]. From these sources, we construct industry-level measures of **Gross Output (GO)**, **Value Added (VA)**, **Capital (CAP)**, **Labor (LAB)**, and **Intermediate Inputs (II)**, in both nominal and real terms. We also provide quantity indices for **GO**, **VA**, **CAP**, **LAB**, and **II**, and compute measures of **Labor Productivity (LP)** and **Total Factor Productivity (TFP)** for the corresponding time periods, following the methodology in *US KLEMS, April 2013 Release* [^5].  

Our dataset reflects the latest version of the [Industry Economic Accounts Data](https://www.bea.gov/industry/input-output-accounts-data) and can be updated annually to incorporate new BEA releases.

Users may download the final dataset, [EV_production_accounts_1947to2023.xlsx](Output/EV_production_accounts_1947to2023.xlsx), from the [Output/](Output/) folder. Alternatively, for users who wish to modify or update the data, or explore the methodology in more depth, we provide Python code in the form of a Jupyter Notebook. The notebook takes the underlying historical datasets as input and reproduces the final dataset using the documented methodology (see [manual.pdf](manual.pdf)).  

The remainder of this README explains:  
- Attribution & licensing  
- The structure of the repository  
- Instructions for setting up a virtual environment to replicate the results  

---
## Attribution & License

The data and code are available for public use, provided that they are appropriately cited:

Elbadri, Selim, and Juan I. Vizcaino (2025). *Measuring US Industry-Level Productivity Between 1947 and 2023* [Data set]. Zenodo. [https://doi.org/10.5281/zenodo.17163103](https://doi.org/10.5281/zenodo.17163103). For BibTeX users, a [EV_Citation.bib](EV_Citation.bib) file is provided in the repository.

This repository is open source and distributed under the MIT License. See the [LICENSE](LICENSE) file for the full text.

---
## Repository Structure

The repository contains the following folders:

- **[Input/](Input/):** Contains the three underlying data files needed to produce industry-level productivity measures (see [manual.pdf](manual.pdf) for full details and sources):
  - [usa_wk_mar_2017.xlsx](Input/usa_wk_mar_2017.xlsx): US KLEMS, March 2017 Release (see Jorgenson et al. (2017)[^1]).  
  - [industry-production-account-experimental.xlsx](Input/industry-production-account-experimental.xlsx): BEA–BLS Integrated Industry-Level Production Account for 1947–2016 (see Eldridge et al. (2020)[^2]).  
  - [industry-production-account-capital.xlsx](Input/industry-production-account-capital.xlsx): BEA–BLS Integrated Industry-Level Production Account (see Gerner et al. (2025)[^3]).  

- **[Notebooks/](Notebooks/):** Contains [main.ipynb](Notebooks/main.ipynb), which processes the input data files to generate the dataset with industry-level production accounts and productivity measures.  

- **[Output/](Output/):** Contains the output file [EV_production_accounts_1947to2023.xlsx](Output/EV_production_accounts_1947to2023.xlsx), produced after running `main.ipynb`.  

Additional files include:

- **[requirements.txt](requirements.txt):** Lists the Python packages required to run `main.ipynb` and reproduce the output.  
- **[manual.pdf](manual.pdf):** Documents the underlying data sources and methodology (following Jorgenson et al. (2007)) used to compute industry-level productivity.  
- **[LICENSE](LICENSE):** Specifies the terms of use for the data and code in this repository.  

---
## Instructions

After downloading the repository from GitHub, save it in a location of your choice. These instructions assume that Python is already installed on your machine.

To replicate the results, you must create a new **virtual environment**. This ensures that all necessary Python packages (listed in [requirements.txt](requirements.txt)) are installed without interfering with your system-wide configuration. The environment can be deleted once replication is complete.

Open a terminal at the repository root.  
- If you are using **VS Code**, use the built-in terminal so that it starts in the repository root.  
- After creating the environment, make sure to select the corresponding kernel in VS Code.  

You can set up the environment in one of two ways:

---

### Option 1: VENV Environment

Run the following commands in the terminal:

```bash
python -m venv venv

# Activate the environment
source venv/bin/activate        # Linux/Mac
.\venv\Scripts\activate         # Windows

# Install required packages
pip install -r requirements.txt
```

### Option 2: Conda Environment

If you prefer to use Conda, first ensure that **Anaconda** (or Miniconda) is installed. Then, open the **Anaconda Prompt** and run the following commands to:  
1. Navigate to the project folder  
2. Create a new Conda environment  
3. Activate the environment  
4. Install the required Python packages  

```bash
cd path\to\your\project           			 # Replace with the actual path to the repository

conda create -n replication-env python=3.9   # Replace 3.9 with your preferred Python version

conda activate replication-env

pip install -r requirements.txt
```

### Next Step: Running the Notebook

Once the virtual environment has been set up (using either VENV or Conda), you are ready to run the Jupyter Notebook that generates the dataset.

1. Launch Jupyter Lab or Jupyter Notebook from within the activated environment:

```bash
jupyter lab
# or
jupyter notebook
```

2. Open [Notebooks/main.ipynb](Notebooks/main.ipynb).  

3. Run all cells in the notebook. This will:

- Read the input data from the [Input/](Input/) folder  
- Apply the methodology described in [manual.pdf](manual.pdf)  
- Generate the final dataset [EV_production_accounts_1947to2023.xlsx](Output/EV_production_accounts_1947to2023.xlsx) in the [Output/](Output/) folder  

In VS Code, you can also open `main.ipynb` directly and select the kernel corresponding to your virtual environment (either `.venv` or `replication-env`).

---
## References

[^1]: *Jorgenson, D. W., Ho, M. S., Samuels, J. D., & Stiroh, K. J. (2007). Industry origins of the American productivity resurgence. Economic Systems Research, 19(3), 229–252.*  

[^2]: *Eldridge, L. P., Garner, C., Howells, T. F., Moyer, B. C., Russell, M., Samuels, J. D., Strassner, E. H., & Wasshausen, D. B. (2020). Toward a BEA–BLS integrated industry-level production account for 1947–2016. In Measuring economic growth and productivity (pp. 221–249). Elsevier.*  

[^3]: *Garner, C., Harper, J., Russell, M., & Samuels, J. (2025). Integrated BEA–BLS industry-level production account, 1997–2023: The sources of U.S. economic growth in the aftermath of the COVID-19 recession (Technical report). Bureau of Economic Analysis & Bureau of Labor Statistics.*  

[^4]: *Jorgenson, D. W., Ho, M. S., & Samuels, J. D. (2017). Educational attainment and the revival of US economic growth. In Education, Skills, and Technical Change: Implications for Future US GDP Growth (pp. 23–60). University of Chicago Press.*  

[^5]: *Jorgenson, D. W., Ho, M. S., & Samuels, J. D. (2012). A prototype industry-level production account for the United States, 1947-2010. Paper presented at the Second World KLEMS Conference, Harvard University, August 9, 2012.*

