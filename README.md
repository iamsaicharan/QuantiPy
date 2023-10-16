# XQuantiPy

xquantipy is a python module for downloading macro economic data & stock data with the modules included for the analysis.

## Installation

Install `xquantipy` using `pip`:

```bash
pip install xquantipy
```

### Requirements

* matplotlib==3.8.0
* pandas==2.1.1
* python_dateutil==2.8.2
* Requests==2.31.0
* seaborn==0.13.0
* yfinance==0.2.29

## Get Started

### macro module

The `Macro` module helps to get the macro economic data:

```python
from xquantipy.macro.macro import Macro

USA = Macro("USA")
IND = Macro("IND")

# Get GDP data for USA with default period of 10 Years
USA_GDP = USA.get_macros(filters=['GDP'])
# Get GDP Growth Rate & GNI for USA with period of 15 Years
USA_GDP_GROWTH_GNI = USA.get_macros(filters=['GDP_GROWTH','GNI'], period='15Y')

# Get GDP data for India with default period of 10 Years
IND_GDP = IND.get_macros(filters=['GDP'])
# Get GDP Growth Rate & GNI for India with period of 15 Years
IND_GDP_GROWTH = IND.get_macros(filters=['GDP_GROWTH', 'GNI'], period='15Y')
```

The `Analysis` module helps to get the macro economic analysis and visualization:

```python
from xquantipy.macro.analysis import Analysis

USA = Macro("USA")
IND = Macro("IND")
Countries = MAnalysis([USA, IND])

# Get merged GDP data for the Countries
GDP_COMPARE_DF = Countries.get_merged_macro('GDP')
# Visualize GDP data for the Countries
Countries.visualize("GDP").show()
```
