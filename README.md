# metatables

This is a repository that enables easy data wrangling on files read with the pyreadstat package.

## Installation

Run the following to install:

``` bash
pip install metatables
```

## Usage

``` python
from metatables import MetaTable

# Add files from pyreadstat to MetaTable
x = MetaTable(df, meta)

# change val_lab of variables 'F5_01' and 'F5_02'
x.val_lab(['F5_01', 'F5_02'], {1: 'Fish', 2: 'Chips'})

# change var_lab of the same variables to 'New Label'
x.var_lab(['F5_01', 'F5_02'], 'New Label')

# select columns that should be kept in MetaTable
x.select_columns(['F5_01', 'F5_02'])

# show info about variable 'F5_01'
x.show('F5_01')

# write to .sav file
x.write_sav('./data/fertig_test.sav')
```

## Developing

To install the package, along with the tools you need to develop and run tests, run the following in your virtualenv:

``` bash
pip install -e .[dev]
```

Create the package files:

``` bash
python setup.py sdist bdist_wheel
```

Upload to [pypi.org](https://pypi.org/project/metatables/):

``` bash
twine upload dist/*
```

