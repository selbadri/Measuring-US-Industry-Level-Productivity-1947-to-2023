## Description

We combine data from US KLEMS, March 2017 Release (see Jorgenson et al. (2017) [^1]), with BEA-BLS Integrated Industry-Level Production Account for 1947–2016 (see Eldridge et al. (2020) [^2]), and BEA-BLS Integrated Industry-Level Production Account for 1997-2023 (see Gerner et al. (2025) [^3]) to produce industry-level measures of Gross Output (GO), Value Added (VA), Capital (CAP), Labor (LAB), and Intermediate Inputs (II), in Nominal and Real terms. We also provide Quantity Indices for GO, VA, CAP, LAB, and II, and utilize these indices to compute measures of  Total Labor Productivity (LP) and Total Factor Productivity (TFP) for the corresponding time period, following the methodology in US KLEMS, April 2013 Release (see Jorgenson et al. (2012) [^5]). Our data covers the 1997-2023 period and is updated to reflect the annual update to the input-output accounts released on September 26, 2024 available here: https://apps.bea.gov/iTable/?reqid=150&step=2&isuri=1&categories=gdpxind

Users may download the final dataset [EV_production_accounts_1947to2023.xlsx](Output/EV_production_accounts_1947to2023.xlsx) from the [Output/](Output/) folder. Alternatively, if users intend to introduce changes, updates or look deeper into the methodology, we also provide a code. This code takes as input the underlying historical datasets and computes the final dataset using the methodology outlined in the documentation (see [manual.pdf](manual.pdf)). The remainder of this README file explains attribution & license, the structure of the repo and offers instructions on how users can set up a virtual environment to replicate the results.

## Attribution & License

The data and code are available for public use provided that they are appropriately cited:

Elbadri, Selim and Juan I. Vizcaino (2025). "Measuring US Industry-Level Productivity Between 1947-2023" [Data set]. DOI: XXXXXXXX

This repo is open source and available under the MIT License. See the [LICENSE](LICENSE) file for the full text.

## Structure

The repo contains the following folders:

- **[Input/](Input/):** This contains the 3 underlying data files needed to produce industry-level productivity measures. See [manual.pdf](manual.pdf) for a full description and source of each dataset. 
	- [prod_accounts_1947to2014.xlsx](Input/prod_accounts_1947to2014.xlsx). This is the dataset by Jorgenson et al. (2017). 
	- [prod_accounts_1947to2016.xlsx](Input/prod_accounts_1947to2016.xlsx). This is the dataset by Eldridge et al. (2020). 
	- [prod_accounts_1997to2023.xlsx](Input/prod_accounts_1997to2023.xlsx). This is the dataset by Gerner et al. (2025).
- **[Notebooks/](Notebooks/):** This contains the [main.ipynb](Notebooks/main.ipynb) file which, after running, takes the input data files and produces our dataset containing industry-level production accounts and productivity measures.
- **[Output/](Output/):** This is where the output file [EV_production_accounts_1947to2023.xlsx](Output/EV_production_accounts_1947to2023.xlsx) will be saved once the main.ipynb file runs.

Additional files include:

- **[requirements.txt](requirements.txt):** This lists the Python packages used by main.ipynb to produce the output file.
- **[manual.pdf](manual.pdf):** This explains the underlying data sources and methods, following Jorgenson et al. (2007), used to compute industry-level productivity.
- **[LICENSE](LICENSE):** This governs the rules of use for the data and codes in this repo.

## Instructions

After downloading the repo from GitHub, the user should save the repo in a location of their preference. The instructions below assume that the user has installed Python in their machine.

A new virtual environment must be created. The purpose of this virtual environment is to ensure that the user has all the necessary Python packages  to replicate the results. These packages are listed in [requirements.txt](requirements.txt) file found in the repo. The environment can be deleted once the user is finished replicating the results.

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

## References

[^1]: Jorgenson, D. W., Ho, M. S., Samuels, J. D., & Stiroh, K. J. (2007). Industry origins of the American productivity resurgence. Economic Systems Research, 19(3), 229–252.

[^2]: Eldridge, L. P., Garner, C., Howells, T. F., Moyer, B. C., Russell, M., Samuels, J. D., Strassner, E. H., & Wasshausen, D. B. (2020). Toward a BEA–BLS integrated industry‑level production account for 1947–2016. In Measuring economic growth and productivity (pp. 221–249). Elsevier.

[^3]: Garner, C., Harper, J., Russell, M., & Samuels, J. (2025). Integrated BEA–BLS industry‑level production account, 1997–2023: The sources of U.S. economic growth in the aftermath of the COVID‑19 recession (Technical report). Bureau of Economic Analysis & Bureau of Labor Statistics.

[^4]: Jorgenson, D. W., Ho, M. S., & Samuels, J. D. (2017). Educational attainment and the revival of US economic growth. In Education, Skills, and Technical Change: Implications for Future US GDP Growth (pp. 23–60). University of Chicago Press.

[^5]: Jorgenson, D. W., Ho, M. S., & Samuels, J. D. (2012) “A Prototype Industry‐Level Production Account for the United States, 1947‐2010,” Second World KLEMS Conference, Harvard University, August 9, 2012.


















