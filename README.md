# FoldEco Error Analysis

## Description

FoldEco is a program for simulating protein folding fates in E. *coli* developed by Evan T. Powers, David L. Powers, and Lila M. Gierasch. The program is detailed in their paper [FoldEco: A Model for Proteostasis in E. coli][1]. None of their code is in this repository. During my work with this program I noticed certain values for Rate and Equilibrium constants for Folding, Misfolding, Aggregation would cause subtle errors. This would make it difficult to do optimizations for these parameters as some optimization algorithms hit on configurations that resulted in an error.

To solve this problem I performed 10,000 simulations and recorded whether or not they resulted in errors. I then trained classifiers and analyzed the data to find patterns in these errors. The first time I tried I got no errors on the upper bounds. To solve this I generated 10,000 more points with larger values and explored the upper bound errors separately.

The analysis is in two jupyter notebooks: `LowErrorFinder.ipynb` and `HighErrorFinder.ipynb`.


## Dependencies

* `jupyter notebook`
* `numpy`
* `collections`
* `scikit-learn`
* `pickle`
* `matplotlib`

## Usage

To look at and tweak the analysis install jupyter notebook with your preferred python package manager (or manually) and run:

`jupyter notebook`

in the directory containing the notebooks. Then read the prompts in the notebooks and tweak and execute desired sections of code.

[1]: http://www.cell.com/cell-reports/abstract/S2211-1247(12)00068-X
