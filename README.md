# TOPSIS implementation in python for multi-criteria decision making

```
Class project for DATA ANALYSIS AND VISUALISATION 2020 - UCS633 Thapar University, Patiala
Navkiran Singh  

COE17
Roll number: 101703365
```

![](/../screenshots/1.png?raw=true "Optional Title")
## Update: Added windows command line support

Output is a dataframe with 3 columns
 - **Alternatives** serial number
 - Corresponding performance **Score** or closeness to ideal solution
 - **Rank**

## Installation
`pip install topsis_navkiran`

*Note the name has an underscore not a hyphen. If installation gives error or package is not found after installing, install as sudo.*

*Recommended - test it out in a virtual environment.* 

## Upgrade
`pip install topsis_navkiran --upgrade`

## To use via command line
`topsis_navkiran_cli data.csv 25,25,25,25 -+++`

First argument after run.py is filename with .csv extension. The .csv file is assumed to have a structure similar to one provided in topsis_navkiran/data.csv

That is, the .csv file should have a header with column names and first column should only list alternatives and not attribute values.

## To use in .py script
```
from topsis_navkiran import topsis
"""
decision_matrix is 2D numpy array, weights is a 1D array and impacts is a string of the form +-+-- 
where + indicates benefit and - indicates cost
"""
output_dataframe = topsis(decision_matrix,weights,impacts)
```
## Debugging and Exception Handling
> The program has several assert statements which raise errors with helpful description in the following cases:
> - Wrong dimensions of decision matrix (*not* 2D), weights (*not* 1D)
> - Length of weights and impacts don't match 
> - Weights or impacts don't match number of attributes
> - For command line, number of arguments is less than 3 required
> - File extension must be .csv

*Based off on a similar package for TOPSIS in R*
